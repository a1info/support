# Analitika

Modul Analitika omogoča pregled in analizo podatkov o veljavnostih, realizaciji opravljenih aktivnosti, izdanih dokumentih ter pripravo letnih poročil za stranke.

---

## 1. Periodika (Pregled veljavnosti)

Poročilo omogoča spremljanje veljavnosti različnih evidenc, kot so usposabljanja zaposlenih, pregledi delovne opreme, meritve delovnega okolja, požarna varnost, zdravniški pregledi in ostale evidence. Rezultati so prikazani v zavihkih z možnostjo iskanja, filtriranja, razvrščanja in izvoza v Excel.

### Dostop

- **Meni:** Analitika → Periodika

### Obrazec za iskanje

![Obrazec za iskanje periodike](img/analytics/validity-search.png)

| Polje | Opis |
|-------|------|
| **Tip iskanja** | Izberite enega ali več tipov veljavnosti (Usposabljanja, Delovna oprema, Tehnična varnost, Meritve, Požarna varnost, Zdravniški pregledi, Ostale evidence). Gumb prikaže barvne značke za izbrane tipe. |
| **Obdobje** | Izberite časovno obdobje, ki se uporabi za filtriranje datumov poteka veljavnosti. |
| **Vključi poteklo** | Če je označeno, so v rezultatih prikazani tudi že potekli zapisi. |
| **Poslovna enota** | Filter po poslovni enoti izbrane stranke (prikaže se, ko je aktivna stranka). |
| **Skrbnik** | Filter po uporabniku sistema, ki je zapis ustvaril ali nazadnje urejal. |
| **Tip stranke** | Kadar ni aktivne stranke, lahko filtrirate po tipu stranke. |

Po nastavitvi kriterijev kliknite **Najdi**.

### Prikaz rezultatov

Rezultati so prikazani v zavihkih glede na izbrane tipe veljavnosti. Vsak zavihek vsebuje tabelo z ustreznimi podatki, polje za hitro iskanje, filter tipa, možnost razvrščanja in stranjenje.

![Zavihki rezultatov](img/analytics/validity-tabs.png)

#### Skupne funkcije

- **Hitro iskanje** – vpis v iskalno polje filtrira vrstice znotraj trenutne tabele.
- **Filter tipa** – spustni seznam omogoča filtriranje po podtipu (npr. tip tečaja, kategorija opreme).
- **Razvrščanje** – klik na glavo stolpca razvrsti podatke naraščajoče/padajoče.
- **Izvozi v Excel** – klik na ikono Excela odpre pogovorno okno za izbiro stolpcev, ki jih želite vključiti v izvoz. Po potrditvi se datoteka prenese.
- **Stranjenje** – s pomočjo številk na dnu tabele se pomikate med stranmi.

#### Zavihki po tipih

| Zavihek | Vsebina |
|---------|--------|
| **Usposabljanja** | Seznam zaposlenih z usposabljanji, datumom usposabljanja, datumom poteka, poslovno enoto itd. |
| **Delovna oprema** | Pregledi delovne opreme z nazivom opreme, serijsko številko, datumom pregleda in potekom. |
| **Tehnična varnost** | Pregledi opreme tehnične varnosti. |
| **Meritve** | Meritve delovnega okolja, hrupa, elektrike, pretoka zraka itd. |
| **Zdravniški pregledi** | Evidence zdravniških pregledov zaposlenih. |
| **Ostale evidence** | Druge evidence (npr. oddaja osebne varovalne opreme). |
| **Požarna varnost** | Združen zavihek, ki vsebuje podzavihke za sisteme APZ, gasilnike, hidrante, strelovode, kurilne naprave in vaje evakuacije. Vsak podtip ima svojo tabelo z ustreznimi filtri in iskanjem. |

Potekli zapisi so označeni z rdečo barvo v stolpcu **Datum poteka**.

### Koledarski pogled

Kliknite gumb s koledarjem v zgornjem desnem kotu obrazca za prikaz/kritje koledarja. Koledar prikazuje periodične naloge (npr. predvidene preglede) kot barvno označene dogodke. S klikom na ikono informacij se odpre meni z opisom dogodka in možnostjo ustvarjanja nove naloge.

Koledarski pogled lahko izvozite v format ICS z gumbom **ICS**.

---

## 2. Pregled realizacije

Poročilo prikazuje število opravljenih aktivnosti (usposabljanja, pregledi delovne opreme, meritve, pregledi požarne varnosti) v izbranem obdobju, združeno po strankah in uporabnikih.

### Dostop

- **Meni:** Analitika → Pregled realizacije

### Obrazec za iskanje

| Polje | Opis |
|-------|------|
| **Datum od** | Začetni datum obdobja. |
| **Datum do** | Končni datum obdobja. |
| **Stranka** | Izberite določeno stranko (neobvezno). |
| **Uporabnik** | Izberite uporabnika sistema, ki je aktivnost izvedel (neobvezno). |

Kliknite **Najdi** za prikaz poročila.

### Rezultati

- **Stolpčni diagram** – prikaže skupno število aktivnosti po kategorijah (usposabljanja, delovna oprema, meritve, VPP gasilniki, VPP APZ). Diagram se posodobi samodejno po vsakem iskanju.
- **Tabele** – pod diagramom so prikazane tabele z dejanskimi zapisi za vsako kategorijo, vključno s stranko, tipom, datumom, veljavnostjo in uporabnikom.

Poročilo je prijazno tiskanju – uporabite gumb **Natisni** za izpis.

---

## 3. Izdani dokumenti

Upravljanje dokumentov, izdanih za stranke (zapisniki, potrdila, poročila). Omogoča iskanje, ogled, nalaganje novih različic in brisanje dokumentov.

### Dostop

- **Meni:** Analitika → Izdani dokumenti

### Obrazec za iskanje

| Polje | Opis |
|-------|------|
| **Tip dokumenta** | Filter po vrsti dokumenta (meritve, delovna oprema, usposabljanja, požarna varnost ipd.). |
| **Št. zapisnika** | Iskanje po številki zapisnika. |
| **Datum od / Datum do** | Omejitev na dokumente, izdane v določenem obdobju. |
| **Ime in priimek zaposlenega** | Iskanje po imenu zaposlenega, če je dokument povezan z osebo. |

Kliknite **Najdi** za prikaz dokumentov.

### Seznam dokumentov

Seznam vsebuje:

- Stranka
- Tip dokumenta
- Datum dokumenta
- Datum shranitve
- Številka zapisnika
- Ime datoteke
- Uporabnik, ki je dokument ustvaril

#### Akcije na dokumentu

| Akcija | Opis |
|--------|------|
| **Nova različica** | Zamenja obstoječo datoteko z novo. Po izbiri datoteke se ta samodejno naloži. |
| **Prenos** | Odpre dokument v novem zavihku. |
| **Izbriši** | Trajno izbriše zapis in datoteko. |

### Dodajanje novega dokumenta

Dokumente je mogoče generirati samodejno iz različnih modulov (npr. iz skupine usposabljanj ali skupine delovne opreme) s klikom na gumb “Dodaj dokument” znotraj modula. Ročen prenos datoteke je prav tako možen prek funkcije “Dodaj dokument” v kontekstu stranke ali poslovne enote.

### Čiščenje starih različic

Nad seznamom dokumentov je gumb **Čiščenje starih datotek**. Ob kliku se odstranijo starejše različice (ohrani se le zadnja različica za posamezen tip in objekt) in tudi osirotele datoteke (datoteke, ki niso več v bazi) starejše od 24 ur. S tem se ohranja prostor na disku.

---

## 4. Poročilo po dejavnosti

Poročilo združuje stranke in opravljene aktivnosti glede na šifro dejavnosti (SKD 2025). Prikazuje število strank v posamezni dejavnosti in število opravljenih pregledov oziroma meritev v izbranem letu.

### Dostop

- **Meni:** Analitika → Poročilo po dejavnosti

### Obrazec za iskanje

| Polje | Opis |
|-------|------|
| **Tip poročila** | Izberite med **Delovna oprema** (pregledi delovne opreme) ali **Meritve delovnega okolja**. |
| **Leto** | Koledarsko leto, za katerega želite združiti podatke. |

Kliknite **Najdi** za prikaz poročila.

### Rezultati

Tabela vsebuje vse šifre dejavnosti na prvi ravni (enoštevilčne kode) z naslednjimi stolpci:

- Koda dejavnosti
- Naziv dejavnosti
- Število strank v tej dejavnosti
- Glede na izbran tip poročila:
  - **Delovna oprema**: število pregledov, število potrdil
  - **Meritve delovnega okolja**: število meritev toplotnih razmer, število meritev osvetljenosti, število meritev hrupa

Na dnu tabele so prikazana skupna števila za vse dejavnosti.

---

## 5. Letno poročilo za stranko

Omogoča generiranje prilagojenega Wordovega dokumenta (DOCX) z letnim povzetkom vseh aktivnosti za izbrano stranko. Poročilo vključuje preglede, usposabljanja, meritve, požarno varnost in ocene tveganj, združene po poslovnih enotah.

### Dostop

- **Meni:** Analitika → Letno poročilo za stranko

### Obrazec za iskanje

| Polje | Opis |
|-------|------|
| **Stranka** | Izberite stranko, za katero želite poročilo. |
| **Leto** | Leto, za katerega se podatki združijo. |
| **Poslovna enota** | Neobvezen filter za določeno poslovno enoto stranke. |
| **Predloga za izpis** | Izberite vnaprej pripravljeno Wordovo predlogo, ki določa strukturo in vsebino poročila. |

Kliknite **Ustvari poročilo**. Datoteka se samodejno prenese; ne shrani se v sistem.

### Vsebina poročila

Generirani dokument vsebuje:

- Podatke o stranki (naziv, naslov, kontaktna oseba, davčna številka, matična številka, šifra dejavnosti)
- Usposabljanja v izbranem letu s številom udeležencev, datumom, številko zapisnika, lokacijo in tipom
- Preglede delovne opreme (skupine) s številom kosov opreme, datumom, številko zapisnika, lokacijo in tipom pregleda
- Meritve (okolje, elektrika itd.) z veljavnostjo, številko zapisnika, lokacijo in tipom meritve
- Ocene tveganj (skupine RASS)
- Dokumente požarne varnosti (VPP) in vaje evakuacije
- Informacije o prihodnjih potekih v naslednjem letu (če predloga to podpira)

Natančna postavitev in izbrani podatki so odvisni od uporabljene predloge.