# Sistemske nastavitve

**Dostop:** Sistem → Nastavitve

V tem razdelku upravljate osnovne podatke podjetja, aktivacijo modulov, nastavitve za pošiljanje e‑pošte, nadgradnjo sistema in digitalno podpisovanje dokumentov.

---

## Podjetje (Company)

### Osnovni podatki

| Polje | Opis |
|-------|------|
| **Ime podjetja** | Polno ime matične družbe |
| **DDV številka** | Identifikacijska številka za DDV |
| **Matična številka** | Registrska številka podjetja |
| **Naslov** | Naslov sedeža podjetja |
| **Kraj** | Mesto / poštna številka sedeža |
| **Telefon** | Stacionarna telefonska številka |
| **Mobilni** | Mobilna telefonska številka |
| **E‑pošta** | Javni kontaktni e-poštni naslov |
| **Spletna stran** | URL spletnega mesta podjetja |
| **Odgovorna oseba** | Ime in priimek odgovorne osebe |

### Logotip in podpis

- **Logotip** – naloži se slikovna datoteka (PNG/JPG); prikaže se v poročilih in na prijavnem zaslonu aplikacije.
- **Podpis** – slikovna datoteka podpisa odgovorne osebe; uporablja se pri digitalnem podpisovanju dokumentov (skupaj s certifikatom P12).

### Poslovne enote (Business Units)

Tabela prikazuje vse poslovne enote matične družbe. Vsaka enota ima svoje ime, naslov in kontaktne podatke.

!!! note "Opomba"
    Dodajanje in brisanje poslovnih enot je omejeno, kadar je sistem aktivno povezan z osrednjo licenčno storitvijo in obstaja lastniška stranka. Poslovne enote se navezujejo na obveščanje in poročila po enotah.

### E‑poštna konfiguracija (SMTP)

**Dostop:** Sistem → Nastavitve → zavihek Podjetje → razdelek Email Configuration

Sistem Optima Prevent omogoča pošiljanje sistemskih obvestil (npr. o poteku veljavnosti usposabljanj in opreme), vendar **nima vgrajenega lastnega SMTP strežnika za pošiljanje e-pošte**. Za uspešno pošiljanje obvestil mora uporabnik priskrbeti in nastaviti svoj lastni SMTP strežnik.

!!! warning "Opozorilo glede MS Office 365 in Gmail (Google Workspace)"
    Glavni ponudniki poslovne e-pošte (kot sta **Microsoft Office 365** in **Google Workspace / Gmail**) zaradi strogih varnostnih politik (onemogočanje t.i. "Basic Authentication", obvezna dvostopenjska avtentikacija - 2FA) **pogosto ne dovoljujejo neposrednega pošiljanja e-pošte** preko preprostega SMTP protokola ali pa zahtevajo zapleteno nastavljanje posebnih aplikacijskih gesel. Uporaba teh ponudnikov za sistemsko pošiljanje ni priporočljiva.

**Kako zagotoviti ustrezen SMTP strežnik?**

Za zanesljivo delovanje priporočamo eno izmed naslednjih rešitev:

1. **Uporaba SMTP strežnika vašega spletnega gostovanja**
   Če ima vaše podjetje zakupljeno klasično spletno gostovanje (npr. cPanel pri ponudnikih kot so Neoserv, Domenca, Hostinger, Domovanje), lahko v njihovi nadzorni plošči ustvarite namenski e-poštni predal (npr. `obvestila@vase-podjetje.si`) in uporabite njihove SMTP podatke.

2. **Namenske storitve za pošiljanje e-pošte (Transactional Email Services)**
   Te storitve so narejene specifično za pošiljanje sistemskih sporočil iz aplikacij in zagotavljajo najvišjo stopnjo dostavljivosti (e-pošta ne konča v vsiljeni pošti/spamu).
   
!!! tip "Brezplačne možnosti (odlične za zagon in manjši obseg obvestil)"
    * **[Brevo (prej Sendinblue)](https://www.brevo.com/)**: Brezplačen paket omogoča do 300 poslanih e-mailov na dan.
    * **[MailerSend](https://www.mailersend.com/)**: Brezplačen paket vključuje do 3.000 sporočil na mesec.
    * **[Mailtrap](https://mailtrap.io/)**: Ponuja brezplačen paket primeren za testiranje in osnovno pošiljanje.
---

!!! info "Plačljive možnosti (za podjetja z velikim obsegom sporočil)"
    * **[Mailgun](https://www.mailgun.com/)**
    * **[SendGrid (Twilio)](https://sendgrid.com/)**
    * **[Postmark](https://postmarkapp.com/)**
    * **[Amazon SES](https://aws.amazon.com/ses/)**
---

**Nastavitve za odhodno pošiljanje:**

V vmesniku izpolnite naslednja polja glede na podatke vašega SMTP ponudnika:

| Polje | Opis | Primer vrednosti |
|-------|------|-----------------|
| **SMTP Mailer** | Vrsta pošiljatelja | `smtp` |
| **Mail Host** | Naslov SMTP strežnika | `smtp-relay.brevo.com` ali `mail.vasadomena.si` |
| **Mail Port** | Vrata strežnika | `587` (TLS) ali `465` (SSL) |
| **Mail Encryption** | Vrsta šifriranja | `tls` ali `ssl` |
| **Mail Username** | Uporabniško ime za prijavo | `sistemska.obvestila@podjetje.si` |
| **Mail Password** | Geslo za SMTP račun | Vaše SMTP ali API geslo |
| **Mail From Name** | Prikazno ime pošiljatelja | `Optima Prevent Sistem` |

---

## Moduli

### Pregled aktivnih modulov

Na zavihku **Moduli** je prikazan seznam vseh modulov, ki jih sistem podpira. Za vsak modul so prikazani:

| Stolpec | Opis |
|---------|------|
| **Ime modula** | Naziv in kratek opis funkcionalnosti |
| **Status** | Aktiven / Neaktiven (pogojeno z licenco) |
| **Nastavitve** | Gumb z ikono zobnika – prikaže se le za module s konfiguracijo |

### Stanje licence

V zgornjem delu zavihka so prikazani podatki o licenci:

| Podatek | Opis |
|---------|------|
| **Trenutni paket / načrt** | Naziv aktivnega licenčnega paketa |
| **Datum poteka licence** | Datum izteka (prazno = neomejena licenca) |
| **Zadnja sinhronizacija** | Datum in čas zadnje uspešne sinhronizacije z licenčnim strežnikom |

Gumb **Sinhroniziraj licenco** ročno sproži preverjanje stanja licence pri osrednjega strežnika Optima Prevent. To je koristno po nakupu novega modula ali podaljšanju licence.

### Konfiguracija modulov

Klik na gumb **Nastavitve** (ikona zobnika ⚙) pri posameznem aktivnem modulu odpre modalno okno z nastavitvami, specifičnimi za ta modul.

**Primer – modul Ocene tveganj (Rass):**

V nastavitvah modula Rass je mogoče konfigurirati **dinamično formulo** za izračun ocene tveganja. Skrbnik vnese matematično formulo, ki se aplicira na vrednosti parametrov tveganja (verjetnost, pogostost, resnost ipd.). Rezultat je numerična vrednost, ki se prikaže v poročilih ocene tveganja.

---

## Nadgradnja sistema

**Dostop:** Sistem → Nastavitve → zavihek Nadgradnja

Na tem zaslonu spremljate različico sistema in izvajate posodobitve.

### Prikaz različic

| Element | Opis |
|---------|------|
| **Nameščena različica** | Trenutna verzija, nameščena na strežniku (pridobljena iz baze) |
| **Razpoložljiva različica** | Najnovejša različica na centralnem strežniku Optima Prevent |
| **Gumb Posodobi** | Prikaže se, ko je na voljo novejša različica ALI ko superadmin želi znova namestiti trenutno verzijo |
| **Gumb Revert to …** | Prikaže se le superadminu, kadar je lokalna različica novejša od strežniške |
| **Dnevnik sprememb** | Na desni strani zaslona – seznam novosti in popravkov za vse objavljene različice |

### Postopek samodejne nadgradnje

Ko kliknete **Posodobi**, sistem samodejno izvede naslednje korake:

1. **Prenos paketa** z osrednjega strežnika Optima Prevent
2. **Odstranitev zastarelih datotek**, ki so bile opredeljene v paketu za nadgradnjo
3. **Razširitev nove kode** na strežnik
4. **Izvedba odvisnosti in migracij** – `composer update` ter Artisan ukazi (`migrate`, `cache:clear`, `config:cache` …)
5. **Posodobitev različice** v podatkovni bazi

!!! warning "Varnostno opozorilo"
    Pred vsako nadgradnjo naredite **varnostno kopijo podatkovne baze in datotek**. Nadgradnja je enosmerna – sistem po nadgradnji ne more samodejno povrniti prejšnje različice.

    Možnost povrnitve (**Revert to …**) je dostopna le superadminu in se **ne priporoča** v produkcijskem okolju.

---

## Digitalno podpisovanje dokumentov

**Dostop:** Nastavitve → Potrdila / Akreditacije

Sistem OP5 podpira samodejno digitalno podpisovanje vseh generiranih PDF dokumentov (zapisniki, poročila, potrdila) s pomočjo osebnega certifikata v formatu P12.

### Postopek nastavitve

1. Odprite **Nastavitve → Potrdila / Akreditacije**
2. Kliknite **Dodaj nov zapis**
3. V polju **Tip** izberite `digitalni podpis`
4. Naložite datoteko **P12** (osebni certifikat)
5. Vnesite **geslo** certifikata
6. Shranite zapis

Po uspešni shranitvi bo sistem ob vsakem generiranju PDF dokumenta le-tega **samodejno digitalno podpisal**.

### Prepoznavanje podpisanih dokumentov

Digitalno podpisani dokumenti so prepoznavni po:

- Vrstici **"DIGITALLY SIGNED"** v dokumentu
- Podatkih o podpisniku (ime, datum in čas podpisa, podatki certifikata)

!!! info "Dostop za stranke"
    Podpisani dokumenti so uporabnikom strank vidni po prijavi v modulu **Izdani dokumenti**, kjer si jih lahko prenesejo in preverijo veljavnost digitalnega podpisa.

---

## Številčenje dokumentov

**Dostop:** Sistem → Številčenje

Modul za samodejno številčenje omogoča definiranje pravil oštevilčevanja za vsako vrsto dokumenta posebej.

### Parametri oštevilčevanja

| Parameter | Opis |
|-----------|------|
| **Leto** | Vključi letnico v številko dokumenta (npr. `2024`) |
| **Stranka** | Vključi kratico ali šifro stranke |
| **Tip dokumenta** | Vključi oznako tipa dokumenta |
| **Zaporedna številka** | Samodejno naraščajoče zaporedje znotraj parametrov |

### Dokumenti s samodejnim številčenjem

- Zapisniki usposabljanj
- Potrdila o usposabljanju
- Zapisniki pregledov delovne opreme
- Certifikati delovne opreme
- Ocene tveganja
- Meritve