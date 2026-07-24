# Začetna nastavitev in vnos podatkov

## Pregled

Ta razdelek zajema korake začetne konfiguracije aplikacije Optima Prevent (OP5). Pred začetkom operativnega dela je priporočljivo izvesti nastavitve, opisane na tej strani — migracija obstoječih podatkov, priprava ključnih sistemskih nastavitev, uvoz podatkov iz Excel datotek ter konfiguracija tekstov in polj po meri.

---

## Migracija podatkov

Migracija omogoča uvoz zgodovinskih podatkov iz drugih programov ali Excel datotek v sistem OP5. Ker se ob migraciji kreirajo **bazni podatki in povezane operacije**, je postopek zahteven in ga je treba izvesti skrbno.

!!! warning "Koordinacija z razvijalcem"
    Migracijo podatkov vedno izvedite v koordinaciji z razvijalcem Optima Prevent. Napačen uvoz lahko povzroči podvojene ali nepovezane zapise, ki jih je naknadno težko popraviti.

**Dostop:** Sistem → Nastavitve

Tipični scenariji migracije:

- Prenos obstoječih evidenc zaposlenih iz Excel preglednic
- Uvoz delovne opreme s pregledi in certifikati
- Prenos zapisnikov o usposabljanju iz starejšega sistema
- Uvoz ocen tveganja in meritev EKO/VZD

---

## Avtomatično številčenje dokumentov

Pred prvo produkcijsko uporabo preverite, da je za vse ključne vrste dokumentov pravilno nastavljeno **avtomatično številčenje**.

**Dostop:** Sistem → Številčenje

!!! tip "Prilagoditev"
    Nastavitve številčenja prilagodite pred prvim izdanim dokumentom. Naknadno popravljanje zaporednih številk zahteva poseg v bazo.

Podrobna referenca za parametre, tipe dokumentov in delovanje števcev je v poglavju [Sistemske nastavitve](sistemske-nastavitve.md#stevilcenje-dokumentov).

---

## Uvoz Excel datotek

Sistem OP5 podpira uvoz podatkov iz Excel datotek na naslednjih seznamih:

- Stranke
- Delovna oprema
- Zaposleni
- Vprašalniki
- Osebna varovalna oprema (OVO)
- Požarna varnost (VPP)

### Pravila za uvoz

!!! important "Upoštevajte naslednja pravila za uspešen uvoz"

1. **Uporabite predloge** — na vnosnih maskah so na voljo predloge v obliki `tplImportXXX.xlsx`. Prenesite ustrezno predlogo pred začetkom.
2. **Prva vrstica mora biti enaka predlogi** — imena polj v prvi vrstici morajo natančno ustrezati predlogi (ne preimenovati, ne dodajati stolpcev).
3. **Shranite v UTF-8** — da so šumniki (č, š, ž) pravilno prikazani, datoteko shranite kot CSV UTF-8 ali Excel z ustreznim kodiranjem.
4. **Izogibajte se dodatnemu oblikovanju** — barvanje celic, spojene celice in komentarji lahko povzročijo napake pri uvozu.

### Priporočeni postopek uvoza

```
1. Prenesite predlogo (tplImportXXX.xlsx) z vnosne maske
2. Odprite predlogo v LibreOffice Calc
3. Vnesite ali prilepite podatke pod naslovno vrstico
4. Shranite datoteko v ustreznem formatu (UTF-8)
5. Na vnosni maski izberite uvoz in naložite datoteko
6. Preverite rezultat (sistem prikaže uspešne / neuspešne vrstice)
```

!!! tip "Testni uvoz"
    Uvoz najprej preizkusite z manjšim naborom podatkov (npr. 3–5 vrstic), preden uvozite celotno datoteko. Tako hitreje odkrijete morebitne napake v strukturi.

!!! note "Uvoz v poslovno enoto"
    Za uvoz podatkov v določeno poslovno enoto stranke najprej izberite **aktivno stranko** v zgornjem meniju aplikacije. Brez izbire aktivne stranke bo uvoz morda dodeljen napačni stranki.

---

## Teksti po meri

Teksti po meri so **ponavljajoča se besedilna vsebina**, ki jo enkrat definirate v sistemu in jo nato prek spremenljivk samodejno dodelite na poljubna polja v vmesnikih.

**Dostop:** Seznami → Teksti po meri

### Primer uporabe

Spremenljivka `txtDevRes` se dodeli polju »Ugotovitev« pri pregledu delovne opreme. Kadar izpolnjujete nov pregled, se to besedilo avtomatično predpopolni v polje — ni ga treba vsakič znova vnašati.

### Nastavitev tekstov po meri

| Polje | Opis |
|---|---|
| Naziv | Opisno ime teksta (za lastno orientacijo) |
| Spremenljivka | Koda, ki jo sistem poveže s poljem (npr. `txtDevRes`) |
| Vsebina | Dejanski besedilni tekst |
| Polja za prikaz | Izbirna polja za različne ekrane / module |
| Zadana vrednost | Če označeno, se tekst **avtomatično** doda v polje ob vsakem odprtju obrazca |

!!! info "Razdelek »Polja za prikaz«"
    V tem razdelku izberete, na katerih ekranih oz. obrazcih bo tekst na voljo. Isti tekst je lahko dodeljen več poljem hkrati.

---

## Polja po meri (EAV)

Modul **Polja po meri** (EAV — Entity-Attribute-Value) omogoča dodajanje **lastnih atributov** objektom in operacijam v sistemu — na primer dodatna polja za delovno opremo, zaposlene ali stranke.

**Dostop:** Seznami → Polja po meri

### Značilnosti

- Polja po meri so vidna v **celotnem sistemu**: pri vnosu, uvozu, izvozu, prikazu na seznamih in v dokumentnih predlogah.
- Sistem ob dodelitvi atributa **samodejno generira kodo polja** (format: `tabelaID`, npr. `custemployee42`).
- Polja so vezana na določeno tabelo (npr. delovna oprema, zaposleni, meritve).
- Vrednosti se shranjujejo v skupni tabeli `fldopt_val` kot **tekstovni podatki** brez omejitve dolžine.

### Tipi polj

Ob kreiranju polja po meri izberete **tip**, ki določa, kako se polje prikaže na obrazcih:

| Tip | Prikaz na obrazcu | Namen |
|---|---|---|
| **Besedilo** (`vchar`) | Vnosno polje (do 250 znakov) | Kratka besedila: številke, oznake, opombe |
| **Številka** (`int`) | Številčno polje | Cela števila: količine, letnice, zaporedne št. |
| **Datum** (`date`) | Izbirnik datuma | Datumi brez ure: veljavnost, rok, datum izdaje |
| **Potrditveno polje** (`boolean`) | Kljukica (checkbox) | DA/NE vrednosti: veljavnost, potrditev, status |
| **Izbirni seznam** (`enum`) | Spustni seznam (select) | Vnaprej določene možnosti: tip delavca, kategorija, prioriteta |

### Izbirni seznam (enum) — podrobna nastavitev

Pri tipu **Izbirni seznam** vnesete možnosti eno za drugo prek gumba `+`. Vsaka možnost se prikaže kot značka, ki jo lahko odstranite s klikom na `×`.

Po vnosu možnosti izberete **privzeto vrednost** iz spustnega seznama — ta vrednost bo samodejno izbrana ob kreiranju novega zapisa.

!!! example "Primer: Tip delavca"
    1. Izberite tabelo **Zaposleni** (`custemployee`)
    2. Izberite tip **Izbirni seznam** (`enum`)
    3. Dodajte možnosti: `študent`, `delavec`
    4. Izberite privzeto vrednost: `delavec`
    5. Shranite

!!! tip "Privzeta vrednost"
    Če ne izberete privzete vrednosti, bo sistem uporabil **prvo možnost** s seznama. Privzeto vrednost lahko kadarkoli spremenite z urejanjem polja.

### Uporaba v dokumentnih predlogah

Za prikaz vrednosti polja po meri v Word/PDF predlogah uporabite kodo s **prefiksom pozicije**:

| Kontekst | Sintaksa | Primer |
|---|---|---|
| Seznam (list) | `${lst<code>}` | `${lstcustemployee42}` |
| Posamezni zapis (detail) | `${dev<code>}` | `${devcustemployee42}` |

!!! tip "Generirana koda"
    Kodo polja poiščite v nastavitvah polja po meri — sistem jo prikaže po shranjevanju atributa (stolpec **Koda**). Kodo kopirajte in jo vstavite v predlogo natančno tako, kot je prikazana.

### Arhitektura

Vrednosti polj po meri se shranjujejo v tabeli **`fldopt_val`** (prej `fldopt_val_vchar`). Tabela uporablja stolpec `value` tipa `text` brez omejitve dolžine, kar omogoča shranjevanje poljubno dolgih vrednosti.

Metapodatki (ime polja, tip, tabela, možnosti) so shranjeni v tabeli **`fldopt`**. Za izbirne sezname se možnosti in privzeta vrednost shranijo v stolpcu `def_val` v JSON formatu:

```json
{"o": ["študent", "delavec"], "d": "delavec"}
```

kjer je `o` seznam možnosti (*options*) in `d` privzeta vrednost (*default*).
