# Portal za zdravnike (Medicina dela)

Optima Prevent vključuje namenski portal za izvajalce medicine dela, prometa in športa. Zdravnikom omogoča neposreden vpogled v napotnice, pregled zaposlenih po podjetjih, vnos rezultatov pregledov ter dostop do podatkov o ocenah tveganja za delovna mesta.

Portal je neposredno povezan z glavno bazo podatkov — vsi rezultati, ki jih zdravnik vnese, so takoj vidni delodajalcu v glavni aplikaciji in na portalu za stranke.

Zdravniki se v portal prijavljajo z ločenimi računi, ki jih upravljajo administratorji v glavni aplikaciji.

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

!!! tip "Geslo za zdravnika"
    Ob kliku na **Ustvari** se prikaže generirano geslo. Tega sporočite zdravniku (po e-pošti, telefonu). Zdravnik si ga lahko kasneje spremeni.

### 1.2 Dodeljevanje ustanov strankam

**Dostop:** Glavni meni → Stranke → urejanje stranke → zavihek Izvajalci MD

V obrazcu za urejanje stranke administrator:

- Označi, katere ustanove medicine dela so pogodbene za to stranko
- Opcijsko izbere **prednostnega zdravnika** za vsako ustanovo

!!! info "Več ustanov na stranko"
    Stranka ima lahko dodeljenih več izvajalcev medicine dela. Ob kreiranju napotnice se med njimi izbere ustrezen izvajalec.

---

## 2. Prijava v portal

Zdravniki do portala dostopajo preko namenske prijavne strani.

**URL naslov:** `https://vaš-naslov.si/mod-medic`

Prijavni zaslon je oblikovan v medicinski modri barvni shemi z jasno oznako »Medicina dela, prometa in športa«. Zdravnik se prijavi s svojo e-pošto in geslom, ki mu ju je dodelil administrator.

---

## 3. Nadzorna plošča (Dashboard)

Po prijavi zdravnik vidi nadzorno ploščo s ključnimi številkami:

| Kazalnik | Pomen |
|---|---|
| **Čakajoči** | Število napotnic, ki še čakajo na vnos rezultata |
| **Opravljeni** | Število že obdelanih pregledov |
| **Zaposleni** | Število vseh zaposlenih pri dodeljenih podjetjih |
| **Poteka** | Število pregledov, ki jim veljavnost poteče v 30 dneh |

Pod kazalniki se nahaja **Koledar potekov** — prikaz zaposlenih, ki jim v naslednjih 12 mesecih poteče veljavnost zdravniškega spričevala. Zaposleni so združeni po mesecih in podjetjih:

- 🔴 **Rdeče obarvani meseci** — zaposleni, ki jim je veljavnost že potekla (v zadnjih 3 mesecih)
- 🟡 **Rumeno obarvan mesec** — zaposleni, ki jim veljavnost poteče v tekočem mesecu
- 🟢 **Zeleno obarvani meseci** — zaposleni, ki jim veljavnost poteče v prihodnosti

Zdravnik tako na enem mestu vidi, katero podjetje mora obiskati v katerem mesecu.

V zgornjem desnem kotu navigacijske vrstice sta prikazana **ime in priimek zdravnika** ter **naziv ustanove**, tako da je vedno jasno, kdo je prijavljen.

Če ima zdravnik dodeljenih več podjetij, se v zgornjem meniju prikaže **izbirnik aktivnega podjetja**, s katerim lahko filtrira prikazane podatke.

---

## 4. Seznam zaposlenih

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
| **Ime in priimek** | Klik na ime odpre podrobno kartico zaposlenega |
| **OT** | Število dejavnikov tveganja iz ocene tveganja (zeleno = ima OT, klik za podrobnosti) |
| **Rezultat** | Zadnji znani rezultat zdravniškega pregleda |
| **+** | Gumb za hitro kreiranje nove napotnice |

### 4.1 Filtri in iskanje

Nad seznamom so na voljo naslednji filtri:

| Filter | Opis |
|---|---|
| **Iskalnik po imenu** | Hitro iskanje po imenu ali priimku |
| **Tip pregleda** | Izbira tipa napotnice, ki se bo ustvarila ob kliku na **+** (obdobni / predhodni / izredni) |
| **Moji pacienti** | Gumb za prikaz samo tistih zaposlenih, ki jih je zdravnik že osebno pregledal |
| **Kategorija tveganja** | Spustni seznam kategorij tveganj (Hrup, Kemikalije, Vibracije …) za filtriranje zaposlenih, ki so izpostavljeni določenemu tveganju |

### 4.2 Izvoz v Excel

Gumb **Excel** v zgornjem desnem kotu izvozi trenutno filtriran seznam zaposlenih v Excel datoteko. Izvoz vključuje: ime, priimek, podjetje, delovno mesto, število in kategorije tveganj, datum OT, veljavnost, datum in oceno zadnjega pregleda ter datum poteka.

Izvoz upošteva vse aktivne filtre — če je vklopljen filter »Moji pacienti« ali izbrana kategorija tveganja, se izvozijo samo filtrirani zaposleni.

### 4.3 Kreiranje napotnice iz portala

Zdravnik lahko neposredno iz seznama zaposlenih ustvari novo napotnico:

1. V spustnem seznamu **Tip pregleda** izbere vrsto pregleda (obdobni / predhodni / izredni).
2. Klikne gumb **+** v vrstici zaposlenega.
3. Sistem samodejno ustvari napotnico z vsemi podatki iz ocene tveganja:
   - prenese dejavnike tveganja delovnega mesta,
   - doda specifične dejavnike zaposlenega,
   - prenese podatke o OVO, opremi in kemikalijah.
4. Zdravnik je preusmerjen na obrazec za vnos rezultata, kjer takoj vpiše oceno.

### 4.4 Kartica zaposlenega

S klikom na ime zaposlenega se odpre podrobna kartica, ki vsebuje:

- **Osebne podatke** — EMŠO, datum rojstva, delovno mesto
- **Zasebne opombe zdravnika** — opombe, ki so vidne **samo prijavljenemu zdravniku** (niso vidne delodajalcu na portalu za stranke). Namenjene so kliničnim opombam, opozorilom in sledenju.
- **Podatke iz ocene tveganja** — delovno mesto, datum OT, oprema, kemikalije, OVO
- **Trend zadnjih pregledov** — primerjava zadnjih treh pregledov (datum, tip, ocena, omejitve) v strnjeni tabeli. Zdravnik tako takoj vidi, ali se ocena skozi čas slabša (npr. 1 → 2 → 3).
- **Seznam dejavnikov tveganja** — vsa tveganja z R0 > 1, razvrščena po kategorijah
- **Specifične dejavnike** — morebitne posebnosti zaposlenega (alergije ipd.)
- **Zgodovino pregledov** — vsi pretekli zdravniški pregledi z rezultati

---

## 5. Seznam pregledov

**Dostop:** Portal → Zdravniški pregledi

Prikaz vseh napotnic, dodeljenih zdravniku ali njegovi ustanovi. Možnosti filtriranja:

- **Čakajoči** — prikaže samo neobdelane napotnice
- **Vsi** — prikaže vse napotnice (tudi že obdelane)
- **Obdobni / Predhodni / Izredni** — gumbi za filtriranje po tipu pregleda. Oba filtra (status in tip) se lahko kombinirata — npr. »Čakajoči + Predhodni« prikaže samo neobdelane predhodne preglede.

| Stolpec | Pomen |
|---|---|
| **Podjetje** | Delodajalec |
| **Delavec** | Ime in priimek zaposlenega |
| **Tip** | Vrsta pregleda (obdobni / predhodni / izredni) |
| **Datum** | Datum napotnice |
| **Rezultat** | Barvna značka z oceno (če je že vnešena) ali "Čaka" |
| **Akcija** | Gumb **Vnesi** (če še ni rezultata) ali **Ogled** (če je že vnešen) |

---

## 6. Vnos rezultata pregleda

**Dostop:** Klik na **Vnesi** v seznamu pregledov ali preko QR kode na napotnici

Obrazec za vnos rezultata vsebuje:

### 6.1 Podatki o delavcu in tveganjih

Na vrhu obrazca so prikazani:
- Ime delavca, podjetje, delovno mesto
- Tip pregleda in datum napotnice
- **Dejavniki tveganja** iz ocene tveganja (kategorije, R0 vrednosti)
- Specifični dejavniki zaposlenega

### 6.2 Vnos rezultata

| Polje | Opis |
|---|---|
| **Datum pregleda** | Dejanski datum opravljenega pregleda. Polje uporablja **koledarski izbirnik (flatpickr)** za enostaven vnos datuma. |
| **Št. zdravniškega spričevala** | Številka izdanega spričevala |
| **Ocena** | 1–6 po uradnem obrazcu |
| **Priloge** | Možnost nalaganja datotek — izvidi, laboratorijski izsledki, avdiogrami, specialistična poročila (PDF, slike, dokumenti do 10 MB). Že naložene datoteke so prikazane kot povezava za prenos in jih je mogoče izbrisati. |

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
- **Ocena 2 ali 3** → polje za vpis omejitev
- **Ocena 5** → polje za predlog drugega dela
- **Ocena 6** → izbira razloga (6.1–6.4)

Na dnu obrazca je polje **Predlagani ukrepi** za morebitne dodatne opombe ali predloge zdravnika.

Po shranjevanju se rezultat takoj zapiše v sistem in je viden delodajalcu.

---

## 7. Dostop preko QR kode

Vsaka tiskana napotnica vsebuje **QR kodo** v nogi dokumenta. Zdravnik lahko s skeniranjem kode (s telefonom) neposredno odpre obrazec za vnos rezultata — **brez prijave v portal**.

To omogoča hiter vnos rezultatov tudi zdravnikom, ki še nimajo ustvarjenega uporabniškega računa, ali kadar želijo rezultat vnesti takoj ob pregledu.

---

## 8. Povezava z glavno aplikacijo

Vsi podatki, ki jih zdravnik vnese preko portala, so takoj na voljo:

- **Delodajalcu** v glavni aplikaciji (Evidence → Zdravniški pregledi)
- **Delodajalcu** na portalu za stranke (mod-cust)
- **Na kartici zaposlenega** v razdelku Dejavniki tveganja

S tem je zagotovljena popolna sledljivost — od izdaje napotnice, preko zdravniškega pregleda, do končnega rezultata.
