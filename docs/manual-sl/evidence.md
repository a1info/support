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

### Tisk napotnice

Napotnico natisnete ali izvozite v **PDF** z gumbom za izpis pri posameznem zapisu.

**Prva stran** (delodajalec) vsebuje:
- osnovne podatke delavca in delodajalca,
- razlog napotitve ali pravno podlago,
- podatke iz ocene tveganja,
- **seznam ugotovljenih dejavnikov tveganja** s pripadajočimi ocenami R0.

**Druga stran** (zdravnik) — Zdravniško spričevalo se **samodejno izpolni** s podatki, vnesenimi v zavihku Rezultat.

### Prikaz tveganj na profilu zaposlenega

Na **kartici zaposlenega** (Zaposleni → klik na ime) so v ločenem razdelku prikazani vsi dejavniki tveganja, ki izhajajo iz ocene tveganja njegovega delovnega mesta. Enak prikaz je viden tudi na **portalu za stranke**.

### Filter po oddelku

Tabela zdravniških pregledov omogoča filtriranje po **oddelku** zaposlenega, kar olajša pregled po organizacijskih enotah.

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
