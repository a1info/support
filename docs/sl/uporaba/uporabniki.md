# Uporabniki

[⬅️ Nazaj na uporabniški priročnik](README.md) | [🏠 Glavni portal](../../index.md)

---

## 👥 Upravljanje uporabnikov

Sistem Optima Prevent podpira **dva tipa uporabnikov**: sistemski uporabniki (zaposleni matične družbe) in uporabniki strank (zaposleni pri strankah z omejenimi pravicami).

---

## 🔐 Sistemski uporabniki

**Sistemski uporabniki** so delavci matične družbe, ki lahko pripadajo različnim skupinam z različnimi nivoji dostopa.

### 👥 Skupine uporabnikov

#### 🔴 Administratorji (Administrators)
**Najvišji nivo dostopa:**
- ✅ **Polni dostop** do vseh podatkov v sistemu
- ✅ **Spreminjanje sistemskih nastavitev**
- ✅ **Upravljanje vseh uporabnikov** (sistemskih in strank)
- ✅ **Pregled in urejanje** vseh podatkov
- ✅ **Dostop do analitike** in poročil
- ✅ **Konfiguracija modulov** in licenc

#### 🟡 Operaterji (Operators)  
**Srednji nivo dostopa:**
- ✅ **Uvid v vse podatke** sistema
- ✅ **Delo v tujem imenu** (za druge uporabnike)
- ✅ **Vnos in urejanje** vseh operacijskih podatkov
- ❌ **Brez dostopa** do sistemskih nastavitev
- ❌ **Ne morejo upravljati** uporabnikov
- ✅ **Dostop do standardnih poročil**

#### 🟢 Navadni uporabniki (Users)
**Osnovni nivo dostopa:**
- ✅ **Dostop do svojih podatkov**
- ✅ **Podatki skupine** (če so del skupine)
- ❌ **Brez administratorskih pravic**
- ❌ **Ne morejo spreminjati** sistemskih nastavitev
- ✅ **Osnovni vnos podatkov** za svojo stranko/projekt

### 🔧 Upravljanje sistemskih uporabnikov

**Dostop:** `Uporabniki → Sistemski uporabniki` v glavnem meniju

#### ➕ Dodajanje novega uporabnika
1. **Kliknite** "Dodaj novega uporabnika"
2. **Izpolnite obvezne podatke:**
   - **Ime in priimek**
   - **Email naslov** (uporabniško ime)
   - **Geslo** (varno geslo)
   - **Skupina** (Administrator/Operater/User)
3. **Dodatne nastavitve:**
   - **Aktiven** (da/ne)
   - **Profil** uporabnika
   - **Pravice** po modulih
4. **Shranite** uporabnika

#### ✏️ Urejanje uporabnika
- **Seznam uporabnikov** z ikonami za urejanje
- **Spreminjanje podatkov**, gesel in pravic
- **Deaktiviranje** namesto brisanja (za ohranjanje zgodovine)

---

## 👔 Uporabniki strank

**Uporabniki strank** so zaposleni vaših strank, katerim želite omogočiti dostop do aplikacije z omejenimi pravicami.

### 🔑 Pravice uporabnikov strank

Pravice se lahko dodelijo za naslednje module:

| Modul | Pregled | Urejanje | Opis |
|-------|---------|----------|------|
| **🔧 Evidenca delovne opreme** | ✅ | ⚙️ | Pregled/vnos delovne opreme |
| **👥 Evidenca zaposlenih** | ✅ | ⚙️ | Upravljanje seznama zaposlenih |
| **🦺 Osebna varovalna oprema** | ✅ | ⚙️ | OVO evidenca in izdaja |
| **🏥 Zdravniški pregledi** | ✅ | ⚙️ | Napotnice in pregledi |
| **🚨 Delovne nezgode** | ✅ | ⚙️ | Prijave nesreč |
| **📋 Naročila** | ✅ | ⚙️ | Pregled naročenih storitev |
| **🔥 Evidence požarne varnosti** | ✅ | ⚙️ | PV dokumentacija |

**Legenda:**
- ✅ = Lahko omogočite
- ⚙️ = Nastavljiva pravica (pregled ali pregled+urejanje)

### 🌐 Dostop za stranke

**URL za prijavo strank:** `https://naslov_vaše_instalacije/mod-cust`

**Primer:** `https://demo.optima-prevent.eu/mod-cust`

### 📊 Uporabniška plošča strank

Po prijavi se prikaže **nadzorna plošča (Dashboard)** z:
- 📊 **Splošne informacije** o sistemu
- 🔗 **Hitre povezave** na dovoljena področja
- 📄 **Dostop do izdanih dokumentov**
- 📅 **Koledar poteka veljavnosti** (Periodika)
- 👥 **Seznam zaposlenih** (če omogočeno)

### ➕ Dodajanje uporabnika stranke

**Dostop:** `Uporabniki → Uporabniki strank`

1. **Izberite stranko** iz seznama
2. **Kliknite** "Dodaj uporabnika stranke"
3. **Izpolnite podatke:**
   - **Ime in priimek**
   - **Email naslov** (uporabniško ime)
   - **Začasno geslo**
   - **Aktivnost** (da/ne)
4. **Dodelite pravice** za module (pregled/urejanje)
5. **Shranite** uporabnika

#### 🔐 Prva prijava stranke
1. Uporabnik prejme **email** z navodili
2. Prijavi se na **mod-cust** naslov
3. **Spremeni geslo** ob prvi prijavi  
4. **Dostopa** do dovoljenih modulov

---

## 🔄 Upravljanje gesel

### 🔑 Sistemski uporabniki
**Administratorji** lahko:
- **Ponastavijo geslo** kateremukoli uporabniku
- **Prisilno spremenijo** geslo
- **Nastavijo** zahteve za kompleksnost gesla

### 🔑 Uporabniki strank  
**Uporabniki strank** lahko:
- **Spremenijo geslo** v svojem profilu
- **Zahtevajo ponastavitev** preko administratorja
- **Nastavljive zahteve** za varnost gesla

---

## 📊 Organizacija dela z uporabniki

### 🎯 Skrbniki strank
**Za organizacijo dela** lahko dodelite:
- **Skrbnika za stranko** - odgovorna oseba
- **Prejemanje obvestil** o aktivnostih stranke
- **Koordinacija nalog** za stranko

### 👥 Skupinsko delo
**Operaterji** lahko delajo:
- **V tujem imenu** (za druge uporabnike)
- **Dodatno polje** za izbiro uporabnika pri vnosu
- **Boljša organizacija** dela v večjih podjetjih

### 📈 Uporabniška analitika
**Sledenje aktivnosti:**
- **Zadnja prijava** uporabnika
- **Število opravljenih działanj**
- **Aktivnost** po modulih
- **Generiranje poročil** o uporabi

---

## ⚙️ Napredne nastavitve

### 🔐 Varnostne nastavitve
- **Sestavljenost gesel** - minimalne zahteve
- **Potek gesel** - avtomatska poteka
- **Neaktivnost** - avtomatska odjava
- **Prijave** - logiranje poskusov

### 📧 E-mail integracija  
- **Avtomatska obvestila** novim uporabnikom
- **Ponastavitev gesel** preko e-maila
- **Obvestila o aktivnostih** strankam
- **SMTP konfiguracija** v sistemskih nastavitvah

### 🔄 Sinhronizacija
- **Active Directory** integracija (opcijsko)
- **LDAP** podpora za velike organizacije
- **Single Sign-On** (SSO) možnosti

---

## 🆘 Pogoste težave

### ❌ Uporabnik se ne more prijaviti
**Preverite:**
- ✅ Ali je uporabnik **aktiven**
- ✅ Ali je geslo **pravilno** (poskusite ponastaviti)
- ✅ Ali uporablja pravilen **URL** (mod-cust za stranke)
- ✅ Ali ima **dodelené pravice**

### ❌ Uporabnik ne vidi podatkov
**Preverite:**
- ✅ Ali je izbrana **aktivna stranka**
- ✅ Ali ima **pravice za modul**
- ✅ Ali ima dostop do **poslovnih enot**
- ✅ Ali ni **filtriran** seznam

### ❌ E-mail obvestila ne delujejo
**Preverite:**
- ✅ **SMTP nastavitve** v .env datoteki
- ✅ **E-mail naslov** uporabnika
- ✅ **Spam** mapo prejemnika
- ✅ **Firewall** nastavitve za SMTP

---

**[▶️ Naprej: Stranke](stranke.md)**

---

<div align="center">

*Za podrobnejša navodila glejte **[manual.md](../../manual.md)**, sekcija "UPORABNIKI"*

</div>