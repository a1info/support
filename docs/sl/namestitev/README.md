# Namestitev Optima Prevent

[⬅️ Nazaj na slovensko dokumentacijo](../README.md) | [🏠 Glavni portal](../../index.md)

---

## 🚀 Pregled namestitve

**Optima Prevent** je Laravel 9.x aplikacija, ki zahteva pravilno konfigurirano strežniško okolje. Ta priročnik vas vodi skozi celoten proces namestitve.

---

## 📋 Pred namestitvijo

### ✅ Preverjanje zahtev
1. **[📊 Preverite sistemske zahteve](zahteve.md)**
2. **Pripravite strežniško okolje**
3. **Pridobite dostop do baze podatkov**
4. **Poskrbite za SSL certifikate**

### 📦 Potrebne datoteke
- **Izvorna koda** Optima Prevent
- **Composer** (PHP dependency manager)
- **Baza podatkov** (PostgreSQL ali Oracle)
- **SSL certifikati** za HTTPS

---

## 🔧 Korak 1: Priprava strežniškega okolja

### Za Ubuntu/Debian
```bash
# Posodobitev sistema
sudo apt update && sudo apt upgrade -y

# Namestitev PHP 8.2 in potrebnih ekstenzij
sudo apt install php8.2 php8.2-cli php8.2-common php8.2-curl \
php8.2-mbstring php8.2-xml php8.2-zip php8.2-pgsql php8.2-bcmath \
php8.2-fileinfo php8.2-json php8.2-tokenizer -y

# Apache ali Nginx
sudo apt install apache2 -y  # ali nginx

# PostgreSQL
sudo apt install postgresql postgresql-contrib -y
```

### Za CentOS/RHEL
```bash
# Omogočiranje EPEL in Remi repozitorijev
sudo yum install epel-release -y
sudo yum install https://rpms.remirepo.net/enterprise/remi-release-8.rpm -y

# PHP 8.2
sudo dnf module enable php:remi-8.2 -y
sudo dnf install php php-cli php-common php-curl php-mbstring \
php-xml php-zip php-pgsql php-bcmath php-fileinfo php-json -y

# Webserver in baza
sudo dnf install httpd postgresql-server -y
```

---

## 🗄️ Korak 2: Konfiguracija baze podatkov

### PostgreSQL nastavitev
```bash
# Inicializacija PostgreSQL (če potrebno)
sudo postgresql-setup --initdb

# Zagon storitve
sudo systemctl start postgresql
sudo systemctl enable postgresql

# Ustvarjanje uporabnika in baze
sudo -u postgres psql << EOF
CREATE USER optima_prevent WITH PASSWORD 'secure_password';
CREATE DATABASE optima_prevent OWNER optima_prevent;
GRANT ALL PRIVILEGES ON DATABASE optima_prevent TO optima_prevent;
ALTER USER optima_prevent CREATEDB;
\q
EOF
```

### Konfiguracija PostgreSQL
```bash
# Urejanje pg_hba.conf za avtentifikacijo
sudo vi /var/lib/pgsql/data/pg_hba.conf

# Dodajte vrstico (prilagodite IP naslove):
# local   optima_prevent   optima_prevent   md5
# host    optima_prevent   optima_prevent   127.0.0.1/32   md5

# Restart PostgreSQL
sudo systemctl restart postgresql
```

---

## 📁 Korak 3: Namestitev aplikacije

### Prenos in priprava
```bash
# Prenos aplikacije (prilagodite pot)
cd /var/www/
sudo git clone https://github.com/a1info/OP5.git optima-prevent
cd optima-prevent

# Nastavitev dovoljenj
sudo chown -R www-data:www-data /var/www/optima-prevent
sudo chmod -R 755 /var/www/optima-prevent
sudo chmod -R 775 /var/www/optima-prevent/storage
sudo chmod -R 775 /var/www/optima-prevent/bootstrap/cache
```

### Composer namestitev
```bash
# Namestitev Composer (če še ni nameščen)
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer

# Namestitev odvisnosti
cd /var/www/optima-prevent
composer install --optimize-autoloader --no-dev
```

---

## ⚙️ Korak 4: Konfiguracija aplikacije

### Osnovna konfiguracija
```bash
# Kopiranje .env datoteke
cp .env.example .env

# Urejanje konfiguracije
nano .env
```

### Ključne nastavitve v .env
```env
# Aplikacijske nastavitve
APP_NAME="Optima Prevent"
APP_ENV=production
APP_DEBUG=false
APP_URL=https://your-domain.com

# Baza podatkov
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=optima_prevent
DB_USERNAME=optima_prevent
DB_PASSWORD=secure_password

# Cache in session
CACHE_DRIVER=file
SESSION_DRIVER=file
QUEUE_CONNECTION=database

# Mail konfiguracija
MAIL_DRIVER=smtp
MAIL_HOST=your-smtp-server
MAIL_PORT=587
MAIL_USERNAME=your-email
MAIL_PASSWORD=your-password
MAIL_ENCRYPTION=tls
```

### Ustvarjanje aplikacijskega ključa
```bash
# Generiranje aplikacijskega ključa
php artisan key:generate

# Optmizacija konfiguracije
php artisan config:cache
php artisan route:cache
php artisan view:cache
```

---

## 🗃️ Korak 5: Migracija baze podatkov

### Zagon migracij
```bash
# Preverjanje povezave z bazo
php artisan migrate:status

# Zagon migracij
php artisan migrate --force

# Napolnjevanje s osnovnimi podatki (če potrebno)
php artisan db:seed --force
```

### Preverjanje namestitve
```bash
# Test povezave z aplikacijo
php artisan tinker
>>> \DB::connection()->getPdo();
>>> exit;
```

---

## 🌐 Korak 6: Webserver konfiguracija

### Apache Virtual Host
```apache
<VirtualHost *:80>
    ServerName your-domain.com
    DocumentRoot /var/www/optima-prevent/public
    
    # Preusmeritev na HTTPS
    RewriteEngine On
    RewriteCond %{HTTPS} off
    RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
</VirtualHost>

<VirtualHost *:443>
    ServerName your-domain.com
    DocumentRoot /var/www/optima-prevent/public

    # SSL konfiguracija
    SSLEngine on
    SSLCertificateFile /path/to/your-cert.crt
    SSLCertificateKeyFile /path/to/your-private.key
    
    # Laravel konfiguracija
    <Directory /var/www/optima-prevent/public>
        Options -Indexes +FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>

    # Varnostni headerji
    Header always set X-Content-Type-Options nosniff
    Header always set X-Frame-Options SAMEORIGIN
    Header always set X-XSS-Protection "1; mode=block"
</VirtualHost>
```

### Nginx konfiguracija
```nginx
server {
    listen 80;
    server_name your-domain.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    server_name your-domain.com;
    root /var/www/optima-prevent/public;
    index index.php;

    # SSL konfiguracija
    ssl_certificate /path/to/your-cert.crt;
    ssl_certificate_key /path/to/your-private.key;
    ssl_protocols TLSv1.2 TLSv1.3;

    # Laravel konfiguracija
    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php8.2-fpm.sock;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
        fastcgi_read_timeout 300;
    }

    # Varnostni headerji
    add_header X-Content-Type-Options nosniff;
    add_header X-Frame-Options SAMEORIGIN;
    add_header X-XSS-Protection "1; mode=block";
}
```

---

## 🔒 Korak 7: Varnostne nastavitve

### Požarni zid
```bash
# UFW (Ubuntu)
sudo ufw allow ssh
sudo ufw allow 'Apache Full'  # ali 'Nginx Full'
sudo ufw enable

# Firewalld (CentOS/RHEL)
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --permanent --add-service=https
sudo firewall-cmd --permanent --add-service=ssh
sudo firewall-cmd --reload
```

### Varnostne nastavitve
```bash
# Skrivanje PHP verzije
echo "expose_php = Off" | sudo tee -a /etc/php/8.2/apache2/php.ini

# Nastavitev server tokens
echo "ServerTokens Prod" | sudo tee -a /etc/apache2/apache2.conf
echo "ServerSignature Off" | sudo tee -a /etc/apache2/apache2.conf
```

---

## ⚡ Korak 8: Optimizacija zmogljivosti

### PHP optimizacija
```ini
# /etc/php/8.2/apache2/php.ini
memory_limit = 256M
upload_max_filesize = 64M
post_max_size = 64M
max_execution_time = 300

# OPcache aktivacija
opcache.enable=1
opcache.memory_consumption=256
opcache.max_accelerated_files=10000
opcache.validate_timestamps=0
```

### Cron naloge
```bash
# Dodajanje cron naloge za Laravel Scheduler
sudo crontab -e

# Dodajte vrstico:
* * * * * cd /var/www/optima-prevent && php artisan schedule:run >> /dev/null 2>&1
```

---

## 🧪 Korak 9: Testiranje namestitve

### Osnovni testi
```bash
# Preverjanje statusa storitev
sudo systemctl status apache2  # ali nginx
sudo systemctl status postgresql

# Test Laravel aplikacije
cd /var/www/optima-prevent
php artisan about

# Test baze podatkov
php artisan migrate:status
```

### Funkcionalni testi
1. **Odprite brskalnik** in pojdite na https://your-domain.com
2. **Preverite SSL certifikat** (zelena ključavnica)
3. **Poskusite se prijaviti** s testnim uporabnikom
4. **Preverite osnovne funkcionalnosti**

---

## 📊 Migracija podatkov

### Uvoz obstoječih podatkov
```bash
# Ustvarjanje backupa trenutne baze (če obstaja)
pg_dump -h localhost -U old_user old_database > backup.sql

# Uvoz v novo bazo
psql -h localhost -U optima_prevent optima_prevent < backup.sql

# Zagon migracijskih skriptov za prilagoditev
php artisan migrate --force
```

### Excel uvozi
**Optima Prevent podpira uvoz iz Excel datotek:**
- Uporabite predloge v UTF-8 kodiranju
- Prva vrstica mora vsebovati imena polj
- Sledite navodilom v aplikaciji za posamezen modul

---

## 🔄 Postprodukcijske naloge

### Varnostno kopiranje
```bash
# Ustvarjanje backup skripta
cat > /etc/cron.daily/optima-prevent-backup << 'EOF'
#!/bin/bash
DATE=$(date +%Y%m%d_%H%M%S)
pg_dump -h localhost -U optima_prevent optima_prevent > /backup/optima_prevent_$DATE.sql
find /backup -name "optima_prevent_*.sql" -mtime +7 -delete
EOF

sudo chmod +x /etc/cron.daily/optima-prevent-backup
```

### Monitoring
```bash
# Logwatch nameščanje
sudo apt install logwatch

# Konfiguracija za Optima Prevent loge
echo "/var/www/optima-prevent/storage/logs/*.log {
    daily
    missingok
    rotate 14
    compress
    notifempty
    create 0644 www-data www-data
}" | sudo tee /etc/logrotate.d/optima-prevent
```

---

## 🆘 Pogoste težave pri namestitvi

### ❌ Permission denied errorsrs
**Rešitev:**
```bash
sudo chown -R www-data:www-data /var/www/optima-prevent
sudo chmod -R 755 /var/www/optima-prevent
sudo chmod -R 775 storage bootstrap/cache
```

### ❌ Class not found error
**Rešitev:**
```bash
composer dump-autoload
php artisan clear-compiled
php artisan config:clear
```

### ❌ Database connection error
**Preverite:**
- Je li PostgreSQL zagnan
- So li credentials pravilni v .env
- Je li uporabnik ustvarjen z ustreznimi pravicami

### ❌ SSL certificate errors
**Rešitev:**
```bash
# Let's Encrypt certbot
sudo apt install certbot python3-certbot-apache
sudo certbot --apache -d your-domain.com
```

---

## ✅ Naslednji koraki

Po uspešni namestitvi:

1. **[👤 Ustvarite prvega administratorja](konfiguracija.md#prvi-uporabnik)**
2. **[⚙️ Konfigurirajte osnovne nastavitve](konfiguracija.md#osnovne-nastavitve)**
3. **[📚 Preberite uporabniški priročnik](../uporaba/README.md)**
4. **[🆘 Seznanite se s podporo](../podpora/README.md)**

---

**[▶️ Naprej: Konfiguracija sistema](konfiguracija.md)**

---

<div align="center">

*Za pomoč pri namestitvi kontaktirajte: **podpora@a1info.si***

</div>