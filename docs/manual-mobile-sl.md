# Mobilna aplikacija Optima Prevent (PWA)

!!! info "Kaj je PWA?"
    Mobilna aplikacija Optima Prevent je **Progressive Web App (PWA)**. Nameščena je neposredno iz brskalnika na telefon ali tablico. Ko jo brskalnik namesti kot PWA, se odpre kot samostojna aplikacija brez naslovne vrstice brskalnika.

    Aplikacija uporablja isto bazo in isto poslovno logiko kot spletni sistem Optima Prevent. Za uporabo ne potrebujete trgovine Google Play, App Store ali datoteke APK.

---

## 1. Kaj omogoča mobilna aplikacija

Mobilni vmesnik je namenjen predvsem terenskemu delu:

- pregled delovne opreme s QR kodo,
- vnos kontrole opreme s kontrolnimi točkami in GPS lokacijo,
- pregled kartice zaposlenega, zdravniških pregledov in usposabljanj,
- reševanje e-testov,
- beleženje prihodov in odhodov zaposlenih prek QR kode ali NFC značke.

Aplikacija se **samodejno posodablja** skupaj s posodobitvami spletnega sistema. Ko je nameščena, je na voljo kot ikona na začetnem zaslonu ali v predalu aplikacij.

!!! warning "Ločen mobilni API ni potreben"
    Mobilna aplikacija ne uporablja več nekdanjih endpointov `/api/mobile/v1`. Ti so bili umaknjeni. Za delo uporabite mobilni vmesnik na naslovu `/mobile`, za integracije med namestitvami pa glejte poglavje [Sinhronizacija](manual-sl/sinhronizacija.md).

---

## 2. Namestitev

### 2.1. Priprava

Pred namestitvijo preverite:

- da imate **točen naslov svoje namestitve**; priporočena oblika je `https://vase-podjetje.aena.si/mobile`,
- da je naslov dosegljiv prek **HTTPS** in da brskalnik ne prikaže opozorila o certifikatu,
- da imate na telefonu nameščen **Chrome** (Android) oziroma **Safari** (iPhone/iPad),
- da imate internetno povezavo.

!!! note "Naslov prejmete od skrbnika"
    Vsaka organizacija uporablja svoj naslov. Uporabite povezavo, ki vam jo je posredoval skrbnik sistema, in je ne zamenjujte z naslovom druge organizacije.

### 2.2. Namestitev na Android

1. Odprite povezavo v brskalniku **Chrome**.
2. Počakajte, da se naloži mobilna stran.
3. Dotaknite se menija s **tremi pikami** v zgornjem desnem kotu.
4. Izberite **Namesti aplikacijo**.
   - Če te možnosti ni, izberite **Dodaj na začetni zaslon**.
5. Potrdite namestitev.
6. Odprite novo ikono **Optima Prevent** na začetnem zaslonu ali v predalu aplikacij.

Če je v aplikaciji prikazan gumb **Namesti aplikacijo**, lahko namestitev začnete tudi z njim.

### 2.3. Namestitev na iPhone ali iPad

1. Odprite povezavo v brskalniku **Safari**.
2. Dotaknite se gumba **Deli**.
3. Izberite **Dodaj na začetni zaslon**.
4. Potrdite z **Dodaj**.
5. Odprite novo ikono **Optima Prevent** na začetnem zaslonu.

!!! tip "Pomoč pri namestitvi"
    V mobilni aplikaciji je na voljo stran **Namestitev aplikacije** na naslovu `/mobile/install`. Na njej so prikazani koraki za Android in iOS ter gumb za namestitev, kadar ga brskalnik ponudi.

### 2.4. Kaj pričakovati po namestitvi

- Ko je nameščena kot PWA, se aplikacija odpre brez naslovne vrstice brskalnika. Pri izbiri **Dodaj na začetni zaslon** je lahko prikaz bližnjice drugačen.
- Prijava ostane v okviru nameščene aplikacije.
- Aplikacija uporablja obstoječe podatke in pravice uporabnika.
- Novosti se naložijo ob naslednjem odprtju ali osvežitvi, ko je naprava povezana z internetom.

!!! warning "Namestitev ni na voljo v vsakem oknu"
    Namestitev običajno ni na voljo v predogledu znotraj druge aplikacije (npr. Facebook, LinkedIn, Outlook) ali v zasebnem načinu brskalnika. Povezavo odprite neposredno v Chromu oziroma Safariju.

---

## 3. Prvi zagon in izbira vloge

Po odprtju aplikacije izberite eno od treh področij:

| Področje | Barva | Namen |
|---|---|---|
| **Inšpektor / administrator** | modra | prijava, skeniranje QR, pregled opreme in vnos kontrol |
| **Zaposleni e-test** | zelena | prijava z e-test podatki in reševanje kviza |
| **HRM prisotnost** | jantarna | beleženje prihodov in odhodov zaposlenih |

Izbira področja ne spremeni vaših pravic. Dostop do posameznih funkcij je odvisen od uporabniškega računa in dodeljenih dovoljenj.

---

## 4. Inšpektor / administrator

### 4.1. Prijava

1. Izberite **Inšpektor / administrator**.
2. Vnesite **e-poštni naslov** in **geslo** svojega uporabniškega računa Optima Prevent.
3. Potrdite prijavo.

Po prijavi se odpre mobilna nadzorna plošča. Na njej so prikazane bližnjice, do katerih ima vaš račun dostop:

- **Odpri skener** – skeniranje opreme in zaposlenih,
- **Odpri prisotnost** – HRM terminal, če imate dovoljenje,
- **Zaposleni e-test** – prehod na e-test prijavo.

Z gumbom **Odjava** v zgornjem delu nadzorne plošče končate sejo.

### 4.2. Skeniranje QR kode

1. Odprite **Odpri skener**.
2. Ob prvem skeniranju dovolite dostop do kamere.
3. Usmerite kamero v QR kodo na opremi ali kartici zaposlenega.
4. Počakajte na potrditev zaznave.

Aplikacija prepozna:

- **delovno opremo** – odpre kartico opreme, zadnjo kontrolo in kontrolne šablone,
- **zaposlenega** – odpre kartico zaposlenega z osnovnimi podatki, zdravniškimi pregledi in usposabljanji.

Če kamera ni na voljo ali koda ni zaznana, uporabite polje **Ročni vnos kode**. Vanj prilepite celotno vsebino QR kode ali povezavo, ki jo vsebuje QR koda.

!!! warning "Gasilni aparati v mobilnem vmesniku"
    Skeniranje gasilnih aparatov v tem mobilnem vmesniku še ni na voljo. Za pregled gasilne opreme uporabite spletni vmesnik Optima Prevent.

### 4.3. Pregled opreme in nova kontrola

Na kartici opreme so prikazani podatki o opremi, lokacija, serijska številka, veljavnost in zadnja kontrola.

Za novo kontrolo:

1. Kliknite **Začni kontrolo opreme**.
2. Preverite datum kontrole in vnesite veljavnost v mesecih.
3. Izberite rezultat **Ustrezno** ali **Neustrezno**.
4. Po potrebi dopolnite lokacijo, uporabnika, naslov in opombe.
5. Izpolnite dinamične kontrolne točke, če so za opremo nastavljene.
6. Za sledljivost priporočamo, da kliknete **Zajem trenutne GPS lokacije** in dovolite dostop do lokacije.
7. Kliknite **Shrani kontrolo**.

Po uspešnem shranjevanju se prikaže potrditev, kontrola pa se zabeleži v centralno bazo. Če shranjevanje ne uspe, preverite internetno povezavo in poskusite znova.

!!! tip "Kontrolne točke"
    Kontrolne točke se preberejo iz šablone, nastavljene v spletnem sistemu. Vsako točko označite posebej. Če šablona ni prikazana, osvežite stran in preverite, ali je oprema pravilno povezana s šablono.

### 4.4. Kartica zaposlenega

Skeniranje QR kode zaposlenega prikaže:

- ime, podjetje in lokacijo,
- delovno mesto in status,
- zdravniške preglede,
- usposabljanja in e-teste.

Kartica je namenjena pregledu. Za urejanje podatkov uporabite spletni vmesnik.

---

## 5. Zaposleni e-test

### 5.1. Prijava

1. Izberite **Zaposleni e-test**.
2. Vnesite **uporabniško ime** in **geslo**, ki sta bila ustvarjena za e-test.
3. Potrdite prijavo.

Če so na e-test kartici natisnjene prijavne QR kode, lahko podatke preberete tudi s skeniranjem. QR koda mora vsebovati obliko `url|uporabniško_ime|geslo`.

!!! warning "QR koda vsebuje geslo"
    Prijavne QR kode ne delite in ne puščajte na javno dostopnem mestu. Če je koda izgubljena, naj skrbnik ustvari novo ali spremeni geslo.

### 5.2. Potek e-testa

1. Pred začetkom kviza si oglejte gradivo in potrdite seznanitev z njim.
2. Kliknite **Nadaljuj na kviz**.
3. Odgovorite na vprašanja z izbiro enega od ponujenih odgovorov.
4. Če je nastavljena časovna omejitev, spremljajte odštevalnik.
5. Na zadnjem vprašanju kliknite **Oddaj kviz**.

Po oddaji se prikaže rezultat. Če test ni uspešen ali če so na voljo dodatni poskusi, uporabite **Nazaj na prijavo** in začnite nov poskus. Ko so poskusi porabljeni, sistem prikaže ustrezno obvestilo.

!!! note "Podatki e-testa"
    Rezultat in morebitno potrdilo se shranita v centralno bazo Optima Prevent. Za prikaz ali prenos dokumentov uporabite spletni sistem ali portal, ki ga določi vaš skrbnik.

---

## 6. HRM prisotnost

HRM prisotnost je namenjena beleženju prihodov in odhodov zaposlenih.

### 6.1. Pogoji

- Prijavljeni morate biti kot inšpektor/administrator z dovoljenjem za HRM.
- Za skeniranje QR kode potrebujete dostop do kamere.
- Za NFC beleženje potrebujete Android napravo z vključenim NFC, brskalnik Chrome in HTTPS povezavo.
- Za shranjevanje dogodka potrebujete internetno povezavo.

### 6.2. Beleženje s QR kodo

1. Odprite **HRM prisotnost**.
2. Usmerite kamero v QR kodo zaposlenega.
3. Počakajte na zaznavo.

Sistem samodejno ugotovi, ali gre za **prihod** ali **odhod**, in prikaže ime zaposlenega ter čas.

### 6.3. Beleženje z NFC značko

1. Na Android napravi se dotaknite **Preberi NFC značko**.
2. Zaposleni prisloni NFC kartico ali obesek na hrbtno stran naprave.
3. Počakajte na potrditev.

!!! warning "NFC ni na voljo na vseh napravah"
    Web NFC trenutno ni podprt v Safariju na iPhonu/iPadu. Na teh napravah uporabite QR kodo ali ročni vnos.

### 6.4. Ročni vnos

Če QR ali NFC ni na voljo, vnesite oziroma prilepite kodo zaposlenega v polje **Ročni vnos kode** in kliknite **Odpri kodo**.

### 6.5. Prikaz rezultata

Po uspešnem beleženju se prikaže:

- ime zaposlenega,
- **Prihod zabeležen** ali **Odhod zabeležen**,
- datum in čas.

Če je bila ista značka skenirana v zadnjih nekaj sekundah, sistem prikaže opozorilo o podvojenem skeniranju. Počakajte in poskusite znova.

---

## 7. Posodobitve in odpravljanje težav

| Težava | Kaj storiti |
|---|---|
| Ni možnosti **Namesti aplikacijo** | Odprite povezavo v Chromu, ne v predogledu druge aplikacije. Posodobite Chrome in poskusite znova. Uporabite lahko **Dodaj na začetni zaslon**. |
| Aplikacija se odpre z naslovno vrstico | Aplikacija je odprta kot zavihek in ne kot nameščena PWA. Ponovno jo namestite ali odprite z ikone na začetnem zaslonu. |
| Kamera ne dela | V nastavitvah Chroma za to spletno mesto dovolite dostop do kamere. Preverite, ali druga aplikacija ne uporablja kamere. |
| NFC ne dela | Uporabite Android + Chrome, vklopite NFC in preverite, ali naprava podpira NFC. Na iPhonu uporabite QR ali ročni vnos. |
| Prijava ne uspe | Preverite točen naslov namestitve, uporabniško ime in geslo ter pravice računa. |
| Prikazana je stara različica | Zaprite aplikacijo in jo znova odprite. Počakajte, da se posodobitev naloži. Po večji posodobitvi pomaga tudi osvežitev strani. |
| Podatki se ne shranijo | Preverite internetno povezavo in poskusite znova. Če se napaka ponovi, posredujte čas dogodka in opis podpori. |
| Stran se ne odpre | Preverite, ali je naslovu dodan `/mobile` in ali je spletno mesto dostopno prek HTTPS. |

!!! tip "Namestitev na skupno napravo"
    Na skupni ali javni napravi se po končanem delu vedno odjavite. Ne puščajte odprte seje in ne shranjujte prijavnih QR kod na javno dostopnem mestu.

---

## 8. Varnost in zasebnost

- Uporabljajte samo naslov, ki vam ga je posredoval pooblaščeni skrbnik.
- Preverite, da je povezava **HTTPS** in da brskalnik ne prikazuje opozorila o certifikatu.
- Ne namestite aplikacije s povezave, ki je prejela po e-pošti ali sporočilu, če je ne pričakujete.
- QR koda zaposlenega in prijavna QR koda e-testa sta osebna podatka; ne delite ju.
- Dostop do kamere in lokacije uporabljajte samo med skeniranjem oziroma vnosom kontrole.
- Za delo brez povezave aplikacija ni namenjena; podatki se shranijo šele, ko je povezava vzpostavljena.

---

## 9. Povezana navodila

- [Prijava v spletni sistem](manual-sl/prijava.md)
- [Delovna oprema in QR kode](manual-sl/delovna-oprema.md)
- [Usposabljanje in e-testi](manual-sl/usposabljanje.md)
- [HRM – upravljanje kadrov](manual-sl/hrm.md)
- [Sinhronizacija med namestitvami](manual-sl/sinhronizacija.md)

Za pomoč se obrnite na svojega skrbnika sistema ali na podporo Optima Prevent.
