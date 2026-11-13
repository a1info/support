# Partner Sync – sinhronizacija med namestitvami

**Dostop:** Sistem → Sinhronizacija (`/mod-partner/manage`)

**Pravice:** superadmin, admin ali oper.

Partner Sync povezuje dve namestitvi programa Optima Prevent. Uporablja se za
sodelovanje z **zunanjimi izvajalci EHS storitev**, ki za vaše stranke izvajajo
usposabljanja, preglede delovne opreme in meritve delovnega okolja.

!!! note "Partner Sync ni ERP sinhronizacija"
    Partner Sync je namenjen izmenjavi operativnih EHS podatkov med dvema
    namestitvama Optima Prevent. Za povezavo z Business Central uporabite
    [ERP – Sinhronizacija z Business Central](erp-sinhronizacija.md).

---

## Kaj se prenaša

Vsaka namestitev je hkrati pošiljatelj in prejemnik. Podatki se izmenjujejo
neposredno med namestitvama, brez skupnega strežnika.

| Smer | Kaj se prenaša | Primer |
|---|---|---|
| **Lastnik podatkov → partner** | matični podatki: lokacije, tipična delovna mesta, delovna mesta, zaposleni, delovna oprema | Izvajalec pri vnosu dela izbira med vašimi zaposlenimi in opremo |
| **Partner → lastnik podatkov** | operacije: tečaji in udeleženci, pregledi opreme, EKO meritve | Izvajalec vnese opravljeno delo; zapis se pojavi pri vas |

**Stranke se ne sinhronizirajo.** Obe namestitvi morata imeti isto stranko
vneseno vsaka na svoji strani. Ujemanje poteka po **davčni številki** (`s_tax`).

Vsak zapis ima skupni **UUID**, ki ga obe strani uporabljata kot identiteto.
Davčna številka pove, h kateri stranki zapis spada; UUID pa prepreči podvajanje
zapisa pri ponovnem prenosu.

### Podprte storitve

Dodelitve trenutno podpirajo tri vrste storitev:

| Koda | Storitev |
|---|---|
| `educourse` | Usposabljanje |
| `mdevice` | Pregledi delovne opreme |
| `measure` | EKO meritve |

Ocene tveganj in požarna varnost v tej različici niso vključene v Partner Sync.

---

## Kako deluje

```text
sprememba zapisa
  → observer
  → odhodna pošta (integration_outbox)
  → urnik / čakalna vrsta
  → podpisan POST na partnerja
  → partnerjev API /api/partner/v1/*
  → potrditev ali napaka
```

Vsaka sprememba se najprej zapiše v **odhodno pošto**. Pošiljanje izvaja
`PublishPartnerSync`, ki ga zažene urnik. Če je nastavljena čakalna vrsta, mora
teči tudi `queue:work`; sicer sporočila ostanejo v čakalni vrsti.

Prejeta sporočila se zapišejo v **nabiralnik** (`integration_inbox`) in se
obdelajo samo enkrat za posamezno povezavo.

---

## Glavno stikalo

Na vrhu strani Sinhronizacija je stikalo **Omogoči sinhronizacijo**:

- **Izklopljeno** (privzeto): opazovalci sprememb niso aktivni; nove spremembe
  podatkov se ne beležijo in ne pošiljajo.
- **Vklopljeno**: ob spremembah podatkov se ustvarijo sporočila v odhodni
  pošti; urnik jih dostavi partnerju.

Stikalo se hrani v tabeli `system` (`sync_enabled`) in preživi brisanje
predpomnilnika ter nadgradnje. Po nadgradnji preverite, da je še vklopljeno.

!!! warning "Stikalo ne blokira prejema"
    Glavno stikalo ureja **pošiljanje**. Prejem preverjata HMAC podpis in
    aktivna partnerska povezava. Priporočamo, da je stikalo vklopljeno na obeh
    straneh, da se spremembe tudi beležijo.

### Brez partnerja ni pošiljanja

Če ni aktivne partnerske povezave z `Base URL`, `API ključem` in `API
skrivnostjo`:

- opazovalci se ne registrirajo;
- `PublishPartnerSync` se ne izvaja;
- `SyncService` ne ustvari nove odhodne pošte;
- `HistoricalSyncJob` se ustavi tudi pri ročnem zagonu.

Dodelitve so posebnost: ob shranjevanju se vpišejo v odhodno pošto, dostavijo
pa se šele, ko so izpolnjeni pogoji za pošiljanje.

---

## 1. Partnerji

Partner je druga namestitev programa Optima Prevent. **Partnerja je treba
definirati na obeh straneh** z enakima **API ključem** in **API skrivnostjo**.

1. Odprite zavihek **Partnerji** in kliknite *Dodaj novega partnerja*.
2. Vnesite naziv, kodo in **Base URL** nasprotne namestitve.
3. Vnesite kontaktno e-pošto (neobvezno).
4. Kliknite *Generiraj* za nov API ključ in skrivnost.
5. Enaki vrednosti vnesite na drugi namestitvi.
6. Označite *Aktivno* in shranite.

**Base URL je koren namestitve**, na primer `https://demo.optima-prevent.eu`.
Sistem sam doda pot `/api/partner/v1/...`; ne vnašajte je v Base URL.

API skrivnost je v bazi shranjena šifrirano in se pri kasnejšem urejanju ne
prikaže. Ob generiranju jo shranite na varno mesto in vnesite na obeh straneh.
Če polje pri urejanju pustite prazno, obstoječa skrivnost ostane nespremenjena.

### Preverjanje povezave

Ob partnerju je gumb za preverjanje povezave. Sistem pošlje podpisan
`POST /api/partner/v1/ping`.

- **200 OK**: na drugi strani obstaja aktiven partner z enakim ključem in
  veljavno skrivnostjo.
- **401**: napačen ključ/skrivnost, neaktiven partner ali preveliko odstopanje
  ure.
- **Druga napaka**: preverite Base URL, omrežno dostopnost in dnevnik na obeh
  straneh.

Preverjanje povezave ne prenaša poslovnih podatkov; preveri samo prijavo.

Partnerja z aktivnimi dodelitvami ni mogoče izbrisati. Ob brisanju se odstranijo
še neposlana sporočila v odhodni pošti.

---

## 2. Dodelitve

Dodelitev pove, **kateri partner, za katero stranko in katere storitve** ima
dostop.

1. Odprite zavihek **Dodelitve**.
2. Izberite **stranko**, **partnerja** in eno ali več **storitev**.
3. Vnesite **začetek veljavnosti** in shranite.

Ob shranitvi:

- se prejšnje aktivne dodelitve za isto kombinacijo zaključijo z začetkom nove
  dodelitve;
- se ustvari nova dodelitev;
- se partnerju pošlje dogodek `syn.assignment.changed`.

Partner dodelitve ne vnaša ročno; prejme jih z vaše strani. Če partner prejme
zapis za storitev brez aktivne dodelitve, ga zavrne z napako
**409 assignment_missing**.

### Zaključitev dodelitve

Z gumbom **Zaključi** dodelitev takoj preneha veljati. Partnerju se pošlje
dogodek `syn.assignment.line.ended`; novih zapisov za to storitev ne sprejema
več. Že preneseni zapisi se ne izbrišejo.

Statusi v tabeli:

| Status | Pomen |
|---|---|
| **AKTIVNO** | Dodelitev velja. |
| **ZAKLJUČENO** | Dodelitev ne velja več. |

---

## 3. Zgodovinska sinhronizacija

Zgodovinska sinhronizacija se uporablja za **enkratni prenos obstoječih
zapisov**, na primer ob prvi povezavi.

1. Odprite zavihek **Zgodovinska sinhronizacija**.
2. Izberite partnerja.
3. Izberite stranko. Če je ne izberete, se uporabi lastno podjetje.
4. Izberite entiteto ali **Vse entitete**.
5. Nastavite velikost serije (10–500; višje vrednosti se omejijo na 500).
6. Kliknite **Začni**.

Potek in napake so vidni v tabeli **Zgodovina sinhronizacij**. Prenos poteka v
serijah in po vrstnem redu odvisnosti:

```text
lokacije → tipična delovna mesta → delovna mesta → zaposleni
→ delovna oprema → pregledi → meritve
→ tipi usposabljanj → tečaji → udeleženci
```

!!! warning "Zaženite na strani, ki ima podatke"
    Matične podatke pošilja lastnik podatkov. Če zgodovinsko sinhronizacijo
    zaženete na prazni partnerski namestitvi, se prenesejo prazni podatki.

Dodelitve se ne prenašajo v sklopu **Vse entitete**; pošiljajo se ob
shranjevanju oziroma zaključitvi dodelitve.

---

## 4. Samodejni prenos

Po začetni sinhronizaciji se spremembe prenašajo samodejno:

- **Ustvarjanje, urejanje in brisanje** zaposlenih, opreme, tečajev, pregledov
  in meritev se zapiše v odhodno pošto.
- **Urnik** zažene dostavo vsako minuto. Primer crontaba:

  ```cron
  * * * * * cd /var/www/html/op5 && php artisan schedule:run >> /dev/null 2>&1
  ```

- Če uporabljate čakalno vrsto, mora teči tudi delavec čakalne vrste
  (`php artisan queue:work`).
- Pri prehodnih napakah (nedosegljiv strežnik, HTTP 5xx, HTTP 429) se sporočilo
  ponovi z zamikom. Po več neuspehih se označi kot **failed**.
- Pri HTTP 4xx (razen 409) se sporočilo ne ponavlja; napaka je treba najprej
  odpraviti.

!!! note "Brisanje prek množičnih akcij"
    Tudi brisanje prek množičnih akcij se prenese, če je glavno stikalo
    vklopljeno in obstaja aktivna dodelitev.

---

## Nadzor in dnevniki

V uporabniškem vmesniku so na voljo:

- seznam partnerjev in preverjanje povezave,
- dodelitve in njihovi statusi,
- zgodovinske sinhronizacije in njihov potek.

**Nabiralnik in odhodna pošta trenutno nimata ločenega zaslona.** Za
diagnostiko se uporabljajo dnevniki in podatkovne tabele:

| Tabela | Namen |
|---|---|
| `integration_outbox` | odhodna sporočila in status dostave |
| `integration_inbox` | prejeta sporočila in idempotentna obdelava |
| `integration_runs` | povzetki izvajanj |
| `integration_errors` | napake pri pošiljanju in prejemu |
| `partner_assignment_lines` | dodelitve strank in storitev |
| `partner_historical_sync` | potek zgodovinskih prenosov |

Dnevnik je `storage/logs/sync.log`. Pri težavi preverite **oba** strežnika:
pošiljatelj beleži pošiljanje in dostavo, prejemnik pa prejem in obdelavo.

---

## Pogoste težave

| Napaka | Pomen | Rešitev |
|---|---|---|
| **401 Unauthorized** | Manjka ali ni veljaven HMAC podpis; partner ni aktiven; napačen ključ/skrivnost; prestar časovni žig | Preverite partnerja in poverilnice na obeh straneh ter uro strežnika. |
| **401 Signature expired** | Razlika med strežnikoma je večja od 5 minut | Nastavite NTP oziroma sinhronizacijo ure. |
| **409 customer_not_found** | Davčna številka stranke se na prejemni strani ne ujema | Vnesite enako davčno številko v obe namestitvi. |
| **409 assignment_missing** | Za stranko in storitev ni aktivne dodelitve | Preverite dodelitev, začetek veljavnosti in ali je dodelitev prispela. |
| **409 in_progress** | Isto sporočilo se že obdeluje | Pošiljatelj naj počaka in poskusi znova. |
| **422 validation failed** | Podatki ne ustrezajo pričakovani obliki | Preverite dnevnik prejemnika in uskladite različici programa. |
| **429 Too Many Requests** | Prejemnik omejuje število zahtev | Sporočilo se ponovi z zamikom; preverite obremenitev. |
| **500 server_error** | Napaka pri obdelavi na prejemniku | Preverite `sync.log` na prejemni strani. |
| Sporočila ostajajo **PENDING** | Urnik ne teče, čakalna vrsta ne teče, stikalo je izklopljeno ali partner ni aktiven | Preverite cron, `queue:work`, stikalo in partnerjeve poverilnice. |

---

## Varnost

- Vsako sporočilo je podpisano z **HMAC-SHA256**.
- Podpis pokriva metodo, pot, časovni žig in **točno telo zahteve**.
- Časovni žig velja **5 minut** v obe smeri.
- Prejemnik sprejema samo sporočila aktivnega partnerja z veljavnim ključem in
  skrivnostjo.
- API skrivnost je šifrirana; v dnevnikih in na zaslonu se ne prikazuje.
- Ne pošiljajte zdravniških izvidov, diagnoz ali drugih občutljivih osebnih
  podatkov, ki jih partner ne potrebuje.

### Tehnična oblika podpisa

Za podporo in integracije:

```text
Authorization: hmac key="<api_key>",sig="<base64>",ts=<unix>
```

Podpisano besedilo je:

```text
UPPERCASE_METHOD
PATH
TIMESTAMP
RAW_BODY
```

Pri tem je `PATH` pot, na primer `/api/partner/v1/wp/upsert`. Podpis je
`base64(HMAC-SHA256(canonical, api_secret))`. Telesa po podpisu ne kodirajte
ponovno.

### API končne točke

Vse poti so pod `/api/partner/v1`:

```text
POST ping
POST custlocation/upsert       POST custlocation/delete
POST mdeviceobj/upsert         POST mdeviceobj/delete
POST mdevice/upsert            POST mdevice/delete
POST wp/upsert                 POST wp/delete
POST wpemp/upsert              POST wpemp/delete
POST custemployee/upsert       POST custemployee/delete
POST edutype/upsert            POST edutype/delete
POST educourse/upsert          POST educourse/delete
POST eduattendee/upsert        POST eduattendee/delete
POST assignment/upsert         POST assignment/close
POST measure/upsert            POST measure/delete
```

Prejem je idempotenten glede na kombinacijo `(connection_id, message_uuid)`.
Če je sporočilo že uspešno obdelano, prejemnik vrne **200** in ga ne obdela
ponovno.

---

## Trenutne omejitve

- Vmesnik pokriva partnerje, dodelitve in zgodovinsko sinhronizacijo; ločen
  zaslon za nabiralnik/odhodno pošto še ni na voljo.
- Podprte so tri storitve: usposabljanje, pregledi delovne opreme in EKO
  meritve.
- Stranke se ne sinhronizirajo; potrebna je enaka davčna številka na obeh
  straneh.
- Pred produkcijsko uporabo preverite celoten tok na testnih podatkih: povezavo,
  dodelitev, eno spremembo, brisanje in zgodovinski prenos.

---

## Povezana dokumentacija

- [Sinhronizacija – pregled](sinhronizacija-pregled.md)
- [ERP – Ponudbe, pogodbe in finance](erp.md)
- [ERP – Sinhronizacija z Business Central](erp-sinhronizacija.md)
- [Sistemske nastavitve](sistemske-nastavitve.md)
