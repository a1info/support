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

Modul omogoča sledenje zdravniškim pregledom zaposlenih in izdajanje napotnic. Podprti tipi pregledov:

| Tip pregleda | Opis |
|---|---|
| **Predhodni** | Pregled pred nastopom dela ali razporeditvijo na novo delovno mesto |
| **Obdobni preventivni** | Redni periodični pregled v skladu s predpisi |
| **Kontrolni** | Pregled po bolezni, poškodbi ali posebni odreditvi |

!!! info "Veljavnost in Periodika"
    Veljavnost pregleda (v mesecih) se samodejno spremlja v modulu **Analitika → Periodika**, ki ob poteku opozori odgovornega uporabnika.

### Polja za vnos

| Polje | Opis |
|---|---|
| **Stranka** | Podjetje / delodajalec |
| **Zaposleni** | Delavec, ki se napotuje na pregled |
| **Tip pregleda** | Predhodni / obdobni preventivni / kontrolni |
| **Datum pregleda** | Datum opravljenega pregleda |
| **Datum napotnice** | Datum izdaje napotnice |
| **Veljavnost (meseci)** | Rok veljavnosti pregleda v mesecih |
| **Polja napotnice** | Dodatni podatki, zahtevani na napotnici (delovno mesto, nevarnosti, ukrepi …) |

!!! tip "Šifranti"
    Mnoga polja so vezana na **šifrante** (kodni seznam). Ikone nad posameznim poljem omogočajo hiter dostop do ustreznega šifranta in dodajanje novih vrednosti.

### Tisk napotnice

Napotnico natisnete ali izvozite v **PDF** z gumbom za izpis pri posameznem zapisu.

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

Modul zagotavlja standardizirano evidentiranje delovnih nezgod v skladu z zakonskimi zahtevami. Zbrani podatki so osnova za obvezno poročanje pristojnim organom.

### Polja za vnos

| Polje | Opis |
|---|---|
| **Stranka** | Podjetje, kjer je nezgoda nastala |
| **Zaposleni** | Poškodovana oseba |
| **Podatki o osebi** | Osebni in zaposlitveni podatki (iz šifranta) |
| **Datum dogodka** | Datum in ura nezgode |
| **Delovno mesto** | Delovno mesto poškodovanca |
| **Kraj dogodka** | Natančen opis kraja nezgode |
| **Izjava o nezgodi** | Opis okoliščin, vzrokov in posledic nezgode |

!!! tip "Šifranti"
    Polja za kraj, vzrok, vrsto poškodbe in ostale standardizirane vrednosti so vezana na **šifrante**, kar zagotavlja enotnost poročanja.

### Tisk

Obrazec delovne nezgode natisnete ali izvozite v **PDF** z gumbom za izpis pri posameznem zapisu.

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
