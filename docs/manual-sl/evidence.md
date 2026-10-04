# Evidence

## Pregled modula

Modul **Evidence** je zbirno mesto za različne vrste evidenc, ki jih zahteva zakonodaja s področja varnosti in zdravja pri delu. Pokriva:

- zdravniške preglede zaposlenih in izdajanje napotnic,
- osebno varovalno opremo (OVO),
- delovne nezgode,
- ostale evidence po meri.

**Dostop:** Glavni meni → Evidence

---

## Zdravniški pregledi

**Dostop:** Evidence → Zdravniški pregledi

### Namen

Modul omogoča sledenje zdravniškim pregledom zaposlenih in izdajanje napotnic. Sistem samodejno poveže oceno tveganja delovnega mesta z zdravniškim pregledom in prenese ugotovljene dejavnike tveganja v napotnico.

Podprti tipi pregledov:

| Tip pregleda | Opis |
|---|---|
| **Predhodni** | Pregled pred nastopom dela, po več kot 12 mesecih prekinitve ali ob menjavi delovnega mesta |
| **Obdobni preventivni** | Redni periodični pregled v skladu s pravilnikom (Ur.l. RS, št. 87/02 s spremembami) |

!!! info "Veljavnost in Periodika"
    Veljavnost pregleda (v mesecih) se samodejno spremlja v modulu **Analitika → Periodika**, ki ob poteku opozori odgovornega uporabnika.

### Obrazec — zavihki

Obrazec za vnos zdravniškega pregleda je razdeljen na štiri zavihke:

| Zavihek | Vsebina |
|---|---|
| **Zdravniški pregled** | Osnovni podatki: stranka, zaposleni, tip pregleda, razlog napotitve / pravna podlaga, datumi |
| **Dodatno** | Podrobni podatki za napotnico: opis delovnega procesa, oprema, predmeti dela, izpostavljenost tveganjem, ukrepi, OVO, zdravstvene zahteve |
| **Dejavniki tveganja** | Seznam ugotovljenih dejavnikov tveganja — samodejno prenesenih iz ocene tveganja in specifičnih za zaposlenega |
| **Rezultat** | Zdravniško spričevalo: datum pregleda, številka spričevala, ocena (1–6), omejitve, predlagani ukrepi |

### Razlog napotitve / Pravna podlaga

Polje pod izbiro tipa pregleda se prilagodi glede na izbrani tip:

- **Obdobni pregled:** vnos člena Pravilnika o preventivnih zdravstvenih pregledih delavcev (npr. *7., 9. in 14. člen*). Gumb `?` prikaže celoten seznam členov s pripadajočimi tveganji.
- **Predhodni pregled:** izbira razloga napotitve (prva zaposlitev, vrnitev po 12 mesecih, menjava delovnega mesta).

### Dejavniki tveganja

Ob izbiri zaposlenega sistem samodejno:

1. Poišče **zadnjo oceno tveganja** za delovno mesto zaposlenega.
2. Prenese vsa tveganja z oceno **R0 > 1** (povišano tveganje) v seznam dejavnikov.
3. Doda **specifične dejavnike**, ki so vpisani na profilu zaposlenega (zavihek Dodatno → *Dejavniki tveganja (specifični)*).

Zdravnik lahko seznam dejavnikov v napotnici poljubno dopolni, uredi ali odstrani.

!!! info "Specifični dejavniki zaposlenega"
    Specifične dejavnike tveganja (npr. alergije, kronične bolezni) vpišete na **profilu zaposlenega** (Zaposleni → urejanje → zavihek Dodatno). Ob vsakem novem zdravniškem pregledu se samodejno dodajo v seznam.

### Rezultat pregleda — Zdravniško spričevalo

Po opravljenem pregledu vnesete rezultate v zavihek **Rezultat**:

| Polje | Opis |
|---|---|
| **Datum pregleda** | Dejanski datum opravljenega pregleda |
| **Št. zdravniškega spričevala** | Številka spričevala, ki ga izda pooblaščeni zdravnik |
| **Ocena** | 1–6 po uradnem obrazcu |
| **Omejitve** | Prikaže se pri ocenah 2 in 3 |
| **Rok naslednjega pregleda** | Prikaže se pri oceni 2. Če rok ni vpisan, velja prvotna veljavnost pregleda |
| **Predlagano drugo delo** | Prikaže se pri oceni 5 |
| **Razlog (6.1–6.4)** | Prikaže se pri oceni 6 |
| **Predlagani ukrepi** | Ukrepi, ki jih predlaga zdravnik |

**Ocene (1–6):**

| Oznaka | Pomen |
|---|---|
| 1 | Izpolnjuje posebne zdravstvene zahteve |
| 2 | Izpolnjuje z omejitvami |
| 3 | Začasno ne izpolnjuje |
| 4 | Trajno ne izpolnjuje |
| 5 | Predlagano drugo delo |
| 6 | Ne moremo podati ocene |

### Izvajalec medicine dela in zdravnik

Napotnici lahko dodelite **izvajalca medicine dela** in opcijsko **zdravnika** (glavni meni → Evidence → Zdravniški pregledi → urejanje napotnice).

- Ob kreiranju napotnice za stranko, ki ima dodeljenega izvajalca medicine dela (Stranke → urejanje → Izvajalci MD), se izvajalec in prednostni zdravnik **samodejno predizpolnita**.
- Dodeljeni izvajalec in zdravnik se izpišeta na tiskani napotnici, napotnica pa se prikaže na portalu za zdravnike (mod-medic).
- Napotnice **brez** dodeljenega izvajalca so na portalu za zdravnike vidne ustanovam, ki imajo stranko dodeljeno (ne dodeljene napotnice).

### Tisk napotnice

Napotnico natisnete ali izvozite v **PDF** z gumbom za izpis pri posameznem zapisu.

**Prva stran** (delodajalec) vsebuje:
- osnovne podatke delavca in delodajalca,
- razlog napotitve ali pravno podlago,
- podatke iz ocene tveganja,
- **seznam ugotovljenih dejavnikov tveganja** s pripadajočimi ocenami R0.

**Druga stran** (zdravnik) — Zdravniško spričevalo se **samodejno izpolni** s podatki, vnesenimi v zavihku Rezultat. V glavi spričevala sta izpisana **naziv in naslov izvajalca medicine dela** ter **ime pooblaščenega zdravnika** (če sta dodeljena), desno od naslova pa je **QR koda**, ki zdravnika pripelje neposredno na obrazec za vnos rezultata.

### Prikaz tveganj na profilu zaposlenega

Na **kartici zaposlenega** (Zaposleni → klik na ime) so v ločenem razdelku prikazani vsi dejavniki tveganja, ki izhajajo iz ocene tveganja njegovega delovnega mesta. Enak prikaz je viden tudi na **portalu za stranke**.

### Filter po oddelku

Tabela zdravniških pregledov omogoča filtriranje po **oddelku** zaposlenega, kar olajša pregled po organizacijskih enotah.

### Status pregleda

Tabela zdravniških pregledov vsebuje stolpca **Izvajalec medicine dela** in **Zdravnik**, ki prikazujeta, komu je napotnica dodeljena.

Stolpec **Status** se prikaže pri napotnicah, ki imajo **dodeljenega izvajalca medicine dela** (izbranega neposredno na napotnici):

- **Čaka** — zdravnik še ni vnesel rezultata pregleda
- **Ocena z datumom** — barvna značka z oceno (1–6) in datumom opravljenega pregleda

Stolpec omogoča hiter pregled, katere napotnice so že obdelane in katere še čakajo na rezultat.

V filtrirni vrstici tabele so na voljo filtri:

| Filter | Opis |
|---|---|
| **Status** | Čakajoče in posamezne ocene (1–6). Prikaže samo napotnice z dodeljenim izvajalcem |
| **Izvajalec medicine dela** | Filtriranje po ustanovi |
| **Zdravnik** | Filtriranje po posameznem zdravniku |

---

## Osebna varovalna oprema (OVO)

**Dostop:** Evidence → Osebna varovalna oprema

### Namen

Evidenca OVO beleži izdajanje osebne varovalne opreme posameznemu zaposlenemu na podlagi ocene tveganja. Zagotavlja sledljivost in dokazovanje ustrezne zaščite delavcev.

### Polja za vnos

| Polje | Opis |
|---|---|
| **Stranka** | Podjetje / delodajalec |
| **Zaposleni** | Prejemnik OVO |
| **Datum izdaje** | Datum izročitve opreme |
| **Veljavnost (meseci)** | Rok zamenjave / ponovne izdaje |
| **Opombe** | Dodatne informacije ali posebna navodila |
| **Seznam opreme** | Posamezni kosi OVO z opisom in standardom |

!!! info "Standardi OVO"
    Na desni strani obrazca je prikazan referenčni seznam veljavnih standardov za OVO. Standardi so vezani na posamezen kos opreme in se izpišejo skupaj z evidenco.

!!! info "Periodika"
    Če je veljavnost nastavljena, sistem samodejno sproži opozorilo ob izteku v modulu **Periodika**.

---

## Delovne nezgode

**Dostop:** Evidence → Delovne nezgode

### Namen

Modul zagotavlja standardizirano evidentiranje delovnih nezgod v skladu z zakonskimi zahtevami in pripravi vse podatke, potrebne za uradno prijavo pristojnim organom.

!!! info "Zakonska podlaga"
    - **ZVZD-1** (Ur. l. RS, št. 43/11), 41. člen: delodajalec mora inšpekciji dela (IRSD) **takoj** prijaviti vsako smrtno nezgodo, nezgodo z več kot tremi delovnimi dnevi odsotnosti in vsako kolektivno nezgodo.
    - **Pravilnik o prijavi nezgode in poškodbe pri delu** (Ur. l. RS, št. 78/22): s **1. 9. 2022** je papirni obrazec ER-8 nadomestila elektronska prijava **ePrijava NPD** prek portala **SPOT**. Vneseni podatki se posredujejo na IRSD, ZZZS in NIJZ; poškodovanec pri izbranem osebnem zdravniku uredi zdravstveni del prijave.
    - Vsako poškodbo z **vsaj enim dnem bolniške odsotnosti** je treba prijaviti tudi ZZZS/NIJZ.

Modul Optima Prevent vodi **interno evidenco** nezgod in pripravi podatke za prepis v uradno prijavo; uradna oddaja poteka izključno na portalu SPOT.

### Seznam

Seznam prikazuje vse zabeležene nezgode s statusom prijave:

| Stolpec | Opis |
|---|---|
| **Ime / Priimek** | Poškodovanec — prikaže se ime, veljavno **ob času dogodka** (spremembe v kadrovski evidenci označi ikona zgodovine) |
| **Stranka** | Podjetje / delodajalec |
| **Poslovna enota** | Enota, v kateri je bil poškodovanec zaposlen ob dogodku |
| **Datum** | Datum nezgode |
| **Lokacija** | Kraj nezgode |
| **Status** | `v pripravi` / `oddano` (z datumom oddaje) / `preklicano` |
| **Datoteka** | Prenos priložene dokumentacije |
| **PDF** | Izpis internega zapisa (obrazec ER-8) |
| **SPOT** | Hitra povezava na portal SPOT za uradno prijavo |
| **Dejanja** | Urejanje, kopiranje zapisa, brisanje |

Na voljo so filtri po **letu**, **poslovni enoti** ter **imenu in priimku**. Za uporabnike z vlogo skrbnika je omogočeno tudi **skupinsko brisanje** več zapisov.

### Obrazec — zavihki

Obrazec za vnos delovne nezgode je razdeljen na tri zavihke:

| Zavihek | Vsebina |
|---|---|
| **Osnovni podatki** | Stranka, poškodovanec, delovno mesto, datum in ura nezgode, datum prijave, kraj nezgode, kratek opis dogodka, priloga datoteke |
| **Šifranti (NPD)** | Standardizirani podatki za ePrijavo NPD: podatki o delodajalcu, poškodovancu in nezgodi |
| **Prijava na SPOT** | Status prijave, datum oddaje, številka prijave NPD, podatki o prijavitelju in povezave na portal SPOT |

### Šifranti (NPD)

Polja za standardizirane vrednosti so opremljena s pomožnimi šifranti, ki se odprejo s klikom na oznako šifre ob polju:

| Šifrant | Vsebina |
|---|---|
| **06** | Število zaposlenih pri delodajalcu |
| **11** | Zaposlitveni status poškodovanca |
| **S13** | Poklic (klasifikacija poklicev) |
| **S21** | Narava poškodbe |
| **S22** | Poškodovani del telesa |
| **S23** | Delovno okolje |
| **S24** | Delovni proces |
| **S25** | Specifična aktivnost v času nezgode |
| **S26** | Vzrok nezgode |
| **S27** | Način poškodbe |
| **S28** | Materialni povzročitelj |

Ob izbiri poškodovanca se polje **spol** samodejno izpolni iz kadrovske evidence.

### Prijava na SPOT — status

Ker uradno oddajo na portalu SPOT izvede pooblaščena oseba s kvalificiranim digitalnim potrdilom, sistem vodi status prijave ročno:

| Status | Pomen |
|---|---|
| **v pripravi** | Zapis še ni oddan na SPOT |
| **oddano na SPOT** | Prijava je bila oddana; samodejno se zabeleži datum oddaje, vnesete lahko številko prijave NPD |
| **preklicano** | Prijava je bila na SPOT preklicana |

Na zavihku so tudi povezavi **Oddaj prijavo na SPOT (ePrijava NPD)** ter **Preklic prijave / pooblastila**.

### Tisk

Z gumbom **PDF** pri posameznem zapisu natisnete **interni zapis** v obliki obrazca ER-8. Zapisu je dodana oznaka, da gre za interno dokumentacijo — uradna prijava se odda izključno prek portala SPOT.

---

## Ostale evidence

**Dostop:** Evidence → Ostale evidence

### Namen

Prilagodljiv modul za beleženje katerekoli evidence, ki ni pokrita z zgornjimi specializiranimi moduli. Primeren za vse vrste zakonsko zahtevanih ali internih evidenc.

### Polja za vnos

| Polje | Opis |
|---|---|
| **Stranka / PE** | Podjetje in poslovna enota |
| **Naziv evidence** | Ime oziroma vrsta evidence |
| **Datum** | Datum vnosa ali veljavnosti |
| **Veljavnost (meseci)** | Rok veljavnosti evidence |
| **Priponke** | Priloženi dokumenti (PDF, slike …) |

!!! info "Periodika"
    Če je veljavnost nastavljena, sistem samodejno sproži opozorilo ob izteku v modulu **Periodika**.

!!! example "Primeri uporabe"
    - Evidenca usposabljanj za varstvo pred požarom,
    - evidence kemikalij in SDS listov,
    - evidenca pregledov ergonomskih delovnih mest,
    - vse druge interne evidence brez lastnega modula.
