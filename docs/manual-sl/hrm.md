# HRM (Upravljanje kadrov)

Modul **HRM** pokriva vodenje kadrov, evidenco delovnega časa, upravljanje dopustov in odsotnosti ter proces zaposlovanja novih sodelavcev.

---

## Pregled modula

HRM združuje vse ključne kadrovske procese na enem mestu:

- pregled prisotnosti, delovnega časa in nadur,
- upravljanje odsotnosti, dopustnih kvot in praznikov,
- načrtovanje odsotnosti po oddelkih,
- samopostrežni portal za zaposlene (Moj HRM),
- proces zaposlovanja od razpisa do zaposlitve,
- karton zaposlenega s pregledom EHS stanja.

### Dostop in navigacija

**Glavni meni → HRM**

Meni modula je zgoščen na štiri področja:

| Meni | Vsebina (zavihki) |
|------|-------------------|
| **Odsotnosti** | Pregled · Odsotnosti · Kvote · Načrtovanje · Prazniki |
| **Moj HRM** | Samopostrežni pogled zaposlenega |
| **Evidenca časa** | Vnosi · Mesečno poročilo · Preverjanje · Nastavitve |
| **Zaposlovanje** | Razpisi · Kandidati |

Vrste odsotnosti so del **Šifrantov** (glavni meni → Seznami).

!!! warning "Pogoj za polno funkcionalnost"
    Za uporabo večine HRM funkcionalnosti morajo imeti zaposleni v sistemu dodeljen in **povezan IT uporabniški račun**. Uporabniški račun ustvarite iz evidence [Zaposleni](zaposleni.md#povezava-z-it-racunom), pravice in vloge pa uredite v poglavju [Uporabniki](uporabniki.md).

---

## Nadzorna plošča (Pregled)

Nadzorna plošča je vstopna točka modula (zavihek **Pregled** v Odsotnostih) in daje hiter pregled stanja na tekoči dan.

### Vsebina nadzorne plošče

| Sekcija | Opis |
|---------|------|
| **Danes odsotni** | Seznam zaposlenih, ki so danes na dopustu ali bolniški odsotnosti. |
| **Čakajoči zahtevki** | Zahtevki za odsotnost, ki čakajo na odobritev – s hitrimi gumbi **Potrdi** / **Zavrni**. |
| **Terminal** | Beleženje prihoda in odhoda zaposlenih (Clock-In / Clock-Out). |
| **Graf: ure po tednih** | Opravljene ure zadnjih 8 tednov. |
| **Graf: odsotnosti po mesecih** | Število odsotnosti zadnjih 6 mesecev. |
| **Graf: prijave po fazah** | Število prijav po fazah selekcije za odprte razpise. |

!!! tip
    Nadzorno ploščo si odprite vsako jutro – čakajoče zahtevke lahko potrdite z enim klikom, ne da bi odpirali posamezni zapis.

---

## Moj HRM (samopostrežba zaposlenih)

Zaposleni v zavihku **Moj HRM** sami:

- beležijo prihod in odhod (terminal je omejen na njihov zapis),
- oddajajo zahtevke za odsotnost (s preverjanjem kvote in prekrivanj),
- prekličejo oddani zahtevek,
- pregledujejo stanje dopusta po vrstah (skupaj / porabljeno / preostalo),
- pregledujejo svoje zapise delovnega časa za tekoči mesec.

Stran deluje tudi, če zaposleni nima IT uporabniškega računa – sistem ga prepozna po e-poštnem naslovu.

---

## Odsotnosti in dopusti

### Vrste odsotnosti

Vrste odsotnosti upravljate v **Šifrantih** (meni → Seznami → Vrste odsotnosti). Vsaka vrsta ima:

| Nastavitev | Opis |
|------------|------|
| **Koda in naziv** | Enolična koda (npr. ANNUAL, SICK). |
| **Dni na leto** | Privzeto letno število dni. |
| **Zahteva potrditev** | Ali zahtevek te vrste potrebuje odobritev nadrejenega. |
| **Prenos v novo leto** | Ali se neizrabljeni dnevi prenašajo v naslednje leto. |
| **Barva** | Barva v koledarju. |
| **Veljavnost** | Globalna (vsa podjetja) ali veljavna za izbrano podjetje. |

### Kvote dopustov

!!! info "Samodejno generiranje"
    Sistem omogoča **množično generiranje letnih kvot** za vse aktivne zaposlene hkrati. Kvota vključuje osnovne dni, **dodatke za delovno dobo in starost** ter prenos neizrabljenega dopusta iz preteklega leta.

| Pregled kvote | Opis |
|---------------|------|
| **Dodeljeno** | Osnovni dopust + prenos iz preteklega leta. |
| **Porabljeno** | Dnevi oddanih in potrjenih odsotnosti v letu. |
| **Preostalo** | Razlika med dodeljenim in porabljenim. |

**Letni prenos (rollover):** ob prehodu v novo leto se pri vrstah z omogočenim prenosom prenesejo neizrabljeni dnevi. Prenos izvedete z ukazom `php artisan op:hrmQuotaRollover` (običajno ob zaključku leta).

### Potek zahtevka

```
Vnos → Oddano → Potrjeno / Zavrnjeno
```

| Korak | Akter | Opis |
|-------|-------|------|
| **Vnos** | Zaposleni / HR | Vnos datuma, vrste in razloga odsotnosti. |
| **Oddano** | Sistem | Vrste brez zahtevane potrditve se potrdijo samodejno; ostale gredo v odobritev. |
| **Potrjeno** | Nadrejeni | Dnevi se odštejejo od kvote; zaposleni prejme e-poštno obvestilo. |
| **Zavrnjeno** | Nadrejeni | Možen vpis opombe vodje; zaposleni prejme e-poštno obvestilo. |

Sistem pri vnosu preveri:

- **prekrivanje** z obstoječimi odsotnostmi zaposlenega,
- **zadostnost kvote** (opozorilo ob presežku),
- **delovne dni** – vikendi in prazniki se ne štejejo v dneve odsotnosti.

!!! tip "Polovični dan"
    Za enodnevno odsotnost lahko označite **polovični dan** – od kvote se odšteje 0,5 dneva.

### Priloge

Zahtevku lahko priložite dokumente (npr. zdravniško potrdilo) do 10 MB. Priloge se shranijo ob zapisu in so dostopne ob vsakem odpiranju zahtevka.

### Prazniki in delovni koledar

- **Sinhronizacija državnih praznikov:** sistem samodejno pridobi in **posodablja** seznam slovenskih državnih praznikov (vključno s premaknjenimi datumi).
- **Prazniki podjetja:** dodate lahko lastne proste dneve (kolektivni dopust, dan podjetja …), veljavne za vsa podjetja ali le za izbrano.
- **Mostovi:** dan lahko označite kot **dela prost** ali **delovni** – dela prosti dnevi se upoštevajo pri izračunu dni odsotnosti.

### Načrtovanje odsotnosti

Zavihek **Načrtovanje** ponuja vodstveni pregled:

| Pogled | Opis |
|--------|------|
| **Danes / jutri odsotni** | Seznam odsotnih po oddelkih. |
| **Opozorila o zasedenosti** | Opozorilo, če bo oddelek v naslednjih 7 dneh ostal brez razpoložljivih zaposlenih. |
| **Preostanek dopusta** | Preostali dnevi po zaposlenih za tekoče leto. |
| **Nizek preostanek** | Opozorilo za zaposlene s ≤ 5 preostalimi dnevi dopusta. |

Klik na ime zaposlenega odpre njegov **Karton zaposlenega**.

### Koledar odsotnosti

Na dnu strani **Načrtovanje** je **koledar odsotnosti po oddelkih**:

- **mesečna mreža** z imeni odsotnih po dnevih (barva = vrsta odsotnosti),
- **rdeča oznaka** dneva, ko število sočasnih odsotnosti doseže dovoljeno mejo,
- **letni pregled** – skupno število dni odsotnosti po mesecih.

Pri potrjevanju zahtevka sistem opozori, če novi dopust povzroči presežek meje sočasnih odsotnosti v oddelku (mejo nastavite v Nastavitvah).

---

## Evidenca delovnega časa

### Vnosi

Zapisi delovnega časa vključujejo:

| Polje | Opis |
|-------|------|
| **Datum in čas** | Prihod / odhod (samodejni izračun minut). |
| **Tip dela** | Redno delo, nadure, nočno delo, vikend, praznik. |
| **Lokacija** | Delovišče (stroškovno mesto) – izbere se ob prijavi na terminalu ali v vnosu. |
| **Odmor** | Samodejni odbitek odmora po pravilu podjetja; lahko ga ročno popravite. |
| **Status** | Osnutek → Oddano → Zaklenjeno. |
| **Čez polnoč** | Oznaka za izmeno, ki sega čez polnoč. |

Seznam omogoča **filtriranje po lokaciji in datumu** ter strani (paginacija).

!!! info "Samodejni odmor"
    Ob odjavi sistem po pravilu podjetja samodejno odšteje odmor (privzeto **30 min po 6 urah**). Pravilo in mejo nastavite v zavihku **Nastavitve**.

### Mesečno poročilo

- Prikaz ur po tipih dela za izbrani mesec in podjetje (skupaj, odmor, neto).
- **Ure po lokacijah:** seštevek ur po deloviščih za obračun stroškov po mestih.
- **Excel izvoz** za obračun plač (vključuje odmor, neto in razdelitev po lokacijah).
- **Zaklepanje meseca:** potrjen mesec se zaklene – zaklenjenih zapisov ni več mogoče urejati (priprava za obračun).

### Preverjanje časa

Zavihek **Preverjanje** preveri delovni čas glede na poenostavljena pravila:

| Preverjanje | Meja |
|-------------|------|
| Delovni dan | nad 10 ur |
| Počitek med izmenama | pod 11 ur |
| Tedenske nadure | nad 8 ur |
| Delo v nedeljo / na praznik | informativno |

!!! warning "Informativni izračun"
    Preverjanje je informativne narave in temelji na poenostavljenih pravilih – ni nadomestilo za uradni obračun.

### Opomnik ob pozabljeni odjavi

Če zaposleni ob koncu dneva ostane prijavljen, sistem ob 18:00 samodejno pošlje **e-poštni opomnik za odjavo**.

### Nastavitve

Zavihek **Nastavitve** vsebuje pravila, ki veljajo globalno ali za izbrano podjetje:

| Nastavitev | Privzeta vrednost | Uporaba |
|------------|-------------------|---------|
| **Največ sočasnih odsotnosti na dan** | 2 (na oddelek) | Opozorila ob potrjevanju in rdeče oznake v koledarju. |
| **Odmor – po opravljenih minutah** | 360 min | Meja, od katere se odšteje odmor. |
| **Odmor – trajanje** | 30 min | Samodejni odbitek ob odjavi. |

Če nastavitev za podjetje ni določena, se uporabi globalna nastavitev ali privzete vrednosti.

---

## Zaposlovanje

### Razpisi

| Status | Pomen |
|--------|-------|
| **Osnutek** | Razpis v pripravi. |
| **Odprt** | Aktiven razpis, sprejema prijave. |
| **Zaprt** | Zaprt ročno ali **samodejno ob preteku datuma zaprtja**. |
| **Zapolnjeno / Preklicano** | Zaključni statusi. |

### Kandidati

Za vsakega kandidata shranite osebne in kontaktne podatke, **življenjepis (CV)** ter opombe. Sistem:

- preprečuje **podvojene kandidate** (isti e-naslov v istem podjetju),
- vodi **GDPR privolitev** (polje in oznaka v seznamu),
- samodejno **briše stare kandidate** brez aktivnih prijav (GDPR hramba).

Z gumbom **Prijavi na razpis** kandidata neposredno prijavite na izbrano delovno mesto.

### Prijave in kanban tabla

Faze selekcije si ogledate na **kanban tabli** posameznega razpisa:

```
Prejeto → V pregledu → Intervju → Ponudba → Zavrnjeno
```

- Premikanje med fazami z **vleci in spusti** ali z gumbi.
- **Dodajanje kandidata:** nov kandidat se vnese neposredno v prijavi (polja za novega kandidata), nato se vrnete na tablo.
- **Zapisi / komentarji** ob prijavi (zgodovina komunikacije).
- **Izid prijave:** z gumbi **Zaposli** / **Zavrni** / **Umik** zaključite prijavo; kandidat prejme e-poštno obvestilo o izidu in spremembi faze.

---

## Karton zaposlenega

Klik na ime zaposlenega (v odsotnostih, kvotah ali načrtovanju) odpre **Karton zaposlenega**, ki na enem mestu prikazuje:

- **osnovne podatke** (oddelek, kontakt, rojstni datum, starost, datum zaposlitve, delovna doba),
- **stanje dopusta** po vrstah za tekoče leto,
- **odsotnosti** v tekočem letu,
- **povzetek delovnega časa** za tekoči mesec,
- **EHS stanje:** zadnja usposabljanja (modul Usposabljanje) in zadnje medicinske preglede (modul Evidence).

---

## E-poštna obvestila

Modul pošilja samodejna obvestila:

| Dogodek | Prejemnik |
|---------|-----------|
| Oddan zahtevek za odsotnost | Nadrejeni (uporabniki s pravico upravljanja HRM) |
| Potrjen / zavrnjen zahtevek | Zaposleni |
| Sprememba faze prijave | Kandidat |
| Izid prijave (zaposlitev / zavrnitev / umik) | Kandidat |
| Pozabljena odjava | Zaposleni |

Pošiljanje ne vpliva na delovanje modula – če pošiljanje ni mogoče, se postopek vseeno izvede.
