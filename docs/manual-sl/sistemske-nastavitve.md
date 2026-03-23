# Sistemske nastavitve

Dostop: Sistem → Nastavitve

Obvezni in ključni podatki:
- ime in polno ime matične družbe,
- DDV številka,
- registrska številka,
- sedež (naslov),
- akreditacije RS,
- kontakt (telefon, mobilni, e-pošta, spletna stran),
- logotip,
- certifikat za podpisovanje dokumentov itd.

V razdelku »Moduli« upravljate izbirne sistemske module in vnašate pridobite licence.

## Nastavitve modulov in matrika ocenjevanja tveganj
V razdelku za konfiguracijo modulov (gumb nastavitve pri aktivnem modulu) lahko skrbniki prilagodijo delovanje posameznih sklopov aplikacije. 
Pri modulu **Ocene tveganj (Rass)** je omogočena konfiguracija **dinamične formule za izračun tveganja**.

V polje za formulo lahko vpišete poljubni matematični izraz z uporabo spremenljivk:
- `a` = Verjetnost
- `b` = Resnost
- `c` = Pogostost (sistem avtomatično prikaže to polje v uporabniškem vmesniku, če je zaznana uporaba spremenljivke v formuli).

Podprte so matematične funkcije (`min`, `max`, `floor`, `ceil`, `round`) in logični operaterji (`==`, `&&`, `?`, `:`). To omogoča preslikavo katerekoli tiskane matrike ocenjevanja tveganja neposredno v sistem. 
*Primer standardne AUWA formule:* `a * b`
*Primer kompleksne prilagojene 5-stopenjske matrike:* `min(a + 2, b + 2, floor((2 * b + a - 1) / 2)) - (a == 3 && b == 4 ? 1 : 0)`

## Nadgradnja sistema

V razdelku »Nadgradnja« je prikazana trenutna verzija. Če je sistem posodobljen, gumb za nadgradnjo ni prikazan.
Na desni strani je prikazan kratek seznam sprememb posamezne različice.

## Digitalno podpisovanje dokumentov

Dostop: Nastavitve → Potrdila/Akreditacije

Potrebno je dodati novi vnos tipa digitalni podpis, izbere se P12 datoteka in pripadajoče geslo. 

Po tem bodo vsi PDF dokumenti samodejno digitalno podpisani in vidni uporabnikom strank po prijavi.
