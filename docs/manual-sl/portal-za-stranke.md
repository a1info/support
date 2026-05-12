# Portal za stranke (B2B portal)

Optima Prevent vključuje namensko spletno aplikacijo (portal) za vaše stranke. Strankam omogoča neposreden in transparenten vpogled v njihovo stanje varnosti in zdravja pri delu, prenose dokumentov ter samostojno urejanje določenih evidenc.

Ker je portal neposredno povezan z glavno bazo podatkov, so vsi dokumenti in spremembe, ki jih ustvarite, stranki vidni takoj.

Portalni uporabniki so **ločeni od sistemskih uporabnikov**. Za interne račune, skupine in dovoljenja glejte poglavje [Uporabniki](uporabniki.md).

---

## 1. Dodeljevanje dostopa (Ustvarjanje uporabnikov strank)

Dostope do portala za stranke upravljajo sistemski uporabniki (administratorji/operaterji) v glavni aplikaciji. 

**Dostop:** Glavni meni → Stranke → Oddaljeni dostop

### Postopek ustvarjanja uporabnika

Za dodajanje novega dostopa kliknite **Dodaj uporabnika** in izpolnite naslednje podatke:

| Polje | Opis |
|-------|------|
| **E-pošta** | Služi kot uporabniško ime za prijavo stranke. |
| **Geslo** | Začetno geslo za prijavo (stranka ga lahko kasneje spremeni). |
| **Ime in priimek** | Ime kontaktne osebe pri stranki. |
| **Stranka** | Izbira matične stranke iz šifranta, do katere bo imel uporabnik dostop. |
| **Poslovna enota (opcijsko)** | Če želite uporabniku omejiti dostop **samo na določeno lokacijo** (poslovno enoto) znotraj podjetja. Če pustite »Vse«, bo videl podatke celotnega podjetja. |

### Upravljanje pravic in pooblastil

Vsakemu uporabniku stranke lahko natančno določite, katere module lahko **vidi (Ogled)** in katere lahko **ureja (Urejanje)**.

Na voljo so naslednje pravice:

- **Zaposleni** (vpogled v kadrovsko evidenco ali možnost dodajanja/odstranjevanja zaposlenih)
- **Delovna oprema** (pregled strojev in naprav ali možnost dodajanja nove opreme)
- **Zdravniški pregledi** (vodenje in pregled evidence zdravniških spričeval)
- **Delovne nezgode** (prijava in evidenca nezgod pri delu)
- **Požarna varnost (VPP)** (vpogled v evidence požarne varnosti)
- **Osebna varovalna oprema (OVO)** (vodenje zadolžitev za varovalno opremo)

!!! tip "Dobra praksa"
    Direktorjem običajno dodelite pravice izključno za **ogled** vseh modulov. Vodjem oddelkov (npr. vodja proizvodnje) pa lahko dodelite pravico za **urejanje** tistih modulov, za katere so zadolženi (npr. Delovna oprema, Delovne nezgode), hkrati pa jih omejite samo na njihovo poslovno enoto.

---

## 2. Prijava v portal

Stranke do portala dostopajo preko posebne prijavne strani. 

**Standardni URL naslov:** `https://naslov_vase_instalacije/mod-cust`

!!! info "Prilagojen izgled (White-label)"
    Prijavni zaslon za stranke je prilagodljiv. Glede na vašo domeno ali blagovno znamko se lahko prikaže vaš lasten logotip, prilagojeno ozadje in barvna shema (npr. podprte so specifične teme za G.A. d.o.o., Varnost.net, VZDplus, Zagros ipd.).

Stranka se prijavi s svojim e-poštnim naslovom in geslom.

---

## 3. Nadzorna plošča in dogodki (Dashboard)

Takoj po uspešni prijavi je stranki prikazana **Nadzorna plošča**, ki ponuja zbirni pregled ključnih informacij.

### Elementi nadzorne plošče:
1. **Statistični števci:** Hiter prikaz skupnega števila dokumentov, delovne opreme, zaposlenih in opravljenih zdravniških pregledov.
2. **Koledar naročil in realizacije:** Vizualni prikaz naročenega in opravljenega dela.
3. **Analitika (Mesečni povzetek):** Grafikon, ki prikazuje opravljena dela in izvedene preglede po mesecih.

### Zadnji dogodki
Desni del nadzorne plošče vsebuje seznam **Zadnjih dogodkov**. 
**Kadarkoli v glavni aplikaciji za to stranko ustvarite in objavite nov dokument** (npr. zapisnik o usposabljanju, nov pregled delovne opreme, oceno tveganja), sistem tukaj samodejno zabeleži dogodek. Stranka tako ob prijavi takoj vidi, katere nove storitve in dokumenti so ji bili nedavno predani.

Za splošna pravila obveščanja, e-poštne opomnike, e-test sporočila in diagnostiko pošte glejte poglavje [Sistem obveščanja](sistem-obvescanja.md).

---

## 4. Funkcionalnosti Portala za stranke

Glavni meni (na levi strani) se stranki prilagaja glede na zgoraj dodeljene pravice. Moduli, do katerih stranka nima dostopa, v meniju niso prikazani.

### Dokumenti
Centralni arhiv vseh uradnih dokumentov (Zapisniki usposabljanj, preizkusi opreme, EKO/VZD meritve, Požarna varnost, Ocene tveganja). Dokumenti so razvrščeni po logičnih zavihkih. Stranka si tukaj lahko prenese (prenos PDF) ali ogleda veljavne dokumente.

### Pregled veljavnosti (Periodika)
Analitični modul, ki stranki omogoča vpogled v datume potekov. Z rdečo barvo so jasno označene postavke (oprema, usposabljanja, zdravniški pregledi), ki so jim roki že potekli ali pa so pred potekom.

### Zaposleni in Delovna mesta
Seznam vseh aktivnih delavcev v podjetju stranke. Če ima stranka pravico za urejanje, lahko sama skrbi za ažurnost svojega kadrovskega seznama (dodaja nove delavce, ureja osebne podatke) ter pregleduje, katera delovna mesta zasedajo.

### Delovna oprema
Evidenca strojev in naprav. Uporabniki lahko pregledujejo tehnične podatke opreme, prenesejo navodila za uporabo in preverjajo statuse zadnjih pregledov.

### Zdravniški pregledi
Dostop do evidence zdravniških pregledov in prenos izdanih zdravniških potrdil/napotnic za svoje zaposlene.

### Delovne nezgode
Modul omogoča strankam, da ob nesreči same kreirajo in izpolnijo obrazec za prijavo nezgode. Prijavi lahko priložijo priponke (slike poškodb, dokumentacijo). Te prijave so takoj vidne tudi vašim skrbnikom v osrednjem sistemu, ki nato lahko izvedejo preiskavo in ukrepe. Na tem seznamu se nahaja tudi hitra povezava do uradne **e-VEM** prijave nezgode.

### Osebna varovalna oprema (OVO)
Vpogled v zadolžitve za osebno varovalno opremo posameznih zaposlenih, skladno s standardi in zahtevami ocene tveganja.
