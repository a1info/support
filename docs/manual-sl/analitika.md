# Analitika

Modul **Analitika** omogoča celovit pregled in analizo podatkov o veljavnostih, realizaciji opravljenih aktivnosti, izdanih dokumentih ter pripravo poročil za stranke.

---

## Periodika (Pregled veljavnosti)

Poročilo omogoča spremljanje veljavnosti različnih evidenc: usposabljanja zaposlenih, pregledi delovne opreme, meritve delovnega okolja, požarna varnost, zdravniški pregledi in ostale evidence. Rezultati so prikazani v ločenih zavihkih z možnostjo iskanja, filtriranja, razvrščanja in izvoza.

### Dostop

**Analitika → Periodika**

### Obrazec za iskanje

| Polje | Opis |
|-------|------|
| **Tip iskanja** | Izberite enega ali več tipov veljavnosti (Usposabljanja, Delovna oprema, Tehnična varnost, Meritve, Požarna varnost, Zdravniški pregledi, Ostale evidence). Vsak izbrani tip se prikaže kot barvna značka. |
| **Obdobje** | Časovno obdobje za filtriranje datumov poteka veljavnosti. |
| **Vključi poteklo** | Ko je označeno, so v rezultatih prikazani tudi že potekli zapisi. |
| **Poslovna enota** | Filter po poslovni enoti izbrane stranke (prikaže se samo, kadar je aktivna stranka). |
| **Delovni status** | Filter po delovnem statusu zaposlenega (npr. samo aktivno delujoči zaposleni). Velja za zavihka **Usposabljanja** in **Zdravniški pregledi**. |
| **Skrbnik** | Filter po uporabniku, ki je zapis ustvaril ali nazadnje urejal. |
| **Tip stranke** | Kadar ni aktivne stranke, filtrirajte po tipu stranke. |

Po nastavitvi kriterijev kliknite **Najdi**.

### Prikaz rezultatov

Rezultati so organizirani v zavihke glede na izbrane tipe veljavnosti. Vsak zavihek vsebuje:

- **Hitro iskanje** – filtriranje vrstic z vpisom ključne besede v iskalno polje,
- **Filter tipa** – spustni seznam za filtriranje po podtipu (npr. tip tečaja, kategorija opreme),
- **Delovni status** – stolpec z značko delovnega statusa zaposlenega (zavihka Usposabljanja in Zdravniški pregledi),
- **Razvrščanje** – klik na glavo stolpca razvrsti podatke naraščajoče ali padajoče,
- **Izvoz v Excel** – pogovorno okno za izbiro stolpcev, ki jih vključite v izvoz; datoteka se prenese samodejno,
- **Stranjenje** – navigacija med stranmi z gumbi na dnu tabele.

!!! warning "Potekli zapisi"
    Zapisi s poteklo veljavnostjo so v stolpcu **Datum poteka** označeni z **rdečo barvo**. Preverite jih redno in načrtujte obnovo.

### Zavihki po tipih

| Zavihek | Vsebina |
|---------|---------|
| **Usposabljanja** | Zaposleni z usposabljanji, datum usposabljanja, datum poteka, poslovna enota. Datum poteka se izračuna po **individualni veljavnosti udeleženca** (polje **Velja (mes)** na tečaju). Zaposleni brez opravljenega usposabljanja so prikazani z oznako **Ni pregledov**. |
| **Delovna oprema** | Pregledi z nazivom opreme, serijsko številko, datumom pregleda in potekom. |
| **Tehnična varnost** | Pregledi opreme tehnične varnosti. |
| **Meritve** | Meritve delovnega okolja, hrupa, elektrike, pretoka zraka itd. |
| **Zdravniški pregledi** | Evidence zdravniških pregledov zaposlenih. Zaposleni brez opravljenega pregleda so prikazani z oznako **Ni pregledov**. |
| **Ostale evidence** | Druge evidence (npr. oddaja osebne varovalne opreme – OVO). |
| **Požarna varnost** | Združeni zavihek s **podzavihki** za: sistemi APZ, gasilniki, hidrantni listi, strelovodi, kurilne naprave, vaje evakuacije. Vsak podzavihek ima lasten filter in iskanje. |

### Koledarski pogled

Kliknite gumb **Prikaži koledar** v zgornjem desnem kotu za prikaz periodičnih nalog v obliki barvno označenega mesečnega/tedenskega koledarja.

Sistem centralno bdi nad vsemi roki (pregledi opreme, usposabljanja, meritve). Periodiko lahko pregledujete v obliki seznama ali **koledarskega pogleda**, kjer so tipi operacij barvno ločeni:

- 🟡 **Rumena:** Pregledi delovne opreme
- 🟢 **Zelena:** EKO / VZD meritve
- 🔵 **Modra:** Usposabljanja zaposlenih
- 🔴 **Rdeča:** Požarna varnost
- 🟣 **Vijolična:** Zdravniški pregledi
- ⚪ **Siva:** Ostale evidence


- Koledarski pogled izvozite v format **ICS** z gumbom ICS (združljivo z Google Calendar, Outlook itd.).

!!! tip
    ICS izvoz je koristen za sinhronizacijo rokov veljavnosti z osebnimi ali skupinskimi koledarji zunaj sistema.

---

## Pregled realizacije

Poročilo prikazuje število in strukturo opravljenih aktivnosti v izbranem obdobju, združenih po strankah in izvajalcih.

### Dostop

**Analitika → Pregled realizacije**

### Obrazec za iskanje

| Polje | Opis |
|-------|------|
| **Datum od** | Začetni datum obdobja. |
| **Datum do** | Končni datum obdobja. |
| **Stranka** | Neobvezno – omeji rezultate na določeno stranko. |
| **Uporabnik** | Neobvezno – omeji rezultate na aktivnosti, ki jih je opravil določen uporabnik. |
| **Skupina usposabljanj** | Neobvezno – omeji usposabljanja na izbrano skupino tipov usposabljanj. |

Kliknite **Najdi** za prikaz poročila.

### Rezultati

**Stolpčni diagram** prikaže skupno število aktivnosti po kategorijah. Kategorije:

| Kategorija | Opis |
|------------|------|
| **Usposabljanja** | Izvedena usposabljanja zaposlenih |
| **Delovna oprema** | Pregledi skupin delovne opreme |
| **Meritve** | Meritve delovnega okolja in elektro meritve |
| **VPP – Gasilniki** | Pregledi ročnih gasilnikov |
| **VPP – APZ** | Pregledi sistemov aktivne požarne zaščite |

Pod diagramom so **podrobne tabele** za vsako kategorijo z zapisi, ki vključujejo stranko, tip, datum, veljavnost in izvajalca. Stolpec **Usposabljanja** prikazuje skupno število udeležb, razdeljen pa je na temnejše segmente po skupinah tipov usposabljanj.

!!! info "Tiskanje"
    Poročilo realizacije je optimizirano za tisk. Kliknite **Natisni** za pošiljanje poročila na tiskalnik ali shranitev kot PDF.

---

## Izdani dokumenti

Upravljanje dokumentov, izdanih za stranke: zapisniki, potrdila, poročila in druge datoteke.

### Dostop

**Analitika → Izdani dokumenti**

### Obrazec za iskanje

| Polje | Opis |
|-------|------|
| **Tip dokumenta** | Filter po vrsti (meritve, delovna oprema, usposabljanja, požarna varnost itd.). |
| **Št. zapisnika** | Iskanje po številki zapisnika. |
| **Datum od / Datum do** | Dokumenti, izdani v izbranem obdobju. |
| **Ime in priimek zaposlenega** | Iskanje po osebi, kadar je dokument vezan na konkretnega zaposlenega. |

Kliknite **Najdi** za prikaz dokumentov.

### Seznam dokumentov

Vsak zapis v seznamu vsebuje:

- Stranka
- Tip dokumenta
- Datum dokumenta
- Datum shranitve v sistem
- Številka zapisnika
- Ime datoteke
- Uporabnik, ki je dokument ustvaril

### Akcije na dokumentu

| Akcija | Opis |
|--------|------|
| **Nova različica** | Zamenja obstoječo datoteko z novo. Po izbiri datoteke se ta naloži samodejno. |
| **Prenos** | Odpre dokument v novem zavihku brskalnika (PDF, DOCX itd.). |
| **Izbriši** | Trajno izbriše zapis in datoteko iz sistema. Dejanje je nepovratno. |

### Dodajanje novega dokumenta

Dokumente je priporočljivo generirati **samodejno iz ustreznih modulov** (npr. iz skupine usposabljanj ali delovne opreme s klikom na »Dodaj dokument«). Ročen prenos datoteke je prav tako možen prek funkcije »Dodaj dokument« v kontekstu stranke ali poslovne enote.

### Čiščenje starih različic

!!! info "Čiščenje starih datotek"
    Gumb **Čiščenje starih datotek** nad seznamom odstrani:

    - **starejše različice** dokumentov (ohrani se le zadnja različica za vsak tip in objekt),
    - **osirotele datoteke** (datoteke na disku brez zapisa v bazi), starejše od 24 ur.

    S čiščenjem ohranjate red in zmanjšujete porabo prostora na strežniku.

---

## Poročilo po dejavnosti

Poročilo združuje stranke in opravljene aktivnosti glede na šifro dejavnosti po klasifikaciji **SKD 2025**. Namenjeno je internim pregledom in poročilom o obsegu dela po panogah.

### Dostop

**Analitika → Poročilo po dejavnosti**

### Obrazec za iskanje

| Polje | Opis |
|-------|------|
| **Tip poročila** | Izberite **Delovna oprema** (pregledi) ali **Meritve delovnega okolja**. |
| **Leto** | Koledarsko leto, za katerega se podatki združijo. |

Kliknite **Najdi** za prikaz poročila.

### Rezultati

Tabela prikazuje vse šifre dejavnosti na **prvi ravni** (enoštevilčne kode SKD 2025):

| Stolpec | Opis |
|---------|------|
| **Koda dejavnosti** | Enoštevilčna koda SKD 2025 (npr. C – Predelovalne dejavnosti). |
| **Naziv dejavnosti** | Polno ime dejavnostne kategorije. |
| **Število strank** | Koliko strank v sistemu spada v to dejavnost. |
| **Pregledi / Potrdila** | *(Delovna oprema)* Število izvedenih pregledov in izdanih potrdil. |
| **Meritve toplotnih razmer** | *(Meritve)* Število opravljenih meritev toplotnih razmer. |
| **Meritve osvetljenosti** | *(Meritve)* Število opravljenih meritev osvetljenosti. |
| **Meritve hrupa** | *(Meritve)* Število opravljenih meritev hrupa. |

Na dnu tabele so prikazane **vsote** za vse dejavnosti skupaj.

!!! tip
    Poročilo po dejavnosti je koristno za letna interna poročila o obsegu dela in za pregled porazdelitve strank po panogah.

---

## Poročila za stranke

Zaslon združuje dve vrsti DOCX poročil za izbrano stranko:

- **Kartica stranke** – stanje na izbrani dan (snapshot).
- **Periodično poročilo** – letno, mesečno ali obdobno poročilo o opravljenih aktivnostih in veljavnostih.

### Dostop

**Analitika → Poročila za stranke**

Stari povezavi `/report/customercard` in `/report/custreport/index` se samodejno preusmerita na nov zaslon.

### Obrazec za izbiro

| Polje | Opis |
|-------|------|
| **Stranka** | Stranka, za katero se pripravi poročilo. |
| **Skrbnik** | Neobvezno omeji seznam strank na skrbnika. |
| **Vrsta poročila** | **Kartica stranke (na dan)** ali **Poročilo stranki (Period)**. |
| **Poslovna enota** | Neobvezno omeji poročilo na izbrano PE. |
| **Predloga za izpis** | Prikažejo se samo predloge, ki ustrezajo izbrani vrsti poročila. |
| **Na dan** | Samo kartica stranke; datum stanja, privzeto današnji dan. |
| **Vključi ostale evidence** | Samo kartica stranke; izberite kategorije evidenc, ki jih želite dodati. |
| **Period** | Samo periodično poročilo: **Letno**, **Mesečno** ali **Obdobje**. |
| **Leto / Mesec / Datum od–do** | Glede na izbrano obdobje. |

Po izbiri kliknite **Ustvari poročilo**. Datoteka DOCX se prenese na računalnik in se ne shrani v sistem.

### Kartica stranke (stanje na dan)

Kartica prikazuje stanje na datum **Na dan**:

- usposabljanja, katerih veljavnost na ta dan še traja,
- preglede delovne opreme in meritve, veljavne na ta dan,
- RASS skupine, VPP dokumente, VPP vaje evakuacije in ostale evidence (Recot), ki so bili izdani ali izvedeni na ta dan ali prej.

Pri RASS/VPP/Recot se upošteva datum evidence (`date_rep`, `date_test`, `date_create`), ne datum veljavnosti. Zato so v izpisu lahko tudi evidence, ki so na izbrani dan že potekle; njihov datum veljavnosti je viden v tabeli. Evidence brez datumskega snapshota (VPP odgovorne osebe) se v kartici ne izpišejo.

### Periodično poročilo

Periodično poročilo je namenjeno letnemu, mesečnemu ali obdobnemu pregledu opravljenih aktivnosti. Konec izbranega obdobja je hkrati mejnik za izračune:

- RASS, RASSL, VPP dokumenti in VPP vaje evakuacije se upoštevajo le, če so z datumom znotraj izbranega obdobja.
- Poročilo **Zapadla VZD/VPP usposabljanja** prikaže vse aktivne zaposlene po obratih. Upošteva najnovejše usposabljanje, katerega teoretični začetek in praktični del sta bila opravljena do konca obdobja; prihodnji tečaji se ne upoštevajo.
- `Rok usp. VZD/VPP` je prejšnji od datumov veljavnosti teoretičnega in praktičnega dela.

### Predloge

| Predloga | Vrsta | Namen |
|----------|-------|-------|
| `ccard` | Kartica stranke | Celovita kartica stranke: usposabljanja, oprema, meritve, RASS, VPP, Recot. |
| `zaposl opreme na dan` | Kartica stranke | Stanje naprav in zaposlenih na izbrani dan. |
| `letno por - bvd` | Periodično | Letno/periodično poročilo o opravljenih aktivnostih. |
| `sij-poskodbe`, `ostali-poskodbe` | Periodično | Poročilo o poškodbah pri delu. |
| `Zapadla delovna oprema po podjetjih` | Periodično | Pregled delovne opreme, ki zapade v izbranem obdobju. |
| `Zapadla VZD VPP usposabljanja` | Periodično | Pregled zapadlih VZD/VPP usposabljanj po zaposlenih in obratih. |

Natančna vsebina je odvisna od predloge; spremenljivke so opisane v [Legendi spremenljivk](variables-sl.md).
