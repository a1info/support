# Legenda spremenljivk (DOCX/FORM)

Ta stran združuje vse skupne (generične) spremenljivke in spremenljivke po tipih poročil/predlog, kot jih uporabljajo kontrolerji in podloge v sistemu Optima Prevent.

Oznake:
- Posamezne (single): enovrednostne spremenljivke.
- Tabele (rows): vrstične spremenljivke za uporabo z `cloneRow('...')`.
- Bloki (clone): ponavljajoči se odseki med `${block}` in `${/block}` (lahko vsebujejo tudi tabelarne spremenljivke).

[← Nazaj na Priročnik](manual-sl.md)

---

## Skupne (generične) spremenljivke

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

## Zapisnik o usposabljanju (Education)

Posamezne:

- `${dateRep}` Datum zapisnika
- `${dateStart}` Datum začetka usposabljanja
- `${custNrRep}` Številka zapisnika
- `${txtCust1}` Tekst po meri 1
- `${txtCust2}` Tekst po meri 2
- `${txtLaw}` Tekst zakonskih odredb
- `${nrHour}` Število ur usposabljanja
- `${nrProg}` Program usposabljanja
- `${location}` Lokacija
- `${mntValid}` Veljavnost — št. mesecev

Tabele — edinstven seznam delavcev:

- `${rowNameUn}` Ime in priimek
  - `${rowCntUn}` Zap. št.
  - `${rowDateBirthUn}` Datum rojstva
  - `${rowWorkPlaceUn}` Delovno mesto
  - `${rowEduTypeUn}` Tip usposabljanja

Tabele — seznam delavcev:

- `${rowName}` Ime in priimek
  - `${rowCnt}` Zap. št.
  - `${rowDateBirth}` Datum rojstva
  - `${rowWorkPlace}` Delovno mesto
  - `${rowNrRep}` Številka potrdila
  - `${rowEduType}` Tip usposabljanja
  - `${rowNrProg}` Program usposabljanja
  - `${rowRes}` Uspešno / Neuspešno

Tabele — seznam tečajev v zapisniku:

- `${rowEdulstEdutype}` Tip usposabljanja
  - `${rowEdulstMntValid}` Veljavnost

Bloki:

- `${cloneCert0}` … `${/cloneCert0}` (blok potrdil)
  - `${attName}` Ime in priimek
  - `${attWorkPlace}` Delovno mesto
  - `${attDateBirth}` Datum rojstva
  - `${attDateValid}` Datum veljavnosti potrdila
  - `${attMntValid}` Velja — meseci
  - `${attDateEtest}` Datum opravljanja usposabljanja
  - `${attLocName}` Poslovna enota
  - `${attLocAddress}` Naslov PE
  - `${attLocCity}` Mesto PE

---

## Zapisnik o pregledu delovne opreme (MDEVICE)

Posamezne:

- `${dateRep}` Datum zapisnika
- `${dateTest}` Datum pregleda
- `${devUser}` Uporabnik delovne opreme
- `${devUserAddr}` Naslov uporabnika opreme
- `${custNrRep}` Številka zapisnika
- `${dateLastRep}` Datum zadnjega pregleda
- `${nrLastRep}` Št. zadnjega pregleda
- `${infoLast}` Opis zadnjega pregleda
- `${txtType}` Tip pregledov
- `${desc}` Opis metodologije
- `${result}` Skupni rezultat

Tabele — kratek seznam pregledane opreme:

- `${rowShortName}` Naziv opreme
  - `${rowShortCnt}` Zap. št.
  - `${rowShortResult}` Rezultat pregleda
  - `${rowInstName}` Naziv merilnika
  - `${rowInstCert}` Certifikat merilnika

Tabele — podroben seznam:

- `${lstName}` Naziv opreme
  - `${lstNrRep}` Št. potrdila
  - `${lstDateTest}` Datum pregleda
  - `${lstSerial}` Serijska št.
  - `${lstNrInv}` Inventarna št.
  - `${lstLocation}` Mikro lokacija pregleda
  - `${lstLocationObj}` Mikro lokacija objekta
  - `${lstTypeDevice}` Tip / model
  - `${lstDesc}` Dodatni opis
  - `${lstDoc}` Predložena dokumentacija
  - `${lstResult}` Rezultat pregleda
  - `${lstIndPass}` Indikator ustreznosti
  - `${lstManufacturer}` Proizvajalec
  - `${lstManufactYear}` Leto izdelave
  - `${lstMesOhm}` Izmerjena upornost
  - `${lstChkName}` Preizkusi po meri
  - `${lstChkResult}` Rezultat preizkusa po meri
  - `${lstChkValue}` Izmerjena vrednost preizkusa po meri
  - `${lstChkSist}` Referenčna vrednost preizkusa po meri
  - `${lstChkElecName}` Električni preizkusi po meri
  - `${lstChkElecResult}` Rezultat el. preizkusa
  - `${lstChkElecValue}` Izmerjena vrednost el. preizkusa
  - `${lstChkElecSist}` Referenčna vrednost el. preizkusa

Bloki:

- `${cloneDevLst}` … `${/cloneDevLst}` (info blok opreme)
- `${cloneCert0}` … `${/cloneCert0}` (blok potrdil)
  - `${devUsage}` Namen opreme

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

## Kartica stranke (povzetek) — CustomercardController

Posamezne:

- Sistem: `${sysName}`, `${sysAddress}`, `${sysCity}`
- Stranka: `${cName}`, `${cNameFull}`, `${cAddress}`, `${cZip}`, `${cCity}`
- Kontakti: `${cTel}`, `${cMail}`, `${cContact}`
- Poslovna enota: `${locName}`, `${locAddress}`, `${locZip}`, `${locCity}`
- Ostalo: `${cPersResp}`, `${cTaxNr}`, `${cRegId}`, `${cBusCode}`, `${cBusCodeName}`

Bloki:

- `${cloneRecot}` … `${/cloneRecot}` — kategorije “recot”
  - Posamezne: `${recotCatName}`
  - Tabela `${rowRecotName}`:
    - `${rowRecotCnt}`, `${rowRecotName}`, `${rowRecotBU}`, `${rowRecotMntValid}`, `${rowRecotDate}`, `${rowRecotDesc}`, `${rowRecotResult}`

Tabele:

- Usposabljanja (veljavnost):
  - `${rowEduDateStart}`:
    - `${rowEduCnt}`, `${rowEduNrPers}`, `${rowEduDateStart}`, `${rowEduDateEnd}`, `${rowEduMntValid}`, `${rowEduNrRep}`, `${rowEduName}`, `${rowEduType}`, `${rowEduBU}`

- Pregledi delovne opreme (skupine):
  - `${rowGdevNr}`:
    - `${rowGdevCnt}`, `${rowGdevNrDev}`, `${rowGdevDate}`, `${rowGdevDateValid}`, `${rowGdevNr}`, `${rowGdevBU}`, `${rowGdevType}`

- Meritve:
  - `${rowMesNr}`:
    - `${rowMesCnt}`, `${rowMesDate}`, `${rowMesDateEnd}`, `${rowMesMntValid}`, `${rowMesNr}`, `${rowMesBU}`, `${rowMesName}`, `${rowMesType}`

- RASS skupine:
  - `${rowRasName}`:
    - `${rowRasCnt}`, `${rowRasDate}`, `${rowRasNr}`, `${rowRasName}`, `${rowRasBU}`

- VPP evakuacije:
  - `${rowVppEvacDate}`:
    - `${rowVppEvacCnt}`, `${rowVppEvacName}`, `${rowVppEvacDate}`, `${rowVppEvacDateValid}`, `${rowVppEvacObj}`, `${rowVppEvacLoc}`

- VPP odgovorne osebe:
  - `${rowVppRespName}`:
    - `${rowVppRespCnt}`, `${rowVppRespName}`, `${rowVppRespDepart}`, `${rowVppRespShift}`, `${rowVppRespBU}`, `${rowVppRespObj}`

- VPP dokumenti:
  - `${rowVppDocName}`:
    - `${rowVppDocCnt}`, `${rowVppDocName}`, `${rowVppDocCatName}`, `${rowVppDocDate}`, `${rowVppDocObj}`, `${rowVppDocMntValid}`

---

## Letno poročilo za stranke (obvestilo) — ReportcustnoticeController

Posamezne:

- Lokacija ali stranka (glava): `${locName}`, `${locAddress}`, `${locZip}`, `${locCity}`
- Stranka (glava): `${cName}`, `${cAddress}`, `${cZip}`, `${cCity}`
- Kontakt in identifikacija:
  - `${cContact}` Odgovorna oseba (glavni kontakt ali fallback na customer.contact)
  - `${cTaxNr}`, `${cRegId}`, `${cBusCode}`, `${cBusCodeName}`
  - `${nrProg}` Program (če obstaja)
  - `${cPersResp}`, `${cPersMed}` (iz RASS)

Tabele — usposabljanja (v letu):

- `${rowEduDate}`:
  - `${rowEduNrPers}`, `${rowEduDate}`, `${rowEduNrRep}`, `${rowEduLname}`, `${rowEduType}`

Tabele — usposabljanja za VPP (v letu):

- `${rowEduDateVPP}`:
  - `${rowEduNrPersVPP}`, `${rowEduDateVPP}`, `${rowEduNrRepVPP}`, `${rowEduLnameVPP}`, `${rowEduTypeVPP}`

Tabele — usposabljanja s potekom do konca naslednjega leta:

- `${rowEduDateExpP}`:
  - `${rowEduNrPersP}`, `${rowEduDateP}`, `${rowEduDateExpP}`, `${rowEduNrRepP}`, `${rowEduLnameP}`, `${rowEduTypeP}`

Tabele — pregledi delovne opreme (v letu):

- `${rowNrGdev}`:
  - `${rowNrDevGdev}`, `${rowDateGdev}`, `${rowNrGdev}`, `${rowLnameGdev}`, `${rowTypeGdev}`

Tabele — pregledi delovne opreme s potekom do konca naslednjega leta:

- `${rowNrGdevP}`:
  - `${rowNrDevGdevP}`, `${rowDateGdevP}`, `${rowDateExpGdevP}`, `${rowNrGdevP}`, `${rowLnameGdevP}`, `${rowTypeGdevP}`

Tabele — meritve (v letu):

- `${rowNrMes}`:
  - `${rowDateMes}`, `${rowValidMes}`, `${rowNrMes}`, `${rowLnameMes}`, `${rowTypeMes}`, `${rowTypeCheckMes}`

Tabele — meritve s potekom do konca naslednjega leta:

- `${rowNrMesP}`:
  - `${rowDateMesP}`, `${rowDateExpMesP}`, `${rowValidMesP}`, `${rowNrMesP}`, `${rowLnameMesP}`, `${rowTypeMesP}`, `${rowTypeCheckMesP}`

Tabele — RASS skupine:

- `${rowNameRas}`:
  - `${rowDateRas}`, `${rowNrRas}`, `${rowNameRas}`, `${rowLnameRas}`

Tabele — VPP dokumenti:

- `${rowDocName}`:
  - `${rowDocName}`, `${rowDocType}`, `${rowDocDate}`, `${rowDocSo}`, `${rowDocBu}`, `${rowDocLoc}`

Tabele — VPP evakuacije:

- `${rowEvacBu}`:
  - `${rowEvacDate}`, `${rowEvacBu}`, `${rowEvacLoc}`

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