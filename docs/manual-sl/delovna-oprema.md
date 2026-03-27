# Delovna oprema

Modul Delovna oprema zagotavlja celovito evidenco strojev, naprav in orodij ter sledenje pregledom in certifikatom. Vključuje digitalni dostop prek QR kod za terensko delo.

---

## Pregled modula

| Komponenta | Opis |
|-----------|------|
| **Evidenca opreme** | Register vse delovne opreme z lastnostmi in fotografijami. |
| **Pregledi** | Evidenca prvih, periodičnih in kontrolnih pregledov. |
| **Zapisniki pregledov** | Združeni dokumenti, ki zajemajo več pregledov v en zapisnik. |
| **QR / ROA** | Hiter terenski dostop do podatkov opreme in pregled prek QR kode. |

**Dostop:** Glavna navigacija → Delovna oprema

---

## Evidenca delovne opreme

**Dostop:** Delovna oprema → Seznam delovne opreme

### Polja evidence

| Polje | Obvezno | Opis |
|-------|---------|------|
| **Stranka** | ✅ | Lastnik opreme. |
| **Poslovna enota** | — | PE znotraj stranke. |
| **Naziv opreme** | ✅ | Opisno ime naprave ali stroja. |
| **Serijska številka** | — | Tovarniška serijska številka. |
| **Inventarna številka** | — | Notranja inventarna oznaka organizacije. |
| **Tip / Model** | — | Šifrant tipa ali model opreme. |
| **Leto izdelave** | — | Letnica proizvodnje. |
| **Proizvajalec** | — | Ime proizvajalca ali dobavitelja. |
| **Slike** | — | Ena ali več fotografij opreme (JPG, PNG). |
| **Datum odpisa** | — | Datum, ko oprema ni več v aktivni uporabi. Oprema ostane v evidenci za zgodovinsko sledenje. |

### Ogled posameznega kosa opreme

Na detajlnem pogledu opreme so razpoložljive naslednje informacije in operacije:

- **Pregled podatkov** – vsa zgoraj navedena polja.
- **Zgodovina pregledov** – seznam vseh preteklih pregledov z datumi in rezultati.
- **QR koda** – generirana QR koda za nalepke in terenski dostop (ROA).
- **Akcije** – urejanje, odpis, tiskanje QR kode.

!!! info "Datum odpisa"
    Ko opremi nastavite datum odpisa, sistem jasno označi, da oprema ni več v aktivni uporabi. Vsi pretekli pregledi ostanejo shranjeni za revizijsko sled.

---

## Pregledi delovne opreme

**Dostop:** Delovna oprema → Pregledi → **Dodaj pregled** (+)

### Polja pregleda

| Polje | Obvezno | Opis |
|-------|---------|------|
| **Stranka** | ✅ | Stranka, pri kateri se pregled izvaja. |
| **Mikro lokacija** | — | Natančna lokacija znotraj objekta (npr. hala A, 1. nadstropje). |
| **Datum pregleda** | ✅ | Datum izvedbe pregleda. |
| **Veljavnost (leta)** | — | Rok veljavnosti pregleda. Sistem samodejno izračuna datum izteka. |
| **Uporabnik / Naslov** | — | Odgovorna oseba ali naslov uporabnika opreme. |
| **Ustreza** | ✅ | Rezultat pregleda: **Da** (ustreza) ali **Ne** (ne ustreza). |
| **Oprema** | ✅ | Izbor enega kosa opreme iz tabele (en pregled = ena enota opreme). |

### Tipi pregledov

| Tip | Opis |
|-----|------|
| **Prvi** | Pregled pred prvo uporabo nove ali premeščene opreme. |
| **Periodični** | Redni pregled v skladu z zakonskimi zahtevami ali navodili proizvajalca. |
| **Kontrolni** | Izredni pregled po popravilu, nesreči ali sumu okvare. |

### Preizkusi po meri

Za specifične tipe opreme (npr. dvigala, tlačne posode) je mogoče dodati **preizkuse po meri**:

**Dostop:** Sistem → Nastavitve → Preizkusi po meri

Preizkusi po meri se prikažejo kot dodatna polja na obrazcu pregleda za ustrezni tip opreme.

### Kopiranje prejšnjega pregleda

!!! tip "Prihranek časa s kopiranjem"
    Če je rezultat pregleda enak ali podoben prejšnjemu (npr. periodični pregled brez sprememb), uporabite funkcijo **Kopiraj pregled**. Sistem prekopira vse vrednosti prejšnjega pregleda – spremenite samo datum in morebitna odstopanja.

---

## Zapisniki pregledov

**Dostop:** Delovna oprema → Zapisniki

Zapisnik je uradni dokument, ki združuje enega ali več pregledov v en koheziven zapisnik za podpis in arhiviranje.

### Ustvarjanje zapisnika

**Dostop:** Delovna oprema → Zapisniki → **Dodaj zapisnik** (+)

Postopek:

1. **Izberite stranko** – določa, kateri pregledi so na voljo.
2. **Izberite preglede** – prikažejo se samo *prosti pregledi* (tisti, ki še niso vključeni v noben drug zapisnik).
3. **Dopolnite podatke:**

| Polje | Opis |
|-------|------|
| **Stranka / Poslovna enota** | Se prenese iz izbranih pregledov. |
| **Datum** | Datum sestave zapisnika. |
| **Tip pregleda** | Vrsta pregleda (npr. periodični, kontrolni). |
| **Merilniki** | Seznam inštrumentov in merilnikov, uporabljenih pri pregledu. |
| **Opombe** | Dodatne ugotovitve, priporočila ali pogoji. |

### Operacije nad zapisnikom

| Operacija | Opis |
|----------|------|
| **Uredi** | Popravite podatke, dokler zapisnik ni zaključen. |
| **Izbriši** | Možno le za nezaključene zapisnike. |
| **Natisni (DOCX)** | Sistem iz predloge generira datoteko DOCX za podpis in arhiviranje. |

!!! info "Avtomatično oštevilčenje"
    Če je oštevilčenje konfigurirano za tip pregleda, zapisnik ob shranitvi samodejno dobi zaporedno številko (npr. ZAP-DO-2024-042).

---

## QR kode – ROA (Remote Object Access)

Vsak kos delovne opreme ima svojo edinstveno **QR kodo**, ki omogoča hiter terenski dostop do podatkov brez prijave v spletni vmesnik.

### Kaj prikaže skeniranje QR kode?

- Osnovne informacije o opremi (naziv, model, serijska številka).
- Datum in rezultat **zadnjega pregleda**.
- Datum izteka veljavnosti pregleda.
- Fotografije opreme (če so naložene).

### Nastavitve javnega dostopa

| Nastavitev | Lokacija | Opis |
|-----------|---------|------|
| **Javni prikaz** | Sistemske nastavitve → ROA | Privzeto **omogočeno** – QR kodo lahko skenira vsakdo brez prijave. |
| **Zahtevaj prijavo** | Sistemske nastavitve → ROA | Če aktivirate, je za ogled podatkov potrebna prijava. |

### Ustvarjanje pregleda s terena

Za ustvarjanje novega pregleda neposredno prek QR kode je potrebna **prijava sistemskega uporabnika** (enkrat na sejo):

```
1. Skenirajte QR kodo na opremi.
2. Kliknite »Dodaj pregled«.
3. Ob prvem dostopu v seji se prikaže prijavni obrazec.
4. Po prijavi izpolnite in shranite pregled neposredno na terenu.
```

!!! tip "Nalepke z QR kodo"
    QR kodo natisnite iz detajlnega pogleda opreme in jo nalepite na fizično opremo. Priporočamo laminiranje za dolgo vzdržljivost v industrijskem okolju.

---

## QR »bulk« ustvarjanje

**Dostop:** Seznami → QR ustvarjanje

Funkcija za masovno ustvarjanje QR kod je namenjena organizacijam, ki uvajajo sistematično označevanje opreme.

### Postopek ustvarjanja

#### Možnost A – Generiranje novih QR kod

1. Določite **število** QR kod, ki jih želite ustvariti.
2. Sistem generira »prazne« QR kode brez dodelitve opremi.
3. Natisnite QR kode in jih nalepite na opremo.
4. Ob prvem skeniranju nalepke izberete:
   - **Dodaj novo opremo** – ustvarite nov zapis v evidenci.
   - **Dodeli obstoječi** – povežete kodo z že obstoječo opremo v sistemu.

#### Možnost B – Uvoz iz CSV/Excel

Ustvarite datoteko CSV ali Excel s stolpcem URL naslovov (obstoječe QR kode ali zunanji sistemi) in jo uvozite v sistem.

| Stolpec CSV | Opis |
|------------|------|
| `url` | URL naslov, ki ga QR koda kodira. |
| `naziv` | (Neobvezno) Opis ali naziv opreme. |

### Prilagoditev izpisa

Na izpisu QR kod je mogoče dodati:

- **Logotip** organizacije ali stranke.
- **Kontaktne informacije** (telefon, e-pošta).
- **Naziv opreme** ali inventarno številko.
- **Navodila** za skeniranje.

!!! tip "Priporočena velikost nalepke"
    Za zanesljivo skeniranje s pametnim telefonom priporočamo QR kode velikosti vsaj **3 × 3 cm**. Za hrupna ali umazana okolja izberite laminat ali kovinsko nalepko.

!!! warning "Dodelitev QR kode je enkratna"
    Ko je QR koda dodeljena določenemu kosu opreme, je ne morete prerazporediti na drugo opremo. Zagotovite pravilno dodelitev pred namestitvijo nalepke.
