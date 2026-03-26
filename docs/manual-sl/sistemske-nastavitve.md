# Sistemske nastavitve

**Dostop:** Sistem → Nastavitve

V tem razdelku upravljate osnovne podatke podjetja, aktivacijo modulov, nastavitve za pošiljanje e‑pošte, nadgradnjo sistema in digitalno podpisovanje dokumentov.

---

## 1. Podjetje (Company)

### 1.1. Osnovni podatki

| Polje | Opis |
|-------|------|
| **Ime podjetja** | Polno ime matične družbe |
| **DDV številka** | Identifikacijska številka za DDV |
| **Matična številka** | Registrska številka |
| **Naslov** | Sedež podjetja |
| **Kraj** | Mesto sedeža |
| **Telefon / Mobilni** | Kontaktni podatki |
| **E‑pošta / Spletna stran** | Javni kontakt |
| **Odgovorna oseba** | Ime in priimek |

### 1.2. Logotip in podpis
- Naložite **logotip** (prikaže se v poročilih in na prijavnem zaslonu).
- Naložite **podpis** (uporablja se pri digitalnem podpisovanju dokumentov).

### 1.3. Poslovne enote (Business Units)
Tabela prikazuje vse poslovne enote matične družbe.  
- Dodajanje in brisanje je dovoljeno le, če ni aktivne lastniške stranke (ko je sistem povezan z osrednjo licenčno storitvijo).  
- Poslovne enote se uporabljajo pri obveščanju in poročilih.

### 1.4. E‑poštna konfiguracija
Nastavitve za odhodno pošiljanje obvestil (SMTP):

| Polje | Opis |
|-------|------|
| **Mailer** | `smtp`, `localmailer` ali `sendmail` |
| **Host** | SMTP strežnik |
| **Port** | Vrata (npr. 587, 465) |
| **Encryption** | `tls` ali `ssl` |
| **Username / Password** | Podatki za avtentikacijo |
| **From Name** | Ime pošiljatelja (npr. »Sistem Optima«) |

---

## 2. Moduli

### 2.1. Pregled aktivnih modulov
Na zavihku **Moduli** je prikazan seznam vseh modulov, ki jih sistem podpira. Za vsak modul je vidno:

- **Ime modula** in kratek opis
- **Status** – aktiven / neaktiven (odvisen od licence)
- **Nastavitve** – gumb se prikaže le za module, ki podpirajo konfiguracijo

### 2.2. Stanje licence
Zgoraj je prikazano:
- **Trenutni paket / načrt**
- **Datum poteka licence** (če je omejena)
- **Zadnja sinhronizacija** z osrednjim strežnikom

Gumb **Sinhroniziraj licenco** ročno požene preverjanje stanja pri osrednjem strežniku.

### 2.3. Konfiguracija modulov
Klik na gumb **Nastavitve** pri aktivnem modulu odpre modalno okno, kjer lahko skrbnik prilagodi specifične parametre modula.  
Primer za modul **Ocene tveganj (Rass)** je opisan v prejšnjem poglavju *Dinamična formula*.

---

## 3. Nadgradnja sistema

**Dostop:** Sistem → Nastavitve → zavihek Nadgradnja

Na tem zaslonu spremljate različico sistema in izvajate posodobitve.

- **Nameščena različica** – trenutna verzija (pridobljena iz licence)
- **Nova različica** – zadnja različica, ki je na voljo na centralnem strežniku
- Gumb **Posodobi** se prikaže, če je na voljo novejša različica ali (le za superadmin) če želite ponovno namestiti trenutno različico.
- V primeru, da je lokalna različica novejša od strežniške (npr. po testiranju), se prikaže opozorilo in gumb **Revert to …**, ki omogoči povratek na starejšo, vendar le superadminu.

Desno je prikazan **dnevnik sprememb (changelog)** za vse različice, ki vsebuje seznam novosti in popravkov.

Postopek nadgradnje samodejno:
1. Prenese paket z osrednjega strežnika.
2. Odstrani zastarele datoteke (če so navedene).
3. Razširi novo kodo.
4. Požene `composer update` in potrebne Artisan ukaze (`migrate`, `cache:clear` …).
5. Posodobi različico v bazi.

!!! warning
    Pred nadgradnjo vedno naredite varnostno kopijo baze in datotek. Nadgradnja je enosmerna, razen če uporabnik izrecno izvede povratek na starejšo različico (kar ni priporočljivo).

---

## 4. Digitalno podpisovanje dokumentov

**Dostop:** Nastavitve → Potrdila / Akreditacije

1. Dodajte nov zapis s tipom **digitalni podpis**.
2. Izberite datoteko **P12** (osebni certifikat) in vnesite pripadajoče geslo.
3. Po shranitvi bo sistem ob vsakem generiranju PDF dokumenta (npr. zapisniki, poročila) le‑tega samodejno digitalno podpisal.

Podpisani dokumenti so prepoznavni po vrstici *“DIGITALLY SIGNED”* in podatkih o podpisniku. Uporabnikom strank so prikazani po prijavi v modulu **Izdani dokumenti**.



