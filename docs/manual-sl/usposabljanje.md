# Usposabljanje

Modul Usposabljanje pokriva celoten cikel izobraževanja in usposabljanj zaposlenih: od načrtovanja in izvedbe do dokumentiranja in elektronskega preverjanja znanja.

---

## Pregled modula

Modul je večplasten in vključuje naslednje komponente:

| Komponenta | Opis |
|-----------|------|
| **Seznam tečajev** | Evidenca vseh izvedenih usposabljanj z udeleženci. |
| **Zapisniki** | Združeni zapisniki, ki zajemajo več tečajev različnih tipov. |
| **Tipi tečajev** | Šifranti za kategorizacijo usposabljanj (VPP, VZD, VPP ODG …). |
| **Vprašalniki** | Elektronski testi za oddaljeno usposabljanje (e-test). |

**Dostop:** Glavna navigacija → Usposabljanje

---

## Tipi tečajev

**Dostop:** Usposabljanje → Tipi tečajev

Tipi tečajev so šifranti, ki določajo, kako se usposabljanja kategorizirajo in oštevilčijo. Vsak tip ima lastne nastavitve.

### Nastavitve tipa tečaja

| Nastavitev | Opis |
|-----------|------|
| **Naziv tipa** | Opisno ime (npr. VPP, VZD, VPP ODG, Požarna varnost). |
| **Ločeno številčenje** | Če je aktivno, tečaji tega tipa dobijo svojo neodvisno zaporedno številko. |
| **Privzete priloge** | Dokumenti, ki se samodejno priložijo vsakemu tečaju tega tipa. |
| **Zakonske podlage** | Sklici na predpise, ki se izpišejo v poročilih in potrdilih. |

!!! tip "Priporočilo za oštevilčenje"
    Z ločenim številčenjem po tipu dosežete pregledne zaporedne številke (npr. VPP-2024-001, VZD-2024-001), kar olajša arhiviranje in iskanje.

---

## Dodajanje tečaja

**Dostop:** Usposabljanje → Seznam tečajev → **Dodaj tečaj** (+)

### Obvezna polja

| Polje | Opis |
|-------|------|
| **Stranka** | Stranka, za katero se usposabljanje izvaja. |
| **Poslovna enota** | PE znotraj stranke. |
| **Datum začetka** | Datum izvedbe usposabljanja. |

### Neobvezna polja

| Polje | Opis |
|-------|------|
| **Lokacija tečaja** | Kraj izvedbe (npr. soba za usposabljanje, zunanji prostor). |
| **Tip tečaja** | Kategorizacija: VZD, VPP, VPP ODG itd. |
| **Veljavnost** | Rok veljavnosti potrdila v letih. Sistem samodejno izračuna datum izteka. |
| **Vprašalnik (e-test)** | Izberite, če usposabljanje vključuje elektronsko preverjanje znanja. |

### Dodajanje udeležencev

Po vnosu osnovnih podatkov tečaja dodate udeležence iz tabele zaposlenih:

1. Uporabite **hitri filter** za iskanje po imenu, oddelku ali delovnem mestu.
2. Označite posamezne zaposlene ali izberite vse filtrirane.
3. Kliknite **Dodaj udeležence**.

!!! danger "Udeleženci so zaklenjeni po shranitvi"
    Ko je tečaj enkrat shranjen, **dodajanje ali odstranjevanje udeležencev ni več mogoče**. Preden shranite, natančno preverite seznam. Če je prišlo do napake, morate ustvariti nov tečaj.

---

## Udeleženci

Udeleženci se dodajajo **izključno med ustvarjanjem tečaja** (pred prvo shranjenjem). Po shranitvi je seznam udeležencev zaklenjen.

### Sledenje statusu

Pri tečajih z e-testom se za vsakega udeleženca samodejno vodi status:

| Status | Pomen |
|--------|-------|
| **Negativno** | Udeleženec še ni opravil e-testa ali je test padel. |
| **Pozitivno** | Udeleženec je uspešno opravil e-test. |

Po uspešno opravljenem testu sistem samodejno:
- Posodobi status udeleženca na **pozitivno**.
- Dodeli **številko potrdila** (če je avtomatično oštevilčenje konfigurirano).

---

## Zapisniki usposabljanj

**Dostop:** Usposabljanje → Zapisniki

Zapisnik je sestavni dokument, ki združuje enega ali več tečajev različnih tipov v en koheziven zapis.

### Ustvarjanje zapisnika

**Dostop:** Usposabljanje → Zapisniki → **Dodaj zapisnik** (+)

Postopek:

1. **Izberite stranko** – določa kontekst zapisnika in nabor programov (glej spodaj).
2. **Izberite tečaje** – prikažejo se samo tečaji, ki še niso vključeni v noben drug zapisnik (*prosti tečaji*).
3. **Dopolnite podatke:**

| Polje | Opis |
|-------|------|
| **Stranka / Poslovna enota** | Se prenese iz izbranih tečajev. |
| **Datum** | Datum sestave zapisnika. |
| **Program(i) usposabljanja** | Izbira enega ali več programov (glej poglavje spodaj). |
| **Ure, odgovorna oseba, mentor** | Podatki, ki se izpišejo v zapisniku in potrdilih. |
| **Tečaji** | Označite tečaje, ki jih zapisnik zajema. |

### Program(i) usposabljanja

Polje omogoča izbiro **več programov** iz spustnega seznama:

- Seznam se filtrira glede na **izbrano stranko**: prikažejo se programi te stranke in prosti programi; če stranka ni izbrana, so prikazani samo prosti programi.
- **Programi stranke so odebeljeni in navedeni na vrhu** seznama, prosti programi so v običajnem prikazu.
- Program lahko v seznamu poiščete z vpisom imena; izbrani programi se prikažejo kot značke (×), ki jih lahko odstranite.
- Če programa ni v šifrantu, lahko **vpišete poljuben naziv** – shrani se kot besedilo, enako kot izbran program.

V zapis se shranijo **imena programov** (več programov je ločenih znotraj zapisa). V DOCX izpisih sta na voljo dve obliki izpisa – v eni vrstici, ločeno z vejico, ali vsak program v svoji vrstici (spremenljivke `nrProg`, `nrProgLst` ipd. — glej [Legendo spremenljivk](variables-sl.md)).

### Operacije nad zapisnikom

| Operacija | Opis |
|----------|------|
| **Uredi** | Popravite podatke zapisnika (dokler ni zaključen). |
| **Izbriši** | Izbrisati je mogoče le nezaključene zapisnike brez tiskanih izpisov. |
| **Natisni (DOCX)** | Sistem iz predloge ustvari datoteko DOCX za podpis in arhiv. |

!!! info "Avtomatično oštevilčenje"
    Če je oštevilčenje konfigurirano za tip tečaja, zapisnik ob shranitvi samodejno dobi zaporedno številko (npr. ZAP-VPP-2024-007).

---

## Oddaljeno usposabljanje (E-test)

E-test omogoča zaposlenim, da usposabljanje in preverjanje znanja opravijo na daljavo – iz pisarne, doma ali s terena.

### Potek e-testa za udeleženca

1. Udeleženec prejme dostopno povezavo ali se prijavi na e-test portal.
2. Opravi predvajanje predstavitvenega gradiva (HTML5), če je nastavljeno – predstavitev se predvaja ob vsaki novi prijavi.
3. Odgovori na vprašanja testa – odgovori se **samodejno shranjujejo**.
4. Sistem samodejno ovrednoti rezultat.
5. Ob uspešno opravljenem testu se izpiše potrdilo.

#### Samodejno shranjevanje napredka

- Vsak odgovor se **takoj shrani na strežnik** – udeleženec lahko med testom varno osveži stran, uporabi gumb nazaj/naprej v brskalniku ali zapre okno in kasneje nadaljuje.
- Ob ponovnem odprtju testa se prikaže zadnje vprašanje z vsemi že podanimi odgovori.
- Vpisi v obrazec ob zaključku testa se prav tako sproti shranjujejo.

#### Navigacija med vprašanji

- Nad vprašanjem je **vrstica s krožci** – vsak krožec predstavlja eno vprašanje.
- Števec ob krožcih prikazuje trenutno vprašanje (npr. »12 / 60«).
- Na že obiskana vprašanja se lahko vrnete s klikom na krožec in spremenite odgovor.
- Naprej lahko preskočite samo na vprašanja, do katerih ste že odgovorili; zaklenjeni krožci so osiveli.
- Krožci vprašanj z gradivom (PDF/MP4) imajo dodano ikono gradiva.

#### Časovna omejitev

- Če ima tečaj nastavljeno časovno omejitev, se števec **ohrani tudi po osvežitvi strani** – preostali čas se s ponovnim nalaganjem ne podaljša.
- Ob izteku časa sistem samodejno odda izpolnjene odgovore.
- Ob novi prijavi na nedokončan test se časovno okno začne znova (vsaka prijava je nov poskus).

#### Gradivo pri vprašanju (PDF / MP4)

- Če je vprašanju priloženo gradivo, ga mora udeleženec najprej potrditi (»Sem v celoti seznanjen z vsebino«), šele nato se prikaže vprašanje.
- Med odgovarjanjem si lahko gradivo kadar koli znova prikaže z gumbom **Prikaži/skrij gradivo**, za vrnitev na vprašanje pa uporabi **Nazaj na vprašanje**.
- Ob prehodu na drugo vprašanje se predvajani videoposnetki samodejno zaustavijo.

#### Predstavitev (HTML5 gradivo)

- Predstavitev se predvaja **ob vsaki novi prijavi**. Ko udeleženec enkrat začne z odgovarjanjem, se ob gumbu nazaj v brskalniku predstavitev ne predvaja več – vrne se neposredno na vprašanja.

#### Rezultat testa

- Po oddaji sistem prikaže **rezultat s točkami** – skupno in po posamezni skupini vprašanj (če so določene).
- Ob neuspehu lahko udeleženec poskusi znova (največ **4 poskusi**); po četrtem neuspehu je nadaljnje reševanje zaklenjeno.
- Rezultat se prikaže na poenoteni svetli strani, enaki videzu samega testa.

### Konfiguracija e-testa pri tečaju

1. Pri ustvarjanju tečaja izberite **vprašalnik** v ustreznem polju.
2. Vsem udeležencem se samodejno nastavi status **negativno**.
3. Po uspešno opravljenem testu sistem:
   - Posodobi status na **pozitivno**.
   - Dodeli **številko potrdila** (če je oštevilčenje konfigurirano).

### Dostop do e-test portala

```
https://[naslov_vaše_instalacije]/mod-etest
Primer: https://demo.optima-prevent.eu/mod-etest
```

!!! tip "Prilagoditev prijavne strani"
    Prijavno predlogo portala (HTML5) je mogoče popolnoma prilagoditi – dodajte logotip organizacije, barvno shemo in navodila za udeležence.

---

## Vprašalniki za oddaljeno usposabljanje

**Dostop:** Usposabljanje → Vprašalniki

Vprašalniki so osnova za e-test. Ustvarite jih v dveh korakih.

### Korak 1 – Splošne informacije

| Polje | Obvezno | Opis |
|-------|---------|------|
| **Naslov** | ✅ | Naziv vprašalnika (prikazuje se udeležencem). |
| **Opis** | — | Kratka navodila ali uvod za udeležence. |
| **Prag uspešnosti** | ✅ | Minimalni delež točk za uspešno opravljanje (privzeto: **80 %**). |
| **ZIP gradivo (HTML5)** | — | Izobraževalno gradivo iz orodij iSpring ali H5P, ki se prikaže pred začetkom testa. |
| **Obrazec ob zaključku** | — | FORM, ki ga udeleženec izpolni po testu. Nastavite, ali je obvezen ali neobvezen. |

!!! info "Podprta gradiva"
    Vprašalnik podpira uvoz interaktivnih HTML5 paketov (iSpring, H5P, Articulate) v obliki ZIP arhiva. Gradivo se prikaže v vdelanem predvajalniku pred začetkom testiranja. Paket naj v zadnjem koraku vsebuje povezavo za nadaljevanje na test.

### Korak 2 – Vprašanja

Za vsako vprašanje določite:

| Nastavitev | Opis |
|-----------|------|
| **Besedilo vprašanja** | Vprašanje, ki se prikaže udeležencu. Namesto besedila lahko naložite **sliko vprašanja**. |
| **Odgovori** | Vnesite možne odgovore in s stikali **A / B / C** označite pravilnega. Vsak odgovor je lahko besedilo ali **slika**. |
| **Točke** | Privzeto **2 točki** na vprašanje. Vrednost je mogoče prilagoditi. |
| **Priloga pred vprašanjem** | Neobvezna datoteka **PDF ali MP4** (gumb »pdf / mp4«), ki se prikaže pred vprašanjem kot kontekst ali navodilo. |

!!! tip "Prilagoditev točkovanja"
    Za zahtevnejša vprašanja dodelite višje število točk. Sistem samodejno preračuna skupni rezultat in ga primerja s pragom uspešnosti.

#### Slikovna vprašanja in odgovori

Vsako polje vprašalnika je lahko **besedilo ali slika**:

- Podprte so slike **JPG in PNG** do **4 MB**.
- Sliko naložite z ikono ob polju; ob naloženi sliki se polje za besedilo onemogoči, prikaže pa se predogled in gumb za izbris.
- V seznamu vprašanj se slikovno vprašanje prikaže kot pomanjšana sličica.
- V testu se slike samodejno prilagodijo velikosti zaslona (tudi na mobilnih napravah) in so obrobljene, da se ločijo od ozadja.

#### Skupine vprašanj

Vprašanja lahko razdelite v **skupine** z lastnim pragom uspešnosti:

- Vsaka skupina ima svoj naziv, vrstni red in zahtevani odstotek točk.
- Rezultat se na koncu prikaže **po skupinah** – udeleženec mora doseči prag v vsaki skupini.
- Že opravljene skupine se ob ponovnem poskusu ne ponavljajo.

#### Uvoz in izvoz vprašanj (Excel)

- Vprašanja lahko **izvozite v Excel** in jih uvozite nazaj ali v drug vprašalnik.
- Uvoz podpira besedilna vprašanja; slikovna vprašanja urejajte neposredno v vmesniku.

### Primer konfiguracije vprašalnika

```
Naslov:         VPP – Varstvo pred požarom (2024)
Prag uspešnosti: 80 %
Gradivo ZIP:    vpp-2024-gradivo.zip  (HTML5 iSpring)
Obrazec:        Potrditev prebranega (neobvezen)

Vprašanje 1:  Kje je nameščen gasilni aparat? (2 točki)
Vprašanje 2:  Kaj storite ob požarnem alarmu? (3 točke, priložen PDF z evakuacijskim načrtom)
...
```
