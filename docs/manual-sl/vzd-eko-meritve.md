# VZD / EKO meritve

## 1. Pregled modula

Modul **EKO meritve** omogoča evidentiranje in upravljanje meritev delovnega okolja ter okoljevarstvenih meritev. Rezultati meritev se navezujejo na ocene tveganj in module požarne varnosti.

**Dostop:** Glavni meni → EKO meritve

### Pregled seznama

- Seznam prikazuje vse meritve, ki jih je vnesel **trenutno prijavljeni uporabnik**.
- **Skrbniki** vidijo meritve vseh uporabnikov.

### Filtri

| Filter | Opis |
|---|---|
| **Stranka** | Filtriranje po podjetju |
| **Tip meritve** | Filtriranje po vrsti meritve |
| **Uporabnik** | Filtriranje po vnositelju (vidno skrbnikom) |

---

## 2. Tipi meritev

Sistem podpira naslednje tipe meritev:

| Skupina | Tip meritve |
|---|---|
| **Delovno okolje** | Toplota (toplotno udobje) |
| **Delovno okolje** | Osvetljenost (osvetlitev delovnih mest) |
| **Elektrika** | Meritve elektroinstalacij |
| **Strelovod** | Meritve strelovodnih naprav |
| **Hrup** | Meritve hrupa v delovnem okolju |
| **Pretok zraka** | Meritve prezračevanja in pretoka zraka |

---

## 3. Dodajanje meritve

Postopek vnosa meritve poteka v **2 do 3 korakih**.

### Korak 1 – Splošno

Na prvem koraku vnesete splošne podatke o meritvi:

| Polje | Opis |
|---|---|
| **Stranka** | Podjetje, za katerega se meritev opravlja |
| **PE** | Poslovna enota |
| **Datum meritve** | Datum izvedbe meritve |
| **Podatki o predhodnih meritvah** | Referenca na prejšnjo meritev (datum, poročilo) |
| **Datum poročila** | Datum izdanega meritvenega poročila |
| **Številka poročila** | Evidenčna številka poročila |
| **Priponke** | Naložite merilno poročilo in spremljajoče dokumente |
| **Uporabljeni merilniki** | Seznam inštrumentov, s katerimi je bila meritev opravljena |

!!! tip "Zaključek brez parametrov"
    Meritev je mogoče zaključiti že na **prvem koraku** (brez vnosa podrobnih parametrov), kadar gre zgolj za evidenco obstoječega poročila oziroma shranjevanje dokumenta.

### Korak 2 – Tip meritve

Izberite vrsto meritve. Glede na izbiro se prikaže ustrezen vnosni obrazec s specifičnimi polji:

| Tip | Parametri |
|---|---|
| **Toplotno okolje** | Temperatura zraka, vlažnost, hitrost zraka, sevalna temperatura, WBGT indeks … |
| **Osvetljenost** | Osvetljenost delovnih površin (lux), enakomerno osvetljenost … |
| **Hrup** | Ekvivalentni nivo hrupa (LAeq), koničasti nivo, dnevna izpostavljenost (LEX) … |
| **Elektrika** | Vrednosti izolacijske odpornosti, ozemljitve, zaščitnih vodnikov … |
| **Strelovod** | Vrednosti odpornosti strelovodnega sistema, prehodne odpornosti … |
| **Pretok zraka** | Hitrost in količina zraka pri prezračevalnih napravah … |

### Korak 3 – Pregled in shranjevanje

Preverite vnesene podatke in potrdite shranjevanje meritve.

---

## 4. Upravljanje meritev

Za vsako obstoječo meritev so na voljo naslednje operacije:

| Operacija | Opis |
|---|---|
| **Uredi** | Spremenite podatke obstoječe meritve |
| **Izbriši** | Trajno odstranite meritev iz sistema |
| **Kopiraj** | Ustvari novo meritev s prekopirano splošnimi podatki — prihrani čas pri rednih ponovnih meritvah na istih lokacijah |
| **Natisni** | Generira izpis iz DOCX predloge |

!!! tip "Kopiranje meritev"
    Funkcija **Kopiraj** je posebej koristna pri rednih meritvah, kjer se splošni podatki (stranka, merilniki, lokacija) ne spremenijo. Po kopiranju prilagodite le datum in vrednosti parametrov.

---

## 5. Povezava s požarno varnostjo

Meritve za **strelovod** in **elektro naprave** so neposredno povezane z modulom **Požarna varnost**.

!!! info "Potek povezave"
    1. Meritve strelovoda in elektroinstalacij se vnesejo v modul EKO meritve.
    2. Pri vnosu objekta v modulu **Požarna varnost** izberete obstoječo meritev iz padajočega seznama.
    3. Rezultati meritve so vidni v **obeh modulih** — v EKO meritvah in v kartici objekta požarne varnosti.

Ta integracija prepreči podvajanje podatkov in zagotavlja enotni vir informacij o stanju inštalacij.
