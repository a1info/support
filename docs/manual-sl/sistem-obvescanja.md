# Sistem obveščanja

Sistem Optima Prevent omogoča napredno avtomatizirano obveščanje strank in zaposlenih preko e-pošte in v aplikaciji. Obvestila pokrivajo:

- **periodične opomnike** o poteku veljavnosti (delovna oprema, usposabljanja, meritve, požarna varnost, zdravniški pregledi, ostale evidence),
- **dogodkovna obvestila** ob poslovnih dogodkih (odobritve dokumentov, HRM, CRM, medicina, sistem, novi dokumenti),
- **e-test pošto** (vabila in opomniki za e-učenje).

Vsa pošiljanja se beležijo v dnevniku, kjer vidite status vsakega sporočila (poslano / napaka) in razlog napake.

!!! warning "Predpogoj: Nastavitev poštnega strežnika"
    Za uspešno delovanje celotnega sistema obveščanja mora biti predhodno pravilno nastavljena e-pošta.
    Navodila za nastavitev najdete v poglavju [Sistemske nastavitve](sistemske-nastavitve.md#e-postna-konfiguracija-smtp).

**Dostop:** Nastavitve → Obveščanje (zavihek **Pravila** in zavihek **Dnevnik**).

---

## 1. Pravila obveščanja

Pravilo pove sistemu **kaj** obveščati (dogodki), **komu** (prejemniki) in **kdaj** (urnik). Eno pravilo lahko združuje več dogodkov in ima več prejemnikov.

### Vrste pravil

| Vrsta | Opis |
|-------|------|
| **Periodično** | Sistem redno (dnevno/tedensko/mesečno) preveri izbrane evidence in pošlje en skupen e-poštni pregled vseh iztekov. |
| **Dogodkovno** | Pošlje se takoj, ko se v sistemu zgodi določen poslovni dogodek (npr. dokument čaka na odobritev, nova CRM naloga). Urnik ne velja. |

Periodičnih in dogodkovnih obvestil **ni mogoče mešati v enem pravilu**. Vrsto izberete na vrhu obrazca (**periodično** ali **dogodkovno**); obrazec nato prikaže samo dogodke in polja izbrane vrste. Ob preklopu vrste se izbrani dogodki počistijo.

Za novo pravilo uporabite gumba **Novo periodično pravilo** ali **Novo dogodkovno pravilo** – obrazec se odpre že v pravi vrsti.

### Polja pravila

| Polje | Opis |
|-------|------|
| **Vrsta** | Periodično ali dogodkovno; določa, kateri dogodki in polja so na voljo. |
| **Naziv** | Samodejno se predlaga iz stranke in izbranih dogodkov; lahko ga spremenite. |
| **Stranka** | Stranka, na katero se pravilo nanaša. |
| **Dogodki** | Ena ali več kategorij izbrane vrste (pri periodičnem npr. veljavnost delovne opreme + meritve; pri dogodkovnem npr. odobritev dokumenta). Pri periodičnih so na voljo dodatni filtri (npr. vključi zapise brez datuma pregleda). |
| **Urnik** | Pogostost (dnevno / tedensko / mesečno), dan in ura pošiljanja, pri mesečnih tudi ponavljanje na več mesecev. |
| **Obdobje** | *Relativno*: koliko dni pred potekom in po poteku zajame pregled. *Naslednji mesec*: pregled zajame celoten naslednji mesec. |
| **Zadeva** | Neobvezna; če je prazna, se uporabi privzeta zadeva. |
| **Prejemniki** | Glej spodaj. |
| **Status** | Pravilo lahko začasno deaktivirate brez brisanja. |

### Prejemniki

Poleg vpisa e-poštnih naslovov (ločenih z vejico ali novo vrstico) lahko dodate prejemnike s seznama:

| Vrsta | Kdo prejme |
|-------|------------|
| **E-naslov** | Točno vpisani naslov. |
| **Uporabnik** | Izbrani uporabnik sistema (na njegov e-naslov). |
| **Vloga** | Vsi aktivni uporabniki z izbrano vlogo. |
| **Zaposleni stranke** | Izbrani zaposleni stranke (na e-naslov iz njegovega profila). |

Pri reševanju se vsi prejemniki združijo; neveljavni ali podvojeni naslovi so izpuščeni, neaktivni prejemniki pa preskočeni.

Pri dogodkih z oznako **osebno** (npr. e-vabilo, odločitev o dopustu, opomnik za e-test) je prejemnik določen ob dogodku. Za pravilo, ki vsebuje samo takšne dogodke, prejemnikov ni treba vpisati.

!!! tip "Pošlji zdaj"
    Pri periodičnem pravilu lahko z gumbom **Pošlji zdaj** pošljete pregled takoj (testno ali izjemoma), ne da bi to vplivalo na redni urnik – redno periodično pošiljanje se kljub temu izvede po urniku.

### Stranke brez pravila

Nad seznamom pravil je obvestilo s številom **strank brez pravila** in hitrim izbirnikom. Izberite vrsto pravila in stranko, nato kliknite **Novo pravilo**; obrazec se odpre s predizbrano stranko in vrsto.

!!! info "Zamujeno pošiljanje (catch-up)"
    Če urnik ob načrtovani uri ni tekel (npr. strežnik nedosegljiv), sistem periodično obvestilo nadoknadi **na kasnejši dan istega tedna oz. meseca**. Vsako pravilo se v enem obdobju pošlje **največ enkrat** (zaščita pred podvojenimi sporočili). Če ob pošiljanju ni podatkov, se obdobje ne zaključi – sistem kasneje v obdobju znova preveri.

!!! info "Samo aktivno delujoči zaposleni"
    Pri obvestilih o **usposabljanjih** in **zdravniških pregledih** sistem vključi samo zaposlene z delovnim statusom **Aktiven**. Zaposleni brez opravljenega pregleda oz. usposabljanja so vključeni samo, če je v pravilu omogočen ustrezen filter.

---

## 2. Dogodkovna obvestila

Dogodkovno pravilo deluje kot **stikalo**: ko je za dogodek aktivno pravilo, sistem ob dogodku pošlje e-pošto prejemnikom pravila in pošiljanje zabeleži v dnevnik. Ko pravila ni, velja prejšnje obnašanje sistema (nekateri dogodki pošljejo obvestilo neposredno, drugi ne pošljejo ničesar). Neposredna pošiljanja se **ne zabeležijo v dnevnik** – za popoln dnevnik mora za dogodek obstajati aktivno pravilo.

Osebna obvestila (odločitev o dopustu, sprememba faze kandidata, opomnik za e-test ...) so vedno poslana **osebi, ki jo določa poslovni dogodek** – pravilo jih ne preusmeri na druge prejemnike. V obrazcu so označena z **osebno**; za pravilo samo s takšnimi dogodki prejemnikov ni treba vpisati.

Razpoložljivi dogodki:

| Modul | Dogodki |
|-------|---------|
| **Odobritve dokumentov** | Dokument čaka na odobritev; dokument je odobren ali zavrnjen. |
| **Kadri (HRM)** | Oddana zahteva za dopust; odločitev o dopustu; kandidat napredoval v fazi; odločitev o kandidatu; pozabljen odhod z dela. |
| **Izobraževanje** | E-test kmalu poteče; e-vabilo s pristopnimi podatki. |
| **Dokumenti** | Dokument je objavljen (vsi izpisani dokumenti, ki se pojavijo tudi na portalu stranke). |
| **CRM** | Nova naloga; naloga ima rok (ob novem ali spremenjenem roku se pošlje največ enkrat na rok). |
| **Medicina** | Nova napotitev na pregled; objavljen izvid. |
| **Sistem** | Neuspela varnostna kopija; neuspela sinhronizacija med namestitvami. |

---

## 3. Obveščanje zaposlenih (eUsposabljanje / eTest)

### Pošiljanje dostopnih podatkov

Ko ustvarite nov tečaj z **e-testom** in obkljukate pošiljanje e-pošte, sistem vsakemu udeležencu z vpisanim e-naslovom pošlje:

- povezavo (URL) do portala za reševanje testa,
- uporabniško ime,
- geslo za prijavo.

Če za dogodek **e-vabilo** obstaja aktivno pravilo, se pošiljanje izvede in zabeleži prek tega pravila (vsebina in prejemnik ostaneta enaka). Brez pravila se vabilo pošlje neposredno in se **ne prikaže v dnevniku**. Za evidentiranje zadošča aktivno dogodkovno pravilo z dogodkom **E-vabilo s pristopnimi podatki**; prejemnikov ni treba vpisati.

### Opomniki pred iztekom e-testa

Sistem nekaj dni pred iztekom roka za reševanje **samodejno pošlje opomnik** zaposlenemu, ki testa še ni rešil.

---

## 4. Dnevnik pošiljanja in ponovni poskusi

Zavihek **Dnevnik** v Nastavitve → Obveščanje prikazuje zadnja poslana sporočila s statusom vsakega pošiljanja:

| Status | Pomen |
|--------|-------|
| **sent** | Sporočilo je bilo uspešno poslano. |
| **failed** | Pošiljanje ni uspelo – ob sporočilu je zapisan razlog napake (npr. neveljaven naslov, zavrnitev strežnika). |
| **pending** | Pošiljanje je v teku. |

**Ponovni poskusi:** periodična obvestila z napako sistem samodejno poskusi poslati znova (v presledkih po približno 10 minut, največ 5-krat). Neuspešna dogodkovna obvestila so prikazana v dnevniku z razlogom napake.

Zgodovina pošiljanja se hrani **60 dni**, nato se samodejno izbriše.

!!! note "Kam so šli stari e-mail dnevniki?"
    Zavihek *Email log* v Dnevniku dejavnosti je zamenjal novi dnevnik obveščanja, ki prikazuje status po sporočilu in po prejemniku.

---

## 5. Obvestila v aplikaciji (za prijavljene uporabnike)

Prijavljeni uporabniki dobijo pomembna obvestila tudi v aplikaciji, ne le po e-pošti.

### Zvonec v zgornji vrstici

- Prikazuje **dokumente, ki čakajo na odobritev**, in **neprebrana obvestila** za prijavljenega uporabnika.
- Številka na zvoncu je vsota obojega in se osveži vsaki 2 minuti.
- Klik na obvestilo odpre povezani dokument ali seznam; s tem se obvestilo označi kot prebrano.
- Na dnu sta povezavi **Prikaži vse** in **Označi vse kot prebrano**.

### Stran Obvestila

Do nje pridete prek zvonca ali uporabniškega menija (**Obvestila**).

| Zavihek | Vsebina |
|---------|---------|
| **Neprebrano** | samo nova obvestila |
| **Vsa obvestila** | celotna zgodovina za vaš račun |
| **Dokumenti za odobritev** | dokumenti, ki čakajo na vašo odobritev |

### Katera obvestila se prikažejo v aplikaciji

Prikažejo se le dogodki, vezani na uporabnika:

- odobritev dokumenta (zahteva in odločitev),
- zahteva za dopust (vodje) in odločitev o dopustu (zaposleni),
- CRM naloga z rokom (izvajalec),
- napaka varnostne kopije ali sinhronizacije.

Periodični pregledi veljavnosti, obvestila strankam (izvidi, vabila na e-test) in obvestila kandidatom se še naprej pošiljajo samo po e-pošti.

### Moje obveznosti (nadzorna plošča)

Na nadzorni plošči je kartica **Moje obveznosti** s tremi števci (dokumenti za odobritev, naloge do danes, neprebrana obvestila) in seznamom do petih nalog z današnjim ali pretečenim rokom.

---

## 6. Obveščanje na Portalu za stranke

Stranke imajo dostop do lastnega portala, kjer pregledujejo opremo, zaposlene, veljavnosti in dokumente. Obvestila so vezana na **aktivno podjetje** (podjetje se preklopi z izbirnikom v zgornji vrstici).

### Zvonec v zgornji vrstici

- Prikazuje število **novih dokumentov** od zadnjega pregleda.
- Spustni seznam prikaže zadnjih 8 dokumentov; klik odpre PDF.
- **Označi vse kot prebrano** ponastavi števec.

### Kartica Dogodki in obvestila (nadzorna plošča)

- **Veljavnost** — skupno število poteklih postavk in postavk, ki potečejo v 30 dneh.
- **Zdravniški pregledi** in **Delovna oprema** — ločena števca, če ima uporabnik ustrezno pravico.
- Seznam zadnjih 20 dokumentov z oznako **Novo**.

Ob prvi prijavi se kot novo štejejo dokumenti zadnjih 30 dni. Nov dokument se na portalu prikaže takoj po objavi (`docissue.ind_for_cust = 1`). Če za dogodek **Dokument je objavljen** obstaja aktivno pravilo, sistem o novem dokumentu pošlje tudi e-pošto prejemnikom pravila.

!!! info "Več informacij o portalu"
    Podrobna navodila o dodeljevanju dostopov strankam so v poglavju [Portal za stranke](portal-za-stranke.md).

---

## 7. Vzdrževanje (za administratorja)

Sistem obveščanja poganjajo naslednji urniki (cron):

| Ukaz | Urnik | Namen |
|------|-------|-------|
| `php artisan op:notifyDispatch` | vsako minuto | Pošiljanje periodičnih pravil, ki so na vrsti. |
| `php artisan op:notifyRetry` | vsakih 10 minut | Ponovni poskusi neuspelih periodičnih pošiljanj. |
| `php artisan op:notifyRetention` | dnevno ob 03:10 | Brisanje zgodovine pošiljanja (privzeto 60 dni). |

Nastavitve preko okoljskih spremenljivk (`.env`):

| Spremenljivka | Privzeto | Opis |
|---------------|----------|------|
| `NOTIFY_DISPATCH_ENABLED` | `true` | Glavno stikalo za periodično pošiljanje. |
| `NOTIFY_RETRY_MINUTES` | `10` | Najkrajši presledek med ponovnimi poskusi po napaki. |
| `NOTIFY_RETRY_MAX_ATTEMPTS` | `5` | Največje število poskusov pošiljanja enega sporočila. |
| `NOTIFY_NO_DATA_RECHECK_MINUTES` | `60` | Kako pogosto se v obdobju ponovno preveri pravilo, ki ob pošiljanju ni imelo podatkov. |
| `NOTIFY_RETENTION_DAYS` | `60` | Koliko dni se hrani zgodovina pošiljanja. |

!!! tip "Diagnostika pošiljanja"
    Za preizkus brez dejanskega pošiljanja lahko zaženete `php artisan op:notifyDispatch --dry-run` (izpiše, kaj bi poslal) ali `php artisan op:notifyRetry --dry-run`.
