# Konfiguracija sistema

[⬅️ Nazaj na namestitev](README.md) | [🏠 Glavni portal](../../index.md)

---

## ⚙️ Osnovna konfiguracija

Po uspešni namestitvi je potrebno sistem pravilo konfigurirati za uporabo. Ta priročnik vas vodi skozi ključne korake začetne konfiguracije.

---

## 👤 Prvi uporabnik (Administrator)

### Ustvarjanje administratorja
```bash
# Preko Laravel Tinker
cd /var/www/optima-prevent
php artisan tinker

# V Tinker konzoli
>>> use App\Models\User;
>>> $admin = new User();
>>> $admin->name = 'Administrator';
>>> $admin->email = 'admin@vase-podjetje.si';
>>> $admin->password = bcrypt('secure_password_123');
>>> $admin->role = 'administrator';
>>> $admin->save();
>>> exit;
```

### Testna prijava
1. Odprite brskalnik in pojdite na vaš Optima Prevent naslov
2. Prijavite se z email in geslom administratorja
3. Po prijavi spremenite geslo v varnostnih nastavitvah

---

## 🏢 Sistemske nastavitve

### Dostop do sistemskih nastavitev
- **Lokacija**: `Sistem → Nastavitve` v glavnem meniju
- **Pravice**: Samo administratorji

### Obvezni parametri matične družbe

**Osnovni podatki:**
- ✅ **Ime matične družbe**
- ✅ **Polno ime družbe**
- ✅ **DDV številka**
- ✅ **Registracijska številka**
- ✅ **Naslov sedeža**

**Kontaktni podatki:**
- Telefon / mobitel
- Email naslov
- WWW spletna stran

**Akreditacije:**
- Akreditacije RS (če jih imate)

**Vizualna identiteta:**
- Logotip podjetja (JPG/PNG)

### Digitalno podpisovanje dokumentov
Za avtomatično digitalno podpisovanje PDF dokumentov:

1. **Pridobite P12 certifikat** za digitalno podpisovanje
2. **Naložite certifikat**: gumb "P12 Cert"
3. **Vnesite geslo** certifikata v predvideno polje
4. **Shranite nastavitve**

Po konfiguraciji bodo vsi generirani PDF dokumenti avtomatično digitalno podpisani.

---

## 🔧 Moduli in licence

### Aktiviranje modulov
V razdelku "Moduli" lahko aktivirate/deaktivirate:
- ✅ **ETEST** - Elektronsko testiranje
- ✅ **RASSL** - Risk Assessment  
- ✅ **CUST** - Upravljanje s strankami
- ✅ **ROA** - Remote Object Access (QR kode)
- ✅ **HRM** - Human Resource Management
- ✅ **CRM** - Customer Relationship Management

### Licence
Za posamezne module vnesite licenčne ključe (če so potrebni).

---

## 🎨 Prilagoditve vmesnika

### Teksti po meri
**Dostop**: `Seznami → Teksti po meri`

Konfigurirajte ponavljajoče se tekste z uporabo spremenljivk:
- `txtDevRes` - tekst za "Ugotovitev" pri pregledu delovne opreme
- `txtCust1` - prvi tekst po meri
- `txtCust2` - drugi tekst po meri
- `txtLaw` - tekst zakonskih odredb

### Polja po meri (EAV)
**Dostop**: `Seznami → Polja po meri`

**Dodajanje dodatnih atributov:**
1. **Izberite entiteto** (delovna oprema, zaposleni, itd.)
2. **Definirajte atribut** (ime, tip, obveznost)
3. **Sistem avtomatično generira kodo** polja
4. **Uporabite kodo v predlogah**: `${lst + koda}` ali `${dev + koda}`

---

## 📊 Števci dokumentov

### Avtomatično številčenje
Vsi izdani dokumenti so avtomatično oštevilčeni:
- Zapisniki o usposabljanju
- Posamezna potrdila o usposabljanju
- Zapisniki o pregledih delovne opreme
- Posamezna potrdila za delovno opremo
- Ocene tveganja
- EKO/VZD meritve

### Konfiguracija števcev
Parametri številčenja:
- **Leto** - vključi leto v številko
- **Stranka** - ločeno številčenje po strankah
- **Tip dokumenta** - različni števci po tipih

Konfiguracija je shranjena v tekstualni datoteki in je možna v vseh različnih kombinacijah parametrov.

---

## 📝 Predloge za izpis

### DOCX predloge
**Dostop**: `Nastavitve → Urejanje predlog`

**Dodajanje nove predloge:**
1. **Določite ime** predloge
2. **Izberite tip** (usposabljanje, delovna oprema, meritve, ocena tveganja)
3. **Nastavite zaporedno številko** (manjša = višja prioriteta)
4. **Naložite DOCX datoteko**

### Struktura DOCX predlog
**Statični del:**
- Formatiranje dokumenta
- Pozicije elementov
- Statični tekst, barve, slike

**Dinamični del:**
- Posamezne spremenljivke: `${imeVar}`
- Spremenljivke tabele: `${rowImeVar}` 
- Blok spremenljivke: `${cloneBlok}...{/cloneBlok}`

### Najpogostejše spremenljivke

**Generalne spremenljivke:**
```
${cName}        - Ime stranke
${cAddress}     - Naslov sedeža stranke
${cCity}        - Mesto sedeža stranke
${cTax}         - Davčna številka stranke
${uName}        - Ime in priimek uporabnika
${uSignImg}     - Podpis uporabnika
${dateRep}      - Datum zapisnika
${custNrRep}    - Številka zapisnika
```

---

## 👥 Uporabniki in pravice

### Sistemski uporabniki
**Ustvarjanje novega uporabnika:**
1. **Pojdite na**: `Uporabniki → Sistemski uporabniki`
2. **Kliknite**: "Dodaj novega uporabnika"
3. **Izpolnite podatke**:
   - Ime in priimek
   - Email (uporabniško ime)
   - Geslo
   - Skupina (Administrator/Operater/User)
4. **Shranite**

### Skupine uporabnikov
**Administratorji:**
- Polni dostop do vseh podatkov
- Spreminjanje sistemskih nastavitev
- Upravljanje vseh uporabnikov

**Operaterji:**
- Uvid v vse podatke
- Delo v tujem imenu (za druge uporabnike)
- Brez dostopa do sistemskih nastavitev

**Navadni uporabniki (Users):**
- Dostop do svojih podatkov
- Podatki skupine
- Brez administratorskih pravic

### Uporabniki strank
**Ustvarjanje uporabnika stranke:**
1. **Izberite stranko**
2. **Dodajte uporabnika** z email naslovom
3. **Dodelite pravice** za module:
   - Evidenca delovne opreme (pregled/urejanje)
   - Evidenca zaposlenih (pregled/urejanje)
   - Osebna varovalna oprema (pregled/urejanje)
   - Zdravniški pregledi (pregled/urejanje)
   - Delovne nezgode (pregled/urejanje)
   - Naročila (pregled/urejanje)
   - Evidence požarne varnosti (pregled/urejanje)

**Dostop za stranke**: `https://vaš-naslov/mod-cust`

---

## 📧 E-mail konfiguracija

### SMTP nastavitve
V `.env` datoteki konfigurirajte:
```env
MAIL_DRIVER=smtp
MAIL_HOST=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=vasa-email@gmail.com
MAIL_PASSWORD=vaše-geslo
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=vasa-email@gmail.com
MAIL_FROM_NAME="Optima Prevent"
```

### Testiranje e-mail pošiljanja
```bash
# Laravel Tinker test
php artisan tinker
>>> Mail::raw('Test email', function($msg) {
...     $msg->to('test@example.com')->subject('Test');
... });
```

---

## 🔔 Sistem obveščanja

### Interna komunikacija
**Aktiviranje:**
- Omogočeno je privzeto za vse sistemske uporabnike
- Real-time sporočila med uporabniki
- Transparentno obveščanje skrbnikov strank

### Zunanja komunikacija
**E-mail obvestila:**
- Avtomatska obvestila o poteku veljavnosti
- Obvestila o novih nalogah
- Poročila o sistemskih dogodkih

---

## 🏗️ Migracija in uvoz podatkov

### Excel uvoz
**Priprava datotek:**
1. **Uporabite predloge** (tplImportXXX.xlsx)
2. **Prva vrstica** mora vsebovati imena polj
3. **Shranite v UTF-8** kodiranju
4. **Izogibajte se** dodatnemu oblikovanju

**Postopek uvoza:**
1. **Odprite predlogo** v LibreOffice
2. **Kopirajte podatke** (copy/paste)
3. **Shranite kot Excel**
4. **V aplikaciji kliknite ikono uvoza** 📥
5. **Izberite datoteko** in kliknite "Import"
6. **Preverite rezultat** (uspešno/neuspešno)

### Migracija iz drugih sistemov
**Koordinacija z razvijalcem:**
- Migracija zahteva koordinacijo z A1 Informatika
- Predhodni pregled podatkov
- Testna migracija na testnem sistemu
- Produkcijska migracija z varnostno kopijo

---

## 🔒 Varnostna konfiguracija

### Backup konfiguracija
```bash
# Nastavitev avtomatskega backupa
cat > /etc/cron.daily/optima-prevent-backup << 'EOF'
#!/bin/bash
DATE=$(date +%Y%m%d_%H%M%S)
pg_dump optima_prevent > /backup/optima_prevent_$DATE.sql
tar -czf /backup/files_$DATE.tar.gz /var/www/optima-prevent/storage
find /backup -name "*_*.sql" -mtime +30 -delete
find /backup -name "*_*.tar.gz" -mtime +30 -delete
EOF

sudo chmod +x /etc/cron.daily/optima-prevent-backup
```

### Log monitoring
```bash
# Log rotation setup
echo "/var/www/optima-prevent/storage/logs/*.log {
    daily
    missingok
    rotate 14
    compress
    notifempty
    create 0644 www-data www-data
    postrotate
        systemctl reload apache2
    endscript
}" | sudo tee /etc/logrotate.d/optima-prevent
```

---

## 🧪 Finalno testiranje

### Funkcionalni testi
Po konfiguraciji testirajte:

1. **Prijava administratorja** ✅
2. **Ustvarjanje prve stranke** ✅
3. **Dodajanje zaposlenega** ✅
4. **Vnos delovne opreme** ✅
5. **Ustvarjanje tečaja** ✅
6. **Generiranje prvega dokumenta** ✅
7. **Test e-mail pošiljanja** ✅

### Testni podatki
Za testiranje dodajte:
- **Testno stranko** s pravimi podatki
- **2-3 zaposlene** testne stranke
- **Nekaj kosov delovne opreme**
- **Preprost test/tečaj**

---

## 🎯 Produkcija ready checklist

**Pred uvedbo v produkcijo preverite:**

- [ ] **SSL certifikat** pravilno nastaven
- [ ] **Backup** sistem deluje
- [ ] **E-mail** pošiljanje deluje
- [ ] **Sistemske nastavitve** izpolnjene
- [ ] **Prvi administrator** ustvarjen in testiran
- [ ] **Dokumentna predloga** naložena in testirana
- [ ] **Firewall** pravilno konfiguriran
- [ ] **Log rotation** nastavljen
- [ ] **Performance monitoring** aktiven
- [ ] **Storsitve** avtomatsko zaganjajo ob reboot
- [ ] **Cron naloge** nastavljene
- [ ] **GDPR** skladnost preverjena

---

**[▶️ Naprej: Uporabniški priročnik](../uporaba/README.md)**

---

<div align="center">

*Za pomoč s konfiguracijo kontaktirajte: **podpora@a1info.si***

</div>