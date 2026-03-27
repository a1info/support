# Sistem obveščanja

## Pregled

Sistem obveščanja v aplikaciji OP5 zagotavlja celovito komunikacijo med vsemi udeleženci – skrbniki sistema, izvajalci in uporabniki strank. Obveščanje poteka po dveh kanalih:

| Kanal | Opis |
|-------|------|
| **Interna sporočila** | Sporočila v realnem času znotraj sistema med vsemi registriranimi uporabniki |
| **Sistemska obvestila** | Avtomatska opozorila za roke, naloge in odobritve |
| **E-poštna obvestila** | Obvestila, poslana prek konfiguriranega SMTP strežnika na zunanji e-poštni naslov |

Sistem pomaga pri usklajevanju dela in zagotavlja, da so vse stranke pravočasno obveščene o pomembnih spremembah, rokih in obveznostih.

---

## Interna sporočila

Interna sporočila omogočajo neposredno komunikacijo v realnem času med vsemi registriranimi uporabniki sistema – tako internimi (zaposleni pri izvajalcu) kot zunanjimi (uporabniki strank).

### Dostop

Kliknite ikono **kuverte** (✉) v zgornji navigacijski vrstici. Ob neprebrani pošti je prikazana **rdeča značka** s številom neprebranih sporočil.

### Funkcionalnosti

- **Neposredno sporočanje** med katerima koli dvema uporabnikoma sistema
- **Transparentno obveščanje strank** – skrbniki strank prejmejo obvestila ob pomembnih spremembah podatkov (npr. oddaja novega poročila, posodobitev ocene tveganja)
- Podpora za **uporabnike stranke** – dostop do sporočil imajo tudi kontaktne osebe na strani naročnika

!!! tip "Nasvet"
    Interna sporočila so primerna za hitra vprašanja in usklajevanje. Za formalno dokumentacijo in sledenje nalogam uporabite modul CRM.

---

## Sistemska obvestila

Sistemska obvestila so **avtomatsko generirana** sporočila, ki vas opozorijo na dogajanje v sistemu brez ročnega posredovanja.

### Dostop

Kliknite ikono **zvonca** (🔔) v zgornji navigacijski vrstici. Ob novih obvestilih je prikazana značka s številom neprebranih vnosov.

### Vrste sistemskih obvestil

| Vrsta obvestila | Opis | Modul |
|----------------|------|-------|
| **Potekajoče veljavnosti** | Opozorilo pred iztekom usposabljanj, pregledov, zdravniških spričeval ipd. | Vsi moduli |
| **Dodelitev naloge** | Obvestilo, ko vam je v CRM sistemu dodeljena nova naloga | CRM |
| **Odobritev dopusta** | Obvestilo o odobritvi ali zavrnitvi vloge za dopust | HRM |
| **Zavrnitev dopusta** | Obvestilo o zavrnitvi vloge za dopust s komentarjem | HRM |

### Navigacija iz obvestil

!!! info
    Klik na posamezno obvestilo vas **neposredno preusmeri** na zadevni zapis v sistemu (npr. na usposabljanje z iztekajočo se veljavnostjo ali na nalogo v CRM-u). Ni potrebno ročno iskati zapisa.

---

## E-poštna obvestila

E-poštna obvestila omogočajo pošiljanje avtomatskih obvestil na zunanje e-poštne naslove. Vsa odhodna e-pošta je **šifrirana** prek konfiguriranega SMTP strežnika.

### Konfiguracija SMTP strežnika

**Dostop:** Sistem → Nastavitve → zavihek Podjetje → razdelek E-poštna konfiguracija

Pred aktivacijo e-poštnega obveščanja je potrebno nastaviti SMTP strežnik:

| Polje | Opis | Primer |
|-------|------|--------|
| **Mailer** | Vrsta pošiljatelja | `smtp` |
| **Host** | Naslov SMTP strežnika | `mail.podjetje.si` |
| **Port** | Vrata strežnika | `587` (TLS) ali `465` (SSL) |
| **Encryption** | Vrsta šifriranja | `tls` ali `ssl` |
| **Username** | Uporabniško ime za prijavo | `obvestila@podjetje.si` |
| **Password** | Geslo za SMTP account | — |
| **From Name** | Prikazno ime pošiljatelja | `Optima Prevent` |

!!! warning "Pomembno"
    Preden aktivirate obveščanje za stranke, preverite delovanje SMTP konfiguracije z gumbom **Testiraj** v Sistemskih nastavitvah.

### Konfiguracija obveščanja po strankah

**Dostop:** Nastavitve → Obveščanje

Ko je SMTP strežnik pravilno konfiguriran, nastavite obveščanje za vsako stranko posebej:

| Polje | Opis |
|-------|------|
| **Stranka** | Izberite stranko iz seznama |
| **Tip obveščanja** | Vrsta obvestil (veljavnosti, periodične naloge …) |
| **Dan v mesecu za pošiljanje** | Kateri dan v mesecu se pošlje mesečno e-poštno obvestilo |

#### Razpoložljivi tipi obveščanja

- **Opomniki veljavnosti** – obvestila o iztekajočih se veljavnostih usposabljanj, pregledov in zdravniških spričeval
- **Periodične naloge** – obvestila o nalogah s periodičnimi roki

### Šifrirana e-pošta

Vsa odhodna e-poštna sporočila, ki jih pošlje sistem OP5, so šifrirana prek konfiguriranega SMTP strežnika. Ni potrebna dodatna konfiguracija – šifriranje se vzpostavi samodejno glede na vrednost polja **Encryption** v nastavitvah SMTP.

---

## Nastavitev obveščanja

**Dostop:** Nastavitve → Obveščanje

### Postopek nastavitve

1. Odprite **Nastavitve → Obveščanje**
2. Kliknite **Dodaj** ali izberite obstoječo nastavitev za stranko
3. Izpolnite polja:
   - **Tip obveščanja** – izberite vrsto obvestil
   - **Dan v mesecu za pošiljanje** – vnesite številko dneva (npr. `1` za prvi dan v mesecu)
4. Shranite nastavitev

!!! tip "Nasvet pred aktivacijo"
    Pred aktivacijo obveščanja za stranke obvezno:

    1. Nastavite SMTP strežnik v **Sistem → Nastavitve → Podjetje**
    2. Preverite, da ima stranka veljavne e-poštne naslove kontaktnih oseb
    3. Testirajte pošiljanje z gumbom **Testiraj** v konfiguraciji e-pošte

### Pogoji za delovanje

| Pogoj | Stanje |
|-------|--------|
| SMTP konfiguracija | ✅ Obvezno konfigurirana |
| Kontaktni e-poštni naslovi stranke | ✅ Vneseni pri stranki |
| Tip obveščanja | ✅ Izbran v nastavitvah obveščanja |
| Dan v mesecu | ✅ Nastavljen (1–28) |
