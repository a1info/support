# Navigacija in skupne akcije

## Meni in navigacija

Uporabniški vmesnik aplikacije Optima Prevent je razdeljen na več ključnih navigacijskih področij:

- **Glavni levi meni** – vsebuje funkcionalne sklope v obliki padajočih menijev (npr. Zaposleni, Delovna oprema, Usposabljanje, Evidence idr.). Meni je vedno dosegljiv na levi strani zaslona.
- **Zgornji uporabniški meni** – desno zgoraj se nahajajo ikone za obvestila (zvonček), interna sporočila (ovojnica), meni profila in odjava.
- **Izbirnik aktivne stranke** – nahaja se v zgornjem desnem delu zaslona in je **ključen za delovanje aplikacije**.

### Aktivna stranka

Izbirnik aktivne stranke določa kontekst za vse vnose in prikaze podatkov v aplikaciji. Ko izberete aktivno stranko:

- so vnosni in urejevalni obrazci **samodejno nastavljeni** na izbrano stranko,
- vsi seznami in poročila prikazujejo podatke **samo za to stranko**,
- zagotovljeno je, da podatki ne mešajo med različnimi strankami.

!!! tip "Nastavite aktivno stranko pred delom"
    Pred pričetkom vnosa ali pregledovanja podatkov vedno preverite, ali je v izbirniku aktivna prava stranka. S tem se izognete napačnim vnosom ali pregledovanju napačnih podatkov.

**Administratorji** imajo na vnosnih obrazcih na voljo dodatno polje za izbiro uporabnika, kar jim omogoča **vnos podatkov v imenu drugega uporabnika**.

Parametri aktivnih filtrov so vedno prikazani nad posameznimi seznami, tako da je jasno razvidno, kateri nabor podatkov je trenutno prikazan.

---

## Iskanje in filtriranje

Večina preglednih seznamov v aplikaciji vsebuje **filter nad tabelo**, s katerim zoži prikaz na ustrezne zapise.

### Uporaba filtrov

1. Izpolnite enega ali več filternih polj nad seznamom (npr. ime, datum, status, kategorija).
2. Kliknite gumb **Najdi** ali **Poišči**, da osvežite prikaz glede na vpisane kriterije.
3. Za ponastavitev filtrov izbrišite vrednosti in znova kliknite gumb za iskanje.

### Hitro iskanje znotraj rezultatov

Poleg nastavljenih filtrov je na voljo tudi **polje za hitro iskanje** znotraj trenutno prikazanih rezultatov. Vnos besedila takoj filtrira prikazane vrstice brez dodatnega klika – iskanje deluje v realnem času med prikazanimi podatki.

---

## Skupne (bulk) akcije

Pregledni seznami podpirajo **skupne akcije**, s katerimi lahko hkrati obdelate več izbranih zapisov.

### Izbor vrstic

- Posamezno vrstico izberete z **označitvenim poljem (checkbox) na desni strani** vrstice.
- Za **izbor vseh vrstic** označite checkbox v **glavi tabele**.
- Po izboru vrstic iz spustnega menija izberete želeno skupno akcijo in jo potrdite.

### Razpoložljive skupne akcije po modulih

| Modul | Razpoložljive akcije |
|---|---|
| **Seznam delovne opreme** | Brisanje, kaskadno brisanje, skupni pregled, brisanje zgodovine sprememb |
| **Seznam pregledov** | Brisanje |
| **Seznam zaposlenih** | Brisanje, brisanje zgodovine sprememb |
| **Seznam usposabljanj** | Brisanje |

#### Opis posameznih akcij

- **Brisanje** – trajno odstrani izbrane zapise.
- **Kaskadno brisanje** – odstrani delovno opremo skupaj z vsemi njenimi pregledi in evidencami.
- **Skupni pregled** – ustvari skupen pregled za vso izbrano delovno opremo z enakimi parametri naenkrat.
- **Brisanje zgodovine sprememb** – odstrani audit log za izbrane zapise (glejte razdelek spodaj).

!!! danger "Kaskadno brisanje je nepovraten postopek"
    Akcija **kaskadno brisanje** trajno in nepovraten odstrani izbrano delovno opremo **ter vse preglede, evidence in zapise**, ki so z njo povezani. Pred izvedbo preverite izbor vrstic. Podatkov po brisanju ni mogoče obnoviti.

---

## Sledenje spremembam (Audit log)

Sistem Optima Prevent samodejno beleži **zgodovino sprememb** za ključne module:

- **Zaposleni**
- **Delovna oprema**

Ob vsakem ustvarjanju ali posodabljanju zapisa sistem v ozadju zabeleži:

| Podatek | Opis |
|---|---|
| **Kdo** | Uporabnik, ki je izvedel spremembo |
| **Kdaj** | Datum in čas spremembe |
| **Kaj** | Katere vrednosti so bile spremenjene (stara in nova vrednost) |

Ta revizijska sled omogoča sledljivost in pregled nad vsemi pomembnimi posegi v podatke.

### Brisanje zgodovine sprememb

Zgodovino sprememb za posamezne zapise je mogoče izbrisati prek skupne akcije **»Izbriši zgodovino izbranih zapisov«** na seznamu zaposlenih ali delovne opreme.

Razlogi za brisanje zgodovine so lahko:

- **GDPR zahteve** – odstranitev osebnih podatkov iz revizijske sledi,
- **čiščenje podatkovne baze** – zmanjšanje obsega podatkov za stare ali zaključene zapise.

!!! warning "Brisanje revizijske sledi je trajno"
    Akcija **»Izbriši zgodovino izbranih zapisov«** nepovraten odstrani celotno preteklo zgodovino sprememb za izbrane zapise. Po izvedbi pregled preteklih sprememb za te zapise ni več mogoč.

---

## Obvestila in sporočila

V zgornjem meniju aplikacije sta dve ikoni za komunikacijo in obveščanje:

### Sistemska obvestila (zvonček 🔔)

Ikona **zvončka** prikazuje sistemska obvestila, ki jih aplikacija samodejno generira – tipično gre za:

- opozorila o **prihajajočih ali preteklih rokih** (periodika pregledov, veljavnost dokumentov, roki usposabljanj),
- obvestila o potrebnih ukrepih.

### Interna sporočila (ovojnica ✉️)

Ikona **ovojnice** omogoča pošiljanje in prejemanje **internih sporočil** med uporabniki aplikacije Optima Prevent.

### Rdeča oznaka z neprebrano vsebino

Na obeh ikonah se prikaže **rdeča oznaka (badge) s številom**, ki kaže količino **neprebranih obvestil ali sporočil**. Ko preberete vsebino, se oznaka samodejno odstrani.