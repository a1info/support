# Ocene tveganj

Ocena tveganja je osrednji dokument varnostnih politik stranke. Nanjo se vežejo usposabljanja, meritve delovnega okolja, osebna varovalna oprema, zdravniški pregledi, evidence nevarnih snovi in pregledi delovne opreme.

Sistem omogoča pripravo ocen po tipičnih delovnih mestih (TDM) z uporabo prilagodljive dinamične matrike, katere formulo lahko skrbnik nastavi v **Sistemskih nastavitvah → Moduli**.

---

## 1. Tveganja in kategorije

**Dostop:** Ocene tveganj → Urejanje tveganj

- Določite tveganja in jih združite v kategorije (standardni nabor je že vključen, lahko ga prilagodite).
- Vsakemu tveganju lahko dodate splošne ukrepe, ki se bodo samodejno prikazali v ocenah TDM.

!!! warning
    Po vnosu tveganj in kategorij jih ne spreminjajte, da ne bi vplivali na že generirane dokumente.

---

## 2. Tipična delovna mesta (TDM)

**Dostop:** Ocene tveganj → Seznam TDM

V tem vmesniku definirate tipična delovna mesta:

| Podatek | Opis |
|---------|------|
| **Ime TDM** | Naziv delovnega mesta |
| **Glavna / občasna opravila** | Opis dela |
| **Trajanje** | Časovni obseg izvajanja |
| **Osebna varovalna oprema (OVO)** | Seznam uporabljene OVO |
| **Povezana tveganja** | Na desni strani tabele izberite tveganja, ki se za to delovno mesto obravnavajo |

Podatki se kasneje prenesejo v obrazec ocene in jih je tam mogoče dodatno urejati.

---

## 3. Ocena tveganja za TDM

**Dostop:** Ocene tveganj → Seznam ocen

Priprava ocene poteka v več korakih:

### 3.1. Splošni podatki
- Izberite **stranko**, **tipično delovno mesto (TDM)** in **datum ocene**.
- Izberite zaposlene, ki spadajo pod to TDM.  
  *Opomba:* zaposleni, ki jim je TDM že dodeljeno v modulu Stranke → Zaposleni, so predizbrani. Ostale lahko dodate ročno.

### 3.2. Urejanje splošnih podatkov TDM
- Uredite opis dela, trajanje, uporabljeno opremo, kemikalije itd.

### 3.3. Vrednotenje tveganj
V tabeli tveganj določite ocene parametrov:

| Parameter | Pomen |
|-----------|-------|
| **Verjetnost (a)** | Možnost, da do škodljivega dogodka pride |
| **Resnost (b)** | Morebitne posledice za zdravje delavca |
| **Pogostost (c)** | Opcijski parameter, prikaže se le, če je vključen v formulo (glej poglavje *Dinamična formula*) |

Sistem na podlagi v naprej določene **dinamične formule** (nastavljive v sistemskih nastavitvah) samodejno izračuna **stopnjo tveganja (T)**. Glede na doseženo vrednost se polje obarva v ustrezno barvo (npr. zelena – nizko tveganje, rdeča – nesprejemljivo tveganje).

### 3.4. Ukrepi
Za tveganja s kritično stopnjo vnesite:
- ukrepe za zmanjšanje tveganja,
- odgovorno osebo,
- rok izvedbe.

### 3.5. Periodike
Določite zahtevane periode za:
- usposabljanja,
- preglede delovne opreme,
- zdravniške preglede,
- meritve delovnega okolja.

Te nastavitve vplivajo na obveščanje o potekih v modulu **Periodika**.

---

## 4. Dokumenti OTV

**Dostop:** Ocene tveganj → Dokumenti OTV

Končni dokument »Ocena tveganja« združi več ocen posameznih TDM v enoten izpis.

1. Izberite **stranko**.
2. Prikaže se seznam ocen, ki še niso vključene v noben končni dokument.
3. Označite želene ocene, izberite **poslovno enoto**, **datum** in **predlogo za izpis**.
4. Na dnu dokumenta se lahko prikaže tudi analiza varnostnega stanja (seznam po meri iz *Nastavitve → Preizkusi po meri*).

---

## 5. Dinamična formula (konfiguracija modula)

V razdelku za konfiguracijo modulov (gumb nastavitve pri aktivnem modulu) lahko skrbniki prilagodijo delovanje posameznih sklopov aplikacije. 
Pri modulu **Ocene tveganj (Rass)** je omogočena konfiguracija **dinamične formule za izračun tveganja**.

V polje za formulo lahko vpišete poljubni matematični izraz z uporabo spremenljivk:
- `a` = Verjetnost
- `b` = Resnost
- `c` = Pogostost (sistem avtomatično prikaže to polje v uporabniškem vmesniku, če je zaznana uporaba spremenljivke v formuli).

Podprte so matematične funkcije (`min`, `max`, `floor`, `ceil`, `round`) in logični operaterji (`==`, `&&`, `?`, `:`). To omogoča preslikavo katerekoli tiskane matrike ocenjevanja tveganja neposredno v sistem. 
*Primer standardne AUWA formule:* `a * b`
*Primer kompleksne prilagojene 5-stopenjske matrike:* `min(a + 2, b + 2, floor((2 * b + a - 1) / 2)) - (a == 3 && b == 4 ? 1 : 0)`