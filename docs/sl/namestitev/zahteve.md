# Sistemske zahteve za Optima Prevent

[⬅️ Nazaj na namestitev](README.md) | [🏠 Glavni portal](../../index.md)

---

## 💻 Minimalne sistemske zahteve

### 🖥️ Strežnik

| Komponenta | Minimalna verzija | Priporočena verzija | Opombe |
|------------|------------------|-------------------|---------|
| **PHP** | 8.0+ | 8.2+ | Laravel 9.x zahteva PHP 8.0+ |
| **Web server** | Apache 2.4+ ali Nginx 1.18+ | Apache 2.4+ ali Nginx 1.20+ | Potreben mod_rewrite (Apache) |
| **Baza podatkov** | PostgreSQL 12+ ali Oracle 12c+ | PostgreSQL 14+ ali Oracle 19c+ | Transakcijska podpora |
| **RAM** | 2 GB | 4+ GB | Odvisno od števila uporabnikov |
| **Prostor na disku** | 5 GB | 20+ GB | + prostor za varnostne kopije |
| **CPU** | 2 jedri @ 2GHz | 4+ jeder @ 3GHz+ | |

### 🔧 PHP ekstenzije

**Obvezne ekstenzije:**
```
✅ mbstring     - Multi-byte string support
✅ openssl      - SSL/TLS podpora  
✅ pdo          - PHP Data Objects
✅ pdo_pgsql    - PostgreSQL PDO driver (ali pdo_oci za Oracle)
✅ tokenizer    - Laravel tokenizacija
✅ xml          - XML podpora
✅ ctype        - Character type functions
✅ json         - JSON podpora
✅ bcmath       - Arbitrary precision mathematics
✅ fileinfo     - File information
✅ zip          - ZIP arhiv podpora
✅ curl         - Client URL library
```

**Priporočene ekstenzije:**
```
🔸 gd ili imagick  - Obdelava slik (za QR kode)
🔸 redis           - Redis cache support
🔸 opcache         - PHP bytecode cache
🔸 memcached       - Memcached podpora
🔸 intl            - Internationalization
```

---

## 🗄️ Zahteve za bazo podatkov

### PostgreSQL (priporočeno)
- **Verzija**: PostgreSQL 12+, priporočeno 14+
- **Konfiguracija**:
  ```sql
  shared_preload_libraries = 'pg_stat_statements'
  max_connections = 100
  shared_buffers = 256MB
  work_mem = 4MB
  ```
- **Uporabniški račun** z ustreznimi pravicami
- **UTF-8 kodiranje** baze

### Oracle Database
- **Verzija**: Oracle Database 12c+, priporočeno 19c+
- **Instant Client** 19.x ali novejši
- **TNS konfiguracija**
- **Ustrezne licence** Oracle

---

## 🌐 Spletni strežnik

### Apache HTTP Server
**Minimalna konfiguracija:**
```apache
LoadModule rewrite_module modules/mod_rewrite.so
LoadModule ssl_module modules/mod_ssl.so

<VirtualHost *:80>
    DocumentRoot "/path/to/optima-prevent/public"
    AllowOverride All
    
    <Directory "/path/to/optima-prevent/public">
        Options -Indexes +FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>

<VirtualHost *:443>
    # SSL konfiguracija za HTTPS
    SSLEngine on
    SSLCertificateFile /path/to/cert.pem
    SSLCertificateKeyFile /path/to/private.key
    
    DocumentRoot "/path/to/optima-prevent/public"
    AllowOverride All
</VirtualHost>
```

### Nginx
**Minimalna konfiguracija:**
```nginx
server {
    listen 80;
    listen 443 ssl http2;
    server_name your-domain.com;
    root /path/to/optima-prevent/public;
    index index.php;

    # SSL configuration
    ssl_certificate /path/to/cert.pem;
    ssl_certificate_key /path/to/private.key;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        fastcgi_pass 127.0.0.1:9000; # ali unix socket
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
    }
}
```

---

## 🔒 Varnostne zahteve

### SSL/TLS certifikati
- **HTTPS obvezen** za produkcijo
- **TLS 1.2+** minimum
- **Močni šifrirni algoritmi**

### Varnostne nastavitve
```apache
# Apache security headers
Header always set X-Content-Type-Options nosniff
Header always set X-Frame-Options DENY
Header always set X-XSS-Protection "1; mode=block"
Header always set Strict-Transport-Security "max-age=63072000; includeSubDomains"
```

### Požarni zid
- **Odprt port 80** (HTTP)
- **Odprt port 443** (HTTPS)  
- **Zaprt dostop** do baze podatkov od zunaj
- **SSH dostop** samo za administratorje

---

## 📊 Zmogljivostne zahteve

### Majhna namestitev (do 10 uporabnikov)
- **CPU**: 2 jedri @ 2GHz
- **RAM**: 4 GB
- **Disk**: 20 GB SSD
- **Mreža**: 10 Mbps

### Srednja namestitev (do 50 uporabnikov)
- **CPU**: 4 jedra @ 3GHz
- **RAM**: 8 GB
- **Disk**: 50 GB SSD
- **Mreža**: 50 Mbps

### Velika namestitev (50+ uporabnikov)
- **CPU**: 8+ jeder @ 3GHz+
- **RAM**: 16+ GB
- **Disk**: 100+ GB SSD (RAID)
- **Mreža**: 100+ Mbps
- **Load balancer** za visoko dostopnost

---

## 🏢 Infrastrukturne zahteve

### Varnostno kopiranje
- **Dnevno varnostno kopiranje** baze podatkov
- **Tedensko polno varnostno kopiranje** aplikacije
- **Testiranje obnove** iz varnostnih kopij
- **Offsite shranjevanje** kopij

### Monitoring
- **Sistemski monitoring** (CPU, RAM, disk)
- **Aplikacijski monitoring** (Laravel logs)
- **Baza podatkov monitoring**
- **Mrežni monitoring**

### Vzdolžno sodelovanje
- **VPN dostop** za administratorje
- **SSH ključi** za varno povezovanje
- **Centralizirano upravljanje** logov

---

## 🎯 Zahteve za različne namestitve

### 🏢 On-premise namestitev
- **Fizični ali virtualni strežnik** v podjetju
- **Aktivna Directory** integracija (opcijsko)
- **Interna IT podpora**
- **Redne posodobitve** sistema

### ☁️ Cloud namestitev
- **AWS, Azure, Google Cloud** podporo
- **Avtomatsko skaliranje**
- **Upravljane baze podatkov** (RDS, Azure SQL)
- **Balansiranje obremenitve**

### 🐳 Docker namestitev
```yaml
# Minimalne Docker zahteve
version: '3.8'
services:
  optima-prevent:
    image: optima-prevent:latest
    environment:
      - DB_CONNECTION=pgsql
      - DB_HOST=postgres
    depends_on:
      - postgres
  
  postgres:
    image: postgres:14
    environment:
      POSTGRES_DB: optima_prevent
      POSTGRES_USER: optima
      POSTGRES_PASSWORD: secure_password
```

---

## ⚡ Optimizacija zmogljivosti

### PHP optimizacije
```ini
# php.ini optimizacije
memory_limit = 256M
upload_max_filesize = 64M
post_max_size = 64M
max_execution_time = 300

# OPcache
opcache.enable=1
opcache.memory_consumption=256
opcache.max_accelerated_files=10000
opcache.validate_timestamps=0
```

### Laravel cache
```bash
# Priporočene cache nastavitve
php artisan config:cache
php artisan route:cache
php artisan view:cache
php artisan queue:work --daemon
```

---

## 🔍 Preverjanje zahtev

### PHP preveritve
```bash
# Preverjanje PHP verzije in ekstenzij
php -v
php -m | grep -E "(mbstring|openssl|pdo|tokenizer|xml|ctype|json|bcmath|fileinfo|zip|curl)"
```

### Sistem preveritve
```bash
# Preverjanje sistemskih virov
free -h          # RAM
df -h            # Disk space
nproc            # CPU cores
```

### Mreža preveritve
```bash
# Preverjanje mrežnih povezav
curl -I https://your-domain.com
openssl s_client -connect your-domain.com:443
```

---

## 🆘 Pogoste težave

### ❌ PHP ekstenzije manjkajo
**Rešitev za Ubuntu/Debian:**
```bash
sudo apt-get update
sudo apt-get install php8.1-mbstring php8.1-xml php8.1-pgsql php8.1-curl php8.1-zip
```

### ❌ Baza podatkov se ne poveže
**Preverite:**
- Zagnana je baza podatkov
- Pravilne povezave parametri
- Firewall nastavitve
- Uporabniške pravice

### ❌ Pomanjkanje prostora na disku
**Preprečite:**
- Redno čiščenje logov
- Rotacija varnostnih kopij
- Monitoring prostora

---

**[▶️ Naprej: Namestitveni proces](README.md)**

---

<div align="center">

*Za tehnično podporo pri namestitvi kontaktirajte: **podpora@a1info.si***

</div>