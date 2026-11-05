# Legenda spremenljivk (DOCX/FORM)

Ta stran združuje vse skupne (generične) spremenljivke in spremenljivke po tipih poročil/predlog, kot jih uporabljajo kontrolerji in podloge v sistemu Optima Prevent.

Oznake:
- Posamezne (single): enovrednostne spremenljivke.
- Tabele (rows): vrstične spremenljivke za uporabo z `cloneRow('...')`.
- Bloki (clone): ponavljajoči se odseki med `${block}` in `${/block}` (lahko vsebujejo tudi tabelarne spremenljivke).

[← Nazaj na dokumentacijo](../index.md)

---

## Skupne (generične) spremenljivke

Posamezne — podjetje (glava dokumenta):

- `${sysName}` Naziv podjetja
- `${sysRegNr}` Registrska (matična) številka podjetja
- `${sysAddress}` Naslov podjetja
- `${sysZip}` Poštna številka podjetja
- `${sysCity}` Mesto podjetja
- `${sysEmail}` E-pošta podjetja
- `${sysWeb}` Spletna stran podjetja
- `${sysLogo}` Logotip podjetja (slika)

!!! info "Vir podatkov o podjetju"
    Naziv, naslov in registrsko številko sistem prebere iz vrstice stranke s kategorijo **OWN** (lastno podjetje); logotip, e-pošta in spletna stran pa so iz *Sistemskih nastavitev → Podjetje*.

Posamezne:

- `${cName}` Ime stranke
- `${cNameFull}` Polno ime stranke
- `${cAddress}` Naslov sedeža
- `${cCity}` Mesto sedeža
- `${cZip}` Poštna št. sedeža
- `${cTax}` Davčna številka stranke
- `${cTaxNr}` Davčna številka (alternativna oznaka v nekaterih predlogah)
- `${cRegId}` Registrska številka
- `${cBusCode}` Šifra dejavnosti (SKD)
- `${cBusCodeName}` Naziv dejavnosti
- `${cContact}` Odgovorna oseba stranke (glavni kontakt)
- `${locContact}` Odgovorna oseba poslovne enote (PE)

Posamezne — poslovna enota (PE):

- `${locName}` Naziv PE
- `${locAddress}` Naslov PE
- `${locCity}` Mesto PE
- `${locZip}` Poštna št. PE

Posamezne — uporabnik:

- `${uName}` Ime in priimek uporabnika (izdajatelja)
- `${expTitle}` Strokovni naziv uporabnika
- `${acron}` Akronim uporabnika
- `${uCity}` Mesto (iz sistema ali BU uporabnika)
- `${uSignImg}` Podpis uporabnika (slika)

Posamezne — certifikati uporabnika:

- `${uCertDev}` Certifikat — delovna oprema
- `${uCertEdu}` Certifikat — usposabljanja
- `${uCertMes}` Certifikat — meritve

Posamezne — datumi in številčenje:

- `${dateRep}` Datum zapisnika/poročila
- `${repY}` Leto (YYYY)
- `${repy}` Leto (YY)
- `${repM}` Mesec (MM)
- `${custNrRep}` Interna št. (zapisnika/poročila)
- `${3NcustNrRep}` Št. s 3 števkami (vodilne ničle)
- `${4NcustNrRep}` Št. s 4 števkami
- `${5NcustNrRep}` Št. s 5 števkami
- `${dateLastRep}` Datum prejšnjega zapisnika
- `${nrLastRep}` Št. prejšnjega zapisnika

Tabele — izvajalci (performers, crm_user_action časovni intervali):

- `${rowPerfUser}` Ime izvajalca
  - `${rowPerfCnt}` Zap. št.
  - `${rowPerfUser}` Ime izvajalca (performer)
  - `${rowPerfStart}` Začetek (dd.mm.yyyy hh:mm)
  - `${rowPerfEnd}` Konec (dd.mm.yyyy hh:mm)
  - `${rowPerfDur}` Trajanje (HH:MM)

Opomba — odstranjevanje praznih blokov:

- Če podatkov za blok ni, uporabite `cloneBlock('blockName', 0)` da se `${blockName}` ... `${/blockName}` odstrani iz DOCX izpisa.

---

## Poročilo naloge (CRM Task) — GentaskController

Podpira tudi vse spremenljivke podjetja (glava dokumenta): `${sysName}`, `${sysAddress}`, `${sysZip}`, `${sysCity}`, `${sysRegNr}`, `${sysEmail}`, `${sysWeb}`, `${sysLogo}`.

Posamezne:

- `${cEmail}` E‑pošta glavnega kontakta stranke
- `${cTel}` Telefon glavnega kontakta
- `${timeStart}` Čas začetka
- `${timeEnd}` Čas konca
- `${location}` Lokacija (opisno, večvrstično)
- `${result}` Rezultat (večvrstično)
- `${desc}` Opis (večvrstično)
- `${cSignImg}` Podpis stranke (slika; če ga predloga uporablja)

Tabele:

- `${rowServiceName}` Naziv storitve
  - `${rowServiceCnt}` Zap. št.
  - `${rowServiceName}` Naziv storitve
  - `${rowServiceUser}` Izvajalec
  - `${rowServiceQty}` Količina
  - `${rowServiceDesc}` Opis

---

## Ponudba (ERP Offer) — GenofferController

Podpira tudi vse spremenljivke podjetja (glava dokumenta) in spremenljivke stranke: `${cName}`, `${cAddress}`, `${cZip}`, `${cCity}`, `${cTax}`.

Posamezne:

- `${offerNr}` Številka ponudbe
- `${dateIssue}` Datum izdaje
- `${dateValid}` Datum veljavnosti ponudbe
- `${notes}` Opombe (večvrstično)
- `${subtotal}` Skupaj brez DDV
- `${taxTotal}` Znesek DDV
- `${total}` Skupaj z DDV

Tabele — postavke ponudbe (cloneRow `${rowServiceCnt}`):

- `${rowServiceCnt}` Zap. št.
  - `${rowServiceCnt}` Zap. št.
  - `${rowServiceName}` Naziv storitve
  - `${rowServiceQty}` Količina
  - `${rowServicePrice}` Cena na enoto (€)
  - `${rowServiceDiscount}` Popust (%)
  - `${rowServiceTax}` Stopnja DDV (%)
  - `${rowServiceLine}` Znesek vrstice (€)

!!! info "Izračun zneskov"
    Zneski (`${rowServiceLine}`, `${subtotal}`, `${taxTotal}`, `${total}`) se izračunajo po enakem pravilu kot v obrazcu ponudbe: količina × cena × (1 − popust/100); DDV se obračuna na znesek vrstice.

---

## Vaja evakuacije (VPPEVAC) — GenvppevacController

Podpira tudi vse skupne spremenljivke (datum zapisa, veljavnost, stranka, uporabnik itd.).

Posamezne:

- `${nrRep}` Naziv vaje / št. poročila
- `${evacLocation}` Specifična lokacija vaje
- `${dateTest}` Datum izvedbe vaje
- `${testBy}` Vajo izvedel
- `${result}` Rezultat (večvrstično)
- `${dateValid}` Datum veljavnosti (potek)
- `${mntValid}` Veljavnost v mesecih

Podrobni opisi (večvrstično podprti):

- `${timeStart}` Čas proženja alarma
- `${descPreparedBy}` Vajo so pripravili
- `${nrExits}` Št. možnih izhodov
- `${nrExitsUsed}` Št. uporabljenih izhodov
- `${nrHumans}` Št. udeležencev
- `${openExitDoor}` Odpiranje vrat (DA/NE)
- `${descExtin}` Sredstva za gašenje
- `${descApz}` Sistemi APZ
- `${descApzInstall}` Izvedba sistemov APZ
- `${descEmpNotice}` Seznanitev zaposlenih
- `${descAlarmStart}` Način proženja alarma
- `${timeFullEvac}` Čas evakuacije
- `${timeSmoke}` Čas zadimljenja
- `${descAlarmResponse}` Odzivni časi
- `${descEvacPath}` Prehodnost poti
- `${descMeet}` Zbirno mesto
- `${descUnusedSpaces}` Stanje prostorov

Bloki — slike (priloge):

- `${cloneImg}` … `${/cloneImg}` (blok za slike)
  - `${imgName}` Originalno ime datoteke
  - `${imgFile}` Slika

---

## Zapisnik o usposabljanju (Education) — GeneduController

Podpira tudi vse skupne spremenljivke (sistem, stranka, PE, uporabnik, certifikati, datumi in številčenje).

!!! info "Veljavnost po udeležencu"
    Vse spremenljivke veljavnosti (npr. `${mntValid}`, `${dateValid}`, `${rowDateValid}`, `${rowPassDateValid}`, `${attMntValid}`, `${attDateValid}`) se izračunajo iz **individualne veljavnosti udeleženca** (polje **Velja (mes)** na tečaju): datum poteka = datum začetka tečaja + meseci udeleženca. V glavi zapisnika (`${mntValid}` / `${dateValid}`) se upošteva prvi udeleženec po vrstnem redu.

Programi usposabljanja (`nr_prog`): v zapisu je lahko več programov, ločenih z `||` (en program je shranjen brez ločila). V predlogah sta na voljo dve formaciji izpisa:

- privzeta (v eni vrstici, ločeno z `, `): `${nrProg}`, `${rowNrProg}`, `${row2NrProg}`, `${rowPassNrProg}`, `${frmNrProg}`, `${attNrProg}`;
- seznam v novih vrsticah: `${nrProgLst}`, `${rowNrProgLst}`, `${row2NrProgLst}`, `${rowPassNrProgLst}`, `${frmNrProgLst}`, `${attNrProgLst}`.

Posamezne:

- `${dateRep}` Datum zapisnika
- `${dateStart}` Datum začetka usposabljanja
- `${datePract}` Datum praktičnega dela (iz prvega udeleženca; za posameznega udeleženca glej `rowDatePract`, `attDatePract`)
- `${custNrRep}` Številka zapisnika (`${nrRep}` je enaka vrednost)
- `${nrProg}` Program(i) usposabljanja (v vrstici, ločeno z `, `)
- `${nrProgLst}` Program(i) usposabljanja (vsak v svoji vrstici)
- `${nrHour}` Število ur usposabljanja
- `${location}` Lokacija
- `${cPersResp}` Odgovorna oseba stranke
- `${cPersMent}` Neposredni vodja / mentor
- `${mntValid}` Veljavnost udeleženca — št. mesecev
- `${dateValid}` Datum veljavnosti udeleženca (izračunan)
- `${txtEduDesc}` Opis tipa usposabljanja
- `${txtEduDescLow}` Opis tipa usposabljanja (male črke)
- `${txtCust1}` Tekst po meri 1
- `${txtCust2}` Tekst po meri 2
- `${txtLaw}` Tekst zakonskih odredb
- `${txtCourseAttach}` Priloge tečaja (večvrstično)
- `${txtCourseDesc}` Opis tečaja (večvrstično)
- `${eduAddress}` Naslov izvedbe (lokacija ali naslov stranke)
- `${edutypeImg}` Slika/logotip tipa usposabljanja
- Dinamična polja tipa usposabljanja (edutype): spremenljivke s kodami polj iz sistemskih nastavitev (Fldopt — `edutype`)

Tabele — edinstven seznam delavcev:

- `${rowNameUn}` Ime in priimek
  - `${rowCntUn}` Zap. št.
  - `${rowNameUn}` Ime in priimek
  - `${rowDateBirthUn}` Datum rojstva
  - `${rowWorkPlaceUn}` Delovno mesto
  - `${rowDatePractUn}` Datum praktičnega dela
  - `${rowEdutypeUn}` Tip(i) usposabljanja (več tipov ločenih z vejico)

Tabele — seznam delavcev:

- `${rowName}` Ime in priimek
  - `${rowCnt}` Zap. št.
  - `${rowName}` Ime in priimek
  - `${rowDateBirth}` Datum rojstva
  - `${rowWorkPlace}` Delovno mesto
  - `${rowDatePract}` Datum praktičnega dela
  - `${rowNrRep}` Številka potrdila
  - `${rowEdutype}` Tip usposabljanja
  - `${rowNrProg}` Program(i) usposabljanja (v vrstici)
  - `${rowNrProgLst}` Program(i) usposabljanja (v novih vrsticah)
  - `${rowDateValid}` Datum veljavnosti udeleženca
  - `${rowDateEtest}` Datum e-testa (če je opravljen)
  - `${rowRes}` Uspešno / Neuspešno (DA/NE)
  - `${rowPass}` Uspešno / Neuspešno (besedilo)

Tabele — dvojnik seznama delavcev (row2, za vzporedno tabelo v predlogi):

- `${row2Name}` Ime in priimek
  - `${row2Cnt}` Zap. št.
  - `${row2Name}` Ime in priimek
  - `${row2DateBirth}` Datum rojstva
  - `${row2WorkPlace}` Delovno mesto
  - `${row2DatePract}` Datum praktičnega dela
  - `${row2NrRep}` Številka potrdila
  - `${row2Edutype}` Tip usposabljanja
  - `${row2NrProg}` Program(i) usposabljanja (v vrstici)
  - `${row2NrProgLst}` Program(i) usposabljanja (v novih vrsticah)
  - `${row2DateValid}` Datum veljavnosti udeleženca
  - `${row2Res}` Uspešno / Neuspešno (DA/NE)
  - `${row2Pass}` Uspešno / Neuspešno (besedilo)

Tabele — samo uspešno opravljena usposabljanja (rowPass):

- `${rowPassName}` Ime in priimek
  - `${rowPassCnt}` Zap. št.
  - `${rowPassName}` Ime in priimek
  - `${rowPassDateBirth}` Datum rojstva
  - `${rowPassWorkPlace}` Delovno mesto
  - `${rowPassDatePract}` Datum praktičnega dela
  - `${rowPassNrRep}` Številka potrdila
  - `${rowPassEdutype}` Tip usposabljanja
  - `${rowPassNrProg}` Program(i) usposabljanja (v vrstici)
  - `${rowPassNrProgLst}` Program(i) usposabljanja (v novih vrsticah)
  - `${rowPassRes}` Rezultat (vedno DA)
  - `${rowPassPass}` Rezultat (besedilo)
  - `${rowPassDateValid}` Datum veljavnosti udeleženca

Tabele — seznam tečajev v zapisniku:

- `${rowEdulstEdutype}` Tip usposabljanja
  - `${rowEdulstEdutype}` Tip usposabljanja
  - `${rowEdulstEdudesc}` Opis tipa usposabljanja
  - `${rowEdulstMntValid}` Veljavnost udeležencev (meseci)

Bloki:

- `${cloneForm0}` … `${/cloneForm0}` (obrazec za vsakega delavca)
  - `${frmName}` Ime in priimek
  - `${frmDateBirth}` Datum rojstva
  - `${frmWorkPlace}` Delovno mesto
  - `${frmDateStart}` Datum usposabljanja
  - `${frmDatePract}` Datum praktičnega dela
  - `${frmnrHour}` Število ur
  - `${frmNrProg}` Program(i) usposabljanja (v vrstici)
  - `${frmNrProgLst}` Program(i) usposabljanja (v novih vrsticah)
  - `${frmEduDesc}` Opis tipa usposabljanja

- `${cloneCert0}` … `${/cloneCert0}` (blok potrdil)
  - Ta blok je hkrati osnova za samodejno izdelano predlogo **Potrdilo o usposabljanju** (tiskanje posameznih potrdil iz kartice zaposlenega).
  - `${attName}` Ime in priimek
  - `${attName2}` Ime in priimek (alternativna oznaka)
  - `${attDateBirth}` Datum rojstva
  - `${attDateBirth2}` Datum rojstva (alternativna oznaka)
  - `${attAddress}` Naslov delavca
  - `${attAddress2}` Naslov delavca (alternativna oznaka)
  - `${attCity}` Mesto delavca
  - `${attCity2}` Mesto delavca (alternativna oznaka)
  - `${attWorkPlace}` Delovno mesto
  - `${attNrRep}` Številka potrdila
  - `${attNrHour}` Število ur
  - `${attNrProg}` Program(i) usposabljanja (v vrstici)
  - `${attNrProgLst}` Program(i) usposabljanja (v novih vrsticah)
  - `${attLocName}` Poslovna enota
  - `${attLocAddress}` Naslov PE
  - `${attLocCity}` Mesto PE
  - `${attEduDesc}` Opis tipa usposabljanja
  - `${attEduDesc2}` Opis tipa usposabljanja (alternativna oznaka)
  - `${attTxtCourseAttach}` Priloge tečaja (večvrstično)
  - `${attTxtCourseDesc}` Opis tečaja (večvrstično)
  - `${attTxtCust1}` Tekst po meri 1 (večvrstično)
  - `${attTxtCust2}` Tekst po meri 2 (večvrstično)
  - `${attdateStart}` Datum usposabljanja
  - `${attDatePract}` Datum praktičnega dela
  - `${attDatePract2}` Datum praktičnega dela (alternativna oznaka)
  - `${attMntValid}` Veljavnost udeleženca — meseci
  - `${attDateValid}` Datum veljavnosti potrdila (izračunan po udeležencu)
  - `${attDateEtest}` Datum opravljanja e-testa
  - Dinamična polja zaposlenega (custemployee): spremenljivke `att<koda_polja>` iz sistemskih nastavitev (Fldopt — `custemployee`)

---

## Zapisnik o pregledu delovne opreme (MDEVICE)

Statusi pregleda (`mdevice.status`): `pass` = Ustreza, `fail` = Ne ustreza, `repair` = V popravilu / okvari, `missing` = Pogrešano. Spremenljivke stanja spodaj prikazujejo te vrednosti. Status **ne** vpliva na prisotnost opreme v evidenci (za izločitev velja samo datum odpisa).

Posamezne:

- `${dateRep}` Datum zapisnika
- `${dateTest}` Datum pregleda (iz prve naprave v zapisniku)
- `${devUser}` Uporabnik delovne opreme
- `${devUserAddr}` Naslov uporabnika opreme
- `${custNrRep}` Številka zapisnika (`${nrRep}` je enaka vrednost)
- `${dateLastRep}` Datum prejšnjega zapisnika (mdevicegrp)
- `${nrLastRep}` Št. prejšnjega zapisnika (s predpono » Št.zap. «)
- `${infoLast}` Opis zadnjega pregleda
- `${txtType}` Tip pregledov
- `${desc}` Opis metodologije (večvrstično)
- `${result}` Skupni rezultat (večvrstično)

Tabele — merilniki (instrumenti):

- `${rowInstName}` Naziv merilnika
  - `${rowInstName}` Naziv merilnika
  - `${rowInstCert}` Certifikat merilnika

Tabele — kratek seznam pregledane opreme:

- `${rowShortName}` Naziv opreme
  - `${rowShortCnt}` Zap. št.
  - `${rowShortName}` Naziv opreme
  - `${rowShortSerial}` Serijska št.
  - `${rowShortNrInv}` Inventarna št.
  - `${rowShortManufacturer}` Proizvajalec
  - `${rowShortManufactYear}` Leto izdelave
  - `${rowShortTypeDevice}` Tip / model
  - `${rowShortLocation}` Mikro lokacija
  - `${rowShortResult}` Rezultat pregleda (Uspešno / Neuspešno — iz `ind_pass`)
  - `${rowShortPass}` Ustreza (Da / Ne — iz `ind_pass`)
  - `${rowShortStatus}` Status opreme (kratko): `DA`, `NE`, `V POPRAVILU`, `POGREŠANO`
  - `${rowShortNote}` Opomba pregleda; če je prazna, se za statusa *V popravilu* in *Pogrešano* samodejno vpiše opomba »potrdilo ni izdano«
  - `${rowShortDesc}` Dodatni opis

Tabele — kratek seznam, neustrezne naprave najprej (rowShortFailFirst):

- `${rowShortNameFailFirst}` Naziv opreme
  - `${rowShortCntFailFirst}` Zap. št.
  - `${rowShortNameFailFirst}` Naziv opreme
  - `${rowShortSerialFailFirst}` Serijska št.
  - `${rowShortNrInvFailFirst}` Inventarna št.
  - `${rowShortManufacturerFailFirst}` Proizvajalec
  - `${rowShortManufactYearFailFirst}` Leto izdelave
  - `${rowShortTypeDeviceFailFirst}` Tip / model
  - `${rowShortLocationFailFirst}` Mikro lokacija
  - `${rowShortResultFailFirst}` Rezultat pregleda (Uspešno / Neuspešno — iz `ind_pass`)
  - `${rowShortPassFailFirst}` Ustreza (Da / Ne — iz `ind_pass`)
  - `${rowShortStatusFailFirst}` Status opreme (kratko: `DA` / `NE` / `V POPRAVILU` / `POGREŠANO`)
  - `${rowShortNoteFailFirst}` Opomba pregleda (avtomatska opomba za popravilo/pogrešano, če ni vpisanega rezultata)
  - `${rowShortDescFailFirst}` Dodatni opis

Tabele — podroben seznam:

- `${lstName}` Naziv opreme
  - `${lstNrCnt}` Zap. št.
  - `${lstName}` Naziv opreme
  - `${lstNrRep}` Št. potrdila
  - `${lstDateTest}` Datum pregleda
  - `${lstSerial}` Serijska št.
  - `${lstNrInv}` Inventarna št.
  - `${lstLocation}` Mikro lokacija pregleda
  - `${lstLocationObj}` Mikro lokacija objekta (zgodovinska vrednost)
  - `${lstTypeDevice}` Tip / model
  - `${lstDesc}` Dodatni opis
  - `${lstDoc}` Predložena dokumentacija
  - `${lstResult}` Rezultat pregleda
  - `${lstIndPass}` Indikator ustreznosti (`DA` / `NE` — iz `ind_pass`)
  - `${lstStatus}` Status opreme (kratko): `DA`, `NE`, `V POPRAVILU`, `POGREŠANO`
  - `${lstManufacturer}` Proizvajalec
  - `${lstManufactYear}` Leto izdelave
  - `${lstKW}` Moč (kW)
  - `${lstMesOhm}` Izmerjena upornost
  - `${lstMesVolt}` Izmerjena napetost
  - `${lstPersResp}` Odgovorna oseba
  - `${lstChkName}` Preizkusi po meri
  - `${lstChkResult}` Rezultat preizkusa po meri
  - `${lstChkValue}` Izmerjena vrednost preizkusa po meri
  - `${lstChkSist}` Referenčna vrednost preizkusa po meri
  - `${lstChkElecName}` Električni preizkusi po meri
  - `${lstChkElecResult}` Rezultat el. preizkusa
  - `${lstChkElecValue}` Izmerjena vrednost el. preizkusa
  - `${lstChkElecSist}` Referenčna vrednost el. preizkusa
  - Dinamična polja objekta (Fldopt — `mdeviceobj`): `${lst<koda_polja>}`
  - Dinamična polja pregleda (Fldopt — `mdevice`): `${lst<koda_polja>}`

Bloki:

- `${cloneDevLst0}` … `${/cloneDevLst0}` (info blok opreme)
- `${cloneCert0}` … `${/cloneCert0}` (blok potrdil — izpolni se **samo za opremo s statusom Ustreza**; oprema s statusi Ne ustreza, V popravilu in Pogrešano se na potrdilih ne pojavi)
  - `${devName}` Naziv opreme
  - `${devNrCnt}` Zap. št.
  - `${devNrRep}` Št. potrdila
  - `${devNrRep2}` Št. potrdila (alternativna oznaka)
  - `${devDateTest}` Datum pregleda
  - `${devDateValid}` Datum veljavnosti (shranjena vrednost `mdevice.date_valid`; izračuna se ob shranjevanju pregleda samo za status *Ustreza*)
  - `${devDateLast}` Datum zadnjega pregleda in preizkusa (najkasnejši `date_test` v `mdevice` za to delovno opremo; če ni, `/`)
  - `${devMntValid}` Veljavnost — št. mesecev
  - `${devSerial}` Serijska št.
  - `${devNrInv}` Inventarna št.
  - `${devTypeDevice}` Tip / model
  - `${devDesc}` Dodatni opis (večvrstično)
  - `${devDevUser}` Uporabnik opreme (iz pregleda)
  - `${devDevUserAddr}` Naslov uporabnika opreme (iz pregleda)
  - `${devPersResp}` Odgovorna oseba
  - `${devResult}` Rezultat pregleda
  - `${devUsage}` Namen opreme
  - `${devDoc}` Predložena dokumentacija (večvrstično)
  - `${devManufacturer}` Proizvajalec
  - `${devManufactYear}` Leto izdelave
  - `${devLocation}` Mikro lokacija (privzeto »Poslovni prostori«)
  - `${devMesOhm}` Izmerjena upornost (privzeto `/`)
  - `${devMesVolt}` Izmerjena napetost (privzeto `/`)
  - Dinamična polja objekta (Fldopt — `mdeviceobj`): `${dev<koda_polja>}`
  - Dinamična polja pregleda (Fldopt — `mdevice`): `${dev<koda_polja>}`

---

## Meritve — GenmesController

Skupne (v vseh tipih meritev):

Posamezne:

- `${dateTest}` Datum meritve
- `${mntValid}` Veljavnost (meseci)
- `${mesDateValid}` Datum poteka veljavnosti (izračunan)
- `${infoLast}` Opis zadnje meritve
- `${txtType}` Tip/vrsta pregleda/meritve
- `${dateLastRep}` Datum prejšnje meritve
- `${nrLastRep}` Št. prejšnje meritve
- `${result}` Skupni rezultat (večvrstično)
- `${desc}` Opis metodologije (večvrstično)

Tabele — merilniki:

- `${rowInstName}` Merilnik — naziv
  - `${rowInstName}` Naziv
  - `${rowInstCert}` Certifikat

### Meritve delovnega okolja (type_measure = envi)

Posamezne (meta okolja):

- `${RH}` Relativna vlaga
- `${Temp}` Temperatura
- `${VA}` Gibanje zraka
- `${Light}` Osvetlitev
- `${Weather}` Vreme
- `${hourTest}` Čas meritve
- `${measureCountAll}` Št. vseh merilnih mest
- `${measureCountM}` Št. merilnih mest (toplotne razmere)
- `${measureCountL}` Št. merilnih mest (osvetlitev)

Tabele — Toplotne razmere:

- `${rowTName}` Naziv merilnega mesta
  - `${rowTCnt}` Zap. št.
  - `${rowTName}` Naziv
  - `${rowTT110}` T110
  - `${rowTT01}` T0.1
  - `${rowTVA}` VA
  - `${rowTRH}` RH
  - `${rowTMet}` MET
  - `${rowTPos}` Položaj
  - `${rowTIclo}` ICLO
  - `${rowTPMV}` PMV
  - `${rowTPPD}` PPD
  - `${rowTResult}` Rezultat

Tabele — Osvetlitev:

- `${rowLName}` Naziv merilnega mesta
  - `${rowLCnt}` Zap. št.
  - `${rowLName}` Naziv
  - `${rowLType}` Tip svetilke
  - `${rowLTypeLum}` Tip osvetljenosti (naravna/umetna/komb.)
  - `${rowLEDN}` E dnevna
  - `${rowLEKOM}` E kombinirana
  - `${rowLEUM}` E umetna (EKOM − EDN)
  - `${rowLEDOD}` E dodatna
  - `${rowLEMIN}` E min izmerjena
  - `${rowLUO}` UO
  - `${rowLUOMIN}` UO min
  - `${rowLSIST}` SIST referenca
  - `${rowLResult}` Rezultat

Bloki:

- `${cloneMesPlace}` … `${/cloneMesPlace}` — kombinirani opis mesta (T + L)
  - Posamezne znotraj bloka (sekvenčno polnjenje, limit=1):
    - `${mesPlaceName}`, `${mesPlaceCnt}`
    - Toplota: `${mesTT110}`, `${mesTT01}`, `${mesTVA}`, `${mesTRH}`, `${mesTMet}`, `${mesTPos}`, `${mesTIclo}`, `${mesTPMV}`, `${mesTPPD}`, `${mesTResult}`
    - Svetloba: `${mesLType}`, `${mesLTypeLum}`, `${mesLEDN}`, `${mesLEKOM}`, `${mesLEUM}`, `${mesLEDOD}`, `${mesLEMIN}`, `${mesLUO}`, `${mesLUOMIN}`, `${mesLSIST}`

- `${cloneMesGrp}` … `${/cloneMesGrp}` — skupine merilnih mest
  - Posamezne znotraj bloka: `${mesGrpName}`
  - Tabela znotraj bloka — `${rowMesName}`:
    - Toplota: `${rowMesCnt}`, `${rowMesName}`, `${rowMesT110}`, `${rowMesT01}`, `${rowMesVA}`, `${rowMesRH}`, `${rowMesMet}`, `${rowMesPos}`, `${rowMesIclo}`, `${rowMesPMV}`, `${rowMesPPD}`, `${rowMesTSO}`
    - Svetloba: `${rowMesLType}`, `${rowMesEDN}`, `${rowMesEKOM}`, `${rowMesEUM}`, `${rowMesEDOD}`, `${rowMesEMIN}`, `${rowMesUO}`, `${rowMesUOMIN}`, `${rowMesLSIST}`, `${rowMesLSO}`

### Meritve hrupa (type_measure = nois)

Tabele — merilna mesta:

- `${rowName}` Naziv merilnega mesta
  - `${rowCnt}` Zap. št.
  - `${rowName}` Naziv
  - `${rowt}` t
  - `${rowtex}` t_ex
  - `${rowLeq}` LAeq
  - `${rowKi}` KI
  - `${rowLai}` LAI
  - `${rowLc}` LC peak
  - `${rowLexmax}` LEXmax
  - `${rowLex8h}` LEX8h
  - `${rowResult}` Rezultat
  - `${rowSource}` Vir hrupa
  - `${rowDesc}` Opis

Bloki:

- `${cloneMesGrp}` … `${/cloneMesGrp}`
  - `${mesGrpName}`
  - Tabela `${rowMesName}`:
    - `${rowMesCnt}`, `${rowMesName}`, `${rowMesT}`, `${rowMesTex}`, `${rowMesLeq}`, `${rowMesKi}`, `${rowMesLai}`, `${rowMesLc}`, `${rowMesLexmax}`, `${rowMesLex8h}`, `${rowMesSource}`, `${rowMesDesc}`

### Električne meritve (type_measure = elec)

Blok:

- `${cloneR0}` … `${/cloneR0}` — skupina električnih tokokrogov
  - Posamezne v bloku: `${rName}` Naziv skupine
  - Tabela `${rowName}`:
    - `${rowNr}` Št. tokokroga
    - `${rowName}` Naziv tokokroga
    - `${rowDiam}` Presek/diameter
    - `${rowIsol0}`, `${rowIsol1}`, `${rowIsol2}` Izolacijske upornosti
    - `${rowMain}` Glavna zaščitna žila
    - `${rowAux}` Dodatna žila
    - `${rowType}` Tip
    - `${rowZ}` Z
    - `${rowIsc}` I_sc
    - `${rowRcdI}`, `${rowRcdIdn}`, `${rowRcdId}`, `${rowRcdIdnx1}`, `${rowRcdIdnx5}`, `${rowRcdUc}` RCD meritve

---

## Ocene tveganja (RASS skupina) — GenrasController

Posamezne:

- `${cContact}` Kontakt stranke (ime in priimek)
- `${cPersResp}` Odgovorna oseba stranke za VZD
- `${cPersMed}` Pooblaščeni zdravnik
- `${descWorkEnv}` Opis delovnih prostorov
- `${dateRep}` Datum poročila
- `${custNrRep}` Št. poročila (in formati 3N/4N/5N)
- `${dateLastRep}` Datum prejšnjega poročila (če obstaja)
- `${nrLastRep}` Št. prejšnjega poročila (če obstaja)
- `${repy}`, `${repY}`, `${repM}` Leto (YY/YYYY) in mesec
- `${cntEmpAll}` Št. zaposlenih (PE)
- Periodike: `${rassMntMed}`, `${rassMntEnv}`, `${rassMntNoise}`, `${rassMntDev}`

Bloki:

- `${cloneRassLst}` … `${/cloneRassLst}` — seznam TDM v skupini
  - Posamezne v bloku:
    - `${rassCnt}` Zap. št.
    - `${rassName}` Naziv TDM
    - `${rassNrEmp}`, `${rassNrStud}`, `${rassNrM}`, `${rassNrF}`, `${rassNrInval2}`, `${rassNrInval3}`
    - `${rassWpDesc}` Opis delovnega mesta (večvrstično)
  - Tabela (opcijsko) `${rowEmpWP}` — zaposleni v TDM:
    - `${rowCnt}`, `${rowEmpName}`, `${rowEmpDateBirth}`, `${rowEmpWP}`

Tabele (izven blokov):

- `${rowRecName}` — priporočila/ugotovitve
  - `${rowRecCnt}`, `${rowRecName}`, `${rowRecLast}`, `${rowRecNote}`

Bloki (rezultati TDM):

- `${cloneRassRes}` … `${/cloneRassRes}` — rezultati po TDM
  - Posamezne:
    - `${rassResCnt}`, `${rassResName}`, `${rassResName2}`
    - `${rassResDesc}`, `${rassResDescWork}`, `${rassResDescWorkAux}`
    - `${rassResWorkDuration}`, `${rassResEquip}`, `${rassResChem}`
    - `${rassResOvo}` Besedilni seznam standardov OVO
    - `${rassResNrEmp}`, `${rassResNrStud}`, `${rassResNrM}`, `${rassResNrF}`, `${rassResNrInval2}`, `${rassResNrInval3}`
    - `${rassResResult}` (večvrstično)
  - Tabela `${rowRiskName}` — tveganja po kategorijah:
    - `${rowRiskNr}`, `${rowRiskName}`, `${rowRprob}`, `${rowRcons}`, `${rowRrisk}`, `${rowRriskTxt}`, `${rowAction}`, `${rowActionDate}`, `${rowPersResp}`
  - Tabela `${rowActRiskName}` — aktivni ukrepi:
    - `${rowActCnt}`, `${rowActRiskName}`, `${rowActRiskProb}`, `${rowActRiskCons}`, `${rowActMark}`, `${rowActAction}`, `${rowActDate}`, `${rowActPersResp}`

Tabele — periodike usposabljanj za TDM:

- `${rowEduRassName}` (po TDM)
  - `${rowEduRassName}` Naziv TDM
  - `${rowEduEduName}` Imena tečajev (vrstice)
  - `${rowEduEduMnt}` Mesečna veljavnost (vrstice)

---

## Ocene tveganj kemičnih snovi (RASSC) — GenrasscController

Posamezne (naslovnica in podatki dokumenta):

- `${cName}`, `${cAddress}`, `${cZip}`, `${cCity}` — stranka (naročnik)
- `${custNrRep}` Št. dokumenta; `${version}` Verzija; `${dateRep}` Datum
- `${rasscGrpName}` Naziv dokumenta OTV KEM
- `${sysName}` Izdelovalec ocene (družba z dovoljenjem)
- `${uName}`, `${expTitle}` Strokovni sodelavec in strokovni naziv
- `${cPersResp}` Odgovorna oseba delodajalca; `${cPersMed}` Pooblaščeni zdravnik; `${cPersRep}` Predstavnik delavcev
- `${descWorkEnv}` Opis tehnološkega postopka
- `${uSignImg}` (opcijsko) slika podpisa izvajalca

Blok ocen delovnih mest:

- `${cloneRasscLst}` … `${/cloneRasscLst}` — seznam ocen v dokumentu
  - `${rasscCnt}` Zap. št.
  - `${rasscName}` Naziv ocene
  - `${rasscTarget}` Delovno mesto / proces (predmet ocene)
  - `${rasscDate}` Datum ocene
  - `${rasscDescExposure}`, `${rasscDescOther}`, `${rasscDescMeasures}`, `${rasscDescHealth}`, `${rasscDescr}` — opisi (večvrstično)

Tabela 1 – Evidenca nevarnih kemičnih snovi (cloneRow `${rowSubCnt}`):

- `${rowSubCnt}`, `${rowSubCode}`, `${rowSubTrg}`, `${rowSubChem}`
- `${rowSubCas}`, `${rowSubEs}`, `${rowSubIndex}`, `${rowSubReach}`
- `${rowSubState}` Agregatno stanje; `${rowSubBoil}` Vrelišče
- `${rowSubR}`, `${rowSubH}` R/H stavki (R = le stari podatki, po CLP opuščeni); `${rowSubClassif}` Klasifikacija
- `${rowSubMv}`, `${rowSubKtv}`, `${rowSubBat}` MV/KTV/BAT
- `${rowSubSupplier}` Dobavitelj; `${rowSubSdsDate}` Datum VL
- `${rowSubForb}` Prepovedana snov; `${rowSubSvhc}` SVHC

Tabela 2 – Podatki o uporabi na delovnem mestu (cloneRow `${rowUseCnt}`):

- `${rowUseCnt}`, `${rowUseTrg}`, `${rowUseChem}`
- `${rowUseH}` H-stavki; `${rowUseClassif}` Klasifikacija
- `${rowUseQty}` Količina; `${rowUseMv}`, `${rowUseKtv}`, `${rowUseBat}`
- `${rowUsePhys}` Fizikalne lastnosti (sestava)

Tabela 3 – Kontrolni listi, Korak 1–3 (cloneRow `${rowItemCnt}`):

- `${rowItemCnt}`, `${rowItemAss}` Ocena; `${rowItemSub}` Snov
- `${rowItemOps}` Operacije (Korak 1)
- `${rowItemGroup}` Skupina A–E; `${rowItemK}` oznaka K
- `${rowItemQty}` Količina; `${rowItemFactor}` Prašnost/hlapnost
- `${rowItemBoil}` Vrelišče; `${rowItemWork}` Delovna temperatura
- `${rowItemLevel}` Stopnja tveganja 1–4
- `${rowItemActions}` Ukrepi (večvrstično); `${rowItemMnt}` Meritve; `${rowItemHealth}` Zdravstveni nadzor; `${rowItemOvo}` OVO; `${rowItemDescr}` Opombe

Tabela 4 – Ukrepi, Korak 4 (cloneRow `${rowUkrCnt}`):

- `${rowUkrCnt}`, `${rowUkrSub}` Snov, `${rowUkrActions}` Ukrepi
- `${rowUkrOvo}` OVO, `${rowUkrMnt}` Meritve, `${rowUkrHealth}` Zdravstveni nadzor, `${rowUkrDescr}` Opombe

!!! info "cloneRow v predlogi"
    Vrstica tabele vsebuje neindeksirane spremenljivke (npr. `${rowSubTrg}`). Generator vrstico samodejno podvoji za vsako snov in polni `${rowSubTrg#1}`, `${rowSubTrg#2}` … V Word predlogi mora biti spremenljivka v **eni vrstici** tabele (prva celica vrstice naj vsebuje `${rowSubCnt}` ipd.).

---

## Kartica stranke (stanje na dan) — CustomerSnapshotReportController

Predloga tipa `card`. Generator uporablja datum **`${onDate}`**; vsi razdelki se filtrirajo na stanje na ta dan. Vrstice brez datumskega snapshota se ne izpišejo.

!!! info "Kaj pomeni »na dan«"
    RASS, VPP dokumenti, VPP vaje evakuacije in Recot se vključijo, če je njihov datum evidence (`date_rep`, `date_create`, `date_test`) enak ali starejši od `${onDate}`. Prikazani so tudi zapisi, katerih veljavnost je na ta dan že potekla; datum veljavnosti ostane v tabeli. VPP odgovorne osebe nimajo datumskega snapshota in se ne izpišejo.

### Skupne spremenljivke

| Spremenljivka | Pomen |
|---------------|-------|
| `${sysName}` | Naziv podjetja |
| `${sysAddress}` | Naslov podjetja |
| `${sysCity}` | Mesto podjetja |
| `${onDate}` | Datum stanja (dd.mm.yyyy) |
| `${cName}` | Naziv stranke |
| `${cNameFull}` | Polni naziv stranke |
| `${cAddress}` | Naslov sedeža |
| `${cZip}` | Poštna številka |
| `${cCity}` | Mesto |
| `${cTel}` | Telefon glavnega kontakta |
| `${cMail}` | E-pošta glavnega kontakta |
| `${cContact}` | Ime in priimek glavnega kontakta |
| `${cPersResp}` | Odgovorna oseba stranke |
| `${cTaxNr}` | Davčna številka |
| `${cRegId}` | Registrska številka |
| `${cBusCode}` | Šifra dejavnosti |
| `${cBusCodeName}` | Naziv dejavnosti |
| `${locName}`, `${locAddress}`, `${locZip}`, `${locCity}` | Podatki poslovne enote, če je izbrana |

### Usposabljanja — `${rowEduDateStart}`

Tabela prikazuje usposabljanja, veljavna na `${onDate}`.

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowEduCnt}` | Zaporedna številka |
| `${rowEduNrPers}` | Število udeležencev |
| `${rowEduDateStart}` | Datum začetka |
| `${rowEduDateEnd}` | Datum poteka |
| `${rowEduMntValid}` | Veljavnost v mesecih |
| `${rowEduNrRep}` | Številka zapisnika |
| `${rowEduName}` | Naziv usposabljanja |
| `${rowEduType}` | Tip usposabljanja |
| `${rowEduBU}` | Poslovna enota |

### Pregledi delovne opreme — `${rowGdevNr}`

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowGdevCnt}` | Zaporedna številka |
| `${rowGdevNrDev}` | Število naprav v skupini |
| `${rowGdevDate}` | Datum pregleda |
| `${rowGdevDateValid}` | Datum veljavnosti |
| `${rowGdevNr}` | Številka zapisnika |
| `${rowGdevBU}` | Poslovna enota |
| `${rowGdevType}` | Tip pregleda |

### Meritve — `${rowMesNr}`

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowMesCnt}` | Zaporedna številka |
| `${rowMesDate}` | Datum meritve |
| `${rowMesDateEnd}` | Datum veljavnosti |
| `${rowMesMntValid}` | Veljavnost v mesecih |
| `${rowMesNr}` | Številka zapisnika |
| `${rowMesBU}` | Poslovna enota |
| `${rowMesName}` | Vrsta meritve |
| `${rowMesType}` | Tip meritve |

### RASS skupine — `${rowRasName}`

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowRasCnt}` | Zaporedna številka |
| `${rowRasDate}` | Datum ocene tveganja |
| `${rowRasNr}` | Številka zapisnika |
| `${rowRasName}` | Naziv / revizija |
| `${rowRasBU}` | Poslovna enota |

### VPP vaje evakuacije — `${rowVppEvacDate}`

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowVppEvacCnt}` | Zaporedna številka |
| `${rowVppEvacObj}` | VPP objekt |
| `${rowVppEvacName}` | Naziv vaje / zapisnik |
| `${rowVppEvacLoc}` | Lokacija vaje |
| `${rowVppEvacDate}` | Datum vaje |
| `${rowVppEvacDateValid}` | Datum poteka |

### VPP dokumenti — `${rowVppDocName}`

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowVppDocCnt}` | Zaporedna številka |
| `${rowVppDocObj}` | VPP objekt |
| `${rowVppDocName}` | Naziv dokumenta |
| `${rowVppDocCatName}` | Kategorija dokumenta |
| `${rowVppDocDate}` | Datum dokumenta |
| `${rowVppDocMntValid}` | Veljavnost v mesecih |

### Ostale evidence (Recot) — `${cloneRecot}` … `${/cloneRecot}`

Blok se ponovi za vsako izbrano kategorijo evidence.

| Spremenljivka | Pomen |
|---------------|-------|
| `${recotCatName}` | Naziv kategorije |
| `${rowRecotCnt}` | Zaporedna številka |
| `${rowRecotName}` | Naziv / revizija |
| `${rowRecotBU}` | Poslovna enota |
| `${rowRecotMntValid}` | Veljavnost v mesecih |
| `${rowRecotDate}` | Datum dokumenta |
| `${rowRecotDesc}` | Opis |
| `${rowRecotResult}` | Rezultat |

### VPP odgovorne osebe — neuporabljeno

`${rowVppRespCnt}`, `${rowVppRespObj}`, `${rowVppRespName}`, `${rowVppRespDepart}`, `${rowVppRespShift}`, `${rowVppRespBU}` so še lahko v starih predlogah, vendar jih generator kartice ne polni. Ker tabela `vppresp` nima datumskega snapshota, se vrstica odstrani; naslov razdelka v predlogi ostane prazen.

### Kartica »Zaposleni in oprema na dan« — predloga 158

| Spremenljivka | Pomen |
|---------------|-------|
| `${onDate}` | Datum stanja |
| `${cName}`, `${cAddress}`, `${cZip}`, `${cCity}`, `${cTaxNr}` | Podatki stranke |
| `${nDevices}` | Število naprav, veljavnih na dan |
| `${nEmployees}` | Število aktivnih zaposlenih na dan |
| `${rowDevCnt}` | Zaporedna številka naprave |
| `${rowDevName}` | Naziv naprave |
| `${rowDevType}` | Tip pregleda |
| `${rowDevBU}` | Poslovna enota |
| `${rowDevDate}` | Datum pregleda |
| `${rowDevDateValid}` | Veljavno do |
| `${rowDevNr}` | Številka zapisnika |
| `${rowEmpCnt}` | Zaporedna številka zaposlenega |
| `${rowEmpName}` | Ime in priimek |
| `${rowEmpDepart}` | Oddelek |
| `${rowEmpPos}` | Delovno mesto |
| `${rowEmpDateEmp}` | Datum zaposlitve |
| `${rowEmpTel}` | Telefon |

---

## Periodično poročilo za stranke — CustomerPeriodReportController

Predloge tipa `repy`. Podprta so letna, mesečna in obdobna poročila. Konec obdobja (`${cPeriodEnd}`) je mejnik za izračune in za vsebine, vezane na datum.

!!! info "Zapadla VZD/VPP usposabljanja"
    Predloga prikaže vse aktivne zaposlene po obratih. Upošteva najnovejše usposabljanje, katerega teoretični začetek in praktični del sta do `${cPeriodEnd}`; prihodnji tečaji se ne upoštevajo. `${rowRok}` je prejšnji od `${rowVzdTeor}` in `${rowVzdPrakt}`.

### Skupne in obdobne spremenljivke

| Spremenljivka | Pomen |
|---------------|-------|
| `${cName}`, `${cAddress}`, `${cCity}` | Podatki stranke |
| `${cTaxNr}`, `${cRegId}`, `${cBusCodeName}` | Davčna številka, registrska številka, dejavnost |
| `${cPersResp}`, `${cPersMed}` | Odgovorna oseba in pooblaščeni zdravnik iz RASS |
| `${cYear}` | Leto (pri obdobju prazno) |
| `${cMonth}` | Mesec (samo mesečno poročilo) |
| `${cPeriod}` | Leto, mesec ali datumsko obdobje |
| `${cPeriodPrep}` | Predlog »za leto«, »za mesec« ali »za obdobje« |
| `${cPeriodTitle}` | Naslov, npr. LETNO POROČILO |
| `${cPeriodType}` | »letno poročilo«, »mesečno poročilo« ali »poročilo« |
| `${cPeriodIn}` | »v letu …«, »v mesecu …« ali »v obdobju …« |
| `${cPeriodAcc}` | »LETO …«, »MESEC …« ali »OBDOBJE …« |
| `${cPeriodStart}` | Začetek obdobja |
| `${cPeriodEnd}` | Konec obdobja |
| `${cDatePrint}` | Datum izpisa |

### Pregledi delovne opreme

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowDevInspBuName}` | Obrat / poslovna enota |
| `${rowDevInspPPCnt}` | Število preventivnih pregledov |
| `${rowDevInspPPCert}` | Število izdanih potrdil za preventivne preglede |
| `${rowDevInspKPCnt}` | Število kontrolnih / prvih pregledov |
| `${rowDevInspKPCert}` | Število izdanih potrdil za kontrolne / prve preglede |
| `${cDevInspCnt}` | Skupaj pregledanih naprav |
| `${cDevCertCnt}` | Skupaj izdanih potrdil |

### Delovna oprema, ki ne izpolnjuje pogojev

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowDevNoncCode}` | Šifra |
| `${rowDevNoncName}` | Naziv opreme |
| `${rowDevNoncSerial}` | Tovarniška številka |
| `${rowDevNoncNrDev}` | Številka stroja |
| `${rowDevNoncManuf}` | Proizvajalec |
| `${rowDevNoncModel}` | Tip / model |
| `${rowDevNoncDate}` | Datum pregleda |
| `${rowDevNoncCert}` | Številka zapisnika |
| `${rowDevNoncPass}` | Rezultat pregleda |
| `${rowDevNoncDateValid}` | Datum naslednjega pregleda |
| `${rowDevNoncNote}` | Opombe |
| `${rowDevNoncLoc}` | Lokacija |
| `${cDevNoncCnt}` | Število neskladnih naprav |

### Meritve

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowDateMes}` | Datum meritve |
| `${rowTypeMes}` | Vrsta meritve |
| `${rowLnameMes}` | Poslovna enota |
| `${rowNrMes}` | Številka zapisnika |
| `${rowValidMes}` | Veljavnost v mesecih |

### Usposabljanja po obratih

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowEduBuName}` | Obrat / poslovna enota |
| `${rowEduBuTeorCnt}` | Število udeležencev — teorija |
| `${rowEduBuPraktCnt}` | Število udeležencev — praksa |

### Tečaji v obdobju

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowCourseDate}` | Datum začetka |
| `${rowCourseType}` | Tip tečaja |
| `${rowCourseLoc}` | Lokacija |
| `${rowCourseNrRep}` | Številka zapisnika |
| `${rowCourseCnt}` | Število udeležencev |
| `${rowCoursePraktCnt}` | Število udeležencev praktičnega dela |
| `${cCourseCnt}` | Število tečajev v obdobju |

### Udeleženci tečajev

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowCourseAttName}` | Ime in priimek |
| `${rowCourseAttBirth}` | Datum rojstva |
| `${rowCourseAttWplace}` | Delovno mesto |
| `${rowCourseAttBu}` | Poslovna enota |
| `${rowCourseAttType}` | Tip usposabljanja |
| `${rowCourseAttDate}` | Datum začetka |
| `${rowCourseAttDateP}` | Datum praktičnega dela |
| `${rowCourseAttPass}` | Opravil (DA/NE) |
| `${rowCourseAttDateValid}` | Datum veljavnosti |
| `${cCourseAttCnt}` | Število udeležencev |

### Funkcionalno znanje

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowFuncKnowName}` | Tip usposabljanja |
| `${rowFuncKnowCnt}` | Število zaposlenih z veljavnim usposabljanjem |

### Zaposleni brez veljavnega VZD/VPP usposabljanja

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowTinpName}` | Ime in priimek |
| `${rowTinpBirth}` | Datum rojstva |
| `${rowTinpCode}` | Šifra BVD |
| `${rowTinpCost}` | Šifra DM |
| `${rowTinpWplace}` | Delovno mesto |
| `${rowTinpBu}` | Poslovna enota |
| `${rowTinpMnt}` | Veljavnost v mesecih |
| `${rowTinpDateTeor}` | Veljavnost teorije |
| `${rowTinpDatePrakt}` | Veljavnost prakse |
| `${cTinpCnt}` | Število zaposlenih brez veljavnega usposabljanja |

### Poškodbe pri delu

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowAccidentDate}` | Datum poškodbe |
| `${rowAccidentReg}` | Registrska številka |
| `${rowAccidentEmp}` | Šifra zaposlenega |
| `${rowAccidentName}` | Ime in priimek |
| `${rowAccidentBirth}` | Datum rojstva |
| `${rowAccidentWplace}` | Delovno mesto |
| `${rowAccidentBu}` | Poslovna enota |
| `${rowAccidentLoc}` | Lokacija |
| `${rowAccidentInjury}` | Vrsta poškodbe |
| `${rowAccidentCause}` | Vzrok |
| `${rowAccidentManner}` | Način nastanka |
| `${rowAccidentBody}` | Poškodovani del telesa |
| `${rowAccidentDevice}` | Naprava / sredstvo |
| `${rowAccidentDesc}` | Opis |
| `${cAccidentCnt}` | Število poškodb |

### Zdravniški pregledi

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowMedicDate}` | Datum pregleda |
| `${rowMedicType}` | Vrsta pregleda |
| `${rowMedicReason}` | Razlog |
| `${rowMedicName}` | Ime in priimek |
| `${rowMedicBirth}` | Datum rojstva |
| `${rowMedicCode}` | Šifra |
| `${rowMedicCost}` | Stroškovno mesto |
| `${rowMedicWplace}` | Delovno mesto |
| `${rowMedicBu}` | Poslovna enota |
| `${rowMedicMnt}` | Veljavnost v mesecih |
| `${rowMedicDateValid}` | Datum veljavnosti |
| `${cMedicCnt}` | Število pregledov |

Potekli zdravniški pregledi:

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowMedicExpType}` | Vrsta pregleda |
| `${rowMedicExpReason}` | Razlog |
| `${rowMedicExpName}` | Ime in priimek |
| `${rowMedicExpBirth}` | Datum rojstva |
| `${rowMedicExpCode}` | Šifra |
| `${rowMedicExpCost}` | Stroškovno mesto |
| `${rowMedicExpWplace}` | Delovno mesto |
| `${rowMedicExpBu}` | Poslovna enota |
| `${rowMedicExpDateExam}` | Datum pregleda |
| `${rowMedicExpDateValid}` | Datum veljavnosti |
| `${cMedicExpCnt}` | Število poteklih pregledov |

### VPP dokumenti in vaje evakuacije

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowDocName}` | Naziv dokumenta |
| `${rowDocType}` | Tip dokumenta |
| `${rowVppDocDate}` | Datum dokumenta |
| `${rowDocBu}` | Objekt / poslovna enota |
| `${rowDocLoc}` | Lokacija |
| `${rowEvacName}` | Naziv vaje / zapisnik |
| `${rowEvacDate}` | Datum vaje |
| `${rowEvacLoc}` | VPP objekt |
| `${rowEvacBu}` | Lokacija / poslovna enota |

### Drugi podprti bloki periodičnih predlog

| Blok | Spremenljivke |
|------|---------------|
| `${rowEduDate}` | `${rowEduNrPers}`, `${rowEduDate}`, `${rowEduNrRep}`, `${rowEduLname}`, `${rowEduType}` |
| `${rowEduDateVPP}` | `${rowEduNrPersVPP}`, `${rowEduDateVPP}`, `${rowEduNrRepVPP}`, `${rowEduLnameVPP}`, `${rowEduTypeVPP}` |
| `${rowNrGdev}` | `${rowNrDevGdev}`, `${rowDateGdev}`, `${rowNrGdev}`, `${rowLnameGdev}`, `${rowTypeGdev}` |
| `${rowNameRas}` | `${rowDateRas}`, `${rowNameRas}`, `${rowLnameRas}` |
| `${rowNameRassl}` | `${rowWpnameRassl}`, `${rowDateRassl}`, `${rowNameRassl}`, `${rowLnameRassl}` |

### Posebne periodične predloge

#### Poškodbe pri delu — `sij-poskodbe` in `ostali-poskodbe`

Blok `${blockAccBu}` … `${/blockAccBu}` se ponovi za vsak obrat.

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowAccBuName}` | Naziv obrata |
| `${rowAccBuCnt}` | Število zapisov v obratu |
| `${rowAccidentNr}` | Zaporedna številka |
| `${rowAccidentReg}` | Registrska številka |
| `${rowAccidentEmp}` | Šifra zaposlenega |
| `${rowAccidentName}` | Ime in priimek |
| `${rowAccidentBirth}` | Datum rojstva |
| `${rowAccidentWplace}` | Delovno mesto |
| `${rowAccidentDate}` | Datum poškodbe |
| `${rowAccidentCause}` | Vzrok |
| `${rowAccidentManner}` | Način nastanka |
| `${rowAccidentInjury}` | Vrsta poškodbe |
| `${rowAccidentBody}` | Poškodovani del telesa |
| `${rowAccidentDesc}` | Opis (v predlogi `sij-poskodbe` je na voljo tudi `${rowAccidentDescRow}`) |
| `${cName}` | Stranka |
| `${cAccidentCnt}` | Število poškodb |
| `${cPeriodStart}`, `${cPeriodEnd}` | Meje obdobja |
| `${cDatePrint}` | Datum izpisa |

#### Zapadla delovna oprema po podjetjih — `Zapadla delovna oprema po podjetjih`

Blok `${blockAccBu}` … `${/blockAccBu}` se ponovi za vsak obrat.

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowAccBuName}` | Naziv obrata |
| `${rowDevNr}` | Zaporedna številka |
| `${rowDevBvd}` | Šifra BVD |
| `${rowDevName}` | Naziv opreme |
| `${rowDevFactoryNr}` | Tovarniška številka |
| `${rowDevMachineNr}` | Številka stroja |
| `${rowDevManufacturer}` | Proizvajalec |
| `${rowDevDate}` | Datum pregleda |
| `${rowDevReportNo}` | Številka zapisnika |
| `${rowDevStatus}` | Status |
| `${rowDevNextDate}` | Naslednji pregled |
| `${rowDevResult}` | Rezultat |
| `${rowDevLocation}` | Lokacija |
| `${cName}` | Stranka |
| `${cPeriodStart}`, `${cPeriodEnd}` | Meje obdobja |
| `${cDatePrint}` | Datum izpisa |

#### Zapadla VZD/VPP usposabljanja — `Zapadla VZD VPP usposabljanja`

Blok `${blockAccBu}` … `${/blockAccBu}` se ponovi za vsak obrat.

| Spremenljivka | Pomen |
|---------------|-------|
| `${rowAccBuName}` | Naziv obrata |
| `${rowAccBuCnt}` | Število zaposlenih v obratu |
| `${rowTrainingNr}` | Zaporedna številka |
| `${rowName}` | Ime in priimek |
| `${rowDateBirth}` | Datum rojstva |
| `${rowBvd}` | Šifra BVD |
| `${rowDm}` | Šifra DM |
| `${rowSm}` | Šifra SM |
| `${rowWorkPlace}` | Delovno mesto |
| `${rowRok}` | Prejšnji od datumov veljavnosti teorije in prakse |
| `${rowVzdTeor}` | Veljavnost teoretičnega dela |
| `${rowVzdPrakt}` | Veljavnost praktičnega dela |
| `${cName}` | Stranka |
| `${cPeriodStart}`, `${cPeriodEnd}` | Meje obdobja |
| `${cDatePrint}` | Datum izpisa |

---

## Sistemi APZ (SAPZ) — (če predloge zahtevajo)

Posamezne:

- `${vppObjName}` Naziv VPP objekta
- `${dateRep}` Datum poročila
- `${dateValid}` Datum veljavnosti
- `${typeName}` Tip SAPZ
- `${descName}` Naziv sistema in proizvajalci
- `${infoLast}` Opis zadnjega pregleda
- `${descGeneral}`, `${descBuildPerm}`, `${descBuildLaw}`, `${descManufactDocs}`
- `${descTehSuperv}`, `${descDuration}`, `${descCharReq}`, `${descCheckMeth}`, `${descPers}`

---

Opombe za avtorje predlog:

- Bloke vedno odstranite, ko ni podatkov: `cloneBlock('blockName', 0)`.
- Tabele klonirajte z natančnim številom vrstic; indeksi so oblike `varName#1`, `varName#2`, ...
- Pri sekvenčnem polnjenju znotraj bloka uporabljajte `setValue('var', $val, 1)` za napredovanje na naslednji pojavi spremenljivke v bloku.
- Večvrstična polja (opis, rezultat) pretvorite v Word prelome: zamenjava prelomov z `</w:t><w:br/><w:t>`.
