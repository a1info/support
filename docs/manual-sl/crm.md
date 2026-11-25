# CRM (Naloge, kampanje in prospekti)

Modul **CRM** omogoča pregled in organizacijo dela z naročniki prek skupnega koledarja, projektov in nalog ter vodenje prospektov in e-poštnih kampanj.

---

## Pregled modula

CRM modul je osrednje mesto za upravljanje delovnih nalog, projektov in komunikacije s strankami.

### Dostop

**Glavni meni → CRM**

V meniju CRM so **Naloge**, **Projekti**, **Kontakti**, **Časovnica**, **Interakcije**, **Kampanje**, **Prospekti** in **Koledarji**.

### Ključne funkcionalnosti

- Vizualni pregled nalog v mesecu in tednu, z urami dogodkov
- Prikaz ali skrivanje koledarja z gumbom **Prikaži/Skrij koledar**
- Premikanje naloge v drug koledar z desnim klikom (**Premakni v ...**)
- Osebni, skupni in deljeni koledarji ter zunanji (ICS) koledarji
- Iskanje in filtriranje nalog po uporabniku, koledarju in statusu
- Barvno ločevanje: projekt (ozadje) in izvajalec (leva črta)
- Naročnina na koledar (ICS) za Google Koledar in Outlook
- Sledenje statusom nalog
- Ponavljanje nalog (dnevno, tedensko, mesečno, letno) s samodejnim ustvarjanjem prihodnjih pojavitev
- Brisanje naloge neposredno iz obrazca naloge
- Samodejno številčenje projektov (`PR-YYYY-NNNNN`) in delovnih nalogov (`DN-YYYY-NNNNN`)
- Ločevanje delovnih nalogov od običajnih opravil in opomnikov
- Izpis delovnih nalogov (PDF)
- Samodejno generiranje periodičnih opomnikov
- Ločen seznam prospektov z uvozom, segmentacijo in sledenjem soglasja
- E-poštne kampanje za stranke, kontakte in prospekte
- Preverjanje pred pošiljanjem, pošiljanje v paketih in sledenje odzivom
- Beleženje telefonskih klicev in samodejno ustvarjanje nalog za nadaljnje stike
- Globalni seznam odjav in blokad prejemnikov

---

## Naloge (Tasks)

Naloga je osnovna delovna enota v modulu CRM.

### Prikaz in dostop

- Naloge so prikazane v **koledarskem pogledu** (mesec/teden) in kot seznam.
- Odprte naloge so vidne tudi na **uporabniškem Dashboardu** (začetni strani).

### Seznam nalog

Seznam je zasnovan tako, da so najpomembnejši podatki vidni brez odpiranja naloge:

| Stolpec | Vsebina |
|---------|---------|
| **Datum** | Začetek in konec naloge. |
| **Naloga** | Naziv, ikona pomembnosti in ponavljanja ter značke koledarja, delovnega naloga in ponudbe. |
| **Stranka** | Stranka in lokacija izvedbe. |
| **Izvajalec** | Dodeljeni uporabnik in storitve z odgovornimi osebami. |
| **Status** | Barvna značka statusa. |
| **Opis** | Polje **Opis** (`descr`) – dodatne informacije o nalogi. |
| **Ugotovitev** | Polje **Ugotovitev** (`result`) – rezultat oziroma ugotovitev opravljene naloge. |
| **Podpis** | Podpis stranke oziroma gumb za podpis. |
| **Dejanja** | Izvoz DOCX, urejanje in brisanje. |

!!! info "Opis in Ugotovitev sta ločeni polji"
    **Opis** in **Ugotovitev** se v obrazcu in seznamu prikazujeta ločeno. Besedilo, vneseno v polje **Ugotovitev**, se ne prepiše v **Opis** in obratno.

### Pravice

| Vloga | Vidnost in urejanje nalog |
|-------|---------------------------|
| **Administrator / Superadmin** | Vidi in ureja vse naloge; naloge lahko dodeljuje kateremu koli uporabniku. |
| **Navadni uporabnik** | Privzeto vidi svoje naloge. Z filtrom lahko doda druge uporabnike ali koledarje, če so mu vidni. Ureja lahko svoje naloge in naloge, kjer je naveden kot izvajalec storitve. |

!!! info "Vidnost koledarjev"
    Naloge v **skupnem koledarju** so vidne vsem uporabnikom. Naloge v **osebnem koledarju** vidijo lastnik in uporabniki, ki jim je lastnik dodelil dovoljenje.

### Polja naloge

| Polje | Opis |
|-------|------|
| **Naziv** | Kratek opis naloge ali naročila. |
| **Št. delovnega naloga (DN)** | Samodejno dodeljena številka delovnega naloga v obliki `DN-YYYY-NNNNN` (npr. `DN-2026-00001`). Prikazana je pri nalogah z dodeljeno številko DN; običajne naloge brez DN je nimajo. |
| **Delovni nalog (DN)** | Kljukica, ki nalogo označi kot delovni nalog. Samo take naloge dobijo številko DN in se prikažejo v pregledu **ERP → Finance → Projekti in naloge**. |
| **Začetek** | Datum in ura začetka naloge. |
| **Konec** | Datum in ura zaključka naloge. |
| **Status** | Trenutno stanje naloge: **Planirano**, **Odprto**, **Končano** ali **Preklicano**. |
| **Opis** | Dodatne informacije o nalogi. |
| **Ugotovitev** | Rezultat oziroma ugotovitev po opravljeni nalogi. |
| **Dodeljen uporabnik** | Izvajalec naloge. |
| **Stranka** | Naročnik, za katerega se naloga izvaja. |
| **Koledar / Projekt** | Razvrstitev v ustrezni koledar ali projekt. |
| **Ponavljanje** | Pravilo ponavljanja; prikazano je samo pri korenski nalogi serije. |
| **Seznam storitev in odgovornih oseb** | Podrobnejši opis storitev, ki jih naloga vključuje, ter odgovorne osebe. |

!!! info "Upravljanje storitev"
    Seznam storitev, ki so na voljo pri nalogah, upravljajo administratorji prek **Nastavitve → Storitve**.

### Povezava s ponudbami (ERP)

Naloga je lahko povezana s ponudbo iz modula **ERP**:

- Nalogo ustvarite neposredno **iz ponudbe** z gumbom *Ustvari nalogo* (glejte poglavje *ERP — Ponudbe in pogodbe*); sistem samodejno poveže nalogo s ponudbo ter predizpolni stranko in naziv naloge.
- Povezava je vidna v obrazcu naloge (**Povezan objekt** s povezavo na ponudbo).
- Na seznamu nalog se pod nazivom naloge izpiše modra značka s **številko ponudbe**; klik nanjo odpre ponudbo.

### Delovni nalog in številčenje (DN)

Naloga je lahko običajno opravilo/opomnik ali **delovni nalog**.

- Kljukica **Delovni nalog (DN)** je privzeto vključena, če nalogo ustvarite iz **projekta**, **ponudbe** ali ko dodate **storitve**.
- Ob shranjevanju sistem dodeli številko `DN-YYYY-NNNNN` (npr. `DN-2026-00001`); `YYYY` je leto nastanka, `NNNNN` pa petmestno zaporedje. Številka je enolična in se po dodelitvi ne spreminja.
- Naloge, ki niso označene kot delovni nalog, ob ustvarjanju ne dobijo številke DN in se ne prikažejo v pregledu **ERP → Finance → Projekti in naloge**.
- Obstoječe naloge niso samodejno označene. Če jih želite vključiti med delovne naloge, jih odprite, obkljukajte **Delovni nalog (DN)** in shranite.
- Številka DN je prikazana v obrazcu naloge, na seznamu nalog, v povezanih nalogah pri ponudbi in v Excel izvozu.
- Če kljukico pozneje odstranite, naloga obdrži že dodeljeno številko, vendar se umakne iz finančnega pregleda delovnih nalogov.

!!! info "Ponovitve"
    Vsaka ponovitev delovnega naloga dobi svojo številko DN. Serija in posamezne ponovitve so tako ločeno sledljive.

### Ponavljanje nalog

Nalogo lahko spremenite v ponavljajočo se serijo v obrazcu naloge z vklopom **Ponavljaj**. Možnosti so:

| Nastavitev | Opis |
|------------|------|
| **Ponavljaj** | Vklopi ali izklopi ponavljanje. Prikazano je samo pri korenski nalogi serije, ne pri posamezni generirani pojavitvi. |
| **Interval in frekvenca** | Dnevno, tedensko, mesečno ali letno; interval pove, vsakih koliko enot se ponovi. |
| **Dnevi** | Pri tedenskem ponavljanju izberite enega ali več dni v tednu. |
| **Konec** | **Nikoli**, **na datum** ali **po določenem številu ponovitev**. |
| **Predogled** | Prikaže naslednje pojavitve pred shranjevanjem. |

Kako deluje:

- Sistem ob shranjevanju ustvari prihodnje pojavitve kot **samostojne naloge**, povezane s korensko nalogo serije.
- Prihodnje pojavitve se sproti dopolnjujejo do približno **60 dni vnaprej**.
- Vsaka pojavitev ima svoj datum, status in morebitno številko DN; spremembe storitev in projekta se prenesejo iz korenske naloge.
- Če uredite posamezno pojavitev, spremenite samo to pojavitev. Za spremembo celotne serije uporabite **Uredi ponavljanje**.
- Sprememba pravila ponavljanja **zamenja prihodnje načrtovane pojavitve**; pretekle, odprte, končane in preklicane ostanejo.
- Ko izklopite **Ponavljaj** in shranite ter obstajajo prihodnje načrtovane pojavitve, sistem prikaže potrditev s številom teh pojavitev. Po potrditvi izbriše samo **prihodnje načrtovane** pojavitve; pretekle, odprte, končane in preklicane ostanejo.

!!! warning "Brisanje prihodnjih pojavitev"
    Izklop ponavljanja ne izbriše celotne zgodovine serije. Če želite izbrisati tudi korensko nalogo, uporabite **Izbriši nalogo** v obrazcu; takrat se izbrišejo korenska naloga in prihodnje načrtovane pojavitve.

### Brisanje naloge

V obrazcu obstoječe naloge je spodaj levo gumb **Izbriši nalogo**. Pred brisanjem sistem zahteva potrditev.

- Pri korenski ponavljajoči se nalogi se izbrišejo korenska naloga in prihodnje načrtovane pojavitve; pretekle, odprte, končane in preklicane ostanejo.
- Pri posamezni generirani pojavitvi se izbriše samo ta pojavitev, serija pa se nadaljuje.
- Gumb ni prikazan pri novi nalogi, ki še ni shranjena.

---

## Koledarji

Naloge so razvrščene v koledarje. Vsak koledar ima **lastnika**, **barvo** in **tip**.

### Vrste koledarjev

| Tip | Namen |
|-----|-------|
| **Skupni (Naročila)** | Sistemski skupni koledar, viden vsem. Vanj se shranijo naloge, če uporabnik ne izbere drugega. Ni ga mogoče izbrisati. |
| **Osebni** | Vsak uporabnik ga dobi samodejno ob ustvaritvi računa. Vidi ga lastnik in uporabniki z dovoljenjem. |
| **Deljeni** | Skupni koledar brez lastnika; dostop je urejen prek dovoljenj. Ustvari ga superadmin. |
| **Zunanji (ICS)** | Povezan Google/Outlook koledar. Dogodki so **samo za branje** in se sinhronizirajo vsakih 15 minut. |

### Osebni koledar

- Ob ustvaritvi uporabnika sistem samodejno ustvari njegov osebni koledar z imenom uporabnika.
- Uporabnik lahko v **CRM → Koledarji** ustvari dodatne koledarje ali uredi svojega.
- Lastnik lahko koledar deli z uporabniki ali skupinami prek ikone **Dovoljenja**.

!!! tip "Skupni koledar kot privzeta izbira"
    Podjetja, ki delo organizirajo v enem skupnem koledarju, lahko še naprej uporabljajo **Naročila**: novi nalogi se samodejno dodeli ta koledar, uporabnik pa ga lahko v obrazcu zamenja.

### Dovoljenja

| Dovoljenje | Opis |
|------------|------|
| **Lastnik** | Upravlja koledar, dovoljenja in brisanje. |
| **Urejanje** | Ureja koledar in njegove naloge; ne more brisati koledarja ali spreminjati dovoljenj. |
| **Vpogled** | Vidi koledar in njegove naloge. |
| **Brez** | Koledarja ne vidi. |

### Barve

- **Ozadje dogodka** = barva projekta.
- **Leva črta** = barva izvajalca (generirana iz uporabnikovega ID-ja).
- **Pika pred imenom** v seznamu nalog = barva izvajalca.
- Naloge brez projekta imajo nevtralno ozadje, tako da je izvajalec še vedno razviden.

### Prikaz in skrivanje koledarja

Nad koledarjem je gumb z ikono očesa:

- ko je koledar viden, gumb prikazuje **Skrij koledar**;
- ko je koledar skrit, gumb prikazuje **Prikaži koledar**.

Skrit koledar ne vpliva na podatke ali filtre; spremeni se samo prikaz.

### Premikanje naloge v drug koledar

Z **desnim klikom** na nalogo v koledarju odprete meni **Premakni v ...** in izberete ciljni koledar.

- Meni je na voljo samo za naloge, ki jih smete urejati, in ne za zunanje (ICS) dogodke.
- Pri ponavljajoči se korenski nalogi se v izbrani koledar premaknejo tudi prihodnje načrtovane pojavitve.
- Superadmin vidi vse koledarje; administratorji in navadni uporabniki vidijo skupne koledarje in koledarje, za katere imajo dovoljenje. Zato so v seznamu lahko tudi osebni koledarji uporabnikov, ki so poimenovani po njihovih imenih.

### Iskanje in filtri

- **Iskalno polje** nad seznamom išče po nazivu naloge, številki DN, stranki in lokaciji.
- **Filtri** (uporabnik, koledar, status) so v zgornji vrstici; izbrani filtri so prikazani kot **čipi**, ki jih odstranite s klikom na ×.
- **Počisti filtre** vrne privzeti pogled (vsi uporabniki, vsi statusi).
- **Mesečni/tedenski pogled**: dogodke lahko **premaknete** (sprememba datuma) ali **raztegnete** (sprememba konca); spremembe se shranijo takoj.

### Naročnina na koledar (ICS)

Uporabnik lahko svoj CRM koledar naroči v Google Koledar, Outlook ali drug ICS odjemalec.

1. Odprite **CRM → Koledarji**.
2. V kartici **Naročnina na koledar (ICS)** kliknite **Ustvari povezavo**.
3. Kopirajte prikazani naslov in ga dodajte v svoj koledar:
   - **Google Koledar**: *Drugi koledarji → Iz URL-ja*.
   - **Outlook**: *Dodaj koledar → Naročnina iz spleta*.
4. Povezava je **osebna** – ne delite je. Z gumbom **Nova povezava** jo prekličete in ustvarite novo; z **Prekliči** onemogočite dostop.

!!! warning "Zasebnost povezave"
    Naslov vsebuje skrivni žeton. Kdor ima povezavo, lahko bere naloge, ki so vidne temu uporabniku. Ob sumu uhajanja povezavo takoj zamenjajte.

### Zunanji koledarji (Google/Outlook → CRM)

1. Odprite **CRM → Koledarji** in kliknite **+**.
2. Izberite tip **Zunanji (ICS)**.
3. Prilepite **skrivni naslov iCal**:
   - **Google Koledar**: *Nastavitve → Nastavitve koledarja → Skrivni naslov v obliki iCal*.
   - **Outlook**: *Objavi koledar → Povezava ICS*.
4. Shranite. Sinhronizacijo lahko takoj sprožite z gumbom **Sinhroniziraj**, sicer se izvede samodejno vsakih 15 minut.
5. Na obrazcu sta prikazana **zadnja sinhronizacija** in morebitna **napaka**.

Zunanji dogodki:

- so prikazani v glavnem koledarju nalog z barvo zunanjega koledarja,
- so **samo za branje** (ni jih mogoče urejati, premikati ali brisati),
- se **ne** prikazujejo v seznamu nalog, Excel izvozu ali na portalu za stranke,
- podpirajo osnovno ponavljanje (dnevno, tedensko, mesečno, letno); izjeme ponavljanja (EXDATE) niso podprte.

!!! info "Varnost povezave"
    Dovoljena je samo povezava **https**. Naslovi, ki kažejo na lokalno omrežje ali zasebne strežnike, so zavrnjeni.

### Periodika in veljavnosti

Opomniki iz evidenc z veljavnostjo (usposabljanja, pregledi, meritve) **niso** del koledarjev CRM. Prikazujejo se v ločenem pregledu **Poročila → Veljavnosti** in so namenjeni samo branju. Ne urejajte jih ročno – ob naslednji posodobitvi se prepišejo.

V koledarju veljavnosti lahko iz posamezne pojavitve ustvarite CRM nalogo: kliknite ikono **i** in izberite **Dodaj nalogo**. Obrazec se predizpolni s stranko, začetkom, nazivom in lokacijo; izberete lahko izvajalca, projekt in storitve. Naloga se shrani v privzeti CRM koledar, periodična evidenca pa ostane nespremenjena. Če za pojavitev že obstaja aktivna CRM naloga, sistem ne ustvari dvojnika.

---

## Projekti

Projekt združuje naloge, datoteke in komentarje v enotnem kronološkem pogledu.

### Dostop

**CRM → Projekti → Ogled**

### Številka projekta

Vsak projekt ob shranjevanju dobi številko `PR-YYYY-NNNNN` (npr. `PR-2026-00001`); `YYYY` je leto nastanka, `NNNNN` pa petmestno zaporedje. Številka je enolična in je prikazana v glavi projekta ter na seznamu projektov. Ustvarjenih številk ni mogoče spreminjati.

### Podatki o projektu

| Podatek | Opis |
|---------|------|
| **Št. projekta** | Samodejno dodeljena številka `PR-YYYY-NNNNN`. |
| **Naziv** | Ime projekta. |
| **Stranka** | Naročnik projekta. |
| **Skrbnik** | Oseba ali vloga, odgovorna za projekt; dodeli se prek ikone **Dovoljenja**. |
| **Status** | **Planirano**, **Odprto**, **Končano** ali **Preklicano**. |
| **Začetek / konec** | Načrtovani časovni okvir projekta. |
| **Odstotek dokončanja** | Napredek projekta od 0 do 100 %. |
| **Opis** | Dodatne informacije o projektu. |

### Seznam projektov in filtri

Na seznamu **CRM → Projekti** lahko kombinirate naslednje filtre:

- **Status projekta** – Planirano, Odprto, Končano, Preklicano.
- **Skrbnik** – uporabnik ali vloga, vključno z možnostjo **Brez skrbnika**.
- **Podjetje** – stranka, ki ji projekt pripada.

Filtri se med seboj kombinirajo. Iskalnik išče po nazivu in številki projekta. Filtre in iskanje upošteva tudi Excel izvoz, ki vsebuje številko projekta.

### Struktura projekta

| Element | Opis |
|---------|------|
| **Naloge** | Vse naloge, ki so dodeljene temu projektu. |
| **Datoteke** | Priponke in dokumenti, vezani na projekt. |
| **Komentarji** | Komunikacija med člani ekipe znotraj projekta. |

### Pravice dostopa

| Nastavitev | Opis |
|-----------|------|
| **Privzeto** | Projekt je dostopen vsem uporabnikom sistema. |
| **Omejeno** | Ogled in urejanje projekta se omeji na točno določene uporabnike. |

!!! tip
    Projekte uporabite za večje naročniške pogodbe ali ponavljajoče se sklope del, kjer želite vse naloge, dokumentacijo in komunikacijo hraniti na enem mestu.

---

## Prospekti

**Dostop:** CRM → Prospekti

Prospekt je potencialna stranka, ki še ni v šifrantu strank. Prospekte vodite ločeno od strank in kontaktov, nato pa jih uporabite kot občinstvo v kampanji. Ko prospekt postane stranka, njegov status ročno označite kot **Pretvorjen**.

### Seznam in urejanje

- Seznam prikazuje naziv, kontaktno osebo, e-pošto, segment in status.
- **Nov prospekt** odpre obrazec v desnem stranskem oknu; klik na obstoječi zapis odpre urejanje.
- Iskalnik išče po nazivu, e-pošti in davčni številki, filter po statusu pa zoži seznam.
- Gumba **Uredi** in **Izbriši** sta na koncu vsake vrstice.

### Polja prospekta

| Polje | Opis |
|-------|------|
| **Naziv** | Obvezno ime podjetja ali osebe. |
| **Tip** | Vrsta prospekta (npr. podjetje, samostojni podjetnik). |
| **Segment** | Tržni ali interni segment za razvrščanje. |
| **Prioriteta** | Prioriteta obdelave (npr. A, B, C). |
| **Davčna številka** | Davčna številka; uporablja se tudi za prepoznavanje dvojnikov pri uvozu. |
| **SKD** | Šifra dejavnosti. |
| **Naslov**, **Pošta**, **Kraj**, **Regija** | Naslov in geografska razvrstitev. |
| **Kontaktna oseba** | Oseba, s katero komunicirate. |
| **E-pošta** | Naslov za kampanje; shrani se v malih črkah. |
| **Telefon** | Telefon za klicanje. |
| **Zaposleni** | Število zaposlenih. |
| **Prihodek** | Letni prihodek. |
| **Vir** | Kako ste prospekt pridobili (npr. sejem, priporočilo, splet). |
| **Pravna podlaga** | Pravna podlaga za obdelavo oziroma komunikacijo. |
| **Vir soglasja** | Kje in kako je bilo soglasje pridobljeno. |
| **Datum soglasja** | Datum pridobitve soglasja. |
| **Status** | Trenutna faza obdelave. |
| **Opomba** | Interna opomba. |

### Statusi prospekta

| Status | Pomen |
|--------|-------|
| **Nov** | Prospekt je vnesen in še ni bil obdelan. |
| **Kontaktiran** | Prvi stik je bil opravljen. |
| **Kvalificiran** | Prospekt je primeren za nadaljnjo obravnavo. |
| **Pretvorjen** | Prospekt je postal stranka. |
| **Blokiran** | Prospekta ne kontaktirajte. |
| **Odjavljen** | Oseba se je odjavila od e-poštnih sporočil. |

!!! warning "Soglasje in pravna podlaga"
    Pred pošiljanjem kampanje preverite, da imate za prospekte ustrezno pravno podlago oziroma soglasje. Preflight opozori na prejemnike brez zabeležene pravne podlage, vendar ne nadomesti vaše presoje.

### Uvoz prospektov

V kartici **Uvozi prospekte** lahko naložite datoteko **CSV**, **XLSX** ali **XLS**. Za lažji začetek uporabite povezavo **Prenesi primer CSV**.

- **Obvezna glava:** `naziv`.
- **Priporočene glave:** `e-posta`, `davcna`, `segment`, `prioriteta`, `regija`.
- **Podprte dodatne glave:** `tip`, `skd`, `naslov`, `posta`, `kraj`, `kontaktna_oseba`, `telefon`, `zaposleni`, `prihodek`, `vir`, `opomba`, `pravna_podlaga`, `vir_soglasja`, `datum_soglasja`.
- **Preizkus** prebere datoteko in prikaže rezultat, ne da bi karkoli shranil. Za dejanski uvoz počistite kljukico **Preizkus** in kliknite **Uvozi**.
- Podvojeni zapisi se prepoznajo po **davčni številki ali e-pošti**. Prazna polja v datoteki ne prepišejo obstoječih podatkov.
- Po uvozu so prikazani števci **Prebrano**, **Ustvarjeno**, **Posodobljeno** in **Izpuščeno** ter morebitne napake po vrsticah.

---

## Kampanje

**Dostop:** CRM → Kampanje

Kampanje omogočajo pošiljanje e-poštnih sporočil strankam, kontaktom ali prospektom ter sledenje odzivom. Zavihek **Predloge** vodi do e-poštnih predlog, zavihek **Odjave** pa do globalnega seznama naslovov, ki jim ne pošiljate. Predloge in spremenljivke so opisane v poglavju [Urejanje predlog → E-poštne predloge](urejanje-podlog.md#e-postne-predloge).

Seznam kampanj prikazuje naziv, namen, status, število prejemnikov, predlogo in datum nastanka. Klik na naziv odpre podrobni pogled, ikona svinčnika pa urejanje.

### Priprava kampanje

Kampanjo ustvarite z gumbom **+** na seznamu kampanj. Obrazec je razdeljen na tri korake:

1. **Predloga**
2. **Občinstvo**
3. **Povzetek**

#### 1. Predloga

| Polje | Opis |
|-------|------|
| **Naziv** | Interno ime kampanje; prikazano je na seznamu in v opravilih. |
| **Namen** | Oznaka vala kampanje: prvi, drugi, tretji val ali drugo. Ne vpliva na vsebino sporočila. |
| **Predloga** | E-poštna predloga iz modula **Kampanje**. Če je ni, jo najprej ustvarite v zavihku **Predloge**. |
| **Poštni račun** | Račun, s katerega se pošilja. Prazno pomeni privzeti kampanjski oziroma sistemski račun. |
| **Izvajalec** | Uporabnik, ki mu sistem dodeli naloge za nadaljnje klice. Prazno pomeni ustvarjalca kampanje. |
| **Dnevna omejitev** | Največje število sporočil na dan za to kampanjo. Upošteva se tudi omejitev izbranega poštnega računa. |
| **Od e-pošte**, **Ime pošiljatelja**, **Odgovori na** | Neobvezne vrednosti, ki preglasijo podatke poštnega računa. |

#### 2. Občinstvo

Izberite **vir občinstva**:

- **Stranke in kontakti** – obstoječe aktivne stranke in njihovi kontaktni naslovi.
- **Prospekti** – zapisi iz zavihka **Prospekti**; pretvorjeni, blokirani in odjavljeni prospekti niso vključeni.

Pri viru **Stranke in kontakti**:

| Filter | Opis |
|--------|------|
| **Kategorije strank** | Če ni izbrana nobena, so vključene vse aktivne stranke. |
| **Kategorije kontaktov** | Dodaten, neobvezen filter po kategoriji kontakta. |

Pri obeh virih:

| Filter | Opis |
|--------|------|
| **Poštne številke (predpone)** | Na primer `1000, 2000`; prazno pomeni vse. |
| **SKD predpone** | Na primer `58., 49.`; prazno pomeni vse. |

Pri viru **Prospekti** so na voljo še:

| Filter | Opis |
|--------|------|
| **Samo s telefonom** | Vključi le prospekte z vpisanim telefonom. |
| **Segmenti** | Seznam segmentov, ločen z vejico. |
| **Prioritete** | Seznam prioritet, ločen z vejico. |
| **Regije** | Seznam regij, ločen z vejico. |
| **Zaposleni od / do** | Spodnja in zgornja meja števila zaposlenih. |
| **Prihodek od / do** | Spodnja in zgornja meja letnega prihodka. |

Sproti se izračunava **število prejemnikov**. Šteje unikatne e-poštne naslove; blokirani kontakti in odjave so izključeni, neveljavne naslove pa sistem izloči pri pošiljanju.

#### 3. Povzetek

Preglejte naziv, predlogo, vir občinstva, filtre in število prejemnikov. S klikom **Shrani** se kampanja shrani kot **Osnutek**.

### Generiranje prejemnikov

Po shranjevanju kampanje odprite njen podrobni pogled in kliknite **Generiraj prejemce**.

- Sistem iz trenutnega občinstva ustvari **posnetek prejemnikov** in jih doda v kampanjo.
- Če postopek ponovite, se dodajo le novi naslovi; obstoječi prejemniki in njihovi statusi ostanejo.
- Ko so prejemniki ustvarjeni, sprememba filtrov občinstva **ne spremeni** obstoječega seznama. Nove prejemnike dodajte s ponovnim generiranjem.
- Seznam prejemnikov lahko izvozite v **CSV**.

### Preflight – preverjanje pred pošiljanjem

Gumb **Preflight** preveri, ali je kampanja pripravljena za pošiljanje. Preverjanje ne pošlje nobenega sporočila.

Preveri:

- ali je na voljo aktiven SMTP poštni račun,
- ali ima kampanja predlogo in ali je predloga aktivna ter neprazna,
- ali so prejemniki generirani,
- ali je kampanja odobrena,
- ali imajo prospekti zabeleženo pravno podlago,
- koliko sporočil je bilo danes že poslanih glede na dnevno omejitev kampanje in računa.

Napake preprečijo odobritev; opozorila (na primer manjkajoča pravna podlaga ali dosežena dnevna omejitev) so prikazana, vendar same po sebi ne blokirajo odobritve.

### Odobritev in pošiljanje

Po uspešnem preflightu lahko **administrator ali superadmin** klikne **Odobri pošiljanje**. Šele s tem se kampanja lahko pošlje prek aplikacije.

- **Pošlji paket** doda v čakalno vrsto naslednji paket prejemnikov.
- Pošiljanje poteka v paketih; dnevna omejitev kampanje in poštnega računa se upošteva skupaj.
- Med pošiljanjem je na voljo **Pavza**; z naslednjim **Pošlji paket** se pošiljanje nadaljuje.
- Ko ni več prejemnikov v čakanju ali z napako, sistem kampanjo zaključi.
- Brez aktivnega SMTP računa se kampanja ne pošlje, tudi če je odobrena.

### Statusi kampanje

| Status | Pomen |
|--------|-------|
| **Osnutek** | Kampanja je shranjena, prejemniki še niso pripravljeni. |
| **Pripravljena** | Prejemniki so generirani; kampanja čaka na odobritev ali pošiljanje. |
| **Ročno pošiljanje** | Uporabnik je prejemnike označil kot ročno poslane; kampanja je v ročnem sledenju. |
| **Pošiljanje** | Pošiljanje je v teku. |
| **Zaustavljena** | Pošiljanje je začasno ustavljeno. |
| **Zaključena** | Vsi čakajoči prejemniki so obdelani. |

### Sledenje prejemnikom

V pregledu kampanje lahko filtrirate po statusu, iščete po prejemnikih in označite več vrstic. Statusi prejemnikov so:

| Status | Pomen |
|--------|-------|
| **V čakanju** | Prejemnik še ni bil obdelan. |
| **Poslano** | Sporočilo je bilo poslano. |
| **Odgovoril** | Prejemnik je odgovoril. |
| **Ni odgovora** | Klica ali sporočila ni bilo mogoče zaključiti. |
| **Klik** | Zabeležen je bil klik (če ga ponudnik posreduje). |
| **Zavrnjeno** | Sporočilo je bilo zavrnjeno (bounce). |
| **Odjava** | Prejemnik se je odjavil. |
| **Napaka** | Pošiljanje ni uspelo. |
| **Izpuščeno** | Prejemnik je bil izključen (blokada, odjava, neveljaven naslov). |

Množične akcije:

- **Označi kot poslano** – ustvari odhodno interakcijo in nalogo za nadaljnji klic.
- **Odgovoril** – zabeleži odgovor.
- **Ni odgovora** – označi neuspešen stik.
- **Odjava** – doda naslov na seznam odjav in posodobi prejemnike.
- **Ne kontaktirati** – trajna ali časovno omejena blokada izbranih kontaktov; po izteku datuma se kontakt samodejno vrne v občinstvo.

### Klicanje prejemnikov

Ob prejemniku kliknite ikono **telefona**. V obrazcu za klic izberite izid in po potrebi vnesite datum naslednjega klica ter opombo.

| Izid | Učinek |
|------|--------|
| **Dosežen** | Zabeleži uspešen stik. |
| **Brez odgovora** | Prejemnik dobi status **Ni odgovora**. |
| **Pokliči kasneje** | Ustvari oziroma posodobi nalogo za naslednji klic. |
| **Dogovorjen sestanek** | Zabeleži dogovorjen sestanek in ustvari nalogo. |
| **Ni relevantno** | Prejemnik se izključi iz nadaljnje obravnave. |
| **Pridobljeno** | Zabeleži pridobljeno stranko oziroma posel. |
| **Izgubljeno** | Zabeleži izgubljen posel. |

Klici se zabeležijo v interakcijah; za **Pokliči kasneje** in **Dogovorjen sestanek** sistem ustvari nalogo v osebnem koledarju izvajalca.

### Odjave in blokade

Vsako kampanjsko sporočilo vsebuje povezavo za odjavo. Če je predloga ne vsebuje, jo sistem doda samodejno.

- Klik na povezavo odpre javno stran za potrditev odjave; prijava ni potrebna.
- Po potrditvi se naslov doda na globalni seznam **Odjave**, vsi prejemniki s tem naslovom pa dobijo status **Odjavljen**.
- Na zavihku **Odjave** lahko naslove dodate tudi ročno (razlog: odjava, zavrnjeno, ročno, pritožba) in jih po potrebi izbrišete.
- Odjava velja za vse prihodnje kampanje; za ponovno privolitev je treba naslov odstraniti s seznama odjav in urediti status prospekta oziroma kontakta.

!!! info "Samodejne posodobitve"
    Če je na poštnem računu nastavljen MailerSend webhook, sistem samodejno obdela odjavo, trdi bounce in pritožbo. Mehki bounce se zabeleži, vendar naslova ne doda na trajni seznam odjav.

!!! warning "Pred pošiljanjem"
    Preverite poštni račun, aktivno predlogo, generirane prejemnike in pravno podlago. Za pošiljanje kampanj je potreben aktiven SMTP račun; glejte [Sistemske nastavitve → E-poštni računi](sistemske-nastavitve.md#e-postni-racuni).

---

## Delovni nalog

Delovni nalog je tiskani (PDF) dokument, ki potrjuje opravljeno delo pri stranki. Priporočamo ga za naloge, označene kot **delovni nalog (DN)**.

### Generiranje

Na **seznamu nalog** ali znotraj posamezne naloge kliknite ikono za **tisk delovnega naloga**.

### Vsebina delovnega naloga

- Glava z nazivom, naslovom, registrsko številko, e-pošto, spletno stranjo in logotipom vašega podjetja (iz nastavitev podjetja — stranka s kategorijo *OWN*)
- Podatki o stranki in naslovu
- Številka delovnega naloga (DN), če je nalogi dodeljena; sicer interna številka naloge
- Datum in čas opravljenega dela
- Opis opravljenih storitev
- Ime izvajalca
- Prostor za **podpis stranke** (potrdi sprejem opravljenega dela)

### Prilagoditev

Oblika in vsebina delovnega naloga sta prilagodljivi prek **predlog za tisk**. Predloge ureja administrator v nastavitvah sistema.

!!! info
    Delovni nalog služi kot uradna potrditev opravljenega dela in se priporoča za vsak terenski obisk pri stranki.
