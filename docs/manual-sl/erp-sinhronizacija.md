# ERP sinhronizacija z Business Central

**Dostop:** Sistem → Nastavitve → ERP Sync

ERP sinhronizacija povezuje Optima Prevent z Microsoft Dynamics 365 Business
Central. Optima ostaja sistem za EHS operacijo, Business Central pa ostaja
sistem za finance, pravne dokumente in izdajanje računov.

---

## Kaj se sinhronizira

Trenutno so podprti trije tokovi:

| Smer | Objekt | Namen |
|---|---|---|
| Optima → Business Central | sprejeta ponudba | ustvari prodajno naročilo |
| Optima → Business Central | aktivna pogodba | ustvari obračunski načrt kot prodajna naročila po obdobjih |
| Business Central → Optima | status naročila in referenca računa | pregled nadaljnjega finančnega toka |

ERP sinhronizacija **ne izdaja računov**. Račune še vedno izdaja Business
Central oziroma odgovorna finančna služba.

---

## Sandbox in produkcija

### Sandbox

Sandbox je ločeno testno okolje Business Central. Uporablja se za:

- preverjanje Azure prijave in dovoljenj,
- preverjanje številk strank in artiklov,
- testni prenos ponudbe in pogodbe,
- preverjanje davčnih skupin, valut in plačilnih pogojev,
- preverjanje napak in ponovnih poskusov.

V sandboxu se ne smejo ustvarjati pravi poslovni dokumenti, ki bi vplivali na
finančno poslovanje.

### Produkcija

Produkcija je živa baza Business Central. Vsako uspešno pisanje lahko ustvari
pravo prodajno naročilo. Zato velja:

- produkcijskih podatkov ne uporabljajte za testiranje,
- za produkcijo uporabite ločeno Azure aplikacijo oziroma ločene poverilnice,
- pred vklopom preverite company ID, tenant ID, valuto, davčne skupine in
  številčenje,
- prvi prenos izvedite na eni testni stranki in eni ponudbi.

V nastavitvah je **Okolje** oznaka okolja (`Sandbox` ali `Produkcija`).
Če je **Osnovni URL** prazen, se uporabi privzeta pot Business Central glede na
izbrano okolje. Če je Osnovni URL izpolnjen, ta neposredno določi končno pot in
ima prednost pred oznako okolja. Vedno preverite, na katero okolje kaže
Osnovni URL.

!!! warning "Produkcijsko pošiljanje je privzeto izklopljeno"
    Tudi če je produkcijska povezava aktivna, se prodajna naročila ne pošiljajo,
    dokler ne vklopite stikala **Omogoči produkcijsko pošiljanje**. To omogoča
    varen vnos poverilnic in preverjanje povezave brez pisanja v živo bazo.
    Stikalo vklopite šele po uspešnem sandbox testu in potrditvi računovodstva.

---

## Nastavitev povezave

1. Odprite **Sistem → Nastavitve → ERP Sync**.
2. Vnesite naziv in kodo povezave.
3. Izberite okolje **Sandbox** ali **Produkcija**.
4. Vnesite Company ID in Tenant ID.
5. Vnesite OAuth2 Client ID in Client Secret.
6. Shranite in kliknite **Preveri povezavo**.
7. Pri produkciji po uspešnem testu vklopite **Omogoči produkcijsko pošiljanje**.

Gumb **Preveri povezavo** preizkusi prijavo in branje seznama strank. Ne
preizkusi pisanja prodajnega naročila; to je treba preveriti ločeno v sandboxu.

Geslo Client Secret je shranjeno šifrirano. Pri kasnejšem urejanju se ne
prikaže; prazno polje pomeni, da obstoječe skrivnosti ne želite zamenjati.

Aktivna je lahko samo ena povezava Business Central. Ob shranjevanju aktivne
povezave se ostale povezave samodejno deaktivirajo.

---

## Povezave strank in storitev

Pred prvim pošiljanjem ponudbe ali pogodbe je treba povezati Optima stranke in
storitve z zapisi v Business Central. Povezave so vezane na posamezno ERP
povezavo in se ne prenašajo med okolji.

1. Odprite **Sistem → Nastavitve → ERP Sync**.
2. Kliknite **Uredi povezave**.
3. Kliknite **Naloži iz Business Central**.
4. Preglejte predloge in jih potrdite ali povežite ročno.

### Predlogi

Sistem pripravi predloge, vendar jih **ne shrani samodejno**:

- **Stranke:** ujemanje po normalizirani davčni številki oziroma VAT številki.
- **Storitve:** ujemanje po kodi (`code` ali `ext_code`) oziroma po točno enakem
  normaliziranem imenu.
- Če je kandidatov več ali je izbrani BC zapis že povezan z drugim zapisom, se
  prikaže **Konflikt**.

Vsak predlog je treba potrditi. Če predloga ni, uporabite **Ročno poveži** in
izberite ustrezen zapis Business Central. Povezavo lahko kadar koli odstranite.

Če za stranko ali storitev ni povezave, pošiljanje ponudbe oziroma pogodbe ne
uspe. To je namerno: sistem ne ugiba, katero stranko ali artikel uporabiti.

---

## Nastavitev pogodb

Za prenos pogodb je treba izbrati način obračuna:

```text
Način pogodb: Naročilo na obračunsko obdobje
Postavka za obračun: <številka artikla v Business Central>
Davčna skupina: <neobvezno>
Valuta: EUR
```

Za vsako obračunsko obdobje pogodbe se ustvari eno prodajno naročilo. To ni
račun; račun se izda v Business Central po potrjenem finančnem procesu.

Če način pogodb ni nastavljen, se pogodbe ne pošiljajo. Dogodki ostanejo v
čakalni vrsti in se prikažejo kot neuspešni z navodilom za nastavitev.

---

## Stanje in napake

Na strani ERP Sync so prikazani:

- ali je povezava nastavljena,
- število sporočil v čakanju,
- število neuspešnih sporočil,
- zadnja izvedba in število obdelanih/neuspešnih zapisov,
- zadnji uspešen stik s strežnikom.

Neuspešna sporočila se ponovijo z zamikom. Pred ponovnim pošiljanjem preverite:

1. ali je povezava aktivna,
2. ali so Company ID, Tenant ID in poverilnice pravilni,
3. ali je Osnovni URL pravilen,
4. ali so vzpostavljene povezave strank in storitev/artiklov,
5. ali je v Business Central omogočen dostop do ustreznih tabel.

---

## ERP nadzor in ponovno pošiljanje

**Sistem → Nastavitve → ERP nadzor** prikazuje:

- **Čakalno vrsto:** čaka, v obdelavi, neuspešno in poslano.
- **Napake:** odprte napake iz pošiljanja in prejema.
- **Izvajanja:** zadnje pošiljanje, uspehe in neuspehe.
- **Kontrolo povezav:** potrjene ponudbe in aktivna pogodbena obdobja brez
  povezave v `external_mappings`.

Neuspešno sporočilo lahko administrator ponovi z gumbom **Ponovi**. Ponovitev
ponastavi število poskusov, odpre novo izvajanje in poskusi znova. Pred tem
odpravite vzrok napake.

Kontrola povezav je **lokalna**: preveri, ali ima dokument zapis o povezavi, ne
kliče pa Business Central. Za preverjanje dejanskega stanja v BC uporabite
povezavo in ročni pregled.

---

## Trenutno stanje in omejitve

To je **prva različica za nadzorovan sandbox test**, ne še produkcijska
izdaja.

Pred produkcijo je treba dokončati in preveriti:

- preverjanje dejanskega API vedenja v izbranem Business Central okolju,
- potrditev davčnih skupin, valut in plačilnih pogojev s strani računovodstva,
- preverjanje pravic Azure aplikacije in načina obdelave podatkov,
- podpis pravilnika o obdelavi podatkov in dogovor o odgovornosti za napake,
- uspešen celoten sandbox test in pisno potrditev za produkcijo.

Do zaključka teh točk ERP sinhronizacijo uporabljajte samo v sandboxu.

---

## Priporočeni vrstni red testiranja

1. Preveri povezavo v sandboxu.
2. Uvozi oziroma ročno poveži eno testno stranko.
3. Poveži eno storitev/artikel.
4. Pošlji eno sprejeto ponudbo.
5. Preveri, da je nastalo natanko eno prodajno naročilo.
6. Ponovi isti postopek in preveri, da se ne ustvari drugo naročilo.
7. Preveri status naročila in referenco računa.
8. Aktiviraj testno pogodbo in preveri eno obračunsko obdobje.
9. Preveri, da v Business Central niso nastali računi brez finančne potrditve.
10. Šele po uspešnem sandbox testu obravnavaj produkcijsko uvedbo.

---

## Povezana dokumentacija

- [Sinhronizacija – pregled](sinhronizacija-pregled.md)
- [ERP – Ponudbe, pogodbe in finance](erp.md)
- [Sinhronizacija med namestitvami](sinhronizacija.md)
- [Sistemske nastavitve](sistemske-nastavitve.md)
