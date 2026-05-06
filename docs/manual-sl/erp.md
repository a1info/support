# ERP (Upravljanje ponudb, pogodb in storitev)

Modul **ERP** je namenjen centraliziranemu vodenju prodajnih aktivnosti. Omogoča enostavno upravljanje šifranta storitev, pripravo in izdajanje ponudb ter vodenje dolgoročnih pogodb s strankami.

---

## Pregled modula

ERP modul združuje tri glavne sklope, ki med seboj sodelujejo za hitro in učinkovito pripravo prodajne dokumentacije:

- **Storitve (Šifrant):** Osnovna baza vaših produktov in storitev.
- **Ponudbe:** Priprava ponudb za stranke z možnostjo izvoza v Word (Docx) dokumente.
- **Pogodbe:** Evidenca naročniških razmerij in dogovorov z možnostjo shranjevanja priponk (npr. skeniranih pogodb).

### Dostop

**Glavni meni → ERP**

---

## Storitve (Šifrant)

Preden začnete z ustvarjanjem ponudb in pogodb, je priporočljivo urediti šifrant storitev. To omogoča hitro dodajanje postavk na dokumente brez ročnega vpisovanja cen.

### Dodajanje in urejanje storitve

Pri vsaki storitvi lahko določite naslednje parametre:

| Polje | Opis |
|-------|------|
| **Naziv** | Ime storitve ali produkta (obvezno polje). |
| **Koda / Zunanja koda** | Interna šifra storitve ali šifra iz vašega računovodskega programa. |
| **Cena in Davek** | Osnovna neto cena in stopnja davka. |
| **Merska enota** | Enota mere (npr. kos, ura, km, pavšal). |
| **Status (Aktivno)** | Če storitev ni več aktualna, jo lahko deaktivirate. Neaktivne storitve se ne prikazujejo pri izdelavi novih ponudb. |

!!! tip "Hitro dodajanje"
    Ko storitev dodate v šifrant z določeno ceno, se bo ob izbiri te storitve na ponudbi ali pogodbi cena **samodejno izpolnila**.

---

## Ponudbe (Offers)

Sistem omogoča hitro pripravo ponudb za obstoječe stranke. 

### Ustvarjanje ponudbe

Ponudba je sestavljena iz osnovnih podatkov in seznama storitev (postavk).

| Podatek | Opis |
|---------|------|
| **Številka ponudbe** | Sistem samodejno predlaga številko (npr. `PON-2024...`), ki pa jo lahko ročno spremenite. |
| **Stranka** | Izbira naročnika iz baze strank. |
| **Datumi** | Datum izdaje in datum veljavnosti ponudbe. |
| **Opombe** | Poljuben tekst, ki se lahko prikaže na dnu ponudbe. |

#### Postavke ponudbe
Na ponudbo dodajate storitve iz šifranta. Za vsako postavko lahko prilagodite:
- **Količino**
- **Ceno** (sistem predlaga ceno iz šifranta, a jo lahko povozite)
- **Popust (%)** 

### Statusi ponudb

Ponudbam lahko spreminjate statuse, kar vam omogoča pregled nad uspešnostjo prodaje:

| Status | Pomen |
|--------|-------|
| **Osnutek** | Ponudba je v pripravi in še ni bila poslana stranki. |
| **Poslano** | Ponudba je poslana stranki, čaka se odziv. |
| **Potrjeno** | Stranka je ponudbo sprejela. |
| **Zavrnjeno** | Stranka je ponudbo zavrnila. |

!!! info "Izvoz v Word (Docx)"
    Na seznamu ponudb boste opazili ikono za **Word (Docx)**. Sistem omogoča generiranje ponudbe neposredno v Wordov dokument na podlagi predpripravljenih predlog (Templates). To vam omogoča, da ponudbo pred pošiljanjem še grafično ali vsebinsko prilagodite.

---

## Pogodbe (Contracts)

Modul za pogodbe je namenjen vodenju dolgoročnih ali pavšalnih dogovorov s strankami.

### Podatki o pogodbi

Poleg izbire stranke in postavk storitev (ki delujejo enako kot pri ponudbah), imajo pogodbe nekaj specifičnih polj:

| Polje | Opis |
|-------|------|
| **Naziv** | Ime ali predmet pogodbe (npr. "Vzdrževanje opreme 2024"). |
| **Šifra po meri** | Številka pogodbe iz fizičnega arhiva ali zunanjega sistema. |
| **Obdobje (Zarčunavanje)** | Kako pogosto se storitev izvaja/zaračunava (**Mesečno, Letno, Ostalo**). |
| **Datum Od - Do** | Časovni okvir veljavnosti pogodbe. |

### Statusi pogodb

| Status | Pomen |
|--------|-------|
| **Aktivno** | Pogodba je trenutno v izvajanju. |
| **Blokirano** | Izvajanje pogodbe je začasno zaustavljeno (npr. neplačila). |
| **Zaključeno** | Pogodba je potekla ali bila prekinjena. |

### Upravljanje z datotekami (Priponke)

Za razliko od ponudb, modul za pogodbe vključuje **napreden sistem za upravljanje z datotekami**. 

Pri vsaki pogodbi lahko naložite poljubno število datotek (do velikosti 20MB na datoteko). Sistem podpira hkratno nalaganje več datotek naenkrat.

!!! tip "Digitalni arhiv"
    Priporočamo, da po podpisu fizične pogodbe s stranko, dokument skenirate (PDF) in ga naložite pod priponke te pogodbe v sistemu. Tako imate celoten arhiv vedno dostopen z enim klikom na seznamu pogodb (ikona sponke 📎).