# Ocene telesnih obremenitev (RASSL)

## 1. Pregled modula

Modul **RASSL** (Ocene telesnih obremenitev) omogoča sistematično ocenjevanje ergonomskih obremenitev delavcev na delovnih mestih. Dopolnjuje modul **Ocene tveganj** z namensko ergonomsko analizo telesnih obremenitev.

**Dostop:** Glavni meni → Ocene tveganj → Ocene telesnih obremenitev

!!! note "Aktivacija modula"
    Modul RASSL zahteva predhodno aktivacijo. Za vzpostavitev in konfiguracijo se obrnite na podporo **Optima Prevent**.

Ocene telesnih obremenitev temeljijo na standardiziranih ergonomskih metodah ocenjevanja in so osnova za načrtovanje preventivnih ukrepov na področju mišično-skeletnih obolenj.

---

## 2. Kategorije telesnih obremenitev

Sistem RASSL podpira strukturirano ocenjevanje po kategorijah telesnih obremenitev. Razvrščene so v dve skupini:

### Kategorija B

| Oznaka | Opis obremenitve |
|---|---|
| **CTM** | Celotno telo med delom — splošna telesna obremenitev |
| **PT** | Roke in prsti — ponavljajoče se gibanje rok in prstov |
| **DDP** | Držanje delovne pozicije — statične obremenitve telesa |
| **PDT** | Pritisk in dvigovanje težkih bremen |
| **RD** | Ročno delo — kombinacija gibalnih obremenitev |
| **VP** | Vibracije in pretres — izpostavljenost vibracijam |

### Kategorija C

| Oznaka | Opis obremenitve |
|---|---|
| **CTM-C** | Celotno telo — napredna analiza |
| **PT-C** | Roke in prsti — napredna analiza |
| **DDP-C** | Držanje delovne pozicije — napredna analiza |
| **PDT-C** | Pritisk in dvigovanje — napredna analiza |
| **RD-C** | Ročno delo — napredna analiza |
| **VP-C** | Vibracije — napredna analiza |

!!! info "Ergonomske metode"
    Kategorije ustrezajo uveljavljenim ergonomskim metodam ocenjevanja (npr. RULA, REBA, KIM in sorodnim slovenskim standardom za ocenjevanje telesnih obremenitev). Sistem samodejno izračuna stopnjo obremenitve na podlagi vnesenih vrednosti.

---

## 3. Tipična delovna mesta (TDM) za RASSL

Ocene telesnih obremenitev so neposredno vezane na **tipična delovna mesta (TDM)**, definirana v modulu Ocene tveganj.

**Dostop:** Ocene tveganj → Seznam TDM

- Vsak TDM je mogoče oceniti z vidika telesnih obremenitev neodvisno od splošne ocene tveganja.
- Ocena telesnih obremenitev za posamezen TDM dopolni celostno sliko tveganj na delovnem mestu.
- Zaposleni, dodeljeni določenemu TDM, so samodejno vključeni v evidenco ocen telesnih obremenitev.

---

## 4. Postopek ocenjevanja

Ocenjevanje telesnih obremenitev poteka v naslednjih korakih:

### Korak 1 – Izbira delovnega mesta

- Izberite **stranko** in **tipično delovno mesto (TDM)**, ki ga ocenjujete.
- Navedite **datum ocene** in vnesite morebitne opombe o delovnem okolju.

### Korak 2 – Vnos vrednosti po kategorijah

Za vsako kategorijo telesnih obremenitev (B ali C), ki je relevantna za to delovno mesto, vnesite ocenjevalne vrednosti:

| Element vnosa | Opis |
|---|---|
| **Kategorija obremenitve** | Izberite ustrezno kategorijo (npr. PT za roke/prste) |
| **Vrednosti parametrov** | Vnesite numerične ocene za posamezne parametre kategorije |
| **Trajanje izpostavljenosti** | Čas dnevne izpostavljenosti tej obremenitvi |
| **Opombe** | Posebnosti ali odstopanja od tipičnih razmer |

### Korak 3 – Izračun stopnje obremenitve

Sistem samodejno izračuna **stopnjo telesne obremenitve** na podlagi vnesenih parametrov in prikaže barvno kodiran rezultat:

| Barva | Stopnja | Priporočilo |
|---|---|---|
| 🟢 Zelena | Nizka obremenitev | Ni posebnih ukrepov |
| 🟡 Rumena | Zmerna obremenitev | Priporočeni preventivni ukrepi |
| 🟠 Oranžna | Povišana obremenitev | Potrebni ukrepi v razumnem roku |
| 🔴 Rdeča | Visoka obremenitev | Takojšnji ergonomski ukrepi |

### Korak 4 – Pregled rezultatov

- Preglejte izračunane stopnje po kategorijah.
- Identificirajte kategorije z visoko ali nesprejemljivo stopnjo obremenitve.
- Preidite na naslednji korak — načrtovanje ukrepov.

---

## 5. Ukrepi

Na podlagi rezultatov ocene načrtujte in dokumentirajte ergonomske izboljšave:

| Polje | Opis |
|---|---|
| **Opis ukrepa** | Konkretni ergonomski ukrep (npr. prilagoditev višine delovne mize, rotacija del, mehanske pripomočke …) |
| **Odgovorna oseba** | Ime osebe, odgovorne za izvedbo ukrepa |
| **Rok izvedbe** | Datum, do katerega mora biti ukrep izveden |
| **Status** | Stanje izvedbe ukrepa (v teku / zaključen) |

!!! tip "Preventivni pristop"
    Ergonomski ukrepi so najučinkovitejši, ko so načrtovani **preventivno** — pred pojavom zdravstvenih težav. Redna ponovna ocenjevanja (priporočeno vsako 2–3 leta ali ob spremembi delovnega procesa) zagotavljajo trajno ustreznost delovnih razmer.

!!! info "Povezava s Periodiko"
    Ukrepi z določenim rokom izvedbe se samodejno pojavijo v modulu **Analitika → Periodika**, ki odgovorno osebo opomni pred potekom roka.
