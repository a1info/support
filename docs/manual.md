# Optima Prevent - Priročnik za uporabo

## Pregled aplikacije

- **Verzija**: 5.2
- **Licenca**: a1-tech V2 @lic

Optima Prevent je celovita rešitev za upravljanje s preventivo in varnostjo v podjetjih. Aplikacija omogoča sledenje različnim vidikom preventive, od testiranja do upravljanja s tveganji in človeškimi viri.

## Glavne funkcionalnosti

### Moduli aplikacije:
- **ETEST** - Oddaljeno usposabljanje
- **VPP** - Varstvo pred požarem
- **RASS** - Splošne ocene tveganj
- **RASSL** - Ocene tveganje telesnih obremenitev
- **CUST** - Dostop za stranke
- **ROA** - Oddaljeni dostop prek QR kod
- **HRM** - Upravljanje s človeškimi viri
- **CRM** - Upravljanje z odnosi s strankami

## Tehnične specifikacije


## Sistemske zahteve

### Minimalne zahteve:
- Laravel / PHP 8.2 ali novejši
- Oracle/PostgreSQL baza podatkov
- Apache/Nginx spletni strežnik
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