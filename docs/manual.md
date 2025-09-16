# Optima Prevent - Priročnik za uporabo

## Pregled aplikacije

Optima Prevent je celovita rešitev za upravljanje s preventivo in varnostjo v podjetjih. Aplikacija omogoča sledenje različnim vidikom preventive, od testiranja do upravljanja s tveganji in človeškimi viri.

## Glavne funkcionalnosti

### Moduli aplikacije:
- **ETEST** - Elektronsko testiranje
- **RASSL** - Upravljanje s tveganji in assessment
- **CUST** - Upravljanje s strankami
- **ROA** - Upravljanje s cestnim prometom
- **HRM** - Upravljanje s človeškimi viri
- **CRM** - Upravljanje z odnosi s strankami

## Tehnične specifikacije

- **Verzija**: 5.2
- **Framework**: Laravel 12.x
- **PHP verzija**: 8.1 ali 8.2
- **Licenca**: a1-info @lic

## Sistemske zahteve

### Minimalne zahteve:
- PHP 8.1 ali novejši
- MySQL/MariaDB baza podatkov
- Apache/Nginx spletni strežnik
- Kompozer za upravljanje odvisnosti

### Priporočene zahteve:
- PHP 8.2
- MySQL 8.0 ali MariaDB 10.6+
- SSD disk za boljše performanse
- Vsaj 2GB RAM
- SSL certifikat za varno povezavo

## Namestitev

1. Kloniraj repozitorij
2. Zaženi `composer install` 
3. Kopiraj `.env.example` v `.env`
4. Nastavi podatke za bazo v `.env` datoteki
5. Zaženi `php artisan key:generate`
6. Zaženi migracije z `php artisan migrate`

## Podpora

Za težave in vprašanja glede aplikacije lahko:
- Prijavite hrošče na GitHub repozitoriju
- Zaprosite za nove funkcionalnosti prek GitHub Issues
- Kontaktirate razvojno ekipo a1-info

---

*Optima Prevent © a1-info, Slovenija*