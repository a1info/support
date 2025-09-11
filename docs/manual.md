![](./docs/media/image1.png){width="0.8152777777777778in"
height="0.8027777777777778in"}

N a v o d i l a z a u p o r a b o\
\
O p t i m a P r e v e n t

v5.1

UVOD

Optima Prevent je EHS (Environmental Health and Safety) sistem, napisan
in prilagojen zakonodaji Republike Slovenije, upošteva vse aktualne
mednarodne standarde in napotke poslovanja na tem področju (OSHAS, ISO).
Sistem je namenjen družbam/službam, ki se ukvarjajo z varnostjo in
zdravjem pri delu, za celovito in enostavno vodenje dela in popolno
kontrolo nad kompleksnim delom, ki ga izvajajo.

Modularna arhitektura aplikacije in večplastni dizajn omogoča visoko
raven prilagodljivosti in možnost prilagajanja vsem vrstam družb glede
na velikost ali delo, ki ga opravljajo.

Aplikacija je sestavljena iz modulov ki so med seboj povezani in vse
spremembe v sistemu so takoj vidne v vseh povezanih modulih.

EAV (Entity Attribute Value) tehnologija omogoča dodelitev atributa po
meri in tako omogoča visoko stopnjo fleksibilnosti načina vnosa in
prikaza podatkov.

Klient/Server arhitektura skupaj z transakcijsko SQL komunikacijo,
omogoča istočasni dostop do podatkov vsem uporabnikom v podjetju, brez
tveganja izgube podatkov ali istočasnega urejanja istih podatkov.

Razvojne tehnologije uporabljene za izdelavo Optima Prevent so PHP8 MVC
(Module/View/Controller) -- Laravel 9x framework v kombinaciji za
Livewire/JQuery2 na uporabniške vmesniku.

Podatkovni SQL sloj podpira več tehnologij in se lahko prilagaja
uporabniškemu okolju.

Podprti SQL strežniki so: PostgreSQL in Oracle.

Vse faze dostopa do podatkov so šifrirane: v SQL bazi, datotečnem
sistemu, mrežnem prenosu (SSL/VPN).

Zaradi zagotavljanja varnosti uporabniških podatkov in usklajenosti
GDPR-u web se piškotki shranjujejo v šifrirani SQL bazi.

Vsi ostali postopki in deli aplikacije z katerim se obdelujejo osebni
podatki fizičnih oseb so v skladu z GDPR in so dokumentirani v priloženi
dokumentaciji Optima Prevent.

Optima Prevent je blagovna znamka podjetja A1 Informatika d.o.o. in je
registrirana v Avtorsko Agencijo RS pod število 030/19.

VMESNIK SISTEMA OPTIMA PREVENT

Vmesnik Optima Prevent je narejen z odzivno tehnologiji, tako da se
lahko prikazuje na mobilnih napravah. Vendar za popolni prikaz in
celovito uporabo prikazanih podatkov je potrebno uporabljati zaslone z
minimalno ločljivostjo 1024x768. Prikazni vmesniki aplikacije vsebujejo
veliko informacij in za učinkovit pregled je potrebno imeti večjo
površino prikaza.

PRIJAVA V SISTEM

Za dostop do Optima Prevent aplikacije je potrebno poznati IP ali
domensko ime strežnika kjer je nameščena aplikacija. Prvi prikaz na
zaslonu je prijava. Uporabniško ime je v formi email@podjetje.si /
geslo. Po prijavi se uporabnik preusmeri na nadzorno ploščo odvisno o
tipu uporabnika.

Nadzorna plošča je dostopna z klikom na logotip Optima Prevent v
zgornjem levem kotu vmesnika.

Uporabniška nadzorna plošča (Dashboard) je izdelana na način, da so
uporabnikov na enem mestu vidna aktualna obvestila, splošna analitika in
sistemske informacije.

MENI IN NAVIGACIJA

Vsak uporabnik ima 3 menija za navigacijo: levi glavi meni in
uporabniški zgornji meni.

Glavni meni je sestavljen iz skupin padajočih menijev in vsaka skupina
predstavlja logično razdelitev funkcionalnosti aplikacije.

Uporabniški meni prikazuje informacije, ki so povezane z uporabnikom oz.
interna sporočila od ostalih uporabnikov, prikaz in urejanje profila in
možnost odjave iz aplikacije.

Na zgornjem desnem delu se nahaja polje za izbiro aktivne stranke. Po
izbiri aktivne stranke so vsi prikazi za vnos ali urejanje podatkov že
nameščeni na aktivno stranko, tako da ni potrebno ponavljati ukaza za
izbiro stranke za vnos.

Administratorji imajo možnost, da vnašajo podatke za ostale sistemske
uporabnike ker pri vnosu imajo dodatno polje za izbiro uporabnika na
katerega se bo nanašal ta zapis v bazi.

Celoten uporabniški vmesnik spremljajo enotne ikone:

  ------------------------------------------------------------ --------------------------- ------------------------------------------------------------ -----------------------
  ![](./docs/media/image2.png){width="0.26458333333333334in"   \- pregled                  ![](./docs/media/image3.png){width="0.18611111111111112in"   \- uvoz podatkov
  height="0.1701388888888889in"}                                                           height="0.23125in"}                                          

  ![](./docs/media/image4.png){width="0.24861111111111112in"   \- urejanje                 ![](./docs/media/image3.png){width="0.18661417322834645in"   \- izvoz / prenašanje
  height="0.24861111111111112in"}                                                          height="0.23188976377952755in"}                              

  ![](./docs/media/image5.png){width="0.22361111111111112in"   \- brisanje                 Excel                                                        \- izvoz tabele v Excel
  height="0.24305555555555555in"}                                                                                                                       

  ![](./docs/media/image6.png){width="0.18611111111111112in"   \- docx potrdilo            PDF                                                          \- izvoz tabele v PDF
  height="0.24791666666666667in"}                                                                                                                       

  ![](./docs/media/image7.png){width="0.19652777777777777in"   \- pdf izpis                Print                                                        \- print seznama
  height="0.23333333333333334in"}                                                                                                                       

  ![](./docs/media/image8.png){width="0.2326388888888889in"    \- filtriranje rezultatov   ![](./docs/media/image9.png){width="0.24097222222222223in"   \- koledar
  height="0.2298611111111111in"}                                                           height="0.23125in"}                                          
  ------------------------------------------------------------ --------------------------- ------------------------------------------------------------ -----------------------

Parametri za filtriranje rezultatov so prikazani v seznamu.

SKUPNE / BULK AKCIJE

Seznami, ki vsebujejo veliko podatkov imajo možnost skupnih akcij
izbranih vrstic seznama (možnost urejanja več vnosov hkrati). Vrstice se
izbirajo klikom na checkbox na desni strani vrstice, ali se izberejo vse
vrstice klikom na checkbox na zgornjem delu tabele.

Po izbiri vrstic se določi akcija v select box zgornjega dela tabele.

Vmesniki ki imajo skupne akcije:

-   seznam delovne opreme -- brisanje, brisanje kaskadno (briši tudi
    preglede), skupni pregled (za preglede ki imajo iste parametre)

```{=html}
<!-- -->
```
-   seznam pregledov -- brisanje

```{=html}
<!-- -->
```
-   seznam zaposlenih -- brisanje

```{=html}
<!-- -->
```
-   seznam usposabljanja - brisanje

![](./docs/media/image10.png){width="6.7875in" height="2.7125in"}

SISTEMSKE NASTAVITVE

> ![](./docs/media/image11.png){width="6.78125in"
> height="4.366666666666666in"}

Osnovni modul aplikacije za definicijo vseh parametrov matične družbe za
prikaz vsem uporabnikom sistema.

DOSTOP: izberete Sistem-\>Nastavitve v glavnem meniju vmesnika.

Osnovni parametri za vnos so:

-   Ime matične družbe,

```{=html}
<!-- -->
```
-   Polno ime družbe,

```{=html}
<!-- -->
```
-   DDV številka,

```{=html}
<!-- -->
```
-   Registracijska številka

```{=html}
<!-- -->
```
-   Naslov sedeža,

```{=html}
<!-- -->
```
-   Akreditacije RS,

```{=html}
<!-- -->
```
-   Telefon / mobitel / email / www

```{=html}
<!-- -->
```
-   Slika logotipa

```{=html}
<!-- -->
```
-   Certifikat za podpisovanje dokumentov \... itd.

V področju »Moduli« se nahaja seznam izbirnih sistemskih modulov in
polja za vnos licenc za posamezne module.

NADGRADNJA SISTEMA

Prikaz trenutne različice sistema in nadgradnja je omogočena na delu
vmesnika »Nadgradnja«.

V kolikor je sistem posodobljen na najnovejšo različico se gumb za
nadgradnjo ne prikaže.

DIGITALNO PODPISOVANJE DOKUMENTOV

Za digitalno podpisovanje dokumentov sistem uporablja digitalne
certifikate v standardni obliki P12 skupaj z geslom certifikata.

DOSTOP: izberete Nastavitve-\>Sistem v glavnem meniju vmesnika.

Da bi se omogočilo avtomatično podpisovanje PDF dokumentom potrebno je
dodati p12 certifikat (gumb P12 Cert) in dodati geslo v polje na desni
strani.

Po vnosu vsi PDF dokumenti ustvarjeni v sistemu bo avtomatično digitalno
podpisani in vidni uporabnikom strank po prijavni v sistem.

![](./docs/media/image12.png){width="3.317361111111111in"
height="1.5888888888888888in"}

UPORABNIKI

SISTEMSKI UPORABNIKI

![](./docs/media/image13.png){width="6.7875in"
height="2.6743055555555557in"}

Sistemski uporabniki so delavci matične družbe, ki lahko pripadajo
skupinam:

-   Administratorji (Administrators)

```{=html}
<!-- -->
```
-   Operatorji

```{=html}
<!-- -->
```
-   Navadni uporabniki (Users).

Odvisno od pripadnosti skupini uporabnikom je določeno do katerih
vmesnikom imajo pravico dostopa in urejanja podatkov.

Generalno pravilo je, da navadni uporabniki imajo pravico dostopa do
svojih podatkov in podatkov skupine, brez pavice dostopa po nastavitvah
sistema.

Skupina operaterji imajo uvid v vse podatke in imajo pravico dela v
tujem imenu. Nimajo dovoljenja za spreminjanje sistemskih nastavitev.

Skupina administratorji ima pravico pregleda in urejanja vseh podatkov v
sistemu.

UPORABNIKI STRANK

![](./docs/media/image14.png){width="6.7875in"
height="2.3319444444444444in"}

Uporabniki strank so zaposleni vaših strank katerim želite omogočiti
pravico do dostopa do aplikacije. Odvisno o dodeljenih pravic imajo
dostop do posameznih delov aplikacije katere vsebujejo samo informacije
njihove stranke.

Pravice do dostopa se lahko dodelijo za naslednje module:

-   evidenca delovne opreme

```{=html}
<!-- -->
```
-   evidenca zaposlenih

```{=html}
<!-- -->
```
-   osebna varovalna oprema

```{=html}
<!-- -->
```
-   zdravniški pregledi

```{=html}
<!-- -->
```
-   delovne nezgode

```{=html}
<!-- -->
```
-   naročila

```{=html}
<!-- -->
```
-   evidence požarne varnosti

\* Moduli vsebujejo samo informacije pripadajoče stranke.

\* Pravice se lahko dodelijo samo za pregleda ali za pregled in
urejanje.

PRIJAVA UPORABNIKA STRANKE

Za dostop do uporabniške plošče strankami je potrebno posredovati
spletni naslov za prijavo:

**https://nasov_vaše_inštalacije/mod-cust**

npr. https://demo.optima-prevent.eu/mod-cust

Kot uporabniško ime za prijavo se uporablja email naslov in geslo katere
ste določili pri vnosu. Stranka lahko spremeni geslo po prvi prijavi.

DOSTOP STRANK DO LASTNIH PODATKOV

Ekran za prijavo stran je mogoče urejati in prilagoditi po meri.

Po prijavi prvi ekran ki se prikaže je nadzorna plošča (Dashboard) z
splošnimi informacijami o sistemu in hitrim povezavami.

![](./docs/media/image15.png){width="6.3875in"
height="2.9881944444444444in"}

Vpogled v izdane dokumente

DOSTOP: izberete Dokumenti v glavnem meniju vmesnika.

Koledar poteka veljavnosti

DOSTOP: Izberite Periodika v glavnem meniju

![](./docs/media/image16.png){width="6.3875in"
height="2.957638888888889in"}

Seznam zaposlenih

DOSTOP: Izberite Zaposleni v glavnem meniju

![](./docs/media/image17.png){width="6.3875in"
height="2.077777777777778in"}

ZAČETNA NASTAVITEV IN VNOS PODATKOV

Preden se začne z delom v Optima Prevent je potrebno narediti začetni
vnos podatkov. Osnovni podatki so informacije o matičnem podjetju
dostopne v Sistemskem modulu.

DOSTOP: Osnovni sistemski modul - Nastavitve -\> Sistem

MIGRACIJA PODATKOV

Migracija je postopek, ki omogoča uvoz zgodovinskih podatkov iz drugih
programov ali Excel datotek.

Ker se pri migraciji kreirajo bazni podatki in operacije povezane z
njimi, jo je potrebno narediti previdno in s preverjenim procedure. Iz
tega razloga priporočamo koordinacijo z razvijalcem Optima Prevent pri
izvajanju procesa migracije.

AVTOMATIČNO ŠTEVILČENJE DOKUMENTOV

Vsi izdati dokumenti so avtomatično oštevilčeni s števci (Counters)
kateri se lahko nastavijo, kako bi se prilagodili številčenju matične
družbe. Dokumenti, ki se številčijo so:

-   Zapisniki o opravljenem usposabljanju

```{=html}
<!-- -->
```
-   Posamezna potrdila o usposabljanju

```{=html}
<!-- -->
```
-   Zapisniki o pregledov delovne opreme

```{=html}
<!-- -->
```
-   Posamezna potrdila za delovno opremo

```{=html}
<!-- -->
```
-   Ocene tveganje

```{=html}
<!-- -->
```
-   EKO / VZD meritve

Številčenje je inkrementalno in parametri pri nastavitvah, ki se lahko
urejajo so: leto, stranka, tip dokumenta.

Konfiguracija je shranjena v tekstualni datoteki in je možna v vseh
različnih kombinacijah parametrov.

UVOZ EXCEL DATOTEK

![](./docs/media/image18.png){width="1.8680555555555556in"
height="1.5472222222222223in"}

Ikona za uvoz se pojavlja na seznamih: Stranka, Delovna oprema,
Zaposleni, Vprašalniki, Osebna varovalna oprema in VPP.

Za pravilen uvoz podatkov prek Excel datotek je potrebno podrobno
spoštovati pravila uvoza. Priporočeno je uporabljati podloge katere so
že dostopne na maskah v katere želite narediti uvoz. Podloge so različne
glede na to kaj želite uvažati (zaposleni, delovna oprema, stranke\...).

Prva vrstica (imena poljih) morajo biti enaka kot v predlogi (template)
tplImportXXX.xlsx.

Excel datoteke morajo biti shranjene v UTF8 jezični kodi za pravilen
prikaz šumnikov.

Izogibajte se dodatnega oblikovanja podatkov Excel datoteke.

Odprite predlogo (template) v LibreOffice in ga napolnite z podatki
(copy/paste) iz dokumenta katerega želite uvoziti v aplikacijo. Po
urejanju shranite podlogo na računalnik in jo izberite kot datoteko za
uvoz. Kliknite na \"Import\" in na koncu poglejte rezultat avtomatičnega
vnosa (število : uspešno / neuspešno).

\* Čeprav obstajajo pravila in filtri, ki vam pomagajo in opozarjajo pri
uvozu preden začnete dobro preverite podatke

\* V slučaju uvoza podatkov v poslovno enoto stranke je potrebno izbrati
aktivno stranko v gornjem meniju.

TEKSTI PO MERI

Teksti po meri so ponavljajoči teksti ki se dodeljujejo posamezno
vmesniku uporabo variabli. Npr. txtDevRes je variabla katere vsebuje
tekst za polje »Ugotovitev« pri pregledu delovne opreme. Za celoten
seznam variabel poglejte seznam vmesnika in opise posameznih variabel.

Na delu vmesnika »Polja za prikaz« se nahaja seznam izbirnih polj vnosa
za različne module. Nekatere matične družbe jih potrebujejo, nekatera pa
ne, če so ta polja onemogočena, ne obremenjujejo pripadajoče vmesnike za
vnos podatkov.

DOSTOP: Seznami - Teksti po meri

POLJA PO MERI - EAV

Modul »Polja po meri« omogoča dodajanje atributov objektom in operacijam
v sistemu. Primer, ki se pogosto dogaja je da želite dodati dodatna
polja za delovno opremo ali za zaposlene in ta polja prikazati v izdanih
dokumentih.

Za te primere ima Optima Prevent implementirano tehnologijo EAV (Entity
Attribute Value) oz. Dodajanje atributov, ki so vidni v celotnemu
sistemu (uvoz, izvoz, prikaz, predloge\...).

Pri dodelitvi atributov, sistem avtomatično generira kodo polja in ta
koda se uporablja za sistemske operacije. Koda polja je vidna v seznamu
vmesnika.

Za prikaz polja v zapisnikih, v predlogah se uporablja koda s prefiksom
pozicije variable v predlogi npr. \${lst + code} ali \${dev + code}.

DOSTOP: Seznami -- Polja po meri

STRANKE

> ![](./docs/media/image19.png){width="6.4006944444444445in"
> height="5.392361111111111in"}

Za delo s strankami, potrebno je ustvariti stranke in poslovne enote
strank. To so osnovni zapisni na katere so vezani ostali podatki
modulov.

Vsaka stranka in poslovna enota dodatno vsebujejo zapise zaposlenih in
delovne opreme, ki so tudi del osnovne strukture na katere se izvajajo
operacije v modulih in povezujejo različni dokumenti.

Stranke so podjetja, ki so naročniki in prejemniki storitev matične
družbe oz. Lastnika aplikacije Optima Prevent.

DOSTOP: Za dostop do vmesnika strank na glavnem meniju izberite »Stanke«

Stranke so pravni subjekti zato morajo imeti definirano svojo unikatno
davčno številko.

Pri vnosu stranke je potrebno izpolniti obvezna polja: Naziv, Naslov,
Mesto in DDV števila. Te informacije lahko vnesete ročno, ali
avtomatično, če poznate davčno številko stranke. Izpolnite polje DDV št.
In kliknite na ikono „Najdi". Sistem je povezan z Ajpes podatkovno bazo
in se avtomatično izpolnijo vsa ostala polja.

Polje za vnos naslova na vmesniku za novo stranko je vedno naslov sedeža
stranke.

»Šifra po meri« je neobvezno polje v katere lahko vnesete številko
računovodskega programa za to stranko ali kaj podobnega.

Na meniju »Dodatno« je možno izbrati uporabnika, ki bo skrbnik za
stranko in bo sprejemal vse informacije za to posamezno stranko.

Če imate stranko vpisano samo zaradi zgodovine in prejšnjega
opravljenega dela, stranko lahko onemogočite oz. umaknete s kljukico
»aktivna«. Mogoče je onemogočiti funkcijo spremljanja veljavnosti za
posamezne stranke če umaknete kljukico »spremljaj veljavnost« na
vmesniku za urejanje stranke. Na ta način se stranka in objekti stranke
ne bodo več prikazovali v analitičnem modulu aplikacije.

POSLOVNE ENOTE

Če ima stranka več poslovnih enot / lokacij jih je potrebno posebno
vnesti. Sedež stranke je tudi ena poslovna enota in sedež ni mogoče
brisati. Aplikacija poslovne enote obravnava kakor zaboje, ki vsebujejo
objekte stranke in kakor objekte, ki so povezani z meritvami, PV
evidence\...itn.

Zapisi poslovnih enot so posebno pomembni pri delu z večjimi strankami,
ker se na ta način lažje organizira delo v odvisnosti od lokacij
objektov stranke po naslovih poslovnih enot (zaposleni, del oprema\...).

Poslovne enote / lokacije stranke se urejajo klikom na gumb »Uredi
lokacije« v seznamu zapisa stranke.

ZAPOSLENI

> ![](./docs/media/image20.png){width="6.260416666666667in"
> height="4.590972222222222in"}

Modul za zaposlene je del aplikacije za urejanje delavcev strank in
pripadajočih vsebin. Modul je v direktni povezavi z ostalimi moduli v
aplikaciji in z zapisi glede na osnovni objekt na katerega so povezane
informacije o usposabljanju, za osebno varovano opremo, za zdravniške
preglede, delovne nezgode, oceno tveganja ..itn.

Skrb o ažurnosti evidenc zaposlenih lahko prepustimo uporabnikom strank
ali delavcem matične družbe.

Za dostop do vmesnika za urejanje zaposlenih strank na glavnem meniju
odprite »Zaposleni«.

Če ste že izbrali aktivno stranko, v seznamu se prikažejo samo zaposleni
te stranke.

Na desni strani vmesnika se nahajajo opcije za Excel uvoz in Filtriranje
seznama.

Optima Prevent preverja podvojene zapise ampak vseeno je potrebna
pozornost pri vnosu zaposlenih in preden se doda zapis preverite ali že
obstaja ta zaposleni v aplikaciji.

Na seznamu, z izbiro ikone na desni strani zapisa, je možno urejati
zaposlene, brisati ali ustvariti PDF poročilo zgodovine posameznega
delavca stranke.

Če obstaja zgodovina za zaposlenega brisanje ni mogoče. Če se klikne
ikono za brisanje, aplikacija samo onemogoči zaposlenega s tem, da
ostane celotna zgodovina in je mogoče zaposlenega na novo omogočiti.

CRM MODUL - ORGANIZACIJA NALOG

CRM je poseben modul za pregled in organizacijo dela z naročniki in se
uporablja za učinkovito organizacijo lastnega poslovanja in planiranje
prihodnjega dela.

Za dostop do vmesnika izberite meni CRM.

![](./docs/media/image21.png){width="6.715972222222222in"
height="3.2006944444444443in"}

NALOGE

Naloge so prikazane v koledarju CRM vmesnika. Naloge so logično
razdeljene po koledarjih in projektih.

Prikaz nalog je odvisen o izbranih filtrov na zgornjem delu koledarja.

V kolikor prijavljeni uporabnik pripada skupini administrator, so mu
vidne vse naloge matičnega podjetja. Skupini administrator je omogočena
razdelitev nalog in na ta način je mogoča učinkovita organizacija
načrtovanega dela razporejanjem nalog različnim delavcem matičnega
podjetja.

Na uporabniški nadzorni plošči je prikazan seznam odprtih nalog
prijavljenega uporabnika.

Navadnim uporabnikom so vidna samo lastne naloge, ki so jim dodeljene.

Parametri za dodajanje nalog:

-   Naziv

```{=html}
<!-- -->
```
-   Začetek / Konec

```{=html}
<!-- -->
```
-   Status

```{=html}
<!-- -->
```
-   Dodeljeno -- uporabnik ki je odgovoren za izvajanje naloge

```{=html}
<!-- -->
```
-   Stranka -- dodeljeno stranki

```{=html}
<!-- -->
```
-   Koledar / Projekt

```{=html}
<!-- -->
```
-   Seznam storitev in uporabnikov ki so odgovorni za posamezno storitev

![](./docs/media/image22.png){width="4.647916666666666in"
height="4.035416666666666in"}

Seznam storitev se dodaja prek vmesnika Nastavitve\>Storitve in so
dostopne samo Administrator uporabniku aplikacije.

KOLEDARJI

Koledarji so logični zaboji CRM ki vsebujejo naloge in povezane
parametre. Zadani koledarji so: koledar naročil in koledar periodike.

Administratorji lahko definirajo več koledarja odvisno od delovnega
procesa podjetja.

Koledar periodike je avtomatično generiran koledar, ki se posodablja
vsakič, ko se v sistem vnese operacija z veljavnostjo (tečaj, pregled
del. Opreme\...). Vendar obstaja možnost urejanja koledarja periodike,
ta koledar je najboljše pustiti samo za branje.

Za urejanje nalog je predviden koledar naročil in vsi ostali koledarji
ki so ročno dodani.

Za vnos novega koledarja izberite + ikono in »Koledar«

![](./docs/media/image23.png){width="2.80625in" height="2.8625in"}

PROJEKTI

Koncept projekta je združevanje nalog / datotek / komentarja v logični
zabojnik kronološki razporejen.

Za vpogled v posamezni projekt izberite CRM -- Projekti in potem ikono
Ogled na desni strani seznama,

Projektom lahko definirate pravice za ogled/urejanje za posamezne
uporabnike. Prednastavljena vrednost je, da je omogočen ogled / urejanje
za vse uporabnike.

![](./docs/media/image24.png){width="6.138888888888889in"
height="2.5791666666666666in"}

DELOVNI NALOG

Na seznamu nalog obstaja možnost izpisa delovnih nalog s klikom na PDF
gumb na desni strani seznama. Ta funkcionalnost je koristna, ko se
delavci nahajajo na terenu kot potrdilo opravljenega dela. Delovni nalog
je v PDF obliki in vsebuje opis opravljenega dela in prostor za podpis
delavca stranke. Oblika delovnega naloga se lahko prilagaja potrebam
matične družbe.

USPOSABLJANJE

Modul za usposabljanje zaposlenih je narejen v večplastni strukturi in
se na ta način aplikacija lahko prilagaja različnim načinom poslovanja
matičnega podjetja. Prvi pogled so posamezna usposabljanja v katera se
dodajajo zaposleni stranke oz. udeleženci tečaja. Usposabljanje, ki se
vnaša je lahko samo enega tipa in ima definirano skupno veljavnost
usposabljanja (število mesecev do obnovitve).

Za dostop do opravljenih tečajev izberite meni Usposabljanje\>Seznam
tečajev.

Zapisnik je drugi pogled modula, zapisnik združuje več usposabljanj, ki
so lahko različnih tipov in različnih veljavnosti.

DOSTOP: izberite meni Usposabljanje\>Zapisniki in se pokaže seznam vseh
zapisnikov.

TIPI TEČAJEV

Tipi tečajev se definirajo v vmesniku Usposabljanje -\> tipi tečajev

V tem pogledu definiramo tipe usposabljanj, ki se bodo pojavljali kot
opcije za izbiro pri vnosu tečajev npr. VPP, VZD, VPP ODG\... Pri vnosu
tipa lahko se izbere opcija za ločeno številčenje tečajev tega tipa,
priloge tečaja, zakonske odredbe \...itn.

DODAJANJE TEČAJA

Za dodajanje novega tečaja izberite v meniju Usposabljanje\>Seznam
tečajev in kliknite na gumb »dodaj tečaj«.

Prikaže se vmesnik vnosa tečaja:

-   Stranka in poslovna enota -- obvezno polje

```{=html}
<!-- -->
```
-   Lokacija tečaja -- vnesite opisno lokacijo tečaja

```{=html}
<!-- -->
```
-   Tip tečaja -- VZD, VPP, VPP ODG\...

```{=html}
<!-- -->
```
-   Datum začetka -- obvezno polje -- izberite datum iz koledarja

```{=html}
<!-- -->
```
-   Veljavnost -- število let veljavnosti narejenega tečaja

Naslednji vmesnik je za dodajo zaposlenih oz. Udeležencev tečaja.

Pri obsežnih seznamih zaposlenih je potrebo uporabljati »hitri filter«
na vrhu tabele zaposlenih. Na ta način se lahko išče posamezne zaposlene
ali se jih razvršča po poslovnih enotah.

\* Pri vnosu zaposlenih je potrebna previdnost ker naknadna dodajanja
ali brisanja zaposlenih iz tečaja niso dovoljena.

ODDALJENO USPOSABLJANJE

Pri vnosu tečaja lahko definirate oz. izberete vprašalnik za oddaljeno
usposabljanje in s tem omogočite dostop zaposlenim do modula »etest« za
prijavo in izpolnjevanje vprašalnika.

Ko se izbere vprašalnik se status udeležencev avtomatično spremeni na
negativno dokler se ne prijavijo v sistem in uspešno rešijo test. Po
uspešno končanem testu se status udeleženca spremeni v pozitivno in
dodeli se mu številka potrdila, v kolikor je tako nameščeno avtomatično
številčenje.

Za dostop do modula in prijavo uporabite naslov:
https://nasov_vaše_inštalacije/mod-etest

Predloga prijave je v html5 obliki in se lahko prilagodi obliki in
zahtevam matičnega podjetja.

VPRAŠALNIKI ZA ODDALJENO USPOSABLJANJE

Za dostop do vmesnika za urejanje vprašalnika »Usposabljanje-\>
Vprašalniki«.

Dodajanje vprašalnika je narejeno v 2 korakih.

V prvem koraku se definirajo splošne informacije vprašalnika.

![](./docs/media/image25.png){width="6.7875in"
height="1.5291666666666666in"}

Gumb »Izberi datoteko« je namenjen za dodajanje zip datoteke ki vsebuje
html5 kodo in se prikaže pred začetkom testa. Datoteka se lahko naredi v
iSpring ali H5P aplikaciji in se prikazuje kako PowerPoint predstavitev
gradiva katere se nanaša na vprašalnik.

Formular za vnos -- lahko izberete FORM predlogo katera se bo prikazala
na koncu tečaja, v kolikor je potrebno, da udeleženec izpolni dodatne
informacije in potrdi pogoje uporabe ali pogoje usposabljanja. V kolikor
se formular označi kot obvezen, je usposabljanje uspešno končano šele po
izpolnitvi in oddaji formularja.

Zahtevana uspešnost je nastavljena na 80% točno označenih vprašanj in se
lahko spreminja.

V drugem koraku se dodajajo vprašanja katera bodo prikazana v testu.

![](./docs/media/image26.png){width="6.7875in" height="2.4875in"}

Pred vsakim vprašanjem lahko dodate datoteko (pdf ali mp4) katere bo
prikazana pred vprašanjem.

Število točk -- nastavljena vrednost je 2 in se lahko spreminja. Lahko
dodelite več točk na bolj pomembna vprašanja ali manj za informativna
vprašanja.

DELOVNA OPREMA

Modul za delovno opremo ima večplastno strukturo (delovna oprema,
pregledi, zapisniki). Modul se lahko prilagaja različnim scenarijem in
situacijah pri pregledih.

EVIDENCA DELOVNE OPREME

Prvi pogled so objekti delovne opreme, ki so razporejeni po strankah in
poslovnih enotah. Pomembno je zagotavljati ažurne sezname delovne opreme
in da vneseni vsi relevantni parametri brez podvajanja opreme. Skrb za
seznam in ažurnost seznama lahko prepustite delavcem stranke kogar last
je delovna oprema, ali pa sami srbite za seznam.

Za vnos in urejanje delovne opreme odprite glavni meni »Delovna oprema
-\> Seznam de. opreme«.

Osnovni parametri za vnos delovne opreme so:

-   Stranka / poslovna enota

```{=html}
<!-- -->
```
-   Naziv delovne opreme

```{=html}
<!-- -->
```
-   Serijska in inventarna številka

```{=html}
<!-- -->
```
-   Tip / model

```{=html}
<!-- -->
```
-   Leto izdelave

```{=html}
<!-- -->
```
-   Proizvajalec

```{=html}
<!-- -->
```
-   Slike opreme

```{=html}
<!-- -->
```
-   Datum odpisa -- če oprema ni več v funkciji

Pri izbiri ikone za pregled na desni strani seznama opreme prikaže se
ekran za pregled parametrov delovne opreme in informacije o zadnjih
pregledih. Na desni strani ekrana je QR koda katera vsebuje URL za hiter
dostop do informacija prek mobilnih naprav.

QR koda je različna za vas posamezni kos delovne opreme in se lahko
uporabi pri oblikovanju nalepke za lažjo identifikacijo in hiter dostop
do informacija.

PREGLEDI DELOVNE OPREME

Drugi pogled so pregledi, ki se ustvarjajo na objekte delovne opreme. En
pregled je povezan z enim kosom delovne opreme.

Za vnos pregleda delovne opreme izberite »Delovna oprema -\> Pregledi
-\> Dodaj pregled«.

Po izbiri stranke, ali če je že izbrana aktivna stranka, bo prikazan
seznam vse delovne opreme izbrane stranke, razen opreme, ki je odpisana.

Osnovi parametri za vnos pregleda so:

-   Stranka

```{=html}
<!-- -->
```
-   Mikro-lokacija

```{=html}
<!-- -->
```
-   Datum pregleda

```{=html}
<!-- -->
```
-   Veljavnost (let)

```{=html}
<!-- -->
```
-   Uporabnik / naslov uporabnika del. Opreme

```{=html}
<!-- -->
```
-   Ustreza: da/ne

```{=html}
<!-- -->
```
-   Tabela za izbiro posamezne delovne opreme

V tabeli seznama del. opreme je možno izbrati samo eden kos opreme in
narediti pregled. Postopek ponovite tolikokrat, da naredite pregled za
vso opremo katero ste pregledali na terenu pri stranki.

Pregledi so lahko: prvi, periodični ali kontrolni.

Pri ustvarjanju novega pregleda lahko izberete Preizkuse po meri katere
lahko definirate na vmesniku »Nastavitve -\> Preizkusi po meri«. Na ta
način lahko dodajate preizkuse kateri so vam potrebni za različno
delovno opremo in za prikazovanje na zapisnikih.

Prejšnje preglede je možno kopirati če je rezultat pregleda enak, ali
podoben kakor predhodni. Za kopiranje izberete ikono (copy) na desni
strani seznama pregledov.

ZAPISNIKI

Zapisniki predstavljano tretji pogled oz. končno storitev katero ste
naredili pri stranki in vsebujejo po navadi več različnih pregledov
delovne opreme.

Za novi zapisnik izberete: »Delovna oprema - \> zapisniki -\> dodaj
zapisnik«

Po izbiri stranke v spodnji tabeli so vidni vsi pregledi stranke, ki še
niso dodeljeni zapisniku (prosti pregledi). Da preglede vnesete v
zapisnik izberite potrditveno polje (checkbox) na desni strani tabele.
Lahko izberete več pregledov. Osnovni parametri vmesnika za vnos so:

-   Stranka / poslovna enota

```{=html}
<!-- -->
```
-   Datum zapisnika

```{=html}
<!-- -->
```
-   Tip pregleda

```{=html}
<!-- -->
```
-   Merilniki

Ko se naredi novi zapisnik o pregledu delovne opreme bo viden na seznamu
in se lahko ureja / briše ali tiska DOCX potrdilo odvisno katero ikono
izberete.

QR KODE -- ROA (Remote object access)

Za dostop do informacija o delovni opremi in ustvarjanja novih pregledov
lahko uporabite modul ROA (Remote Object Access).

Pri vnosu delovne opreme, sistem avtomatično generira QR kodo katera se
lahko uporablja na terenu za identifikacijo in operacije na delovni
opremi.

Skeniranjem QR kode se prikaže ekran z informacijami o delovni opremi in
zadnjega pregleda. Ta informacija je po prednastavljeni vrednosti javno
dostopna in sistem ne zahteva prijave. Ta nastavitev se lahko premeni na
seznamu sistemskih modula, v kolikor se označi »zahtevaj prijavo«.

V kolikor se želi ustvariti pregled opreme na terenu se klikne na gumb
»Ustvari pregled«. Ta operacija zahteva prijavo kot sistemski uporabnik
Optime Prevent. Prijavo je potrebno narediti samo pri skeniranju prve
delovne opreme.

QR BULK USTVARJANJE

Drugi način dodeljevanja QR kod delovni opremi je prek ustvarjanja
»bianko« QR kod ki so proste in se na terenu dodeljujejo delovni opremi.

Za dostop izberite na glavnem meniju »Seznami« - QR ustvarjanje

Pri skeniranju bianko QR kode sistem zahteva inicialno prijavo in potem
ponuja opcijo vnosa nove delovne opreme ali dodeljevanja QR kode že
obstajajoči delovni opremi.

Po združitvi QR kode delovni opremi, skeniranjem QR kode se prikaže info
ekran z možnostjo dodajanja pregleda.

QR kode lahko ustvarite iz CSV/Excel datoteke katera vsebuje URL
povezave bulka. Pri tem lahko dodate svoj logo, kontaktne informacije
itn.

![](./docs/media/image27.png){width="1.8444444444444446in"
height="2.1104166666666666in"}

OCENE TVEGANJ

Ocena tveganja je centralni dokument varnostnih politik stranke in na ta
dokument so povezane informacije usposabljanja, VZD/EKO meritvah, osebne
varovalne opreme, zdravniških pregledov, evidenc nevarnih snov in
pregledov delovne opreme.

Vsi vmesniki za vnos in urejanje ocen tveganja v aplikaciji Optima
Prevent se nahajajo v glavnem meniju.

TVEGANJA IN KATEGORIJE

Preden se začne z vnosom ocen, je potrebno definirati tveganja in
določiti stopnjo tveganja. Uporablja se standardni nabor za
klasificiranje tveganj, vendar se lahko razlikuje pri posameznih
družbah.

Za dostop do vmesnika za urejanje tveganj izberite »Ocene tveganj -\>
Urejanje tveganj«.

Pri vnosu tveganja se lahko določijo splošni ukrepi za posamezna
tveganja katera se bodo prikazala na oceni tveganja za tipično delovno
mesto TDM.

\* POMEMBNO: Ko se tveganja in kategorije enkrat vnesejo jih ne
spreminjati več, ker spremembe bo vplivale pri dinamični generaciji
dokumentov že opravljenih ocen.

TIPIČNA DELOVNA MESTA

Tipična delovna mesta so kategorije delovnih mest z skupnimi
karakteristikami. V aplikaciji se definirajo splošni TDM-ji, ki so vidni
pri izbiri TDM za izdelavo ocen tveganj.

Pri dodajanju TDM-ja lahko definirate splošne karakteristike TDM-ja kot
so: ime, glavna in občasna opravila, trajanje opravil, opis dela, osebna
varovala oprema\... Ta polja se bodo prikazala pri vnosu ocene z
možnostjo urejanja in dodajanja teksta.

Za dostop do vmesnika za urejanje TDM izberite »Ocene tveganj -\> Seznam
TDM«.

Pri vnosu/urejanju TDM so vidna vsa tveganja in kategorije tveganj
definirana v aplikaciji. Na desni strani preglednice seznama se izbirajo
tveganja katera se bo obravnavala za posamezno TDM pri vnosu ocene.

OCENE ZA TDM

Ko so definirani zgornji objekti v sistemu, lahko se začne z
ustvarjanjem ocene tveganja. V sistemu termin »ocena tveganja« se
uporablja za varnostno oceno posameznega TDM-ja. Končni dokument OTV je
vsota več ocen tveganja za TDM-je.

Za dostop do vmesnika za urejanje ocen »Ocene tveganj -\> Seznam ocen«.

Ocena za TDM se izvaja v več korakih:

-   Na prvem koraku se izbere stranka, že definiran TDM in datum ocene.

```{=html}
<!-- -->
```
-   Na drugem koraku se izberejo zaposleni v stranki, ki spadajo po ta
    TDM. Zaposleni, ki so že določeni za ta TDM na vmesniku
    »Stranke-\>Zaposleni« so avtomatično izbrani. Ostale zaposlena lahko
    dodelite TDM-ju na tem vmesniku.

```{=html}
<!-- -->
```
-   Na tretjem koraku se prikažejo splošne informacije za TDM katere
    lahko urejate in dodajate. Na spodnjem delu vmesnika je tabela
    seznama tveganj kateri se obravnavajo za TDN. V tabeli so standardni
    parametri: R0, t, Kon, Kš, Ku in ocene pogostosti, verjetnosti in
    posledic.

```{=html}
<!-- -->
```
-   Na četrtem koraku se prikažejo tveganja za katere je vsota
    pogostosti, verjetnosti in posledic večja od 3 in na tem vmesniku se
    lahko urejajo ukrepi za tveganja kakor in odgovorna oseba stranke za
    izvedbo ukrep. Na tem poslednjem vmesniku se definirajo število
    mesecev oz. Periodika izvedbe usposabljanja, pregledov del. Opreme,
    zdravniški pregledi in meritve za TDM. Te številke so pomembne ker
    sistem spremlja periodiko za posamezno stranko če ima definirano
    oceno tveganja.

DOKUMENTI OTV

Dokument oz. zapis OTV je sestavljen iz več ocen za TDM-je in je končni
dokument za stranko oz. Poslovno enoto stranke.

Za dostop do vmesnika za urejanje zapisnikov OTV »Ocene tveganj -\>
Dokumenti OTV«.

Pri dodajanju zapisnika je potrebno izbrati stranko, če še ni izbrana
aktiva stranka. Po izbiri so vidne ocene tveganja za TDM-je katere še
niso združene v končni dokument in se izbirajo na desni strani vmesnika.

Na vmesniku se tudi izbira poslovna enota, datum zapisnika, podloga za
izpis\....

Na spodnji strani se nahaja tabela analize varnostnega stanja za objekt,
kje se lahko vpiše kaj je že izvedeno in opombe. Ta seznam se lahko
definira na vmesniku »Nastavitve -\> preizkusi po meri« in se lahko
prilagaja potrebam matične družbe.

VZD / EKO MERITVE

Za pregled vseh opravljenih meritev na glavnem meniju izberite EKO
meritve.

V seznamu so vidne vse opravljene meritve uporabnika, če ste prijavljeni
kakor Administrator, so vam vidne vse meritve v sistemu.

Za filtriranje rezultatov seznama opravljenih meritvah lahko uporabljate
»Filter« funkcionalnost (stranka, tip meritve, uporabnik).

DODAJANJE MERITVE

Postopek dodajanja meritve se izvaja v 2 do 3 korakih odvisno o tipu
meritve.

Prvi pogled so splošne informacije skupne vsem tipom meritvah. To so:

-   Stranka,

```{=html}
<!-- -->
```
-   Poslovna enota,

```{=html}
<!-- -->
```
-   Datum meritve,

```{=html}
<!-- -->
```
-   Podatki o predhodnih meritvah,

```{=html}
<!-- -->
```
-   Datum in številka poročila,

```{=html}
<!-- -->
```
-   Priložene datoteke,

```{=html}
<!-- -->
```
-   Uporabljeni merilniki\...itn.

Tip meritve je lahko: meritev okolja (toplota / osvetljenost),
elektrike, strelovoda, hrupa, pretoka zraka\...

Odvisno o izbranem tipu meritve prikaže se drugi pogled za vnos
parametrov meritve. Vnos meritev je možno končati na prvem pogledu, če
ne želite vnašati parametre meritve in želite imeti podatke samo za
evidenco.

Po končanemu vnosu podatkov o meritvah je prikaz na seznamu in jih lahko
urejate, brišete, kopirate ali tiskate potrdilo iz že določene DOCX
podloge.

Že vnesene meritve lahko kopirate s klikom na akcijski gumb za kopiranje
in izbrano meritev uporabite kot podlago za novo meritev, če imate isto
ali podobno meritev. Kopirana meritev je nova meritev in se lahko
spreminja vse parametre. Na ta način lahko prihranite čas, ko se
izognete ponavljajočim vnosom podatkov.

Za kopiranje meritev izberite ikono za kopiranje na desni strani tablice
seznama meritev v akcijskem meniju .

POŽARNA VARNOST

Požarna varnost je modul za spreminjanje vseh relevantnih evidenc
požarne varnosti. Evidence so vezane na posamezne poslovne enote strank.
Pri oblikovanju modula so upoštevani vsi zakonski predpisi RS.

DOSTOP: izberite »Požarna varnost -\> Seznam objektov«.

Odvisno o izbrani aktivni stranki se prikaže seznam objektov za katere
se spremlja veljavnost požarnih evidenc.

Za dodajanje novega objekta izberite gumb »Dodaj objekt«.

Osnovni parametri za vnos novega objekta so:

-   Stranka / Poslovna enota

```{=html}
<!-- -->
```
-   Ocena požarne ogroženosti / število oseb -- če je številka 3 ali
    večja in število oseb 100 ali več, za objekt se prikaže evidenca za
    izvajanje letnih vaj evakuacije

```{=html}
<!-- -->
```
-   Možnost izbira ostalih datotek povezanih za objekt

V formi za vnos se lahko določi veljavnost (število mesecev) za vse
zapise in na ta način je možno v modulu »Periodika« spremljati
veljavnost vseh evidenc.

Po uvodnem pogledu za dodajanje objekta, se dodatno prikažejo seznami
evidenc:

-   Aktivna požarna zaščita -- tipe APZ lahko dodajate / urejate
    »Požarna zaščita -\> tip APZ«.

```{=html}
<!-- -->
```
-   Ročni gasilniki -- Seznam ročnih gasilnikov lahko uvozite prek CSV
    datoteke.

```{=html}
<!-- -->
```
-   Usposabljanje zaposlenih -- evidenca povezana z modulom
    usposabljanja

```{=html}
<!-- -->
```
-   Vaje evakuacije

```{=html}
<!-- -->
```
-   Kurilne in dimne naprave

```{=html}
<!-- -->
```
-   Strelovodi in elektro naprave -- evidenca povezana z modulom EKO/VZD
    meritve

```{=html}
<!-- -->
```
-   Odgovorne osebe za PV

```{=html}
<!-- -->
```
-   Hidrantni list

```{=html}
<!-- -->
```
-   Seznam požari in eksplozij

Veljavnosti evidenc (število mesecev do obnovitve) se spremljajo v
analitičnem modulu.

Meritve strelovoda in elektrike lahko uvozite iz modula EKO/VZD meritve,
ali se ročno napišejo podatki kot informacija v skupni evidenci.

Evidence lahko izvozite v PDF obliki klikom na PDF ikono na desni strani
seznam evidenc.

Evidenco usposabljanja zaposlenih za gašenje začetnih požarov in
evakuacije lahko avtomatično povežete z glavnim modulom usposabljanja
sistema izbiro tipa tečaja za spremljanje v formi za vnos objekta.

EVIDENCE

ZDRAVNIŠKI PREGLEDI

Je modul narejen za spremljanje zdravniških pregledov zaposlenih in
izdajo napotnic. Pregled je lahko predhodni, obdobni preventivni ali
kontrolni.

Veljavnost zdravniških pregledov se spremlja v modulu za Analitiko.

Za dostop do vmesnika izbere se „Evidence -\> Zdravniški pregledi".

Na maski za dodajanje pregledov glavni parametri za vnos so:

-   Stranka,

```{=html}
<!-- -->
```
-   Zaposleni,

```{=html}
<!-- -->
```
-   Tip pregleda,

```{=html}
<!-- -->
```
-   Datum pregleda,

```{=html}
<!-- -->
```
-   Datum napotnice,

```{=html}
<!-- -->
```
-   Veljavnost (št. mes) pregleda,

```{=html}
<!-- -->
```
-   Ostala polja potrebna za napotnico

Polja so povezana z šifranti kot olajšava za vnos podatkov za izdajo
napotnic. Šifranti so dosegljivi s klikom na ikono na vrhu polja za
vnos. Napotnice z obliko upoštevajo zakonske odredbe RS in se lahko
tiskajo z izbiro PDF ikone na desni strani tabele seznama pregledov.

OSTALE EVIDENCE

Modul »Ostale evidence« je fleksibilen in omogoča vnos vseh evidenc, ki
niso direktno poimenovane v sistemu Optima Prevent.

DOSTOP: izberite »Evidence -\> Ostale evidence«.

Pri seznamu je omogočena filter opcija podatkov zaradi lažjega prikaza
relevantnih zapisov.

Pri vnosu evidence so osnovni parametri naslednji:

-   Stranka / poslovna enota,

```{=html}
<!-- -->
```
-   Naziv evidence,

```{=html}
<!-- -->
```
-   Datum evidence,

```{=html}
<!-- -->
```
-   Veljavnost (število mesecev),

```{=html}
<!-- -->
```
-   Datoteke kot priponke evidenci.

V analitičnem modulu so vidni podatki ostalih evidenc in odvisno če je
vnesen parameter veljavnosti spremlja se veljavnost ostalih evidenc.

DELOVNE NEZGODE

Za dostop do vmesnika izbere se »Evidence -\> Delovne nezgode«

Na maski za dodajanje prijave nezgode so glavni parametri za vnos
naslednji:

-   Stranka,

```{=html}
<!-- -->
```
-   Zaposleni,

```{=html}
<!-- -->
```
-   Informacije o osebi

```{=html}
<!-- -->
```
-   Datum dogodka,

```{=html}
<!-- -->
```
-   Delovno mesto,

```{=html}
<!-- -->
```
-   Kraj dogodka,

```{=html}
<!-- -->
```
-   Ostala polja potrebna za izjavo o delovni nezgodi

Polja so povezana z šifranti tako, da se olajša vnos podatkov. Šifranti
so dosegljivi klikom na ikono na vrhu polja za vnos. Prijave z obliko
upoštevajo zakonske odredbe RS in se lahko tiskajo (PDF ikona na desni
strani tabele seznama).

OSEBNA VAROVALNA OPREMA

OVO modul je narejen za spremljanje izdaje osebne varovalne opreme
zaposlenim in s tem skladnosti z oceno tveganja za stranko.

Za dostop izberite »Evidence -\> Osebna var. Oprema«.

Glavni parametri so:

-   Stranka,

```{=html}
<!-- -->
```
-   Zaposleni,

```{=html}
<!-- -->
```
-   Datum izdaje

```{=html}
<!-- -->
```
-   Veljavnost,

```{=html}
<!-- -->
```
-   Opombe,

```{=html}
<!-- -->
```
-   Seznam opreme in Standardi

Na desni strani vmesnika za vnos je prikazan seznam standardov in
kategorij kot pomoč pri vnosu podatkov.

ANALITIKA

PERIODIKA

Modul za spremljanje periodike je osnovni modul analitičnega dela
aplikacije in je zadolžen za spremljanje veljavnosti vseh vnosov strank
:

-   Pregledi delovne opreme

```{=html}
<!-- -->
```
-   Veljavnost narejenih tečajev

```{=html}
<!-- -->
```
-   Usposabljanje za zaposlene

```{=html}
<!-- -->
```
-   Evidence požarne varnosti

```{=html}
<!-- -->
```
-   Veljavnosti EKO/VZD meritvah

```{=html}
<!-- -->
```
-   Zdravniški pregledi

```{=html}
<!-- -->
```
-   Ostale evidence

Za dostop po vmesnika periodike, izberite »Analitika -\> Periodika«.

Podroben vpogled v podatke veljavnosti je viden v ločenih tabelah
glavnega dela vmesnika.

Pri delu uporabniki pogosto potrebujejo specifične podatke za posamezno
stranko, določeno obdobje, uporabnika \...itn. Za prikaz relevantnih
informacija se uporablja izbira aktivne stranke in filter gumb na desni
strani.

Obstaja tudi koledarski način prikaza periodike in na tem delu so
prikazani roki različnih veljavnosti po dnevih / mesecih / letih.
Različni tipi periodike so obarvani s pripadajočimi barvami:

-   delovna oprema -- rumena,

```{=html}
<!-- -->
```
-   EKO/VZD meritve -- zelena,

```{=html}
<!-- -->
```
-   usposabljanje -- modra,

```{=html}
<!-- -->
```
-   požarna varnost -- rdeča,

```{=html}
<!-- -->
```
-   zdravniški pregledi -- vijolična,

```{=html}
<!-- -->
```
-   ostale evidence -- siva.

V seznamu so tudi prikazani novi zaposleni, ki še niso imeli
usposabljanje, enako delovna oprema, ki še ni bila pregledana.

Posamezna vrstica je sestavljena iz osnovnih podatkov: ime objekta,
stranka / poslovna enota, datum pregleda / usposabljanja, veljavnost, in
datum poteka.

Če je veljavnost že potekla so črke v vrstici obarvane rdeče.

PREGLED REALIZACIJE

Pregled realizacije je vmesnik, ki vam omogoča vpogled v sva opravljena
dela in podpira filtriranje, z možnostjo izbire prikazov podatkov.

Za dostop po vmesnika izberite »Analitika - \> Pregled realizacije« .

Možnosti filtriranja: Datum od, Datum do, Uporabnik.

Podatki se prikažejo v tabelah in v BAR diagramu kje so različni tipi
podatkov obarvani v različnih barvah.

IZDANI DOKUMENTI

Vmesnik omogoča vpogled v vse izdane dokumente matične družbe. Isti
dokument lahko ima več različic, ki so vidne na seznamu.

Dostop do vmesnika »Analitika -\> Izdani dokumenti«

Na zgornjem delu je iskalnik za izbiro parametrov kako bi se našli
relevantni dokumenti. Parametri iskalnika so: stranka (aktiva stranka),
tip dokumenta, vremenski period izdaje, zaposleni ....

Izdane dokumente je možno ročno spreminjati in dodajati nove verzije na
način, da se prenese dokument s klikom na ikono za prenos (download) na
desni strani osnovne vrstice dokumenta. Ko se ročno uredi dokument
izberete gumb »Nova verzija« in se izberete dokument za urejanje na
lokalnemu računalniku.

POROČILO PO DEJAVNOSTI

Zakoni RS predpisujejo, da se oddajajo letna poročila za število
objektov / opreme na katerih so narejeni pregledi. Ta modul vam lahko
pomaga in olajša številčenje in izdajo potrebnih letnih poročil.

SISTEM OBVEŠČANJA

Sistem komunikacije in obveščanje je razdeljen na dve ravni: interna in
zunanja komunikacija.

Interna komunikacije se izvaja med uporabnikom sistema in omogoča
uporabnikom real-time komunikacijo za lažje usklajevanje in delovanje na
projektih. Interna komunikacije je možna tudi uporabnikom stranke, da
lahko komunicirajo z dodeljenim skrbnikom.

Sistem podpira tudi transparentno obveščanje skrbnikov strank s tem so
uporabniki/skrbniki pravočasno obveščeni o narejenih spremembah v
objektih posameznih strank.

Zunanja komunikacije se izvaja prek šifrirane e-mail komunikacije.
Nastavitve e-mail parametrov so dostopne v konfiguraciji sistemskih
uporabnikov in v nastavitvah matičnega podjetja.

UREJANJE PODLOG ZA IZPIS

PREDLOGE FORMS

Predloge tipa FORMS so omogočene v sistem prek zasebnega modula in
omogočajo ustvarjanje dokumentov za netipične preglede (kontrolni
pregledi, vaje evakuacije\....).

Za dostop do FORMS predlog izberite Nastavitve -- Predloge FORM

Elementi predloge so:

-   Naslov

```{=html}
<!-- -->
```
-   Podnaslov

```{=html}
<!-- -->
```
-   Naslov tabele

```{=html}
<!-- -->
```
-   Tekst

```{=html}
<!-- -->
```
-   Polje za vnos -- input field

```{=html}
<!-- -->
```
-   Potrditveno polje - checkbox

```{=html}
<!-- -->
```
-   Potrditveno polje dvojno -- da / ne checkbox

```{=html}
<!-- -->
```
-   SQL koda

Kot vrednosti elementov se lahko uporabljajo variable ( cCustomer,
cAddress ....)

PREDLOGE DOCX

Podloge za izpis se uporablja za izdajo potrdil / zapisnikov in jih je
možno prilagajati s formo in vsebino glede na zahteve stranke. Format
podlog je Word dokument (DOCX), ki je sestavljen iz statičnega in
dinamičnega dela.

Statični del vsebuje informacije formatiranja dokumenta (pozicije
elementov, statični tekst, barve, slike...).

Dinamični del je sestavljen iz spremenljivega formata \${imeVar}
katerega izpolni dinamični sistem. Spremenljivke so lahko:

-   Posamezne variable

```{=html}
<!-- -->
```
-   Variable tabele katere sestavljajo tabele (vrstne variable)

```{=html}
<!-- -->
```
-   Blok variable -- paragrafi, ki se ponavljajo. Paragrafi tudi lahko
    vsebujejo posamezne ali variable tabele.

Podloge za izpis se urejajo na maski Nastavite -\> urejanje predlog.

Ko dodate novo podlogo, določite ime, tip podloge, zaporedno številko in
DOCX datoteko.

Tipi podloge so: usposabljanje, delovna oprema, meritve, ocena tveganja.
Odvisno od tipa podloge, sistem avtomatično izbira podlogo za izpis pri
vnosu storitve. Možno je uporabljati več podlog za isto storitev. Če jih
je več na voljo, avtomatično se izbira tista, ki ima manjšo zaporedno
številko. To se lahko spremeni ročno pri vnosu storitve.

LEGENDA GENERALIH VAR

\${cName} Ime stranke

\${cAddress} Naslov sedeža stranke

\${cCity} Mesto sedeža stranke

\${cZip} Poštna št. sedeža stranke

\${cTax} Davčna št. stranke

\${cPersResp} Kontakt / Odgovorna oseba stranke

\${locContact} Kontakt / Odgovorna oseba poslovne enote

\${cBusCode} Šifra delavnosti

\${cBusCodeName} Naziv delavnosti

\${locName} Ime poslovne enote stranke (PE)

\${locCity} Mesto PE

\${locZip} Poštna št. PE

\${uName} Ime in Priimek uporabnika

\${uSignImg} Podpis uporabnika

\${uCertDev} Uporabniški certifikat -- delovna oprema

\${uCertEdu} Uporabniški certifikat -- usposabljanje

\${uCertMes} Uporabniški certifikat -- meritve

\${acron} akronim uporabnika

\${expTitle} strokovni naziv uporabnika

\${repY} leto

\${repy} leto -- krajša forma

\${repM} mesec

LEGENDA VAR ZAPISNIKA O USPOSABLJANJU

**Posamezne spremenljivke:**

\${dateRep} Datum zapisnika

\${dateStart} Datum začetka usposabljanja

\${custNrRep} Številka zapisnika

\${txtCust1} Tekst po meri 1

\${txtCust2} Tekst po meri 2

\${txtLaw} Tekst zakonskih odredb

\${nrHour} Število ur usposabljanja

\${nrProg} Program usposabljanja

\${location} Lokacija

\${mntValid} Veljavnost -- št. mesecev

**Spremenljivke tabel:**

TABELA -- EDINSTVEN SEZNAM DELAVCEV:

\${rowNameUn} Ime in Priimek delavca

\${rowCntUn} Redna št.

\${rowDateBirthUn} Datum rojstva

\${rowWorkPlaceUn} Delovno mesto

\${rowEduTypeUn} Tip usposabljanja

TABELA -- SEZNAM DELAVCEV :

\${rowName} Ime in Priimek delavca

\${rowCnt} Redna št.

\${rowDateBirth} Datum rojstva

\${rowWorkPlace} Delovno mesto

\${rowNrRep} Številka potrdila

\${rowEduType} Tip usposabljanja

\${rowNrProg} Program usposabljanja

\${rowRes} uspešno / neuspešno

TABELA -- SEZNAM TEČAJEV V ZAPISNIKU

\${rowEdulstEdutype} Tip usposabljanja

\${rowEdulstMntValid} Veljavnost

**Blok spremenljivke:**

\${cloneCert0} {/\$cloneCert0} Blok v katerem se ponavljajo potrdila

\${attName} Ime Priimek

\${attWorkPlace} Delovno mesto

\${attDateBirth} Datum rojstva

\${attDateValid} Datum veljavnosti potrdila

\${attMntValid} Velja -- mes.

\${attDateEtest} Datum opravljanja usposabljanja

\${attLocName} Poslovna enota zaposlenega

\${attLocAddress} Naslov poslovne enote zaposlenega

\${attLocCity} Naslov poslovne enote zaposlenega

LEGENDA VAR ZAPISNIKA O PREGLEDU DEL. OPREME

**Posamezne spremenljivke:**

\${dateRep} Datum zapisnika

\${dateTest} Datum pregleda

\${devUser} Uporabnik delovne opreme

\${devUserAddr} Naslov uporabnika delovne opreme

\${custNrRep} Številka zapisnika

\${dateLastRep} Datum zadnjega pregleda

\${nrLastRep} Št. Zadnjega pregleda

\${infoLast} tekst opis zadnjega pregleda

\${nrHour} Število ur usposabljanja

\${txtType} Tip pregledov

\${desc} opis metodologije

\${result} Skupni rezultat

**Spremenljivke tabel:**

TABELE -- KRATEK SEZNAM PREGLEDANE OPREME:

\${rowShortName} Naziv opreme

\${rowShortCnt} Redna št.

\${rowShortResult} Rezultat pregleda

\${rowInstName} Naziv merilnika

\${rowInstCert} Certifikat merilnika

TABELA -- PODROBEN SEZNAM PREGLEDANE OPREME

\${lstName} Naziv opreme

\${lstNrRep} Št. potrdila

\${lstDateTest} Datum pregleda

\${lstSerial} Serijska št.

\${lstNrInv} Inventarna št.

\${lstLocation} Mikro lokacija pregleda delovne opreme

\${lstLocationObj} Mikro lokacija objekta delovne opreme

\${lstTypeDevice} Tip / Model opreme

\${lstDesc} Dodaten opis

\${lstDoc} Predložena dokumentacija

\${lstResult} Rezultat pregleda

\${lstIndPass} Indikator ustreznosti

\${lstManufacturer} Proizvajalec

\${lstManufactYear} Leto izdelave

\${lstMesOhm} Izmerjena upornost

\${lstChkName} Pregledi po meri

\${lstChkResult} Rezultat pregleda po meri

\${lstChkValue} Izmerjena vrednost pregleda po meri

\${lstChkSist} Referenčna vrednost pregleda po meri

\${lstChkElecName} El. Pregledi po meri

\${lstChkElecResult} Rezultat el. pregleda po meri

\${lstChkElecValue} Izmerjena vrednost el pregleda

\${lstChkElecSist} Referenčna vrednost el. pregleda

**Blok spremenljivke:**

\${cloneDevLst} {/\$cloneDevLst} Info blok pregledane opreme

\${cloneCert0} {/\$cloneCert0} Blok v katerem se ponavljajo potrdila

\${devUsage} Namen delovne opreme

LEGENDA VAR ZAPISNIKA MERITVE DELOVNEGA OKOLJA

**Posamezne spremenljivke:**

\${dateRep} Datum zapisnika

\${dateTest} Datum pregleda

\${hourTest} Čas pregleda

\${custNrRep} Številka zapisnika

\${dateLastRep} Datum zadnjega pregleda

\${nrLastRep} Št. Zadnjega pregleda

\${infoLast} tekst opis zadnjega pregleda

\${RH} Relativna vlaga

\${Temp} Zunanja Temperatura

\${VA} Gibanje zraka

\${Weather} Vreme

\${result} Skupni rezultat

**Spremenljivke tabel:**

TABELA -- KRATEK SEZNAM PREGLEDANE OPREME:

\${rowShortName} Naziv opreme

\${rowShortCnt} Redna št.

\${rowShortResult} Rezultat pregleda

\${rowInstName} Naziv merilnika

\${rowInstCert} Certifikat merilnika

TABELA -- MERILNA MESTA -- TOPLOTNE RAZMERE

\${rowTCnt} Redna št.

\${rowTName} Nazive merilnega mesta

\${rowTT110} Temp T110

\${rowTVA} Gibanje zraka

\${rowTRH} Rel. vlaga

\${rowTMet} MET

\${rowTPos} Položaj

\${rowTIclo} ICLO

\${rowTPMV} PMV

\${rowTPPD} PPD

\${rowTResult} Rezultat

TABELA -- MERILNA MESTA -- SVETLOBA

\${rowLCnt} Redna št.

\${rowLName} Naziv merilnega mesta

\${rowLType} Tip svetilke

\${rowLTypeLum} Tip osvetljenosti

\${rowLEDN} E dnevna

\${rowLEKOM} E Kombinirana

\${rowLEUM} E Umetna

\${rowLEDOD} E Dodatna

\${rowLEMIN} E Minimalna izmerjena

\${rowLUO} Emin / Ekomb

\${rowLUOMIN} Uo Min

\${rowLSIST} SIST -- nominalna vrednost

\${rowLResult} Rezultat

MERITVE PO SKUPINAH:

\${cloneMesGrp} clone var

\${mesGrpName} naziv skupine

\${rowMesName} naziv mer. mesta

\${rowMesCnt} zap. št.

\${rowMesT110}

\${rowMesT01}

\${rowMesVA}

\${rowMesRH}

\${rowMesMet}

\${rowMesPos}

\${rowMesIclo}

\${rowMesPMV}

\${rowMesPPD}

\${rowMesTSO}

\${rowMesLType}

\${rowMesTypeLum}

\${rowMesEDN}

\${rowMesEKOM}

\${rowMesEUM}

\${rowMesEDOD}

\${rowMesEMIN}

\${rowMesUO}

\${rowMesUOMIN}

\${rowMesLSIST}

\${rowMesLSO}

\${rowMesT}

\${rowMesTex}

\${rowMesLeq}

\${rowMesKi}

\${rowMesLai}

\${rowMesLc}

\${rowMesLexmax}

\${rowMesLex8h}

\${rowMesSource}

\${rowMesDesc}

\${rowMesNSO}

LEGENDA VAR ZAPISNIKA MERITVE DELOVNEGA HRUPA

**Posamezne spremenljivke:**

\${dateRep} Datum zapisnika

\${dateTest} Datum pregleda

\${custNrRep} Številka zapisnika

\${dateLastRep} Datum zadnjega pregleda

\${nrLastRep} Št. Zadnjega pregleda

\${infoLast} tekst opis zadnjega pregleda

\${Temp} Zunanja Temperatura

\${result} Skupni rezultat

**Spremenljivke tabel:**

\${rowInstName} Naziv merilnika

\${rowInstCert} Certifikat merilnika

TABELA

\${rowCnt} Redna št.

\${rowName} Naziv merilnega mesta

\${rowt} Čas izvajanja meritve

\${rowtex} Čas ekspozicije

\${rowLeq} Laq

\${rowKi} KI korekcija

\${rowLai} Lai

\${rowLc} Lc peak

\${rowLexmax} Lexmax

\${rowLex8h} Lex8h

\${rowResult} Rezultat

\${rowSource} Vir hrupa

\${rowDesc} Dodaten opis

LEGENDA VAR OCEN TVEGANJA

**Posamezne spremenljivke:**

\${dateRep} Datum izdelave zapisnika

\${cPersResp} Odgovorna oseba stranke za VZD

\${cPersMed} Pooblaščeni zdravnik

\${cntEmp} Število zaposlenih

\${cntEmpM} Število zaposlenih -- moški

\${cntEmpF} Število zaposlenih -- ženske

\${descWorkEnv} Opis delovnih prostorov

**Spremenljivke tabel:**

\${rassName} Naziv TDM

\${rassCnt} Zap. št. TDM

\${rowEmpName} Ime in Priimek zaposlenega

\${rowEmpDateBirth}Datum roj. zaposlenega

\${rowEmpWM} Delovno mesto zaposlenega

\${rassMntMed} Periodika zdr. pregledov

\${rassMntEnv} Periodika meritev delo. okolja

\${rassMntNoise} Periodika meritev hupa

\${rassMntDev} Periodika pregledov del. opreme

\${rowRassEduName} Ime tečaja

\${rowRassEduMnt} Periodika usposabljanja

LEGENDA VAR LETNEGA POROČILA ZA STRANKE

**Posamezne spremenljivke:**

\${cTaxNr} DDV številka

\${cRegId} Registracijska številka

\${cBusCodeName} Čas pregleda

\${cPersResp} Odgovorna oseba

**Spremenljivke tabel:**

TABELA -- ZAPISNIKI USPOSABLJANJA:

\${rowLnameGedu} Poslovna enota

\${rowNrGedu} Št. zapisnika

\${rowDateGedu} Datum zapisnika

\${rowNrPers} Št. oseb

TABELA -- ZAPISNIKI DELOVNE OPREME:

\${rowLnameGdev} Poslovna enota

\${rowNrGdev} Št. zapisnika

\${rowDateGdev} Datum zapisnika

\${rowTypeGdev} Tip pregleda

TABELA -- OCENE TVEGANJA:

\${rowLname} Naziv opreme

TABELA -- SEZNAM ZAPISNIKOV USPOSABLJANJA:

\${rowLname} Naziv opreme

LEGENDA VAR SISTEMA APZ

**Posamezne spremenljivke:**

\${vppObjName} Naziv VPP objekta

\${dateRep} Datum izdelave poročila

\${dateValid} Datum veljavnosti pregleda

\${typeName} Tip SAPZ

\${descName} Naziv sistema in proizvajalci

\${infoLast} Opis zadnjega pregleda

\${descGeneral} Splošen opis

\${descBuildPerm} Gradbeno in uporabno dovoljenje

\${descBuildLaw} Gradbeni predpisi

\${descManufactDocs} Predpisane listine proizvajalca

\${descTehSuperv} Tehnični pregledi SAPZ

\${descDuration} Trajanje preizkusa

\${descCharReq} Karakteristične zahteve

\${descCheckMeth} Metodologija preizkusa

\${descPers} Sodelujoči
