# Urejanje predlog za izpis

## Pregled

Sistem OP5 podpira dve vrsti predlog za generiranje tiskovin in obrazcev:

| Vrsta predloge | Opis | Primeri uporabe |
|----------------|------|-----------------|
| **FORMS** | Interaktivni obrazci za vnos podatkov na terenu | Nestandardni pregledi, vaje evakuacije, kontrolne liste |
| **DOCX** | Predloge za tiskane dokumente (potrdila, zapisniki) | Potrdila o usposabljanju, zapisniki pregledov, poročila |

Predloge določajo postavitev, vsebino in obliko izpisanih dokumentov. Vsaka predloga je vezana na določen tip dokumenta in se ob generiranju samodejno napolni z dejanskimi podatki iz baze.

---

## Predloge FORMS

**Dostop:** Nastavitve → Predloge FORM

### Namen

Predloge FORMS se uporabljajo za **nestandardne preglede in obrazce**, kjer je treba zbirati strukturirane podatke po meri stranke. Primeri:

- Nestandardni kontrolni pregledi
- Vaje evakuacije
- Prilagojene kontrolne liste
- Interni varnostni obrazci

### Elementi obrazca

Pri urejanju predloge FORM dodajate elemente iz nabora razpoložljivih tipov:

| Element | Tip | Opis |
|---------|-----|------|
| **Naslov** | Prikaz | Glavni naslov obrazca ali razdelka |
| **Podnaslov** | Prikaz | Podrejeni naslov / opis razdelka |
| **Naslov tabele** | Prikaz | Glava tabele za tabelarni prikaz |
| **Besedilo** | Prikaz | Statično besedilo (navodila, opisi) |
| **Polje za vnos (input)** | Vnos | Besedilno vnosno polje za prosti vnos |
| **Potrditveno polje (checkbox)** | Vnos | Eno potrditveno polje (označeno / neoznačeno) |
| **Dvojno potrditveno polje (da/ne)** | Vnos | Par polj Da / Ne za binarno izbiro |
| **SQL koda** | Dinamično | Dinamični prikaz podatkov iz baze na podlagi SQL poizvedbe |

### Spremenljivke v besedilu elementov

V besedilu elementov obrazca lahko uporabite naslednje vgrajene spremenljivke:

| Spremenljivka | Opis |
|---------------|------|
| `cCustomer` | Polno ime stranke |
| `cAddress` | Naslov stranke |

**Primer uporabe:**
```
Izvajalec pregleda za stranko: ${cCustomer}, ${cAddress}
```

!!! tip "Nasvet"
    Element tipa **SQL koda** je namenjen naprednim uporabnikom. Poizvedba mora vračati podatke, ki so smiselni v kontekstu obrazca. Za pomoč pri oblikovanju SQL poizvedb se obrnite na ekipo Optima Prevent.

---

## Predloge DOCX

**Dostop:** Nastavitve → Urejanje predlog

### Namen

Predloge DOCX se uporabljajo za generiranje **formalnih tiskovin** – dokumentov s statično postavitvijo (logotipi, stili, slike) in dinamičnim delom (spremenljivke, ki se zapolnijo s podatki ob generiranju).

Podprti tipi dokumentov:

| Tip | Opis |
|-----|------|
| **usposabljanje** | Potrdila o usposabljanju, zapisniki usposabljanj |
| **delovna oprema** | Zapisniki pregledov delovne opreme, certifikati |
| **meritve** | Poročila o meritvah (hrup, osvetljenost, kemikalije …) |
| **ocena tveganja** | Dokumenti ocene tveganja po delovnih mestih |

### Vrste spremenljivk

| Vrsta | Opis | Primer |
|-------|------|--------|
| **Posamezne spremenljivke** | Enkratna vrednost – zamenjana z enim podatkom | Ime stranke, datum pregleda |
| **Tabelarne spremenljivke (vrstične)** | Ponovijo se za vsako vrstico v tabeli | Seznam udeležencev usposabljanja |
| **Blok spremenljivke** | Ponavljajoči se paragrafi; vsebujejo posamezne ali tabelarne spremenljivke | Blok za vsak pregledani stroj |

### Format spremenljivk

Vse spremenljivke v DOCX datoteki sledijo isti sintaksi:

```
${imeSpremenljivke}
```

- **Posamezne** – vstavljene neposredno v besedilo ali celico
- **Tabelarne** – vstavljene v celice tabele; sistem samodejno doda vrstice za vsak zapis
- **Blok** – vstavljene znotraj označenega bloka, ki se ponovi za vsak objekt

**Primer za posamezno spremenljivko:**
```
Stranka: ${customerName}
Datum pregleda: ${inspectionDate}
```

**Primer za tabelarno spremenljivko (v vrstici tabele):**
```
| ${participantName} | ${participantRole} | ${participantSignature} |
```

### Spremenljivke za lastna polja (EAV)

Za **lastna polja** (polja po meri, dodana posamezni stranki) se uporablja posebna sintaksa z oznako polja in predpono pozicije:

| Predpona | Kontekst | Primer |
|----------|----------|--------|
| `lst` | Polje na ravni usposabljanja / pregleda | `${lst<code>}` |
| `dev` | Polje na ravni naprave / opreme | `${dev<code>}` |

Kjer je `<code>` koda lastnega polja, definirana v nastavitvah.

!!! info "Celoten seznam spremenljivk"
    Razpoložljive spremenljivke so odvisne od tipa dokumenta. Popoln seznam spremenljivk po tipih predlog je zbran v [Legendi spremenljivk (DOCX/FORM)](variables-sl.md).

---

## Dodajanje in upravljanje predlog DOCX

### Dodajanje nove predloge

1. Odprite **Nastavitve → Urejanje predlog**
2. Kliknite gumb **Dodaj**
3. Izpolnite polja:

| Polje | Opis |
|-------|------|
| **Ime** | Naziv predloge (prikazano pri izbiri) |
| **Tip** | Vrsta dokumenta (`usposabljanje`, `delovna oprema`, `meritve`, `ocena tveganja`) |
| **Zaporedna številka** | Določa prioriteto; nižja številka = višja prioriteta |
| **DOCX datoteka** | Naložite pripravljeno DOCX datoteko s spremenljivkami |

4. Shranite zapis

### Prioriteta predlog

Kadar je za isti tip dokumenta na voljo **več predlog**, sistem privzeto uporabi tisto z **najnižjo zaporedno številko**.

### Izbira predloge pri generiranju

Pred generiranjem dokumenta je mogoče izbrati katero koli predlogo za ta tip dokumenta:

- V seznamu zapisov (npr. Zapisniki usposabljanj, Zapisniki delovne opreme, Meritve …) imata ikona **Dok. za stranko** (PDF) in ikona **DOCX** spustni seznam vseh predlog za ta tip dokumenta.
- Predloga, ki je bila **zadnjič uporabljena** za generiranje dokumenta tega zapisa, je v seznamu označena s kljukico ✓.
- Sistem si izbrano predlogo **zapomni** za posamezen zapis – ob naslednjem generiranju je takoj razvidno, katera predloga je bila uporabljena nazadnje.

### Generiranje dokumentov iz seznamov

Generiranje dokumentov poteka neposredno iz seznama zapisov, brez osveževanja strani:

| Ikona | Namembnost |
|-------|------------|
| **PDF (Dok. za stranko)** | Generira PDF dokument za stranko iz izbrane DOCX predloge. Če je nastavljeno digitalno podpisovanje, je dokument tudi digitalno podpisan. |
| **PDF po meri** | V istem spustnem seznamu lahko namesto generiranja naložite **lasten PDF dokument** (npr. ročno podpisan izpis). |
| **DOCX** | Generira DOCX datoteko za podpis in arhiv iz izbrane predloge. |

Ko je dokument za stranko enkrat ustvarjen, se na njegovem mestu prikažeta ikona za **prenos** in ikona za **brisanje** dokumenta. Po brisanju se ponovno prikaže spustni seznam za novo generiranje.

!!! info "Obvestila"
    Uspešno generiranje in morebitne napake sistem sporoči z obvestilom v kotu zaslona. Vneseni dokument (PDF po meri) mora biti datoteka tipa PDF in velikosti do 10 MB.

### Urejanje obstoječe predloge

1. V seznamu predlog kliknite na naziv predloge
2. Izvedite željene spremembe (zamenjava DOCX datoteke, sprememba naziva ali prioritete)
3. Shranite spremembe

!!! warning "Pozor"
    Zamenjava DOCX datoteke pri obstoječi predlogi vpliva na vse **prihodnje** generacije dokumentov. Že generirani dokumenti ostanejo nespremenjeni.

---

## Predloga potrdila za usposabljanje (samodejno generiranje)

Predloge tipa **usposabljanje** običajno vsebujejo zapisnik in prilogo s potrdili. Sistem iz naložene predloge **samodejno izdela ločeno predlogo samo za potrdilo** (tip **Potrdilo o usposabljanju**), ki se uporablja pri tiskanju posameznih potrdil iz kartice zaposlenega.

### Kako deluje

- Zadnji del predloge usposabljanja mora vsebovati blok potrdila, označen s spremenljivkama `${cloneCert0}` in `${/cloneCert0}` – enako kot pri zapisniku.
- Ob vsakem nalaganju nove predloge tipa **usposabljanje** sistem:

    1. iz naložene datoteke izreže zadnje poglavje (blok potrdila),
    2. ga shrani kot samostojno predlogo tipa **Potrdilo o usposabljanju**,
    3. staro predlogo potrdila nadomesti z novo in jo izbriše.

- Če naložena predloga ne vsebuje bloka potrdila, sistem obdrži obstoječo predlogo potrdila in izpiše opozorilo.

### Opozorila

- Predloga potrdila se praviloma upravlja samodejno; po potrebi jo lahko ročno nadomestite z nalaganjem lastne DOCX datoteke tipa **Potrdilo o usposabljanju**.
- Že natisnjena potrdila se ob zamenjavi predloge ne spremenijo. Pri ponovnem tiskanju starejšega potrdila sistem uporabi predlogo, ki je bila shranjena ob generiranju zapisnika; če ta ne obstaja več, uporabi trenutno predlogo.
