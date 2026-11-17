# Urejanje predlog (dokumenti, obrazci in e-pošta)

## Pregled

Sistem OP5 podpira tri vrste predlog za dokumente, obrazce in e-pošto:

| Vrsta predloge | Opis | Primeri uporabe |
|----------------|------|-----------------|
| **FORMS** | Interaktivni obrazci za vnos podatkov na terenu | Nestandardni pregledi, vaje evakuacije, kontrolne liste |
| **DOCX** | Predloge za tiskane dokumente (potrdila, zapisniki) | Potrdila o usposabljanju, zapisniki pregledov, poročila |
| **E-poštne predloge** | Zadeva in telo e-poštnih sporočil | Opomniki, e-test vabila, obvestila in kampanje |

Predloge določajo postavitev, vsebino in obliko izpisanih dokumentov. Vsaka predloga je vezana na določen tip dokumenta in se ob generiranju samodejno napolni z dejanskimi podatki iz baze.

---

## Predloge FORMS

**Dostop:** Sistem → Predloge → zavihek **FORMS**

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

## E-poštne predloge

**Dostop:** Sistem → Predloge → zavihek **E-poštne predloge**

E-poštne predloge določajo **zadevo in telo** sporočila. Pošiljateljski račun, naslov From in Reply-To niso del predloge – ti podatki se določijo v [E-poštnih računih](sistemske-nastavitve.md#e-postni-racuni).

Predloge uporabljajo samodejna obvestila, e-test vabila in opomniki ter CRM kampanje. Brez aktivnega SMTP računa se sporočila ne pošljejo, tudi če je predloga aktivna.

### Moduli predlog

| Modul | Uporaba |
|-------|---------|
| **Kampanje** | E-poštne kampanje v CRM; predlogo izberete na kampanji. |
| **E-test / izobraževanja** | Vabila in opomniki za e-učenje. |
| **Veljavnosti** | Periodična poročila o potekih. |
| **HRM** | Dopust, kandidati in druga kadrovska obvestila. |
| **Dokumentni tok** | Zahteve in odločitve pri odobritvah. |
| **CRM** | Naloge in dogodki v CRM. |
| **Medicina dela** | Napotitve in izvidi. |
| **ERP** | Obvestila, povezana s ponudbami in financami. |
| **Sistem** | Varnostne kopije, sinhronizacija in sistemska opozorila. |

### Polja predloge

| Polje | Opis |
|-------|------|
| **Koda** | Enolična oznaka predloge; priporočena je kratka oznaka, npr. `etest_invite_sl`. |
| **Jezik** | Slovenščina ali angleščina. Sistem izbere jezik glede na jezik aplikacije, sicer slovenščino. |
| **Dogodek** | Koda dogodka iz sistemskega kataloga, na katerega se predloga veže (npr. `etest.invite`, `etest.expiring`, `crm.task_created`). Začetek vnosa prikaže predloge z opisi; prazno polje pomeni splošno predlogo. Pri kampanjah polje ni prikazano. |
| **Naziv** | Naziv za skrbnike; ni del poslanega sporočila. |
| **Zadeva** | Zadeva e-pošte. |
| **Nadomestna zadeva (A/B)** | Neobvezna druga zadeva za poznejše A/B preizkuse. |
| **Telo (tekst)** | Besedilna različica sporočila; priporočena je za zanesljivo dostavo. |
| **Telo (HTML)** | Neobvezna obogatena različica. Če je prazna, se uporabi besedilna različica. |
| **Opombe** | Interne opombe, ki se ne pošljejo. |
| **Aktivna** | Neaktivna predloga se ne uporabi; sistem uporabi privzeto vsebino, če ta obstaja. |

!!! info "Kako izberem dogodek"
    V polje **Dogodek** vnesite kodo iz sistemskega kataloga. Ko začnete tipkati, se prikažejo razpoložljive kode z opisom; prazno polje pomeni splošno predlogo. Če koda ni v katalogu, je shranjevanje zavrnjeno. Za kampanje izberite modul **Kampanje**; polje Dogodek je pri njih skrito, ker predlogo izbere kampanja.

### Spremenljivke

Spremenljivke vstavite v dvojnih zavitih oklepajih, na primer `{{sender_name}}`. Med pošiljanjem jih sistem zamenja z dejanskimi podatki.

| Spremenljivka | Pomen |
|---------------|-------|
| `{{sender_name}}` | Ime pošiljatelja oziroma prijavljenega uporabnika. |
| `{{phone}}`, `{{email}}`, `{{website}}` | Kontaktni podatki podjetja. |
| `{{date}}`, `{{time}}` | Datum in čas pošiljanja. |
| `{{first_name}}`, `{{last_name}}`, `{{company}}` | Podatki prejemnika oziroma osebe. |
| `{{syscompany}}`, `{{sysaddress}}`, `{{sysemail}}`, `{{systel}}`, `{{sysweb}}` | Podatki sistemskega podjetja. |
| `{{course}}`, `{{username}}`, `{{password}}`, `{{link}}` | Podatki e-testa (samo modul E-test). |
| `{{expiry_date}}`, `{{days_left}}` | Rok veljavnosti in število preostalih dni (e-test). |
| `{{previous_subject}}` | Zadeva prejšnjega sporočila (kampanje). |
| `{{unsubscribe_url}}` | Povezava za odjavo. Pri kampanjah jo sistem doda samodejno, če je v sporočilu ni. |

Razpoložljive spremenljivke so prikazane tudi pod poljem **Telo (tekst)**; uporabite jih lahko s klikom oziroma ročnim vnosom.

### Predogled in upravljanje

1. Odprite **Sistem → Predloge → E-poštne predloge**.
2. Izberite modul in predlogo s seznama ali kliknite **Dodaj** za novo predlogo.
3. Izpolnite polja in po potrebi kliknite **Predogled** – prikazani so zamenljivi deli s primerom za izbrani modul.
4. Shranite predlogo. Izbrišete jo lahko z ikono koša; predloga, ki jo uporablja kampanja, najprej preverite.

!!! tip "Kampanjske predloge"
    Za kampanje izberite modul **Kampanje**. Predlogo nato izberete v koraku **Predloga** pri posamezni kampanji. Dogodek ni potreben, povezava za odjavo pa se doda samodejno, tudi če v predlogi ni `{{unsubscribe_url}}`.

!!! note "Predloga ne določa pošiljatelja"
    Če želite spremeniti From, Reply-To ali strežnik, uredite [E-poštni račun](sistemske-nastavitve.md#e-postni-racuni). Predloga določa samo vsebino sporočila.

---

## Predloge DOCX

**Dostop:** Sistem → Predloge → zavihek **DOCX**

### Namen

Predloge DOCX se uporabljajo za generiranje **formalnih tiskovin** – dokumentov s statično postavitvijo (logotipi, stili, slike) in dinamičnim delom (spremenljivke, ki se zapolnijo s podatki ob generiranju).

Podprti tipi dokumentov:

| Tip | Opis |
|-----|------|
| **usposabljanje** | Potrdila o usposabljanju, zapisniki usposabljanj |
| **delovna oprema** | Zapisniki pregledov delovne opreme, certifikati |
| **meritve** | Poročila o meritvah (hrup, osvetljenost, kemikalije …) |
| **ocena tveganja** | Dokumenti ocene tveganja po delovnih mestih |
| **kartica stranke** (`card`) | Kartica stanja stranke na izbrani dan |
| **periodično poročilo** (`repy`) | Letno, mesečno ali obdobno poročilo za stranko |

!!! info "Poročila za stranke"
    Predlogi tipov `card` in `repy` se izbereta na zaslonu **Analitika → Poročila za stranke**. Seznam njunih spremenljivk je v [Legendi spremenljivk](variables-sl.md).

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

1. Odprite **Sistem → Predloge → zavihek DOCX**
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
