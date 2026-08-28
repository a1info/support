# Sinhronizacija med namestitvami

**Dostop:** Sistem → Sinhronizacija

Sinhronizacija omogoča povezovanje dveh ali več namestitev programa Optima Prevent. Uporablja se predvsem za sodelovanje z **zunanjimi izvajalci EHS storitev** (druga podjetja), ki za vaše stranke izvajajo usposabljanja, preglede delovne opreme in meritve delovnega okolja.

---

## Kako deluje

Namestitvi si podatke izmenjujeta **neposredno (P2P)** preko varnega API‑ja. Vsaka namestitev je hkrati pošiljatelj in prejemnik:

| Smer | Kaj se prenaša | Primer |
|------|----------------|--------|
| **Lastnik podatkov → partner** | matični podatki: poslovne enote, tipična delovna mesta, zaposleni, delovna oprema | Vaša namestitev pošlje podatke stranke zunanjemu izvajalcu, da lahko izbira zaposlene in opremo pri vnosu dela |
| **Partner → lastnik podatkov** | operacije: tečaji in udeleženci, pregledi opreme, EKO meritve | Izvajalec vnese opravljeno delo v svoji namestitvi; zapisi se samodejno pojavijo pri vas |

**Stranke se ne sinhronizirajo.** Namestitvi morata imeti isto stranko (isti davčni številki) vneseno vsaka na svoji strani — po davčni številki se namreč izvaja ujemanje pri prenosu.

Obseg prenosa določajo **dodelitve**: vrstica *stranka × partner × storitev × veljavnost*. Partner lahko za določeno stranko prejema in pošilja le tiste vrste podatkov, za katere ima aktivno dodelitev.

!!! note "Podprte storitve"
    Trenutno so podprte storitve **Usposabljanje**, **Pregledi delovne opreme** in **EKO meritve**. Ocene tveganj in požarna varnost so pripravljene, vendar še niso vključene v prenos.

---

## Glavno stikalo

Na vrhu strani Sinhronizacija je stikalo **Omogoči sinhronizacijo**:

- **Izklopljeno** (privzeto): spremembe se ne beležijo in nič se ne pošilja.
- **Vklopljeno**: ob vsaki spremembi podatkov se ustvarijo sporočila za prenos, urnik pa jih samodejno dostavi.

Stanje stikala se hrani v podatkovni bazi, zato preživi brisanje predpomnilnika in nadgradnje. Po nadgradnji programa vedno preverite, da je stikalo vklopljeno.

---

## 1. Partnerji

Partner je namestitev programa, s katero sinhronizirate. **Partnerja je treba definirati na obeh straneh** z enakima vrednostma **API ključa** in **API skrivnosti**:

1. V zavihku **Partnerji** kliknite *Dodaj novega partnerja*.
2. Vnesite naziv, kodo in **Base URL** nasprotne namestitve (npr. `https://demo.optima-prevent.eu`).
3. Z gumbom *Generiraj* ustvarite ključ in skrivnost ter **enaki vrednosti vnesite tudi na drugi namestitvi** (partner z obrnjenim URL‑jem).
4. Označite *Aktivno* in shranite.

!!! warning "Enak ključ na obeh straneh"
    Ključ in skrivnost sta poverilnici, s katerima se namestitvi prepoznata. Če se na prejemni strani ne ujemata, prenos vrne napako **401 Unauthorized**.

**Preverjanje povezave:** ob vsakem partnerju je gumb z ikono vtiča. Preveri, ali je na nasprotni strani definiran aktiven partner z enakim ključem. Uporabite ga **pred** ustvarjanjem dodelitev.

---

## 2. Dodelitve

Dodelitev pove, **kateri partner, za katero stranko in katere storitve** ima dostop:

1. V zavihku **Dodelitve** izberite **stranko**, **partnerja** in **storitve** (Ctrl/CMD za več izbir).
2. Vnesite **začetek** veljavnosti in shranite.

Ob shranitvi se dodelitev samodejno prenese na partnerjevo namestitev (zrcalna vrstica). V tabeli spodaj vidite vse dodelitve in njihov status (**AKTIVNO** / **ZAKLJUČENO**).

- **Zaključi** — ročno prekinete veljavnost; partner takoj preneha prejemati podatke te stranke in njegovi zapisi se zavrnejo z napako *assignment_missing*.
- Novo shranjevanje iste kombinacije stare dodelitve samodejno zaključi in ustvari nove.

!!! tip "Kje ustvariti dodelitev?"
    Dodelitve ustvarjate **samo na strani lastnika podatkov**. Na partnerjevi namestitvi se pojavijo samodejno; tam jih ne vnašajte ročno.

---

## 3. Zgodovinska sinhronizacija

Uporablja se za **enkratni prenos vseh obstoječih zapisov** (npr. ob prvi povezavi):

1. Zavihek **Zgodovinska sinhronizacija**.
2. Izberite partnerja in **stranko** (privzeta izbira je lastno podjetje — pazite, da izberete pravo stranko).
3. Izberite entiteto (ali *Vse entitete*) in velikost serije ter kliknite *Začni*.

Prenos poteka v serijah po vrstnem redu, ki zagotavlja odvisnosti (najprej poslovne enote, nato oprema in zaposleni …). Potek vidite v tabeli zgodovine.

!!! warning "Zgodovinsko sinhronizacijo poganjajte na strani, ki ima podatke"
    Če jo zaženete na prazni (partnerski) namestitvi, se prenesejo njeni — torej prazni — podatki. Matične podatke lastnik podatkov pošilja partnerju; operacije partner pošilja lastniku.

---

## 4. Samodejni prenos (po začetni sinhronizaciji)

Po uspešni začetni sinhronizaciji vse nadaljnje spremembe potujejo samodejno:

- **Spremembe in brisanja** zapisov (zaposleni, oprema, tečaji, pregledi, meritve …) sistem zazna in pripravi sporočilo v *odhodni pošti*.
- **Urnik** (cron) sporočila dostavi vsako minuto:

  ```
  * * * * * sudo -u www-data php /var/www/html/op5/artisan schedule:run >> /dev/null 2>&1
  ```

- Ob napaki (nedosegljiv strežnik, manjkajoči podatek) sporočilo ostane v čakalni vrsti in se **samodejno ponovi** s postopnim podaljševanjem intervala.
- Prejeta sporočila so vidna v **nabiralniku** (Recent Inbox), poslana pa v **odhodni pošti** (Recent Outbox) na obeh straneh.

!!! note "Brisanje prek množičnih akcij"
    Tudi brisanje prek množičnih akcij (bulk) v tabelah se prenese — pod pogojem, da je glavno stikalo vklopljeno.

---

## Izvor operacij

Zapisi, ki so prispeli od partnerja, so v seznamih označeni z **značko z imenom partnerja** (tečaji, pregledi opreme, meritve). Lokalno ustvarjeni zapisi nimajo značke.

V seznamih je na voljo filter **Izvor** (posamezen partner ali *Lastni zapisi*), s katerim hitro ločite svoje delo od dela zunanjih izvajalcev.

---

## Beleženje

Vse dogajanje se zapisuje v dnevnik `storage/logs/sync.log` na obeh namestitvah. Pri odkrivanju težav vedno preverite dnevnik **obeh** strani: pošiljatelj beleži *sending/delivered/failed*, prejemnik pa *received/applied*.

---

## Pogoste težave

| Napaka | Pomen | Rešitev |
|--------|-------|---------|
| **401 Unauthorized** | Partner na prejemni strani ni definiran, ni aktiven ali ima drug ključ | Preverite partnerja na prejemni strani; uporabite *Preveri povezavo* |
| **409 customer_not_found** | Davčna številka stranke se na prejemni strani ne ujema | Vnesite enako davčno številko v obe namestitvi |
| **409 assignment_missing** | Za stranko/storitev ni aktivne dodelitve (ali še ni prispela) | Počakajte na dostavo dodelitve; preverite status v zavihku Dodelitve |
| **422 validation failed** | Različici programa na obeh straneh se ne ujemata | Nadgradite obe namestitvi na isto verzijo |
| **master switch off** | Sinhronizacija je izklopljena | Vklopite glavno stikalo na obeh namestitvah |
| Sporočila ostajajo **PENDING** | Urnik ne teče ali stikalo je izklopljeno | Preverite cron vrstico in stikalo; ročno zaženite `php artisan schedule:run` |

---

## Varnost

- Vsako sporočilo je podpisano z **HMAC‑SHA256** in časovnim žigom (veljavnost 5 minut); sporočila brez veljavnega podpisa se zavrnejo.
- Prejemnik sprejema sporočila le od **aktivnih** partnerjev s pravilnim ključem.
- Obseg podatkov omejujejo dodelitve: partner prejme le podatke strank, za katere ima aktivno dodelitev, in lahko pošilja le storitve iz dodelitve.
