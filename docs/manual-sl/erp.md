# ERP (Upravljanje ponudb, pogodb in storitev)

Modul **ERP** je namenjen centraliziranemu vodenju prodajnih aktivnosti. Omogoča upravljanje šifranta storitev, pripravo in izdajanje ponudb, vodenje dolgoročnih pogodb s strankami ter spremljanje obračunskih obdobij.

---

## Pregled modula

ERP modul združuje naslednje sklope, ki med seboj sodelujejo pri pripravi prodajne dokumentacije:

- **Storitve (šifrant):** osnovna baza storitev in produktov.
- **Cenik po strankah:** posebne cene in popusti storitev za posamezne stranke.
- **Ponudbe:** priprava ponudb z izvozom v Word (Docx) in Excel.
- **Pogodbe:** evidenca naročniških razmerij z obračunskimi obdobji, priponkami ter izvozom v Word (Docx) in Excel.

### Dostop in pravice

**Glavni meni → ERP**

Vidnost posameznih sklopov modula je odvisna od dodeljenih pravic:

| Pravica | Sklop |
|---------|-------|
| `view_erp_service` / `manage_erp_service` | Storitve (šifrant) |
| `view_erp_offer` / `manage_erp_offer` | Ponudbe in cenik po strankah |
| `view_erp_contract` / `manage_erp_contract` | Pogodbe |

Pravice se dodeljujejo prek vlog uporabnikov (glejte poglavje *Uporabniki in pravice*). Modul ERP je vključen v licenčna paketa **1** in **9** (glejte poglavje *Sistemske nastavitve*).

---

## Storitve (Šifrant)

Preden začnete z ustvarjanjem ponudb in pogodb, uredite šifrant storitev. To omogoča hitro dodajanje postavk na dokumente brez ročnega vpisovanja cen.

### Dodajanje in urejanje storitve

| Polje | Opis |
|-------|------|
| **Naziv** | Ime storitve ali produkta (obvezno polje). |
| **Koda / Zunanja koda** | Interna šifra storitve ali šifra iz vašega računovodskega programa. |
| **Cena in davek** | Osnovna neto cena in stopnja davka (%). |
| **Merska enota** | Enota mere (npr. kos, ura, km, pavšal). |
| **Tip storitve** | Poljubna kategorizacija storitev. |
| **Status (Aktivno)** | Neaktivne storitve se ne prikazujejo pri izdelavi novih ponudb in pogodb. |

!!! tip "Hitro dodajanje"
    Ko storitev dodate v šifrant s ceno, se ob izbiri storitve na ponudbi ali pogodbi **cena samodejno izpolni**. Če za izbrano stranko obstaja zapis v **ceniku po strankah**, ima ta prednost pred ceno iz šifranta.

---

## Ponudbe (Offers)

### Ustvarjanje ponudbe

| Podatek | Opis |
|---------|------|
| **Številka ponudbe** | Sistem samodejno predlaga številko v obliki `PON-LLLL-NNNNN` (npr. `PON-2026-00001`) iz sistema številčenja; številko lahko ročno spremenite. |
| **Stranka** | Izbira naročnika iz baze strank. |
| **Posl. enota** | Izbrana poslovna enota stranke (uporabi se tudi na Word dokumentu). |
| **Datumi** | Datum izdaje in datum veljavnosti ponudbe. |
| **Opombe** | Poljuben tekst, ki se prikaže na dnu ponudbe. |

### Postavke ponudbe

Na ponudbo dodajate storitve iz šifranta. Za vsako postavko lahko določite:

- **Storitev** – izbira iz šifranta (obvezen podatek).
- **Naziv (po meri)** – po želji povozite naziv storitve na dokumentu.
- **Objekt dela** – povezava postavke na konkretno izvedeno delo stranke (delovno mesto, zapisnik delovne opreme, zapisnik varnostne opreme, izobraževanje, dokument OTV ali požarna varnost). Ob spremembi stranke se izbrani objekti počistijo, saj pripadajo prejšnji stranki.
- **Količina** – obvezno polje.
- **Cena** – sistem predlaga ceno (šifrant ali cenik stranke), lahko jo povozite.
- **Popust (%)** – popust v odstotkih.
- **DDV (%)** – stopnja davka; ob izbiri storitve se predlaga iz šifranta.

Pod tabelo postavk sistem sproti izračunava **Skupaj brez DDV**, **DDV** in **Skupaj z DDV**.

### Statusi ponudb

Status ponudbe spreminjate z gumbi ob trenutnem statusu. Sistem dovoljuje le predpisane prehode:

| Status | Možni prehodi | Pomen |
|--------|---------------|-------|
| **Osnutek** | → Poslano | Ponudba je v pripravi. |
| **Poslano** | → Sprejeto, Zavrnjeno, nazaj v Osnutek | Ponudba je poslana stranki. |
| **Sprejeto** | (končni status) | Stranka je ponudbo sprejela. |
| **Zavrnjeno** | → nazaj v Osnutek | Ponudba je zavrnjena; za ponovno oddajo jo vrnite v osnutek. |

### Izvoz ponudbe

- **Word (Docx):** na seznamu ponudb izberite ikono Word in predlogo dokumenta. Sistem pripravi Word dokument na podlagi predlog (glejte poglavje *Urejanje predlog*); izpisani dokumenti se zabeležijo v evidenci izdanih dokumentov.
- **Excel:** z zelenim gumbom na seznamu izvozite seznam ponudb (številka, stranka, poslovna enota, datumi, status ter izračunani zneski).

### Dokumentni tok

Ponudbe lahko vključite v **dokumentni tok potrjevanja** (pošiljanje v potrditev, potrjevanje, zavrnitev, vrnitev v popravek). Možnost se prikaže, ko ima stranka nastavljen potek za modul ERP – glejte poglavje *Dokumentni tok in potrjevanje*.

---

## Pogodbe (Contracts)

### Podatki o pogodbi

| Polje | Opis |
|-------|------|
| **Številka** | Sistem predlaga številko v obliki `POG-LLLL-NNNNN` (npr. `POG-2026-00001`); lahko jo spremenite. |
| **Stranka / Posl. enota** | Naročnik in izbrana poslovna enota. |
| **Naziv** | Ime ali predmet pogodbe (obvezno polje). |
| **Obdobje (obračunski cikel)** | Kako pogosto se storitev izvaja/zaračunava: **Mesečno, Letno, Ostalo**. |
| **Datum od – do** | Časovni okvir veljavnosti pogodbe. |
| **Šifra po meri** | Številka pogodbe iz fizičnega arhiva ali zunanjega sistema. |
| **Opombe** | Poljubno besedilo. |

### Statusi pogodb

| Status | Možni prehodi | Pomen |
|--------|---------------|-------|
| **Aktivno** | → Pavzirano, Zaključeno | Pogodba je v izvajanju. |
| **Pavzirano** | → Aktivno, Zaključeno | Izvajanje je začasno zaustavljeno. |
| **Zaključeno** | → Aktivno | Pogodba je potekla ali prekinjena; po potrebi jo ponovno aktivirate. |

### Postavke pogodbe

Postavke delujejo enako kot pri ponudbah: izbira storitve, **objekt dela**, količina, cena in popust. Cena se predlaga iz šifranta oziroma cenika stranke. Pod tabelo se izpiše **Skupaj**.

### Obračunska obdobja

Vsaki pogodbi lahko dodate **obračunska obdobja** za spremljanje zaračunavanja:

| Polje | Opis |
|-------|------|
| **Obdobje** | Oznaka obdobja (npr. `2026-10`). |
| **Znesek (€)** | Znesek za obdobje. |
| **Status** | **Odprto**, **Fakturirano** ali **Plačano**. |

Na seznamu pogodb se pri vsaki pogodbi izpiše seštevek **odprtih** (še nefakturiranih) zneskov.

### Upravljanje z datotekami (priponke)

Pri vsaki pogodbi lahko naložite poljubno število datotek (do 20 MB na datoteko) in jih tudi izbrišete neposredno v obrazcu. Ob brisanju pogodbe se datoteke izbrišejo iz sistema.

!!! tip "Digitalni arhiv"
    Po podpisu fizične pogodbe dokument skenirajte (PDF) in ga naložite med priponke pogodbe – arhiv bo vedno dostopen z enim klikom na seznamu pogodb (ikona sponke).

### Izvoz pogodbe

- **Word (Docx):** na seznamu pogodb izberite ikono Word in predlogo. Sistem pripravi Word dokument na podlagi predlog ter ga zabeleži v evidenco izdanih dokumentov.
- **Excel:** z zelenim gumbom izvozite seznam pogodb (številka, naziv, stranka, poslovna enota, datumi, cikel, status, zunanja koda, skupaj in odprto za obračun).

### Dokumentni tok

Tudi pogodbe lahko vključite v dokumentni tok potrjevanja (enako kot ponudbe).

---

## Cenik po strankah {: #cenik }

**Glavni meni → ERP → Cenik po strankah**

Cenik omogoča, da za posamezno stranko določite **posebno ceno in popust** za storitev:

- **Dodajanje:** izberite stranko in storitev ter vnesite ceno in popust.
- **Urejanje:** z ikono svinčnika spremenite obstoječi zapis.
- **Brisanje:** z ikono koša odstranite zapis.

Cena iz cenika se **samodejno uporabi** ob izbiri storitve na ponudbi ali pogodbi za to stranko, prav tako pa se postavke preravnajo ob spremembi stranke na dokumentu.

---

## Nastavitve

- **Številčenje:** zaporedne številke ponudb in pogodb se upravljajo v *Sistemu številčenja* (vrsti **ERP Ponudbe** in **ERP Pogodbe**). Določite lahko začetno številko in številčenje po letih.
- **Word predloge:** predloge za ponudbe in pogodbe pripravite v *Urejanje predlog* (vrsta predloge `offer` oziroma `contract`); razpoložljive spremenljivke so opisane v poglavju *Legenda spremenljivk*.
- **Dokumentni tok:** potek potrjevanja za posamezno stranko nastavite na strani *Dokumentni tok* (modul `ERP`).
- **Pravice:** dostop do sklopov modula se ureja prek vlog uporabnikov (pravice `view_erp_*` / `manage_erp_*`).
