# Ocene tveganj kemičnih snovi (RASSC)

## Pregled modula

Modul **RASSC** (Ocene tveganj kemičnih snovi) omogoča izdelavo ocene tveganja zaradi izpostavljenosti delavcev kemičnim snovem na delovnem mestu. Dopolnjuje modula **Ocene tveganj** (splošna OTV) in **RASSL** (telesne obremenitve).

Pravna podlaga:

- 2. odstavek 6. člena **Pravilnika o varovanju delavcev pred tveganji zaradi izpostavljenosti kemičnim snovem pri delu** (Uradni list RS, št. 72/21, 29/24 in 26/25),
- Pravilnik o varovanju delavcev pred tveganji zaradi izpostavljenosti rakotvornim, mutagenim ali reprotoksičnim snovem pri delu.

Izračun temelji na **poenostavljeni metodi** po *Praktičnih smernicah MDDSZ (2006)* (kontrolni listi, koraki 1–4).

**Dostop:** Glavni meni → Ocenjevanje tveganj → OTV kemične snovi

!!! note "Aktivacija modula"
    Modul RASSC zahteva aktivacijo (`modules_statuses.json` → `Rassc`) in dodelitev pravic `view_rassc` / `manage_rassc`. Za vzpostavitev se obrnite na podporo **Optima Prevent**.

Modul sestavljajo trije zasloni:

| Zaslon | Namen |
|---|---|
| **OTV kemične snovi** | Ocene tveganja za posamezna delovna mesta / procese s kontrolnimi listi |
| **Dokumenti OTV kem.** | Dokumenti OTV (rasscgrp), ki združujejo ocene delovnih mest in iz katerih se generira DOCX |
| **Baza kemičnih snovi** | Skupni katalog kemičnih snovi (zmesi/snovi) z varnostnimi podatki |

---

## Baza kemičnih snovi

Skupna baza snovi, ki se uporabljajo v kontrolnih listih. Enkrat vnesena snov se uporablja v vseh ocenah.

**Dostop:** Ocenjevanje tveganj → Baza kemičnih snovi

### Podatki o snovi

| Polje | Opis |
|---|---|
| **Trgovsko ime** | Trgovsko ime izdelka (npr. barva, topilo) |
| **Kemijsko ime** | Kemijsko ime snovi/zmesi (obvezno) |
| **Koda proizvoda** | Interna oznaka |
| **CAS / ES / Indeks / REACH** | Identifikacijske številke snovi; gumb 🔍 ob CAS izvede **iskanje v ECHA bazi** |
| **Agregatno stanje** | trdna / tekoča / plinasta |
| **Vrelišče [°C]** | Za določitev hlapnosti (Graf 1) |
| **H-stavki** | Izbor iz kataloga CLP (Uredba 1272/2008): H3xx (H300–H373) in njihove kombinacije + EUH stavki; določajo skupino nevarnosti A–E in skupino K |
| **Klasifikacija (CLP)** | Klasifikacija po Uredbi 1272/2008 |
| **Sestava (SDS/GHS)** | Sestava iz varnostnega lista |
| **MV / KTV / BAT** | Mejna vrednost, kratkotrajna vrednost, biološka mejna vrednost |
| **Dobavitelj, datum VL** | Dobavitelj in datum varnostnega lista |
| **Prepovedana snov / SVHC** | Oznaki prepovedane uporabe in snovi s seznama SVHC (REACH) |
| **Aktivna** | Snov je na voljo v kontrolnih listih |

Ob izbiri H-stavkov sistem sproti prikaže izračunano **skupino nevarnosti (A–E)** in oznako **K** (stik s kožo/očmi). Vnos z enako **CAS številko** je blokiran (deduplikacija).

!!! info "CLP - ukinitev R-stavkov"
    R- in S-stavki se po **1. juniju 2017** ne smejo več uporabljati (Uredba CLP 1272/2008). V programu se zato vnašajo le **H-stavki**. Stari R-stavki ostajajo v bazi zgolj za prehodno obdobje (stara evidenčna polja se pri urejanju ne spreminjajo).

!!! info "Iskanje v lokalni ECHA bazi"
    Ob vnosu **CAS** ali **ES številke** gumb 🔍 poišče snov v lokalni bazi ECHA (harmonizirani seznam CLP Annex VI + SVHC seznam). Prazna polja se samodejno izpolnijo: kemijsko ime, ES, indeks, klasifikacija in **H-stavki** (samo kode iz kataloga H3xx/EUH). Snovi s **SVHC seznama** se samodejno označijo. Baza se osvežuje ročno (artisan `op:importechadb`).

### Uvoz (Excel)

Na seznamu snovi je gumb za **uvoz** (ikona nalaganja). Odpre se čarovnik za uvoz (upload → prepoznavanje stolpcev → uvoz):

- podprte datoteke: `.xlsx`, `.xls`, `.csv`,
- prva vrstica mora vsebovati **naslove stolpcev**; čarovnik jih samodejno preslika v polja snovi (ujemanje po imenu, nato po podobnosti),
- obvezen je le **Kemijsko ime**; ostali stolpci so neobvezni,
- H-stavki so lahko ločeni z `;` ali `,` (tudi kombinacije, npr. `H302+H312`),
- vrstice z obstoječo CAS številko se preskočijo; na koncu se izpiše povzetek (vneseno / napake / obstoječe CAS).

### Izvoz (Excel)

Na seznamu snovi je v **skupinskih akcijah** (bulk) na voljo **Izvozi** za označene snovi — datoteka `.xlsx` s podatki snovi in slovenskimi naslovi stolpcev.

---

## Ocene delovnih mest (OTV kemične snovi)

Ocena tveganja se izdela za eno delovno mesto / proces in je lahko vezana na dokument OTV.

**Dostop:** Ocenjevanje tveganj → OTV kemične snovi → (plus) Nova ocena

### Podatki ocene

| Polje | Opis |
|---|---|
| **Stranka / poslovna enota** | Izbor iz evidence strank |
| **Naziv** | Naziv ocene |
| **Dokument OTV KEM** | Neobvezna pripadnost dokumentu (rasscgrp) |
| **Tip in predmet** | Tipično delovno mesto (TDM) / Dejansko delovno mesto / Proces |
| **Datum izdelave / revizije** | Datuma ocene |
| **Opisi** | Izpostavljenost, druge okoliščine, tehnični ukrepi, zdravstveni nadzor, opombe |

Po shranjevanju se odpre zaslon **Kontrolni listi** za vnos snovi.

---

## Kontrolni listi (Korak 1–4)

Za vsako snov se izdela kontrolni list po poenostavljeni metodi:

| Korak | Vsebina | Vnos |
|---|---|---|
| **Korak 1** | Operacije, kjer se snov uporablja | prosti opis |
| **Korak 2A** | Skupina nevarnosti **A–E** + oznaka **K** | samodejno iz H-stavkov (možen ročni popravek) |
| **Korak 2B** | Količina: majhna (g/ml) / srednja (kg/l) / velika (t/m³) | izbor |
| **Korak 2C** | Prašnost/hlapnost: nizka / srednja / visoka | samodejno iz agregatnega stanja in vrelišča (možna ročna izbira) |
| **Korak 3** | Stopnja tveganja **1–4** (Tabela 3 smernic) | samodejno iz matrike |
| **Korak 4** | Ukrepi | samodejno iz kataloga ukrepov (gumb za samodejni vnos) + ročni dodatki |

Dodatne evidence na kontrolnem listu:

- **OVO** — izbor osebne varovalne opreme (skupina K / K-OVO),
- **Meritve (SIST EN 689)** — status: ni zahtevano / potrebno / izvedeno / preseženo,
- **Zdravstveni nadzor** — oznaka potrebe po zdravstvenem nadzoru (12. člen pravilnika),
- **Opombe**.

!!! info "Izračun poenostavljene metode"
    - Skupina A–E in K se določita iz H-stavkov (katalog `rassc_rhmap`, Tabela 1 smernic). Velja najvišja skupina (E > D > C > B > A).
    - Hlapnost tekočin se določi iz vrelišča: < 50 °C → visoka, 50–150 °C → srednja, > 150 °C → nizka; pri povišani delovni temperaturi se meje premaknejo (Graf 1). Plini so vedno visoka hlapnost, prašnost trdnih snovi se izbere ročno.
    - Stopnja 1–4 se odčita iz matrike (skupina × količina × hlapnost/prašnost); skupina **E** je vedno stopnja 4.
    - Izračunane vrednosti (skupina, stopnja, ukrepi) se ob shranjevanju **zapišejo v kontrolni list** (`rassc_item`), zato kasnejše spremembe katalogov ne spreminjajo že izdelanih ocen.

Prikaz stopnje tveganja:

| Barva | Stopnja | Pomen |
|---|---|---|
| 🟢 Zelena | 1 | Nepomembno tveganje |
| 🔵 Modra | 2 | Majhno tveganje |
| 🟡 Rumena | 3 | Zmerno tveganje |
| 🔴 Rdeča | 4 | Visoko tveganje — takojšnji ukrepi |

---

## Dokumenti OTV KEM

Ocene delovnih mest se združijo v **dokument OTV KEM** (rasscgrp), ki predstavlja izdano oceno tveganja za stranko.

**Dostop:** Ocenjevanje tveganj → Dokumenti OTV kem.

### Podatki dokumenta

| Polje | Opis |
|---|---|
| **Stranka / poslovna enota** | Nosilec dokumenta |
| **Naziv** | Naziv dokumenta (npr. delovni proces) |
| **Številka dokumenta** | Interna številka (npr. 25/2026-OTV KEM) |
| **Verzija, datum** | Verzija in datum izdelave |
| **Odgovorna oseba / zdravnik / predstavnik delavcev** | Podpisniki dokumenta |
| **Opis tehnološkega postopka** | Opis postopka (${descWorkEnv}) |
| **Izbrane ocene** | Ocene delovnih mest, vključene v dokument |

!!! warning "Zamenjava stranke"
    Ob spremembi stranke se izbor ocen počisti — ocene prejšnje stranke ne smejo ostati vezane na nov dokument.

### Generiranje DOCX

Na seznamu dokumentov je v stolpcu **Docx** spustni meni s predlogami, registriranimi v **Repooffice** (tip predloge `rassc`). Generiranje ustvari Word dokument s štirimi tabelami:

- **Tabela 1** – Evidenca nevarnih kemičnih snovi,
- **Tabela 2** – Podatki o uporabi na delovnem mestu,
- **Tabela 3** – Kontrolni listi (Korak 1–3),
- **Tabela 4** – Ukrepi (Korak 4).

Generirani dokumenti se zabeležijo v **dokumentni tok** (`docissue`, tip `rassc`).

Predloge se urejajo v Repooffice (Dokumenti → Urejanje predlog); seznam spremenljivk predloge je v poglavju [Legenda spremenljivk](variables-sl.md).

---

## Povezava z ostalimi moduli

- **Ocene tveganj (RASS)** — osnovna ocena tveganja; RASSC je njen dodatek za kemične snovi.
- **RASSL** — enaka struktura dokumenta za ocene telesnih obremenitev.
- **Baza kemičnih snovi** — skupna za vse ocene RASSC.
- **Repooffice / Dokumentni tok** — predloge DOCX in evidenca generiranih dokumentov.
