# CRM (Organizacija nalog in projektov)

Modul **CRM** omogoča pregled in organizacijo dela z naročniki prek skupnega koledarja, projektov in nalog.

---

## 1. Pregled modula

CRM modul je osrednje mesto za upravljanje delovnih nalog, projektov in komunikacije s strankami.

### Dostop

**Glavni meni → CRM**

### Ključne funkcionalnosti

- Vizualni pregled nalog v kalendarski obliki
- Organizacija dela po koledarjih in projektih
- Sledenje statusom nalog
- Izpis delovnih nalogov (PDF)
- Samodejno generiranje periodičnih opomnikov

---

## 2. Naloge (Tasks)

Naloga je osnovna delovna enota v modulu CRM.

### Prikaz in dostop

- Naloge so prikazane v **koledarskem pogledu** (dan/teden/mesec) in kot seznam.
- Odprte naloge so vidne tudi na **uporabniškem Dashboardu** (začetni strani).

### Pravice

| Vloga | Vidnost nalog |
|-------|---------------|
| **Administrator** | Vidi vse naloge vseh uporabnikov; naloge lahko dodeljuje kateremu koli uporabniku. |
| **Navadni uporabnik** | Vidi samo naloge, ki so mu dodeljene. |

### Polja naloge

| Polje | Opis |
|-------|------|
| **Naziv** | Kratek opis naloge ali naročila. |
| **Začetek** | Datum in ura začetka naloge. |
| **Konec** | Datum in ura zaključka naloge. |
| **Status** | Trenutno stanje naloge (npr. Odprt, V teku, Zaključen). |
| **Dodeljen uporabnik** | Izvajalec naloge. |
| **Stranka** | Naročnik, za katerega se naloga izvaja. |
| **Koledar / Projekt** | Razvrstitev v ustrezni koledar ali projekt. |
| **Seznam storitev in odgovornih oseb** | Podrobnejši opis storitev, ki jih naloga vključuje, ter odgovorne osebe. |

!!! info "Upravljanje storitev"
    Seznam storitev, ki so na voljo pri nalogah, upravljajo administratorji prek **Nastavitve → Storitve**.

---

## 3. Koledarji

Naloge so organizirane po koledarjih. Vsak koledar ima svojo barvo in namen.

### Privzeti koledarji

| Koledar | Namen | Urejanje |
|---------|-------|----------|
| **Naročila** | Ročno ustvarjene naloge in delovni nalogi za stranke. | ✅ Prosto urejanje |
| **Periodika** | Samodejno generirane opomniške naloge iz evidenc z veljavnostjo (tečaji, pregledi, meritve). | ⛔ Samo za branje |

!!! warning "Periodika – samo za branje"
    Koledar **Periodika** se samodejno posodablja ob vnosu operacij z veljavnostjo v katerem koli modulu (usposabljanja, delovna oprema, požarna varnost itd.). **Ne urejajte nalog v tem koledarju ročno** – spremembe se bodo ob naslednji posodobitvi prepisale.

!!! tip
    Za ustvarjanje in urejanje nalog vedno uporabite koledar **Naročila** ali kateri koli ročno dodan koledar.

### Dodajanje lastnih koledarjev

Administratorji lahko dodajajo neomejeno število lastnih koledarjev (npr. »Inšpekcije«, »Meritve«, »Vzdrževanje«). Kliknite **Dodaj koledar** na levi stranski vrstici.

---

## 4. Projekti

Projekt združuje naloge, datoteke in komentarje v enotnem kronološkem pogledu.

### Dostop

**CRM → Projekti → Ogled**

### Struktura projekta

| Element | Opis |
|---------|------|
| **Naloge** | Vse naloge, ki so dodeljene temu projektu. |
| **Datoteke** | Priponke in dokumenti, vezani na projekt. |
| **Komentarji** | Komunikacija med člani ekipe znotraj projekta. |

### Pravice dostopa

| Nastavitev | Opis |
|-----------|------|
| **Privzeto** | Projekt je dostopen vsem uporabnikom sistema. |
| **Omejeno** | Ogled in urejanje projekta se omeji na točno določene uporabnike. |

!!! tip
    Projekte uporabite za večje naročniške pogodbe ali ponavljajoče se sklope del, kjer želite vse naloge, dokumentacijo in komunikacijo hraniti na enem mestu.

---

## 5. Delovni nalog

Delovni nalog je tiskani (PDF) dokument, ki potrjuje opravljeno delo pri stranki.

### Generiranje

Na **seznamu nalog** ali znotraj posamezne naloge kliknite ikono za **tisk delovnega naloga**.

### Vsebina delovnega naloga

- Podatki o stranki in naslovu
- Datum in čas opravljenega dela
- Opis opravljenih storitev
- Ime izvajalca
- Prostor za **podpis stranke** (potrdi sprejem opravljenega dela)

### Prilagoditev

Oblika in vsebina delovnega naloga sta prilagodljivi prek **predlog za tisk**. Predloge ureja administrator v nastavitvah sistema.

!!! info
    Delovni nalog služi kot uradna potrditev opravljenega dela in se priporoča za vsak terenski obisk pri stranki.
