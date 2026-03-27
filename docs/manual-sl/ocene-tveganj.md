# Ocene tveganj

Ocena tveganja je **osrednji dokument varnostnih politik stranke**. Nanjo se navezujejo usposabljanja, meritve delovnega okolja, osebna varovalna oprema, zdravniški pregledi, evidence nevarnih snovi in pregledi delovne opreme.

Sistem omogoča pripravo ocen po tipičnih delovnih mestih (TDM) z uporabo **prilagodljive dinamične matrike**, katere formulo nastavi skrbnik v konfiguraciji modula.

**Dostop:** Glavni meni → Ocene tveganj

---

## 1. Tveganja in kategorije

**Dostop:** Ocene tveganj → Urejanje tveganj

Tveganja in kategorije predstavljajo osnovo celotnega sistema ocenjevanja. Standardni nabor je že vključen, prilagodite ga potrebam stranke.

- Tveganja se združujejo v **kategorije** (npr. fizikalni dejavniki, kemični dejavniki, ergonomija …).
- Vsakemu tveganju lahko dodate **splošne ukrepe**, ki se samodejno prikažejo v ocenah TDM.

!!! warning "Pozor pri spreminjanju"
    Po vnosu tveganj in kategorij jih **ne spreminjajte**, saj vsaka sprememba vpliva na vse že obstoječe dokumente, v katerih je to tveganje ali kategorija uporabljena.

---

## 2. Tipična delovna mesta (TDM)

**Dostop:** Ocene tveganj → Seznam TDM

Tipično delovno mesto (TDM) opisuje skupino delavcev z istovrstnimi delovnimi nalogami in izpostavljenostmi. V tem vmesniku definirate osnovne karakteristike vsakega TDM:

| Podatek | Opis |
|---|---|
| **Ime TDM** | Naziv tipičnega delovnega mesta |
| **Glavna opravila** | Opis pretežnih delovnih nalog |
| **Občasna opravila** | Opis redkejših, a relevantnih delovnih nalog |
| **Trajanje** | Časovni obseg posameznih opravil |
| **OVO** | Osebna varovalna oprema, predpisana za to delovno mesto |
| **Povezana tveganja** | Seznam tveganj (izberite na desni strani tabele), ki se obravnavajo za to TDM |

!!! info
    Podatki iz TDM se samodejno prenesejo v obrazec ocene tveganja in jih je tam mogoče po potrebi dodatno urejati.

---

## 3. Ocena tveganja za TDM

**Dostop:** Ocene tveganj → Seznam ocen

Priprava ocene tveganja poteka v **petih korakih**.

### Korak 1 – Splošni podatki

- Izberite **stranko**, **tipično delovno mesto (TDM)** in **datum ocene**.
- Iz seznama izberite **zaposlene**, ki spadajo pod to TDM.

!!! tip "Predizbirani zaposleni"
    Zaposlenim, ki jim je TDM že dodeljeno v modulu **Zaposleni**, je le-to ob odprtju ocene samodejno predizbrano. Ostale zaposlene lahko dodate ročno.

### Korak 2 – Urejanje splošnih podatkov TDM

Preglejte in dopolnite opis delovnega mesta, prenesen iz TDM:

- opis dela in trajanje,
- delovna oprema in stroji,
- kemikalije in nevarne snovi,
- druge relevantne okoliščine.

### Korak 3 – Vrednotenje tveganj

Za vsako tveganje, vezano na TDM, ocenite parametre:

| Parameter | Oznaka | Opis |
|---|---|---|
| **Verjetnost** | `a` | Možnost, da do škodljivega dogodka sploh pride |
| **Resnost** | `b` | Morebitne posledice za zdravje ali varnost delavca |
| **Pogostost** | `c` | Pogostost izpostavljenosti tveganju (prikaže se le, če je vključena v formulo) |

Sistem na podlagi nastavljene **dinamične formule** samodejno izračuna **stopnjo tveganja (T)** in polje obarva glede na rezultat:

| Barva | Pomen |
|---|---|
| 🟢 Zelena | Nizko / sprejemljivo tveganje |
| 🟡 Rumena | Zmerno tveganje — priporočeni ukrepi |
| 🔴 Rdeča | Nesprejemljivo tveganje — obvezni ukrepi |

### Korak 4 – Ukrepi

Za vsa tveganja s kritično ali nesprejemljivo stopnjo vnesite:

- **ukrepe** za zmanjšanje tveganja,
- **odgovorno osebo** za izvedbo ukrepa,
- **rok izvedbe**.

### Korak 5 – Periodike

Določite zahtevane **periode** za posamezne aktivnosti, vezane na to delovno mesto:

| Aktivnost | Opis |
|---|---|
| **Usposabljanja** | Rok ponavljanja usposabljanj za varnost pri delu |
| **Pregledi delovne opreme** | Rok rednih tehničnih pregledov |
| **Zdravniški pregledi** | Rok ponavljanja obdobnih preventivnih pregledov |
| **Meritve delovnega okolja** | Rok ponavljanja meritev (hrup, osvetljenost …) |

!!! info "Modul Periodika"
    Nastavitve periodik vplivajo na **obveščanje** v modulu **Analitika → Periodika**. Ko se rok izteče, sistem samodejno obvesti odgovornega uporabnika.

---

## 4. Dokumenti OTV

**Dostop:** Ocene tveganj → Dokumenti OTV

Modul **Dokumenti OTV** združi več ocen posameznih TDM v enoten, celovit dokument ocene tveganja za stranko.

**Postopek:**

1. Izberite **stranko**.
2. Prikaže se seznam ocen TDM, ki **še niso vključene** v noben končni dokument.
3. Označite želene ocene.
4. Izberite **poslovno enoto (PE)**, **datum dokumenta** in **predlogo za izpis**.
5. Na dnu dokumenta se po želji doda **analiza varnostnega stanja** (konfigurirljiv seznam iz *Nastavitve → Preizkusi po meri*).
6. Potrdite in generirajte dokument.

!!! tip
    Dokument OTV je uradni zaključni dokument, ki ga stranke predložijo inšpekcijskim organom ali ga hranijo v arhivu. Priporočamo uporabo odobrene predloge podjetja.

---

## 5. Dinamična formula

**Dostop:** Gumb za nastavitve (zobnik ⚙) pri aktivnem modulu Ocene tveganj v konfiguracijski plošči modulov

Dinamična formula določa, **kako se iz vhodnih parametrov izračuna stopnja tveganja**. To omogoča, da sistem podpira katerokoli matriko ocenjevanja tveganja, ki jo stranka ali zakonodaja zahteva.

### Spremenljivke

| Spremenljivka | Pomen |
|---|---|
| `a` | Verjetnost |
| `b` | Resnost |
| `c` | Pogostost (stolpec se v vmesniku prikaže le, če je spremenljivka `c` prisotna v formuli) |

### Podprte funkcije in operatorji

| Element | Opis |
|---|---|
| `min(x, y)` | Vrne manjšo vrednost |
| `max(x, y)` | Vrne večjo vrednost |
| `floor(x)` | Zaokroži navzdol na celo število |
| `ceil(x)` | Zaokroži navzgor na celo število |
| `round(x)` | Zaokroži na najbližje celo število |
| `==` | Primerjalni operator (enakost) |
| `&&` | Logični operator IN |
| `? :` | Pogojni (ternarni) operator |

### Primeri formul

**Standardna formula** (produkt verjetnosti in resnosti):

```
a * b
```

**Kompleksna 5-stopenjska matrika** (prilagojena):

```
min(a + 2, b + 2, floor((2 * b + a - 1) / 2)) - (a == 3 && b == 4 ? 1 : 0)
```

!!! info "Preslikava matrike"
    Dinamična formula omogoča neposredno preslikavo **katere koli tiskane matrike ocenjevanja tveganja** v sistem. Vzamete vrednosti iz matrike, izpeljete formulo in jo vnesete v polje — sistem nato samodejno izračunava stopnje za vse ocene.
