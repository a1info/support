# HRM (Upravljanje kadrov)

Modul **HRM** poenostavlja procese vodenja kadrov, evidence delovnega časa, upravljanje dopustov in odsotnosti ter zaposlovanje novih sodelavcev.

---

## 1. Pregled modula

HRM zagotavlja celovito podporo vsem ključnim kadrovskim procesom:

- pregled prisotnosti in delovnega časa,
- upravljanje odsotnosti in dopustnih kvot,
- proces zaposlovanja novih sodelavcev,
- vodenje delovnega koledarja in praznikov.

### Dostop

**Glavni meni → HRM**

!!! warning "Pogoj za polno funkcionalnost"
    Za uporabo večine HRM funkcionalnosti morajo imeti zaposleni v sistemu dodeljen in **povezan IT uporabniški račun**. Račune povežite prek modula **Zaposleni** (zavihek Uporabnik).

---

## 2. Nadzorna plošča (Dashboard)

HRM nadzorna plošča daje hiter pregled stanja na tekočo dan.

### Vsebina nadzorne plošče

| Sekcija | Opis |
|---------|------|
| **Trenutno odsotni** | Seznam zaposlenih, ki so danes na dopustu ali bolniški odsotnosti. |
| **Čakajoči zahtevki** | Zahtevki za odsotnost, ki čakajo na odobritev nadrejenega. |
| **Hitra odobritev** | Gumb za takojšnje potrjevanje ali zavrnitev čakajočih zahtevkov neposredno z nadzorne plošče. |
| **Zaposlovanje** | Število novih kandidatov in odprtih razpisov (prikazano le, če je aktiven pod-modul za zaposlovanje). |
| **Terminal** | Bližnjica za hitro beleženje prihoda ali odhoda zaposlenega. |

!!! tip
    Nadzorno ploščo si odprite vsako jutro za hiter pregled stanja prisotnosti in morebitnih čakajočih zahtevkov, ki zahtevajo vašo pozornost.

---

## 3. Evidenca delovnega časa (Terminal)

Terminal (**Time Clock**) beleži prisotnost zaposlenih na delovnem mestu.

### Delovanje

- Zaposleni ob prihodu na delo klikne **Prihod (Clock-In)**.
- Zaposleni ob koncu izmene klikne **Odhod (Clock-Out)**.
- Sistem **preprečuje podvojene klice** znotraj iste minute (zaščita pred napaknim klikom).

### Vrste beleženih ur

| Vrsta | Opis |
|-------|------|
| **Redne ure** | Standardni delovni čas v okviru delovnika. |
| **Nadure** | Ure, opravljene nad standardnim delovnim časom. |
| **Nočno delo** | Ure, opravljene med nočno izmeno. |
| **Delo med prazniki** | Ure, opravljene na državni ali kolektivni praznik. |

!!! tip "Tablični terminal"
    Terminal je primeren za namestitev na skupni tablici pri vhodu v objekt. Zaposleni se zjutraj prijavijo, zvečer odjavijo – brez potrebe po računalniku.

---

## 4. Odsotnosti in dopusti

### Vrste odsotnosti

- Letni dopust
- Bolniška odsotnost
- Študijski dopust
- Neplačan dopust
- Druge vrste (po potrebi definirane v nastavitvah)

### Kvote dopustov

!!! info "Generiranje kvot"
    Sistem omogoča **hitro generiranje letnih dopustnih kvot** za vse aktivne zaposlene hkrati. Kvota vključuje:

    - osnovno število dni letnega dopusta,
    - prenos neuporabljenega dopusta iz preteklega leta.

Zaposleni lahko kadar koli preverijo stanje svojega dopusta (porabljeno / preostalo) prek lastnega profila.

### Potek zahtevka

```
Osnutek → Oddano → Potrjeno / Zavrnjeno
```

| Korak | Akter | Opis |
|-------|-------|------|
| **Osnutek** | Zaposleni | Vnos zahtevka z datumi in vrsto odsotnosti; ni še poslan. |
| **Oddano** | Zaposleni | Zahtevek je poslan v odobritev. |
| **Potrjeno** | Nadrejeni/HR | Zahtevek je odobren; dnevi se odštejejo od kvote. |
| **Zavrnjeno** | Nadrejeni/HR | Zahtevek je zavrnjen z možnostjo vpisa razloga. |

!!! tip
    Nadrejeni ali kadrovski referent vidi vse čakajoče zahtevke na **nadzorni plošči** in jih potrdi z enim klikom, brez potrebe po odpiranju posameznega zapisa.

---

## 5. Prazniki in delovni koledar

### Državni prazniki

Sistem samodejno sinhronizira seznam **slovenskih državnih praznikov**. To zagotavlja, da:

- vloge za dopust na praznike ne odštejejo dni iz letne kvote,
- terminal pravilno kategorizira ure kot »delo med prazniki«.

### Prilagojeni prazniki podjetja

Poleg državnih praznikov lahko dodate lastne proste dni:

| Tip | Primer |
|-----|--------|
| **Kolektivni dopust** | Kolektivni letni dopust podjetja v avgustu |
| **Dan podjetja** | Obletnica ustanovitve |
| **Druga zaprtja** | Inventura, selitev ipd. |

!!! warning
    Prilagojeni prazniki vplivajo na vse zaposlene. Preverite nastavitve pred dodajanjem.

---

## 6. Zaposlovanje (Recruitment)

Pod-modul za zaposlovanje pokriva celoten proces iskanja in selekcije novih sodelavcev.

### Razpisi

Upravljajte odprta delovna mesta:

| Status | Pomen |
|--------|-------|
| **Osnutek** | Razpis v pripravi, ni javno objavljen. |
| **Odprto** | Aktiven razpis, sprejem prijav. |
| **Zapolnjeno** | Mesto je zasedeno, razpis je zaključen. |

### Kandidati

Za vsakega kandidata shranite:

- osebne podatke in kontaktne podatke,
- življenjepis (CV) in morebitne priponke,
- notranje opombe kadrovske službe.

### Kanban tabla – sledenje fazam selekcije

Kandidati se premikajo skozi faze zaposlitvene selekcije s preprostim **vleci in spusti (drag-and-drop)**:

```
Prejeto → V pregledu → Intervju → Ponudba → Zavrnjeno
```

| Faza | Opis |
|------|------|
| **Prijava prejeta** | Nova prijava, prejeta po e-pošti ali ročnem vnosu. |
| **V pregledu** | Kadrovska služba pregleduje dokumentacijo. |
| **Intervju** | Kandidat je povabljen na razgovor. |
| **Ponudba** | Kandidatu je posredovana ponudba za zaposlitev. |
| **Zavrnjeno** | Kandidat ni bil izbran v tej fazi. |

!!! tip
    Kanban tabla omogoča hiter vizualni pregled vseh aktivnih kandidatov za posamezni razpis. S klikom na kandidatovo kartico dostopate do vseh shranjenih dokumentov in opomb.
