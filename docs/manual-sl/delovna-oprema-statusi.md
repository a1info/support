# Statusi delovne opreme in poročila

Ta stran opisuje nov sistem statusov delovne opreme (DA / NE / V popravilu / Pogrešano),
prikaz statusov v evidencah in poročilih ter spremenljivke za generiranje zapisnikov,
mesečnega poročila (PDF) in Excel izvoza.

---

## Statusi pregleda opreme

Status se določi **ob pregledu** opreme (obrazec *Pregled delovne opreme* → polje **Stanje**)
in se shrani v `mdevice.status`.

| Vrednost v bazi | Status | Pomen | Veljavnost | Potrdilo |
|-----------------|--------|-------|-----------|----------|
| `pass` | **Ustreza** | Oprema pregledana in ustrezna. | da (meseci veljavnosti) | **da** |
| `fail` | **Ne ustreza** | Oprema pregledana, ugotovljene neskladnosti. | ne | ne (samo zapisnik) |
| `repair` | **V popravilu / okvari** | Začasno izločena iz uporabe, ostaja last podjetja. | ne | ne (samo zapisnik) |
| `missing` | **Pogrešano** | Opreme ni bilo mogoče najti na lokaciji. | ne | ne (samo zapisnik) |

**Pomembno pravilo:** status **ne** vpliva na prisotnost opreme v evidenci.
Oprema se iz evidence izloči **samo** z datumom odpisa (`mdeviceobj.date_decom`).
Oprema s statusom NE, V popravilu ali Pogrešano tako ostane vidna v aktivnem seznamu
in se upošteva v skupnem številu opreme.

### Tehnična izvedba

- `mdevice.status` – vrednost statusa (`pass`, `fail`, `repair`, `missing`).
- `mdevice.ind_pass` – izpeljan zapis (1 samo za `pass`); ohranjen zaradi združljivosti.
- `mdevice.date_valid` in `mdevice.mnt_valid` – izračunata se **samo** pri statusu `pass`
  (datum pregleda + meseci veljavnosti); pri ostalih statusih je veljavnost prazna.
- Stari zapisi so bili dopolnjeni z migracijo (backfill `pass`/`fail` iz `ind_pass`).

---

## Prikaz statusov

### Evidenca delovne opreme
Seznam delovne opreme ima stolpec **Stanje** (barvna značka): zelena *Ustreza*,
rdeča *Ne ustreza*, rumena *V popravilu / okvari*, siva *Pogrešano*. Prikaže se status
zadnjega pregleda posameznega kosa.

### Pregled realizacije (report/dashboard)
- Tabela **Delovna oprema**: stolpca **Datum veljavnosti** in **Stanje**.
- Na dnu tabele Delovna oprema je povzetek **stanja opreme** po stranki:
  `Skupaj | Ustreza | Ne ustreza | V popravilu / okvari | Pogrešano`.
- Tabela **Usposabljanje**: stolpec **Datum veljavnosti** (izračunan iz začetka tečaja
  in mesecev veljavnosti).
- Tabela **Zdravniški pregledi**: stolpec **Datum veljavnosti** (`recmedic.date_valid`).

### Mesečno poročilo (PDF)
PDF (predloga `pdfgen.monthreport`) vsebuje enake informacije:

- Sekcija **Delovna oprema** s stolpcema Datum veljavnosti in Stanje ter povzetkom
  stanja v nogi tabele.
- Sekcija **Zdravniški pregledi** s stolpcem Datum veljavnosti.
- Sekcija **Usposabljanje** z glavo stolpcev *Zaposleni | Del. mesto | Uspešno* in
  podatkom *Datum veljavnosti* v vrstici tečaja.
- Naslovi sekcij (h2) so temno modri z belim besedilom; vrstice glave tabel (`th`)
  so svetlo sive.

### Excel izvoz
Excel izvoz (*Pregled realizacije* → Excel) vsebuje zavihke:

- **Povzetek** (po strankah), **Tečaji** (z Datumom veljavnosti), **Udeleženci**,
  **Delovna oprema** (Datum veljavnosti, Stanje in povzetek stanja na dnu),
  **Eko meritve**, **Zdravniški pregledi** (Datum veljavnosti), **Delovne nezgode**.

---

## Generiranje zapisnikov in potrdil (`GendevController`)

Zapisnike in potrdila delovne opreme generira
`App\Http\Controllers\Report\GendevController`, metoda `repDevGen($id, $idTpl, $returnFile)`.
Uporablja DOCX predloge (`repoffice`, tip `devi`) in knjižnico PhpWord (`TemplateProcessor`).
Če `idTpl` ni podan, se uporabi privzeta predloga tipa `devi`.

### Skupne spremenljivke predloge

| Spremenljivka | Vsebina |
|---------------|---------|
| `sysName`, `sysAddress`, `sysCity` | Podatki podjetja (tabela `system`). |
| `cName`, `cAddress`, `cZip`, `cCity`, `cBusCode`, `cBusCodeName`, `cTax` | Podatki stranke. |
| `locName`, `locAddress`, `locZip`, `locCity` | Podatki poslovne enote. |
| `cContact`, `locContact` | Kontaktni osebi stranke / PE. |
| `uName`, `expTitle`, `acron`, `creatorName`, `uCity`, `uSignImg` | Podatki preglednika (podpis). |
| `uCertEdu`, `uCertDev`, `uCertMes` | Certifikati preglednika. |
| `nrRep`, `custNrRep`, `3NcustNrRep`, `4NcustNrRep`, `5NcustNrRep` | Številka zapisnika (navadna / dopolnjena na 3, 4, 5 mest). |
| `dateRep`, `repy`, `repY`, `repM` | Datum zapisnika (letnica, mesec). |
| `dateLastRep`, `nrLastRep` | Datum in št. zadnjega predhodnega zapisnika stranke. |
| `infoLast`, `txtType`, `result`, `desc` | Polja zapisnika (tip pregleda, rezultat, opis). |
| `dateTest`, `devUser`, `devUserAddr` | Datum pregleda in uporabnik opreme (iz prvega kosa). |

### Vrstice instrumentov in izvajalcev

- `rowInstName#n`, `rowInstCert#n` (cloneRow `rowInstName`) – merilni instrumenti.
- `rowPerfCnt#n`, `rowPerfUser#n`, `rowPerfStart#n`, `rowPerfEnd#n`, `rowPerfDur#n`
  (cloneRow `rowPerfUser`) – izvajalci pregleda.

### Kratki seznam opreme (cloneRow `rowShortName`)

`rowShortCnt`, `rowShortName`, `rowShortSerial`, `rowShortNrInv`, `rowShortManufacturer`,
`rowShortManufactYear`, `rowShortTypeDevice`, `rowShortLocation`, `rowShortResult`,
`rowShortPass`, `rowShortStatus`, `rowShortNote`, `rowShortDesc`.

Obstaja tudi različica z neustreznimi kosi na vrhu: `rowShortNameFailFirst` z enakimi
spremenljivkami s pripono `FailFirst`.

### Polni seznam opreme (cloneBlock `cloneDevLst0`)

`lstName`, `lstNrCnt`, `lstNrRep`, `lstDateTest`, `lstSerial`, `lstNrInv`,
`lstInternalCode`, `lstTypeDevice`, `lstPersResp`, `lstLocation`, `lstLocationObj`,
`lstDesc`, `lstResult`, `lstDoc`, `lstIndPass`, `lstStatus`, `lstManufacturer`, `lstManufactYear`,
`lstKW`, `lstMesOhm`, `lstMesVolt`.

Preizkusi: `lstChkName#j`, `lstChkResult#j`, `lstChkValue#j`, `lstChkSist#j` ter
elektro preizkusi `lstChkElecName#j`, `lstChkElecResult#j`, `lstChkElecValue#j`,
`lstChkElecSist#j`.

### Vrednosti statusov v zapisniku

- `rowShortStatus`, `lstStatus` → kratke oznake **DA / NE / V POPRAVILU / POGREŠANO**.
- `rowShortResult` → rezultat pregleda (Uspešno / Neuspešno — iz `ind_pass`).
- `rowShortPass` → Ustreza (Da / Ne — iz `ind_pass`).
- `rowShortNote` → vpisan rezultat; če je prazen, se za statusa `repair` in `missing`
  samodejno vpiše opomba:
  - *Stroj je v okvari / na popravilu – potrdilo ni izdano.* (`mdevice.noteRepair`)
  - *Stroj ni bil najden na lokaciji – potrdilo ni izdano.* (`mdevice.noteMissing`)

### Potrdila (cloneBlock `cloneCert0`)

Blok potrdil se izpolni **samo za kose s statusom `pass`**. Kosi s statusi NE,
V popravilu in Pogrešano se na potrdilih **ne** pojavijo.

Spremenljivke: `devName`, `devNrCnt`, `devNrRep`, `devNrRep2`, `devDateTest`,
`devDateValid`, `devDateLast`, `devMntValid`, `devSerial`, `devNrInv`,
`devInternalCode`, `devTypeDevice`, `devDesc`, `devDevUser`, `devDevUserAddr`,
`devPersResp`, `devResult`, `devUsage`, `devDoc`, `devManufacturer`,
`devManufactYear`, `devLocation`, `devMesOhm`, `devMesVolt`.

---

## Mesečno poročilo – stanje opreme (`RealizationData`)

Podatke za Pregled realizacije in PDF pripravi `App\Services\Report\RealizationData::get($f)`.
Za vsako stranko izračuna stanje opreme v `$devState`:

```
$devState[] = ['customer_id', 'cname', 'total', 'da', 'ne', 'repair', 'missing']
```

- `total` = število aktivnih kosov (`mdeviceobj.date_decom IS NULL`) stranke.
- `da`/`ne`/`repair`/`missing` = porazdelitev po statusu **zadnjega pregleda** posameznega kosa (vrednosti v bazi: `pass`/`fail`/`repair`/`missing`).
- Upoštevajo se filtri stranke, poslovne enote in oddelka.
- V PDF predlogi je na voljo preslikava oznak `$stLblPdf`
  (`pass`, `fail`, `repair`, `missing` → lokalizirana besedila).

## Jezikovni ključi

| Ključ | Besedilo (sl) |
|-------|----------------|
| `mdevice.stDa` | Ustreza |
| `mdevice.stNe` | Ne ustreza |
| `mdevice.stRepair` | V popravilu / okvari |
| `mdevice.stMissing` | Pogrešano |
| `mdevice.eqState` | Delovna oprema – stanje |
| `mdevice.state` | Stanje |
| `mdevice.noteRepair` | Stroj je v okvari / na popravilu – potrdilo ni izdano. |
| `mdevice.noteMissing` | Stroj ni bil najden na lokaciji – potrdilo ni izdano. |
| `gen.dateValid` | Datum veljavnosti |
| `gen.persons` | Osebe |

## Veljavnost pri drugih tipih pregledov

- **Zdravniški pregledi** (`recmedic.date_valid`): ob shranjevanju se samodejno
  izračuna iz datuma pregleda in mesecev veljavnosti, če ni vpisan ročno.
  Stari zapisi so dopolnjeni z migracijo.
- **Usposabljanje** (`educourse`): shranjene vrednosti `date_valid` ni; datum
  veljavnosti se prikaže kot izračun (`date_start` + `mnt_valid` mesecev).
- **Delovna oprema** (`mdevice.date_valid`): izračunana ob shranjevanju pregleda,
  samo za status `da`.
