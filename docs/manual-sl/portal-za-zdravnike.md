# Portal za zdravnike (Medicina dela)

Optima Prevent vključuje namenski portal za izvajalce medicine dela, prometa in športa. Zdravnikom omogoča neposreden vpogled v napotnice, pregled zaposlenih po podjetjih, vnos rezultatov pregledov ter dostop do podatkov o ocenah tveganja za delovna mesta.

Portal je neposredno povezan z glavno bazo podatkov — vsi rezultati, ki jih zdravnik vnese, so takoj vidni delodajalcu v glavni aplikaciji in na portalu za stranke.

Zdravniki se v portal prijavljajo z ločenimi računi, ki jih upravljajo administratorji v glavni aplikaciji oziroma **administratorji ustanove** neposredno v portalu.

!!! info "Javna vstopna stran"
    Na naslovu `https://vaš-naslov.si/mod-medic` se gostom prikaže **javna predstavitvena stran** portala (opis funkcionalnosti, potek dela in kontakt za pridobitev dostopa). Prijavljeni uporabniki so namesto tega preusmerjeni na nadzorno ploščo.

---

## 1. Upravljanje izvajalcev in zdravnikov

Preden lahko zdravnik dostopa do portala, mora administrator v glavni aplikaciji:

1. Ustvariti **ustanovo** (izvajalca medicine dela)
2. Dodati **zdravnike** k ustanovi
3. Dodeliti ustanovo **stranki** (podjetju)
4. Ustvariti **uporabniški račun** za zdravnika

### 1.1 Ustanove in zdravniki

**Dostop:** Glavni meni → Stranke → Izvajalci medicine dela

V tem vmesniku administrator:

- Ustvari in ureja ustanove (naziv, naslov, kontakt)
- Dodaja zdravnike k posamezni ustanovi (ime, priimek, e-pošta, licenčna številka)
- Ustvarja uporabniške račune za zdravnike — gumb **Ustvari** ob vsakem zdravniku generira e-poštni naslov in geslo za prijavo v portal
- Z oznako **Admin ustanove** podeli zdravniku pravice za upravljanje dostopov znotraj ustanove (glej poglavje [9. Ustanova](#9-ustanova-administrator-ustanove))

!!! tip "Geslo za zdravnika"
    Ob kliku na **Ustvari** se prikaže generirano geslo. Tega sporočite zdravniku (po e-pošti, telefonu). Zdravnik si ga lahko kasneje spremeni sam (glej poglavje [10. Sprememba gesla](#10-sprememba-gesla)), geslo pa lahko kadar koli ponastavi tudi administrator ustanove.

### 1.2 Dodeljevanje ustanov strankam

**Dostop:** Glavni meni → Stranke → urejanje stranke → zavihek Izvajalci MD

V obrazcu za urejanje stranke administrator:

- Označi, katere ustanove medicine dela so pogodbene za to stranko
- Za vsako ustanovo izbere **zdravnika** ali možnost **Vsi zdravniki** (dostop do napotnic ima celotna ustanova)

!!! info "Samodejno predizpolnjevanje napotnice"
    Ob kreiranju nove napotnice za stranko sistem **samodejno izbere izvajalca medicine dela in zdravnika**, kot sta dodeljena stranki — administratorju ju ni treba izbirati vsakič znova. Izbira se seveda lahko poljubno spremeni.

---

## 2. Prijava v portal

**URL naslov:** `https://vaš-naslov.si/mod-medic`

Na javni vstopni strani je gumb **Prijava v portal**, ki odpre prijavni zaslon. Prijavni zaslon je oblikovan v medicinski modri barvni shemi z jasno oznako »Medicina dela, prometa in športa«. Zdravnik se prijavi s svojo e-pošto in geslom, ki mu ju je dodelil administrator.

!!! warning "Deaktiviran račun"
    Prijava je mogoča samo za **aktivne** uporabniške račune. Deaktiviranim uporabnikom se prijava zavrne — ponovno jih aktivira administrator ustanove ali administrator v glavni aplikaciji.

---

## 3. Nadzorna plošča (Dashboard)

Po prijavi zdravnik vidi nadzorno ploščo s pozdravom, hitrimi akcijami in ključnimi številkami:

| Kazalnik | Pomen |
|---|---|
| **Čakajoči** | Število napotnic, ki še čakajo na vnos rezultata |
| **Opravljeni** | Število že obdelanih pregledov |
| **Zaposleni** | Število vseh zaposlenih pri dodeljenih podjetjih |
| **Podjetja** | Število dodeljenih podjetij |
| **Poteka** | Število pregledov, ki jim veljavnost (oziroma **rok naslednjega pregleda**, če ga je zdravnik določil) poteče v 30 dneh |

Pod kazalniki se nahaja **Koledar potekov** — prikaz zaposlenih, ki jim v naslednjih 12 mesecih poteče veljavnost spričevala, združenih po mesecih in podjetjih:

- 🔴 **Rdeče obarvani meseci** — veljavnost je že potekla
- 🟡 **Rumeno obarvan mesec** — veljavnost poteče v tekočem mesecu
- 🟢 **Zeleno obarvani meseci** — veljavnost poteče v prihodnosti

V zgornjem desnem kotu navigacijske vrstice sta prikazana **ime in priimek zdravnika** ter **naziv ustanove**.

Če ima zdravnik dodeljenih več podjetij, se v zgornjem meniju prikaže **izbirnik aktivnega podjetja**, s katerim lahko filtrira prikazane podatke.

---

## 4. Koledar

**Dostop:** Portal → Koledar

Koledar prikazuje **12-mesečno preglednico** od tekočega meseca naprej — tudi če podatkov ni, je mreža mesecev vedno vidna:

- **Tekoči mesec** — rumeno označeno polje
- **Meseci s pregledi** — zelena polja s številom zaposlenih in seznamom podjetij (klik na podjetje odpre seznam zaposlenih, filtriran na to podjetje)
- **Meseci brez pregledov** — siva polja z oznako »Ni predvidenih pregledov«
- Nad mrežo so posebej izpisani **Pretečeni roki** — zaposleni, ki jim je veljavnost že potekla, z datumom poteka

---

## 5. Seznam zaposlenih

**Dostop:** Portal → Zaposleni

Prikaz vseh aktivnih zaposlenih iz podjetij, ki so dodeljena zdravnikovi ustanovi. Zaposleni so razvrščeni **po podjetjih in nato po delovnih mestih**.

Vsako delovno mesto ima svojo glavo, ki prikazuje:

- **Naziv delovnega mesta**
- **Datum zadnje ocene tveganja**
- **Število dejavnikov tveganja** (R0 > 1)
- **Veljavnost pregledov** (v mesecih)
- **Kategorije tveganj** (npr. Hrup, Prah, Vibracije)

| Stolpec | Pomen |
|---|---|
| **☑** | Izbira zaposlenih za **skupinsko kreiranje napotnic** (glej 5.3) |
| **Ime in priimek** | Klik na ime odpre podrobno kartico zaposlenega |
| **OT** | Število dejavnikov tveganja iz ocene tveganja |
| **Rezultat** | Zadnji znani rezultat zdravniškega pregleda |
| **+** | Gumb za hitro kreiranje nove napotnice |

### 5.1 Filtri in iskanje

Nad seznamom so na voljo naslednji filtri:

| Filter | Opis |
|---|---|
| **Iskalnik po imenu** | Hitro iskanje po imenu ali priimku |
| **Tip pregleda** | Izbira tipa napotnice, ki se bo ustvarila (obdobni / predhodni / izredni) |
| **Moji pacienti** | Prikaz samo tistih zaposlenih, ki jih je zdravnik že osebno pregledal |
| **Kategorija tveganja** | Filtriranje zaposlenih po kategoriji tveganja (Hrup, Kemikalije, Vibracije …) |

### 5.2 Izvoz v Excel

Gumb **Excel** v zgornjem desnem kotu izvozi trenutno filtriran seznam zaposlenih v Excel datoteko. Izvoz vključuje: ime, priimek, podjetje, delovno mesto, število in kategorije tveganj, datum OT, veljavnost, datum in oceno zadnjega pregleda ter datum poteka (upošteva tudi rok naslednjega pregleda, če je vpisan).

### 5.3 Kreiranje napotnic iz portala

Zdravnik lahko ustvari napotnico na dva načina:

**Posamično:**
1. V spustnem seznamu **Tip pregleda** izbere vrsto pregleda (obdobni / predhodni / izredni).
2. Klikne gumb **+** v vrstici zaposlenega.
3. Sistem samodejno ustvari napotnico z vsemi podatki iz ocene tveganja (dejavniki tveganja, OVO, oprema, kemikalije).
4. Zdravnik je preusmerjen na obrazec za vnos rezultata.

**Skupinsko (za cel oddelek ali podjetje):**
1. V stolpcu ☑ označi več zaposlenih.
2. Klikne gumb **Ustvari preglede (N)**, ki se prikaže v zgornjem desnem kotu.
3. Po potrditvi sistem ustvari napotnico za vsakega izbranega zaposlenega in preusmeri na seznam pregledov.

### 5.4 Kartica zaposlenega

S klikom na ime zaposlenega se odpre podrobna kartica, ki vsebuje:

- **Osebne podatke** — EMŠO, datum rojstva, delovno mesto
- **Zasebne opombe zdravnika** — opombe, ki so vidne **samo prijavljenemu zdravniku** (niso vidne delodajalcu)
- **Podatke iz ocene tveganja** — delovno mesto, datum OT, oprema, kemikalije, OVO
- **Trend zadnjih pregledov** — primerjava zadnjih treh pregledov (datum, tip, ocena, omejitve)
- **Seznam dejavnikov tveganja** — vsa tveganja z R0 > 1, razvrščena po kategorijah
- **Zgodovino pregledov** — vsi pretekli pregledi z ocenami in veljavnostjo

---

## 6. Seznam pregledov

**Dostop:** Portal → Zdravniški pregledi

Prikaz vseh napotnic, dodeljenih zdravniku ali njegovi ustanovi. Privzeto so prikazani **vsi** pregledi.

### 6.1 Filtri

| Filter | Opis |
|---|---|
| **Na čakanju / Vsi** | Gumba s številom napotnic v posamezni kategoriji (značka ob gumbu) |
| **Moji pacienti** | Prikaz samo napotnic, dodeljenih prijavljenemu zdravniku |
| **Iskalnik po imenu** | Hitro iskanje po imenu ali priimku zaposlenega |
| **Obdobni / Predhodni / Izredni** | Filtri po tipu pregleda — filtri se lahko poljubno kombinirajo |

### 6.2 Stolpci

| Stolpec | Pomen |
|---|---|
| **Podjetje** | Delodajalec |
| **Delavec** | Ime in priimek zaposlenega |
| **Tip** | Vrsta pregleda (obdobni / predhodni / izredni) |
| **Datum** | Datum napotnice |
| **Status** | Barvna značka z oceno (1–6) in **datumom pregleda**; pri oceni 2 tudi značka **Rok naslednjega pregleda**; neobdelane napotnice imajo oznako **Čaka** |
| **Pripomba zdravnika** | Omejitve oziroma predlagani ukrepi (krajši izvleček, celotno besedilo se prikaže ob prehodu z miško) |
| **Akcija** | Gumb **Vnesi** (če še ni rezultata) ali **Ogled** |

### 6.3 Izvoz v Excel

Gumb **Excel** izvozi trenutno filtriran seznam pregledov: zaposleni, podjetje, tip, datumi, ocena, omejitve, **rok naslednjega pregleda**, predlagani ukrepi, številka spričevala in datum pregleda.

---

## 7. Vnos rezultata pregleda

**Dostop:** Klik na **Vnesi** v seznamu pregledov ali preko QR kode na napotnici

### 7.1 Podatki o delavcu in napotnici

Na vrhu obrazca so prikazani vsi podatki napotnice:

- **Delavec** — ime, EMŠO, datum rojstva, naslov, izobrazba, delovno mesto, šifra poklica, delodajalec
- **Napotnica** — tip pregleda, datum napotnice, datum pregleda, razlog napotitve, zadnji preventivni pregled, datum ocene tveganja, veljavnost pregledov
- **Dejavniki tveganja** — kratek opis delovnega procesa, delovna oprema, predmeti dela, izpostavljenost tveganjem, ugotovljeni dejavniki tveganja (R0), izvedeni ukrepi, osebna varovalna oprema, posebne zdravstvene zahteve, delovno mesto neustrezno za, pripombe delodajalca

### 7.2 Vnos rezultata

| Polje | Opis |
|---|---|
| **Datum pregleda** | Dejanski datum opravljenega pregleda (koledarski izbirnik) |
| **Št. zdravniškega spričevala** | Številka izdanega spričevala |
| **Ocena** | 1–6 po uradnem obrazcu (obvezno polje) |
| **Rok naslednjega pregleda** | Prikazan pri oceni **2 (z omejitvami)** — **neobvezno** polje. Če je vpisan, velja ta rok za naslednji pregled; če je prazen, velja prvotna veljavnost iz ocene tveganja |
| **Priloge** | Nalaganje datotek — izvidi, laboratorijski izsledki, avdiogrami (PDF, slike, dokumenti do 10 MB) |

**Ocene po uradnem obrazcu:**

| Oznaka | Pomen |
|---|---|
| 1 | Izpolnjuje posebne zdravstvene zahteve |
| 2 | Izpolnjuje z omejitvami |
| 3 | Začasno ne izpolnjuje |
| 4 | Trajno ne izpolnjuje |
| 5 | Predlagano drugo delo |
| 6 | Ne moremo podati ocene |

Glede na izbrano oceno se prikažejo dodatna polja:

- **Ocena 2 ali 3** → polje za vpis omejitev; pri oceni 2 dodatno **Rok naslednjega pregleda**
- **Ocena 5** → polje za predlog drugega dela
- **Ocena 6** → izbira razloga (6.1–6.4)

Na dnu obrazca je polje **Predlagani ukrepi** za morebitne dodatne opombe ali predloge zdravnika.

!!! info "Rok naslednjega pregleda in veljavnost"
    Če zdravnik pri oceni 2 vpiše rok naslednjega pregleda, se ta datum upošteva povsod v sistemu: v koledarju portala, pri opozorilih o poteku ter v pregledu veljavnosti v glavni aplikaciji. Če rok ni vpisan, sistem uporabi prvotno veljavnost pregleda.

---

## 8. Dostop preko QR kode

Vsaka tiskana napotnica vsebuje **QR kodo** na drugi strani dokumenta (v glavi spričevala, desno od naslova). Zdravnik lahko s skeniranjem kode (s telefonom) neposredno odpre obrazec za vnos rezultata — **brez prijave v portal**.

Lastnosti QR dostopa:

- Na zaslonu so prikazani **vsi podatki napotnice**, enako kot v portalu.
- Če je napotnica že obdelana, se prikaže obvestilo »Pregled je že bil ocenjen«.
- Če je zdravnik med skeniranjem **prijavljen v portal**, se rezultat samodejno pripiše njemu in njegovi ustanovi.
- V glavi zaslona je gumb **Portal Medicina dela**, ki vodi na vstopno stran portala (prijavljenim na nadzorno ploščo).

---

## 9. Ustanova (administrator ustanove)

**Dostop:** Portal → Ustanova (viden samo uporabnikom z oznako **Admin ustanove**)

Administrator ustanove lahko samostojno upravlja dostope zdravnikov svoje ustanove, brez posredovanja administratorja glavne aplikacije:

| Dejanje | Opis |
|---|---|
| **Ustvari dostop** | Ustvari uporabniški račun za zdravnika (generirano geslo se prikaže enkrat) |
| **Novo geslo** | Ponastavi geslo zdravnika (novo geslo se prikaže enkrat) |
| **Aktiviraj / Deaktiviraj** | Vklopi ali izklopi dostop zdravnika do portala |

Pravice so omejene na lastno ustanovo — administrator ustanove ne more upravljati zdravnikov drugih ustanov.

---

## 10. Sprememba gesla

**Dostop:** ikona ključa 🔑 v navigacijski vrstici portala

Vsak zdravnik si lahko sam spremeni geslo:

1. Vpiše trenutno geslo.
2. Vpiše novo geslo (najmanj 8 znakov) in ga potrdi.
3. Shrani — geslo se posodobi takoj, naslednja prijava poteka z novim geslom.

---

## 11. Povezava z glavno aplikacijo

Vsi podatki, ki jih zdravnik vnese preko portala, so takoj na voljo:

- **Delodajalcu** v glavni aplikaciji (Evidence → Zdravniški pregledi)
- **Delodajalcu** na portalu za stranke (mod-cust)
- **Na kartici zaposlenega** v razdelku Dejavniki tveganja

V seznamu zdravniških pregledov v glavni aplikaciji so na voljo:

- **Stolpca** *Izvajalec medicine dela* in *Zdravnik* — kateri ustanovi in zdravniku je napotnica dodeljena
- **Filter Status** — čakajoče in posamezne ocene (1–6); status se prikaže samo za napotnice z dodeljenim izvajalcem medicine dela
- **Filtra** *Izvajalec medicine dela* in *Zdravnik*

Tiskana napotnica vsebuje poleg QR kode tudi **naziv in naslov izvajalca medicine dela** ter **ime pooblaščenega zdravnika**, če sta dodeljena.

S tem je zagotovljena popolna sledljivost — od izdaje napotnice, preko zdravniškega pregleda, do končnega rezultata in roka naslednjega pregleda.
