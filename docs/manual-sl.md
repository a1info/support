# Navodila za uporabo — Optima Prevent v5.1

## Uvod

Optima Prevent je EHS (Environmental Health and Safety) sistem, prilagojen zakonodaji Republike Slovenije. Upošteva aktualne mednarodne standarde in napotke (OHSAS, ISO). Namenjen je organizacijam in službam, ki se ukvarjajo z varnostjo in zdravjem pri delu, za celovito in enostavno vodenje dela ter popoln nadzor nad kompleksom procesov.

Modularna arhitektura in večplastni dizajn omogočata visoko raven prilagodljivosti za vse vrste organizacij, ne glede na velikost ali dejavnost. Aplikacija je sestavljena iz medsebojno povezanih modulov, zato so vse spremembe takoj vidne tam, kjer so relevantne.

Tehnologija EAV (Entity-Attribute-Value) omogoča dodajanje atributov po meri, kar zagotavlja fleksibilnost pri vnosu in prikazu podatkov.

Klient/strežnik arhitektura s transakcijsko SQL komunikacijo omogoča istočasni dostop vseh uporabnikov brez tveganja izgube podatkov ali sočasnega konflikta pri urejanju.

Razvojne tehnologije: PHP 8, MVC (Model-View-Controller) — Laravel 9.x, z Livewire in jQuery 2 na uporabniškem vmesniku. Podatkovni sloj podpira PostgreSQL in Oracle.

Vsi sloji dostopa do podatkov so šifrirani: SQL baza, datotečni sistem, omrežni prenos (SSL/VPN). Za GDPR skladnost se sejni piškotki hranijo v šifrirani SQL bazi. Obravnava osebnih podatkov je skladna z GDPR in dokumentirana v priloženi dokumentaciji Optima Prevent.

Optima Prevent je blagovna znamka podjetja A1 Informatika d.o.o. in je registrirana pri Avtorski agenciji RS pod številko 030/19.


## Vmesnik in prijava

### Vmesnik sistema Optima Prevent

Vmesnik je odziven (responsive) in se prilagaja mobilnim napravam. Za popoln prikaz in učinkovito delo priporočamo zaslone z najmanj 1024×768. Vmesniki prikazujejo veliko informacij, zato je večja površina zaslona prednost.

### Prijava v sistem

Za dostop potrebujete IP ali domeno strežnika, kjer je nameščena aplikacija. Prvi prikaz ob obisku je prijavna stran. Prijava: e-poštni naslov in geslo. Po prijavi je uporabnik preusmerjen na nadzorno ploščo (Dashboard), prilagojeno tipu uporabnika.

Do nadzorne plošče dostopate s klikom na logotip Optima Prevent v zgornjem levem kotu.


## Navigacija in skupne akcije

### Meni in navigacija

Uporabniški vmesnik vsebuje:
- glavni levi meni (skupine padajočih menijev po funkcionalnih sklopih),
- zgornji uporabniški meni (obvestila, interna sporočila, profil, odjava),
- izbirnik aktivne stranke (zgoraj desno).

Po izbiri aktivne stranke so vnosni in urejevalni vmesniki avtomatsko nastavljeni na izbrano stranko. Administratorji lahko vnašajo podatke v imenu drugih uporabnikov (dodatno polje za izbiro uporabnika).

Parametri filtriranja so prikazani nad seznami.

### Skupne (bulk) akcije

Seznami z več podatki omogočajo skupne akcije nad izbranimi vrsticami. Izbor vrstice z označitvenim poljem na desni strani; za izbor vseh vrstic označite polje v glavi tabele. Po izboru določite akcijo nad tabelo.

Vmesniki s skupnimi akcijami:
- seznam delovne opreme — brisanje, kaskadno brisanje (briše tudi preglede), skupni pregled (za preglede z enakimi parametri),
- seznam pregledov — brisanje,
- seznam zaposlenih — brisanje,
- seznam usposabljanj — brisanje.


## Sistemske nastavitve

Dostop: Sistem → Nastavitve

Obvezni in ključni podatki:
- ime in polno ime matične družbe,
- DDV številka,
- registrska številka,
- sedež (naslov),
- akreditacije RS,
- kontakt (telefon, mobilni, e-pošta, spletna stran),
- logotip,
- certifikat za podpisovanje dokumentov itd.

V razdelku »Moduli« upravljate izbirne sistemske module in vnašate licence.

### Nadgradnja sistema

V razdelku »Nadgradnja« je prikazana trenutna verzija. Če je sistem posodobljen, gumb za nadgradnjo ni prikazan.

### Digitalno podpisovanje dokumentov

Dostop: Nastavitve → Sistem

Podprti so P12 certifikati z geslom. Za samodejno podpisovanje PDF dokumentov dodajte P12 certifikat in geslo. Po tem bodo vsi PDF dokumenti samodejno digitalno podpisani in vidni uporabnikom strank po prijavi.


## Uporabniki

### Sistemski uporabniki

Sistemski uporabniki (zaposleni matične družbe) spadajo v skupine:
- Administratorji,
- Operaterji,
- Uporabniki.

Pravice:
- Uporabniki: dostop do lastnih in skupinskih podatkov; brez pravic nad sistemskimi nastavitvami.
- Operaterji: vpogled v vse podatke, delo v tujem imenu; brez pravic nad sistemskimi nastavitvami.
- Administratorji: polne pravice pregleda in urejanja.

### Uporabniki strank

Uporabniki strank (njihovi zaposleni) imajo, glede na dodeljene pravice, dostop do delov aplikacije z informacijami svoje stranke. Modulne pravice:
- delovna oprema,
- zaposleni,
- osebna varovalna oprema,
- zdravniški pregledi,
- delovne nezgode,
- naročila,
- evidence požarne varnosti.

Pravice je možno dodeliti samo za pregled ali za pregled in urejanje.

### Prijava uporabnika stranke

URL za prijavo: https://naslov_vaše_inštalacije/mod-cust  
Primer: https://demo.optima-prevent.eu/mod-cust

Uporabniško ime je e-poštni naslov; geslo določite ob vnosu uporabnika. Geslo lahko uporabnik po prvi prijavi spremeni.

### Dostop strank do lastnih podatkov

Po prijavi je prikazan Dashboard s splošnimi informacijami in hitrimi povezavami.

- Dokumenti: Dostop prek menija »Dokumenti«.
- Koledar veljavnosti (Periodika): Dostop prek menija »Periodika«.
- Seznam zaposlenih: Dostop prek menija »Zaposleni«.

Prijavno stran za stranke je možno prilagoditi.


## Začetna nastavitev in vnos podatkov

Dostop: Sistem → Nastavitve → Sistem

### Migracija podatkov

Migracija omogoča uvoz zgodovinskih podatkov iz drugih programov ali Excel datotek. Ker se ob migraciji kreirajo bazni podatki in povezane operacije, postopek izvedite skrbno in v koordinaciji z razvijalcem Optima Prevent.

### Avtomatično številčenje dokumentov

Vsi izdani dokumenti so avtomatično oštevilčeni s števci, prilagodljivimi pravilom matične družbe. Številčijo se:
- zapisniki o usposabljanju,
- potrdila o usposabljanju,
- zapisniki o pregledih delovne opreme,
- potrdila za delovno opremo,
- ocene tveganja,
- EKO/VZD meritve.

Parametri: leto, stranka, tip dokumenta. Konfiguracija je v tekstovni datoteki in podpira različne kombinacije.

### Uvoz Excel datotek

Funkcija uvoza je na seznamih: Stranke, Delovna oprema, Zaposleni, Vprašalniki, Osebna varovalna oprema, VPP.

Pravila:
- Uporabljajte predloge (template) na vnosnih maskah (npr. tplImportXXX.xlsx).
- Prva vrstica (imena polj) mora biti enaka kot v predlogi.
- Shranjevanje v UTF-8 (pravilen prikaz šumnikov).
- Izogibajte se dodatnemu oblikovanju.
- Urejajte predlogo v LibreOffice in vnesite podatke (copy/paste). Nato jo uvozite in preverite rezultat (uspešno/neuspešno).

Opomba: Za uvoz v poslovno enoto stranke najprej izberite aktivno stranko v zgornjem meniju.

### Teksti po meri

Teksti po meri so ponavljajoča se besedila, ki se preko spremenljivk dodeljujejo v vmesnike (npr. `txtDevRes` za polje »Ugotovitev« pri pregledu delovne opreme). Seznam spremenljivk je na vmesnikih modulov.

V razdelku »Polja za prikaz« so izbirna polja za različne module. Če jih ne potrebujete, jih onemogočite, da ne obremenjujejo vnosnih mask.

Dostop: Seznami → Teksti po meri

### Polja po meri (EAV)

Modul omogoča dodajanje atributov objektom in operacijam (npr. dodatna polja za delovno opremo ali zaposlene), vidnih v celotnem sistemu (uvoz, izvoz, prikaz, predloge).

Sistem ob dodelitvi atributa generira kodo polja. Za prikaz v predlogah uporabite kodo s prefiksom pozicije spremenljivke, npr. `${lst<code>}` ali `${dev<code>}`.

Dostop: Seznami → Polja po meri


## Stranke in poslovne enote

### Stranke

Stranke so naročniki in prejemniki storitev matične družbe. Vsaka stranka in poslovna enota lahko vsebujeta zapise zaposlenih in delovne opreme, na katere se navezujejo operacije in dokumenti.

Dostop: glavni meni → Stranke

Obvezna polja: Naziv, Naslov, Mesto, DDV številka.  
Možen je samodejni vnos podatkov prek Ajpes: vnesite DDV št. in izberite možnost »Najdi«.

Dodatno:
- »Šifra po meri«: neobvezno (npr. šifra v računovodskem programu).
- »Skrbnik« stranke: izberite uporabnika, ki prejema obvestila.
- Stranko lahko deaktivirate (ohranite zgodovino).
- Možno je izključiti spremljanje veljavnosti (stranka se ne prikaže v analitiki).

### Poslovne enote

Če ima stranka več lokacij, jih vnesite kot poslovne enote. Sedež je vedno ena od poslovnih enot (ni ga možno brisati).

Poslovne enote so pomembne za organizacijo dela pri večjih strankah (lokacije zaposlenih, delovne opreme itd.).

Urejanje lokacij: na seznamu strank izberite »Uredi lokacije«.


## Zaposleni

Modul za upravljanje zaposlenih strank je povezan z drugimi moduli (usposabljanja, OVO, zdravniški pregledi, delovne nezgode, ocene tveganja itd.).

Dostop: glavni meni → Zaposleni

- Ob izbiri aktivne stranke so prikazani samo njeni zaposleni.
- Na desni so možnosti za Excel uvoz in filtriranje.
- Sistem preverja podvojene zapise, vseeno pred vnosom preverite obstoj.
- Na seznamu lahko urejate, deaktivirate ali ustvarite PDF poročilo zgodovine zaposlenega.
- Če obstaja zgodovina, brisanje ni možno; zapis se deaktivira (možna ponovna aktivacija).


## CRM (organizacija nalog)

CRM modul omogoča pregled in organizacijo dela z naročniki (koledar, projekti, naloge).

### Naloge

- Prikazane so v koledarju; logično so razdeljene po koledarjih in projektih.
- Administratorji vidijo vse naloge in jih razporejajo med uporabnike.
- Navadni uporabniki vidijo svoje naloge.
- Odprte naloge so vidne na uporabniškem Dashboardu.

Parametri naloge:
- naziv,
- začetek/konec,
- status,
- dodeljen uporabnik,
- stranka,
- koledar/projekt,
- seznam storitev in odgovornih oseb.

Seznam storitev urejajo administratorji (Nastavitve → Storitve).

### Koledarji

- Privzeti: koledar naročil in koledar periodike.
- Administratorji lahko dodajajo dodatne koledarje.
- Koledar periodike se generira samodejno in se posodablja ob vnosu operacij z veljavnostjo (tečaji, pregledi).
- Koledar periodike priporočamo uporabljati samo za branje.
- Za urejanje nalog uporabite koledar naročil in ostale ročno dodane koledarje.

Dodajanje koledarja: izberite možnost »Dodaj koledar«.

### Projekti

Projekt združuje naloge, datoteke in komentarje v kronološko organiziran zabojnik.

- Dostop: CRM → Projekti → Ogled
- Pravice ogleda/urejanja: možno omejiti na uporabnike; privzeto dostopno vsem.

### Delovni nalog

Na seznamu nalog lahko izpišete delovne naloge (PDF) kot potrdilo o opravljenem delu (vključno s prostorom za podpis stranke). Oblika je prilagodljiva.


## Usposabljanje

Modul je večplasten: usposabljanja, zapisniki, udeleženci, e-test.

- Seznam tečajev: Usposabljanje → Seznam tečajev
- Zapisniki: Usposabljanje → Zapisniki (združujejo več tečajev različnih tipov)

### Tipi tečajev

Dostop: Usposabljanje → Tipi tečajev

Določite:
- tip (VPP, VZD, VPP ODG ...),
- ločeno številčenje,
- priloge,
- zakonske podlage itd.

### Dodajanje tečaja

Usposabljanje → Seznam tečajev → »Dodaj tečaj«

Vnos:
- stranka in poslovna enota (obvezno),
- lokacija tečaja,
- tip tečaja (VZD, VPP, VPP ODG ...),
- datum začetka (obvezno),
- veljavnost (v letih).

Nato dodate udeležence (zaposlene). Uporabite hitri filter v tabeli zaposlenih.  
Opomba: Naknadno dodajanje ali brisanje udeležencev iz tečaja ni dovoljeno.

### Oddaljeno usposabljanje

Pri vnosu tečaja izberite vprašalnik za e-test (modul »etest«).  
- Udeležencem se status nastavi na negativno do uspešno opravljenega testa.  
- Po uspehu se status spremeni v pozitivno in dodeli številka potrdila (če je omogočeno avtomatično številčenje).

Dostop do e-testa: https://naslov_vaše_inštalacije/mod-etest  
Prijavno predlogo (HTML5) je možno prilagoditi.

### Vprašalniki za oddaljeno usposabljanje

Dostop: Usposabljanje → Vprašalniki

1) Splošne informacije:
- naslov, opis, zahtevan prag uspešnosti (privzeto 80%),
- opcijski ZIP (HTML5 gradivo iz iSpring/H5P) pred začetkom testa,
- opcijski formular (FORM) ob zaključku (obvezen/neobvezen).

2) Vprašanja:
- opcijska priloga (PDF/MP4) pred vprašanjem,
- dodelitev točk (privzeto 2; možnost prilagoditve).


## Delovna oprema

Modul vključuje: delovno opremo, preglede, zapisnike in QR dostop (ROA).

### Evidenca delovne opreme

Dostop: Delovna oprema → Seznam delovne opreme

Osnovni parametri:
- stranka / poslovna enota,
- naziv opreme,
- serijska in inventarna številka,
- tip/model,
- leto izdelave,
- proizvajalec,
- slike opreme,
- datum odpisa (če oprema ni več v uporabi).

Na pregledu opreme je QR koda za hiter dostop (ROA). QR je lahko uporabljen na nalepkah. Nastavitev »zahtevaj prijavo« je v sistemskih nastavitvah (privzeto javno).

### Pregledi delovne opreme

Dostop: Delovna oprema → Pregledi → Dodaj pregled

Osnovni parametri:
- stranka,
- mikro lokacija,
- datum pregleda,
- veljavnost (v letih),
- uporabnik/naslov uporabnika opreme,
- »ustreza« (da/ne),
- izbor enega kosa opreme iz tabele.

Tip pregleda: prvi, periodični ali kontrolni.

- Možno je dodati »Preizkuse po meri« (Nastavitve → Preizkusi po meri).
- Prejšnje preglede lahko kopirate (če je rezultat enak ali podoben).

### Zapisniki

Dostop: Delovna oprema → Zapisniki → Dodaj zapisnik

Postopek:
- izberite stranko,
- izberite proste preglede (tisti brez zapisnika),
- podatki: stranka/PE, datum, tip pregleda, merilniki.

Zapisnik je možno urejati, brisati in tiskati (DOCX podloga).

### QR kode — ROA (Remote Object Access)

Skeniranje QR kode prikaže informacije o opremi in zadnjem pregledu.  
- Javni prikaz je privzeto omogočen (opcijsko zahteva prijavo).
- Za ustvarjanje pregleda na terenu je potrebna prijava (sistemski uporabnik), enkrat na sejo.

### QR »bulk« ustvarjanje

Dostop: Seznami → QR ustvarjanje

Možno je ustvariti »bianko« QR kode in jih na terenu dodeljevati opremi.  
- Ob skeniranju se omogoči vnos nove opreme ali dodelitev obstoječi.  
- QR lahko ustvarite iz CSV/Excel datoteke z URL povezavami.  
- Možno je dodati logotip, kontaktne informacije itd.


## Ocene tveganj

Ocena tveganja je osrednji dokument varnostnih politik stranke. Nanj se vežejo usposabljanja, VZD/EKO meritve, OVO, zdravniški pregledi, evidence nevarnih snovi in pregledi delovne opreme.

Vsi vmesniki za ocene tveganja so v glavnem meniju.

### Tveganja in kategorije

Dostop: Ocene tveganj → Urejanje tveganj

- Definirajte tveganja in kategorije ter stopnje tveganja (standardni nabor, po potrebi prilagodljiv).
- Možno je določiti splošne ukrepe za posamezna tveganja (prikažejo se v ocenah TDM).

Pomembno: Po vnosu tveganj/kategorij jih ne spreminjajte, da ne vplivate na že generirane dokumente.

### Tipična delovna mesta (TDM)

Dostop: Ocene tveganj → Seznam TDM

- Definirajte TDM-je (ime, glavna/občasna opravila, trajanje, opis dela, OVO ...). Polja se prikažejo v oceni in so urejanja.
- Izberite tveganja, ki se obravnavajo za TDM (na desni strani tabele).

### Ocene za TDM

Dostop: Ocene tveganj → Seznam ocen

Koraki:
1) izberite stranko, TDM in datum ocene;  
2) izberite zaposlene, ki spadajo pod TDM (predizbrani so tisti, že dodeljeni TDM na vmesniku Stranke → Zaposleni; ostale lahko dodate tukaj);  
3) uredite splošne podatke TDM; v tabeli tveganj vnesite R0, t, Kon, Kš, Ku ter ocene pogostosti, verjetnosti in posledic;  
4) za tveganja z vsoto F+V+P > 3 določite ukrepe in odgovorno osebo; določite periodike (usposabljanja, pregledi opreme, zdravniški pregledi, meritve).

### Dokumenti OTV

Dostop: Ocene tveganj → Dokumenti OTV

- Končni dokument je sestavljen iz več ocen TDM.  
- Izberite stranko; prikazane so ocene, ki še niso združene v končni dokument.  
- Izberite PE, datum, podlogo za izpis.  
- Na dnu je analiza varnostnega stanja (seznam po meri iz Nastavitve → Preizkusi po meri).


## VZD / EKO meritve

Dostop: glavni meni → EKO meritve

Seznam prikazuje vse opravljene meritve uporabnika; administrator vidi vse.

Filter: stranka, tip meritve, uporabnik.

### Dodajanje meritve

Postopek v 2–3 korakih:

1) Splošno:
- stranka, PE,
- datum meritve,
- podatki o predhodnih meritvah,
- datum in št. poročila,
- priloge,
- uporabljeni merilniki.

2) Tip meritve:
- delovno okolje (toplota, osvetljenost),
- elektrika,
- strelovod,
- hrup,
- pretok zraka itd.

Vnos parametrov je odvisen od tipa. Meritve se lahko zaključijo že na prvem koraku (brez parametrov), če gre le za evidenco.

Operacije: urejanje, brisanje, kopiranje, izpis iz DOCX podloge. Kopiranje prihrani čas pri podobnih meritvah.


## Požarna varnost

Dostop: Požarna varnost → Seznam objektov

Prikaz objektov glede na aktivno stranko. Dodajanje novega objekta z »Dodaj objekt«.

Osnovni parametri:
- stranka / PE,
- ocena požarne ogroženosti / št. oseb (če ogroženost ≥ 3 in št. oseb ≥ 100, se prikaže evidenca letnih vaj evakuacije),
- ostale priponke in podatki.

Možno je določiti veljavnost vnosov (št. mesecev) za spremljanje v modulu Periodika.

Evidence v okviru objekta:
- aktivna požarna zaščita (tipi APZ se urejajo v Požarna zaščita → Tip APZ),
- ročni gasilniki (možen CSV uvoz),
- usposabljanje zaposlenih (povezano z modulom usposabljanja),
- vaje evakuacije,
- kurilne in dimne naprave,
- strelovodi in elektro naprave (povezano z modulom EKO/VZD meritve),
- odgovorne osebe za PV,
- hidrantni list,
- seznam požarov in eksplozij.

Izvoz evidenc v PDF je na voljo na seznamih. Evidenco usposabljanja za začetne požare/evakuacijo lahko povežete z glavnim modulom usposabljanja (izbira tipa tečaja v vnosu objekta).


## Evidence

### Zdravniški pregledi

Dostop: Evidence → Zdravniški pregledi

Namen: spremljanje pregledov in izdajanje napotnic (predhodni, obdobni preventivni, kontrolni).

Veljavnost se spremlja v Analitiki.

Vnos:
- stranka,
- zaposleni,
- tip pregleda,
- datum pregleda,
- datum napotnice,
- veljavnost (št. mesecev),
- ostala polja za napotnico.

Polja so vezana na šifrante (ikone nad polji). Tisk napotnic v PDF.

### Ostale evidence

Dostop: Evidence → Ostale evidence

Fleksibilen modul za evidence, ki niso neposredno poimenovane drugje.

Vnos:
- stranka / PE,
- naziv evidence,
- datum,
- veljavnost (št. mesecev),
- priponke.

V Analitiki se spremlja veljavnost, če je določena.

### Delovne nezgode

Dostop: Evidence → Delovne nezgode

Vnos:
- stranka,
- zaposleni,
- podatki o osebi,
- datum dogodka,
- delovno mesto,
- kraj dogodka,
- ostala polja za izjavo o nezgodi.

Polja uporabljajo šifrante. Tisk v PDF.

### Osebna varovalna oprema (OVO)

Dostop: Evidence → Osebna varovalna oprema

Namen: spremljanje izdaje OVO zaposlenim, skladno z oceno tveganja.

Vnos:
- stranka,
- zaposleni,
- datum izdaje,
- veljavnost,
- opombe,
- seznam opreme in standardi (na desni kot pomoč).


## Analitika

### Periodika

Dostop: Analitika → Periodika

Spremlja veljavnosti:
- pregledi delovne opreme,
- veljavnosti tečajev,
- usposabljanja zaposlenih,
- evidence požarne varnosti,
- EKO/VZD meritve,
- zdravniški pregledi,
- ostale evidence.

Prikaz:
- tabele z možnostjo filtriranja (aktivna stranka, filter gumb),
- koledarski pogled (različne barve tipov: delovna oprema — rumena; EKO/VZD — zelena; usposabljanja — modra; požarna varnost — rdeča; zdravniški pregledi — vijolična; ostale evidence — siva),
- prikaz novo vnesenih zaposlenih brez usposabljanja in opreme brez pregledov.

Če je veljavnost potekla, so vrstice označene rdeče.

### Pregled realizacije

Dostop: Analitika → Pregled realizacije

Filter: datum od, datum do, uporabnik.  
Prikaz v tabelah in bar diagramih (tipi podatkov so barvno ločeni).

### Izdani dokumenti

Dostop: Analitika → Izdani dokumenti

Iskanje po: stranki (aktivna), tipu dokumenta, obdobju, zaposlenem itd.

Dokumente lahko ročno posodabljate in dodajate nove verzije:
- prenesite dokument,
- uredite lokalno,
- izberite »Nova verzija« in naložite.

### Poročilo po dejavnosti

Priprava letnih poročil o številu objektov/opreme, na katerih so bili opravljeni pregledi (v skladu z zakonodajo RS).


## Sistem obveščanja

Komunikacija je interna in zunanja.

- Interna: med uporabniki sistema (tudi uporabniki stranke) v realnem času; olajša usklajevanje in delo na projektih. Podpira transparentno obveščanje skrbnikov strank o spremembah.
- Zunanja: prek šifrirane e-pošte. Nastavitve e-pošte so v konfiguraciji sistemskih uporabnikov in v nastavitvah matične družbe.


## Urejanje podlog za izpis

### Predloge FORMS

Dostop: Nastavitve → Predloge FORM

Za netipične preglede (npr. kontrolni pregledi, vaje evakuacije). Elementi:
- naslov, podnaslov, naslov tabele, besedilo,
- polje za vnos (input),
- potrditveno polje (checkbox), dvojno potrditveno polje (da/ne),
- SQL koda.

Uporabite spremenljivke, npr. `cCustomer`, `cAddress`.

### Predloge DOCX

Uporabljajo se za potrdila/zapisnike; prilagodljive po obliki in vsebini.  
Format: DOCX, sestavljen iz statičnega (postavitev, slogi, slike) in dinamičnega dela (spremenljivke).

Vrste spremenljivk:
- Posamezne spremenljivke,
- Tabelarne spremenljivke (vrstične),
- Blok spremenljivke (ponavljajoči se paragrafi, lahko vsebujejo posamezne ali tabelarne spremenljivke).

Dostop: Nastavitve → Urejanje predlog

Pri dodajanju podloge določite ime, tip, zaporedno številko in DOCX datoteko.  
Tipi: usposabljanje, delovna oprema, meritve, ocena tveganja.  
Če je na voljo več podlog istega tipa, se privzeto uporablja podloga z najnižjo zaporedno številko (možno spremeniti pri vnosu storitve).


## Legenda spremenljivk

### Generične spremenljivke

- `${cName}` Ime stranke  
- `${cAddress}` Naslov sedeža stranke  
- `${cCity}` Mesto sedeža stranke  
- `${cZip}` Poštna št. sedeža stranke  
- `${cTax}` Davčna št. stranke  
- `${cPersResp}` Kontakt / Odgovorna oseba stranke  
- `${locContact}` Kontakt / Odgovorna oseba poslovne enote  
- `${cBusCode}` Šifra dejavnosti  
- `${cBusCodeName}` Naziv dejavnosti  
- `${locName}` Ime poslovne enote stranke (PE)  
- `${locCity}` Mesto PE  
- `${locZip}` Poštna št. PE  
- `${uName}` Ime in priimek uporabnika  
- `${uSignImg}` Podpis uporabnika  
- `${uCertDev}` Uporabniški certifikat — delovna oprema  
- `${uCertEdu}` Uporabniški certifikat — usposabljanje  
- `${uCertMes}` Uporabniški certifikat — meritve  
- `${acron}` Akronim uporabnika  
- `${expTitle}` Strokovni naziv uporabnika  
- `${repY}` Leto (YYYY)  
- `${repy}` Leto — krajša oblika (YY)  
- `${repM}` Mesec

### Zapisnik o usposabljanju

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

Blok:
- `${cloneCert0}` … `{/$cloneCert0}` (blok potrdil)  
- `${attName}` Ime in priimek  
- `${attWorkPlace}` Delovno mesto  
- `${attDateBirth}` Datum rojstva  
- `${attDateValid}` Datum veljavnosti potrdila  
- `${attMntValid}` Velja — meseci  
- `${attDateEtest}` Datum opravljanja usposabljanja  
- `${attLocName}` Poslovna enota  
- `${attLocAddress}` Naslov PE  
- `${attLocCity}` Mesto PE

### Zapisnik o pregledu delovne opreme

Posamezne:
- `${dateRep}` Datum zapisnika  
- `${dateTest}` Datum pregleda  
- `${devUser}` Uporabnik delovne opreme  
- `${devUserAddr}` Naslov uporabnika opreme  
- `${custNrRep}` Številka zapisnika  
- `${dateLastRep}` Datum zadnjega pregleda  
- `${nrLastRep}` Št. zadnjega pregleda  
- `${infoLast}` Opis zadnjega pregleda  
- `${nrHour}` Število ur usposabljanja  
- `${txtType}` Tip pregledov  
- `${desc}` Opis metodologije  
- `${result}` Skupni rezultat

Tabele — kratek seznam pregledane opreme:
- `${rowShortName}` Naziv opreme  
- `${rowShortCnt}` Zap. št.  
- `${rowShortResult}` Rezultat pregleda  
- `${rowInstName}` Naziv merilnika  
- `${rowInstCert}` Certifikat merilnika

Tabela — podroben seznam:
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

Blok:
- `${cloneDevLst}` … `{/$cloneDevLst}` (info blok opreme)  
- `${cloneCert0}` … `{/$cloneCert0}` (blok potrdil)  
- `${devUsage}` Namen opreme

### Zapisnik meritve delovnega okolja

Posamezne:
- `${dateRep}` Datum zapisnika  
- `${dateTest}` Datum pregleda  
- `${hourTest}` Čas pregleda  
- `${custNrRep}` Številka zapisnika  
- `${dateLastRep}` Datum zadnjega pregleda  
- `${nrLastRep}` Št. zadnjega pregleda  
- `${infoLast}` Opis zadnjega pregleda  
- `${RH}` Relativna vlaga  
- `${Temp}` Zunanja temperatura  
- `${VA}` Gibanje zraka  
- `${Weather}` Vreme  
- `${result}` Skupni rezultat

Tabele — kratek seznam:
- `${rowShortName}` Naziv opreme  
- `${rowShortCnt}` Zap. št.  
- `${rowShortResult}` Rezultat  
- `${rowInstName}` Naziv merilnika  
- `${rowInstCert}` Certifikat merilnika

Tabela — merilna mesta (toplotne razmere):
- `${rowTCnt}` Zap. št.  
- `${rowTName}` Naziv merilnega mesta  
- `${rowTT110}` Temp T110  
- `${rowTVA}` Gibanje zraka  
- `${rowTRH}` Rel. vlaga  
- `${rowTMet}` MET  
- `${rowTPos}` Položaj  
- `${rowTIclo}` ICLO  
- `${rowTPMV}` PMV  
- `${rowTPPD}` PPD  
- `${rowTResult}` Rezultat

Tabela — merilna mesta (svetloba):
- `${rowLCnt}` Zap. št.  
- `${rowLName}` Naziv merilnega mesta  
- `${rowLType}` Tip svetilke  
- `${rowLTypeLum}` Tip osvetljenosti  
- `${rowLEDN}` E dnevna  
- `${rowLEKOM}` E kombinirana  
- `${rowLEUM}` E umetna  
- `${rowLEDOD}` E dodatna  
- `${rowLEMIN}` E minimalna izmerjena  
- `${rowLUO}` Emin/Ekomb  
- `${rowLUOMIN}` Uo min  
- `${rowLSIST}` SIST — nominalna vrednost  
- `${rowLResult}` Rezultat

Meritve po skupinah (blok):
- `${cloneMesGrp}` (začetek bloka)  
- `${mesGrpName}` Naziv skupine  
- `${rowMesName}` Naziv mer. mesta  
- `${rowMesCnt}` Zap. št.  
- `${rowMesT110}`  
- `${rowMesT01}`  
- `${rowMesVA}`  
- `${rowMesRH}`  
- `${rowMesMet}`  
- `${rowMesPos}`  
- `${rowMesIclo}`  
- `${rowMesPMV}`  
- `${rowMesPPD}`  
- `${rowMesTSO}`  
- `${rowMesLType}`  
- `${rowMesTypeLum}`  
- `${rowMesEDN}`  
- `${rowMesEKOM}`  
- `${rowMesEUM}`  
- `${rowMesEDOD}`  
- `${rowMesEMIN}`  
- `${rowMesUO}`  
- `${rowMesUOMIN}`  
- `${rowMesLSIST}`  
- `${rowMesLSO}`  
- `${rowMesT}`  
- `${rowMesTex}`  
- `${rowMesLeq}`  
- `${rowMesKi}`  
- `${rowMesLai}`  
- `${rowMesLc}`  
- `${rowMesLexmax}`  
- `${rowMesLex8h}`  
- `${rowMesSource}`  
- `${rowMesDesc}`  
- `${rowMesNSO}`

### Zapisnik meritve delovnega hrupa

Posamezne:
- `${dateRep}` Datum zapisnika  
- `${dateTest}` Datum pregleda  
- `${custNrRep}` Številka zapisnika  
- `${dateLastRep}` Datum zadnjega pregleda  
- `${nrLastRep}` Št. zadnjega pregleda  
- `${infoLast}` Opis zadnjega pregleda  
- `${Temp}` Zunanja temperatura  
- `${result}` Skupni rezultat

Tabele:
- `${rowInstName}` Naziv merilnika  
- `${rowInstCert}` Certifikat merilnika

Tabela — merilna mesta:
- `${rowCnt}` Zap. št.  
- `${rowName}` Naziv merilnega mesta  
- `${rowt}` Čas izvajanja meritve  
- `${rowtex}` Čas ekspozicije  
- `${rowLeq}` LAeq  
- `${rowKi}` KI korekcija  
- `${rowLai}` LAI  
- `${rowLc}` LC peak  
- `${rowLexmax}` LEXmax  
- `${rowLex8h}` LEX8h  
- `${rowResult}` Rezultat  
- `${rowSource}` Vir hrupa  
- `${rowDesc}` Dodatni opis

### Ocene tveganja (spremenljivke)

Posamezne:
- `${dateRep}` Datum zapisnika  
- `${cPersResp}` Odgovorna oseba stranke za VZD  
- `${cPersMed}` Pooblaščeni zdravnik  
- `${cntEmp}` Število zaposlenih  
- `${cntEmpM}` Število zaposlenih — moški  
- `${cntEmpF}` Število zaposlenih — ženske  
- `${descWorkEnv}` Opis delovnih prostorov

Tabele:
- `${rassName}` Naziv TDM  
- `${rassCnt}` Zap. št. TDM  
- `${rowEmpName}` Ime in priimek zaposlenega  
- `${rowEmpDateBirth}` Datum rojstva  
- `${rowEmpWM}` Delovno mesto  
- `${rassMntMed}` Periodika zdr. pregledov  
- `${rassMntEnv}` Periodika meritev del. okolja  
- `${rassMntNoise}` Periodika meritev hrupa  
- `${rassMntDev}` Periodika pregledov del. opreme  
- `${rowRassEduName}` Ime tečaja  
- `${rowRassEduMnt}` Periodika usposabljanja

### Letno poročilo za stranke (spremenljivke)

Posamezne:
- `${cTaxNr}` DDV številka  
- `${cRegId}` Registrska številka  
- `${cBusCodeName}` Čas pregleda  
- `${cPersResp}` Odgovorna oseba

Tabele — zapisniki usposabljanja:
- `${rowLnameGedu}` Poslovna enota  
- `${rowNrGedu}` Št. zapisnika  
- `${rowDateGedu}` Datum zapisnika  
- `${rowNrPers}` Št. oseb

Tabele — zapisniki delovne opreme:
- `${rowLnameGdev}` Poslovna enota  
- `${rowNrGdev}` Št. zapisnika  
- `${rowDateGdev}` Datum zapisnika  
- `${rowTypeGdev}` Tip pregleda

Tabele — ocene tveganja:
- `${rowLname}` Naziv opreme

Tabele — seznam zapisnikov usposabljanja:
- `${rowLname}` Naziv opreme

### Sistem APZ (spremenljivke)

Posamezne:
- `${vppObjName}` Naziv VPP objekta  
- `${dateRep}` Datum poročila  
- `${dateValid}` Datum veljavnosti pregleda  
- `${typeName}` Tip SAPZ  
- `${descName}` Naziv sistema in proizvajalci  
- `${infoLast}` Opis zadnjega pregleda  
- `${descGeneral}` Splošni opis  
- `${descBuildPerm}` Gradbeno in uporabno dovoljenje  
- `${descBuildLaw}` Gradbeni predpisi  
- `${descManufactDocs}` Predpisane listine proizvajalca  
- `${descTehSuperv}` Tehnični pregledi SAPZ  
- `${descDuration}` Trajanje preizkusa  
- `${descCharReq}` Karakteristične zahteve  
- `${descCheckMeth}` Metodologija preizkusa  
- `${descPers}` Sodelujoči
