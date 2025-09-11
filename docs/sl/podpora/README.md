# Podpora in pomoč

[⬅️ Nazaj na slovensko dokumentacijo](../README.md) | [🏠 Glavni portal](../../index.md)

---

## 🆘 Potrebujete pomoč?

Tukaj najdete odgovore na najpogostejša vprašanja in kontaktne informacije za tehnično podporo sistema **Optima Prevent**.

---

## 📞 Kontakt za podporo

### 🏢 A1 Informatika d.o.o.
**Glavni razvijalec in ponudnik podpore za Optima Prevent**

**📍 Naslov:**
```
A1 Informatika d.o.o.
Polje, Cesta XLVI 1
1260 Ljubljana-Polje
Slovenija
```

**📞 Telefon:** +386 40 211 989  
**📧 E-pošta:** info@a1info.si  
**🌐 Spletna stran:** [www.a1info.si](https://www.a1info.si)

### ⚡ Hitri kontakt za tehnično podporo
**📧 Tehnična podpora:** podpora@a1info.si  
**🐛 Prijava napak:** [GitHub Issues](https://github.com/a1info/OP5/issues)  
**💡 Nova funkcionalnost:** [Feature Request](https://github.com/a1info/OP5/issues/new?template=feature_request.md)

---

## ❓ Pogosta vprašanja (FAQ)

### 🔐 Prijava in dostop

**Q: Pozabil/a sem geslo. Kako ga lahko ponastavim?**
A: Kontaktirajte sistemskega administratorja vašega podjetja ali pošljite zahtevo na podpora@a1info.si z navedbo vašega uporabniškega imena (email).

**Q: Dobivam sporočilo "Nimate pravic za dostop". Kaj naj naredim?**
A: Preverite:
- Ali ste izbrani aktivno stranko (če ste uporabnik stranke)
- Ali imate ustrezne pravice za dostop do modula
- Kontaktirajte administratorja za dodelitev pravic

**Q: Sistem se ne naloži ali je zelo počasen. Kaj lahko naredim?**
A: Preverite:
- Internetno povezavo (min. ločljivost 1024x768)
- Očistite cache brskalnika (Ctrl+F5)
- Poskusite z drugim brskalnikom
- Če se težava ponavlja, kontaktirajte podporo

### 📊 Delo s podatki

**Q: Kako uvozim podatke iz Excel datoteke?**
A: 
1. Prenesite predlogo (tplImportXXX.xlsx) iz vmesnika
2. Izpolnite podatke v LibreOffice (ohranite UTF-8)
3. Shranite datoteko
4. V aplikaciji kliknite ikono uvoza 📤
5. Izberite datoteko in kliknite "Import"

**Q: Uvoz Excel datoteke se ni uspešno izvedel. Kaj naj preverim?**
A: Preverite:
- Ali prva vrstica vsebuje pravilna imena polj (kot v predlogi)
- Ali je datoteka shranjena v UTF-8 kodiranju
- Ali ni dodatnega oblikovanja v Excel datoteki
- Ali ste izbrali aktivno stranko pred uvozom

**Q: Kako lahko izvozim podatke iz sistema?**
A: Uporabite gumbove:
- 📊 **Excel** - izvoz tabele v Excel format
- 📄 **PDF** - izvoz tabele v PDF format
- 🖨️ **Print** - tiskanje seznama

### 🔧 Delovna oprema in QR kode

**Q: QR koda se ne skenira ali ne deluje. Kaj naj naredim?**
A: Preverite:
- Ali imate internetno povezavo na mobilni napravi
- Ali skenirate pravo QR kodo (vsak kos opreme ima svojo)
- Ali je QR koda čista in čitljiva
- Poskusite z drugim QR skenerjem

**Q: Kako ustvarim QR kodo za novo delovno opremo?**
A: QR koda se ustvari avtomatično ob vnosu nove delovne opreme. Najdete jo:
1. Pojdite na "Delovna oprema → Seznam del. opreme"
2. Kliknite ikono pregleda 👁️ pri opremi
3. QR koda je prikazana na desni strani ekrana

### 📋 Usposabljanje in tečaji

**Q: Kako omogočim oddaljeno usposabljanje (e-test)?**
A: 
1. Ustvarite vprašalnik v "Usposabljanje → Vprašalniki"
2. Pri dodajanju tečaja izberite vprašalnik
3. Udeleženci dobijo dostop preko: `https://vaš-naslov/mod-etest`

**Q: Udeleženec ne more rešiti testa. Kaj je lahko narobe?**
A: Preverite:
- Ali je test aktiven in ni potekel rok
- Ali ima udeleženec pravilen email in geslo
- Ali je uporabil pravilen naslov (mod-etest)
- Ali je uspešnost testa dosegljiva (privzeto 80%)

### 📄 Dokumenti in predloge

**Q: Kako prilagodim DOCX predlogo za dokumente?**
A: 
1. Pojdite na "Nastavitve → Urejanje predlog"
2. Prenesite obstoječo predlogo ali ustvarite novo
3. Uredite Word dokument z dinamičnimi spremenljivkami ${variable}
4. Naložite novo verzijo predloge

**Q: Spremenljivke v predlogi se ne izpolnjujejo. Kaj je narobe?**
A: Preverite:
- Ali uporabljate pravilno sintakso ${imenaSpremenljivke}
- Ali spremenljivka obstaja za izbrani tip dokumenta
- Ali ni tipnih napak v imenu spremenljivke
- Seznam spremenljivk je v [manual.md](../../manual.md)

### 🔔 Obvestila in e-mail

**Q: Ne prejemam e-mail obvestil. Kako to popravim?**
A: Kontaktirajte sistemskega administratorja, da preveri:
- SMTP nastavitve v .env datoteki  
- Ali je e-mail naslov pravilen v vašem profilu
- Ali sporočila padajo v spam mapo

---

## 🔧 Reševanje tehničnih težav

### ⚠️ Pogoste napake in rešitve

#### "500 Internal Server Error"
**Vzroki:**
- PHP napaka v aplikaciji
- Premalo pomnilnika (memory_limit)
- Napaka v bazi podatkov

**Rešitve:**
1. Preverite logs: `/var/www/optima-prevent/storage/logs/`
2. Povečajte PHP memory_limit v php.ini
3. Kontaktirajte administratorja z log datotekami

#### "403 Forbidden" napaka
**Vzroki:**
- Napačne pravice datotek/map
- Apache/Nginx konfiguracija

**Rešitve:**
```bash
sudo chown -R www-data:www-data /var/www/optima-prevent
sudo chmod -R 755 /var/www/optima-prevent
sudo chmod -R 775 storage bootstrap/cache
```

#### "Connection refused" - baza podatkov
**Vzroki:**
- PostgreSQL/Oracle ni zagnan
- Napačne povezave nastavitve

**Rešitve:**
```bash
# Preverite status baze
sudo systemctl status postgresql

# Zagotovite bazo
sudo systemctl start postgresql

# Preverite .env nastavitve
```

#### Počasno delovanje sistema
**Možne rešitve:**
1. **Očistite cache:**
   ```bash
   php artisan cache:clear
   php artisan config:clear
   php artisan view:clear
   ```

2. **Optimizirajte aplikacijo:**
   ```bash
   php artisan config:cache
   php artisan route:cache
   php artisan view:cache
   ```

3. **Preverite strežniške vire (CPU, RAM, disk)**

### 🐛 Prijavljanje napak

**Pred prijavo napake zberite:**
- 📋 **Opis problema** (korak za korakom)
- 🖥️ **Brskalnik** in verzija (Chrome, Firefox, ...)
- 🔢 **Verzija Optima Prevent** (vidna v sistemu)
- ⏰ **Datum in čas** ko se je napaka zgodila
- 📊 **Tip uporabnika** (administrator, operater, uporabnik)
- 📸 **Screenshot** napake (če je možno)

**Kanali za prijavo:**
1. **GitHub Issues:** [Prijavite napako](https://github.com/a1info/OP5/issues/new?template=bug_report.md)
2. **E-pošta:** podpora@a1info.si
3. **Telefon:** +386 40 211 989

---

## 📚 Dodatni viri

### 📖 Dokumentacija
- **[Celotni priročnik](../../manual.md)** - Izčrpna dokumentacija vseh funkcij
- **[Namestitev](../namestitev/README.md)** - Tehnična navodila za namestitev
- **[Konfiguracija](../namestitev/konfiguracija.md)** - Nastavitve sistema

### 🎥 Video gradiva
*Video posnetki so dostopni na zahtevu preko podpora@a1info.si*

### 🔄 Posodobitve in novosti
- **GitHub:** [github.com/a1info/OP5](https://github.com/a1info/OP5)
- **Changelog:** [CHANGELOG.md](../../CHANGELOG.md)
- **Spletna stran:** [www.a1info.si](https://www.a1info.si)

---

## 🎯 Dodatne storitve

### 🏫 Usposabljanje uporabnikov
**A1 Informatika ponuja:**
- 👨‍🏫 **Osebno usposabljanje** na vaši lokaciji
- 💻 **Spletno usposabljanje** preko video klicev
- 📋 **Prilagojeno usposabljanje** po modulih
- 📄 **Pisna dokumentacija** in priročniki

### 🛠️ Tehnične storitve
- ⚙️ **Namestitev in konfiguracija** sistema
- 🔄 **Migracija podatkov** iz starih sistemov
- 🎨 **Prilagojene DOCX predloge** za dokumente
- 🔧 **Vzdrževano sistema** in posodobitve
- ☁️ **Cloud hosting** na zahtevo

### 📞 Kontakt za dodatne storitve
**E-pošta:** info@a1info.si  
**Telefon:** +386 40 211 989

---

## ⏰ Časi podpore

**Uradni časi podpore:**
- **Ponedeljek - Petek:** 8:00 - 16:00 (CET)
- **Sobota, Nedelja:** Le nujne intervencije

**Odzivni časi:**
- **Kritične napake:** 4 ure
- **Pomembne napake:** 24 ur  
- **Splošne poizvedbe:** 48 ur
- **Nove funkcionalnosti:** Po dogovoru

---

<div align="center">

*Optima Prevent © 2024 A1 Informatika d.o.o.*

**Za vso dodatno pomoč smo vam na voljo na podpora@a1info.si**

</div>