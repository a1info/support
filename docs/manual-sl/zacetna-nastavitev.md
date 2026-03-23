# Začetna nastavitev in vnos podatkov

Dostop: Sistem → Nastavitve

## Migracija podatkov

Migracija omogoča uvoz zgodovinskih podatkov iz drugih programov ali Excel datotek. Ker se ob migraciji kreirajo bazni podatki in povezane operacije, postopek izvedite skrbno in v koordinaciji z razvijalcem Optima Prevent.

## Avtomatično številčenje dokumentov

Vsi izdani dokumenti so avtomatično oštevilčeni s števci, prilagodljivimi pravilom matične družbe. Številčijo se:
- zapisniki o usposabljanju,
- potrdila o usposabljanju,
- zapisniki o pregledih delovne opreme,
- potrdila za delovno opremo,
- ocene tveganja,
- EKO/VZD meritve.

Parametri: leto, stranka, tip dokumenta.

Dostop: Sistem → Številčenje

## Uvoz Excel datotek

Funkcija uvoza je na seznamih: Stranke, Delovna oprema, Zaposleni, Vprašalniki, Osebna varovalna oprema, VPP.

Pravila:
- Uporabljajte predloge (template) na vnosnih maskah (npr. tplImportXXX.xlsx).
- Prva vrstica (imena polj) mora biti enaka kot v predlogi.
- Shranjevanje v UTF-8 (pravilen prikaz šumnikov).
- Izogibajte se dodatnemu oblikovanju.
- Urejajte predlogo v LibreOffice in vnesite podatke (copy/paste). Nato jo uvozite in preverite rezultat (uspešno/neuspešno).

Opomba: Za uvoz v poslovno enoto stranke najprej izberite aktivno stranko v zgornjem meniju.

## Teksti po meri

Teksti po meri so ponavljajoča se besedila, ki se preko spremenljivk dodeljujejo v vmesnike (npr. `txtDevRes` za polje »Ugotovitev« pri pregledu delovne opreme).

V razdelku »Polja za prikaz« so izbirna polja za različne ekrane.

Če se izbere kljukica »Zadana vrednost«, potem se ta text avtomatično doda v izbrano polje.

Dostop: Seznami → Teksti po meri

## Polja po meri (EAV)

Modul omogoča dodajanje atributov objektom in operacijam (npr. dodatna polja za delovno opremo ali zaposlene), vidnih v celotnem sistemu (uvoz, izvoz, prikaz, predloge).

Sistem ob dodelitvi atributa generira kodo polja. Za prikaz v predlogah uporabite kodo s prefiksom pozicije spremenljivke, npr. `${lst<code>}` ali `${dev<code>}`.

Dostop: Seznami → Polja po meri
