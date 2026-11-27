# Urejanje predlog (dokumenti, obrazci in e-pošta)

## Pregled

Sistem OP5 podpira štiri vrste predlog za dokumente, obrazce in e-pošto:

| Vrsta predloge | Opis | Primeri uporabe |
|----------------|------|-----------------|
| **FORMS** | Interaktivni obrazci za vnos podatkov na terenu | Nestandardni pregledi, vaje evakuacije, kontrolne liste |
| **PDF** | Nastavitve videza sistemsko generiranih PDF poročil | Poročilo o veljavnosti, glava z logotipom, izbor stolpcev |
| **DOCX** | Predloge za tiskane dokumente (potrdila, zapisniki) | Potrdila o usposabljanju, zapisniki pregledov, poročila |
| **E-poštne predloge** | Zadeva in telo e-poštnih sporočil | Opomniki, e-test vabila, obvestila in kampanje |

Predloge določajo postavitev, vsebino in obliko izpisanih dokumentov. Vsaka predloga je vezana na določen tip dokumenta in se ob generiranju samodejno napolni z dejanskimi podatki iz baze.

---

## Predloge FORMS

**Dostop:** Sistem → Predloge → zavihek **FORMS**

### Namen

Predloge FORMS se uporabljajo za **nestandardne preglede in obrazce**, kjer je treba zbirati strukturirane podatke po meri stranke. Primeri:

- Nestandardni kontrolni pregledi
- Vaje evakuacije
- Prilagojene kontrolne liste
- Interni varnostni obrazci

### Elementi obrazca

Pri urejanju predloge FORM dodajate elemente iz nabora razpoložljivih tipov:

| Element | Tip | Opis |
|---------|-----|------|
| **Naslov** | Prikaz | Glavni naslov obrazca ali razdelka |
| **Podnaslov** | Prikaz | Podrejeni naslov / opis razdelka |
| **Besedilo** | Prikaz | Statično besedilo (navodila, opisi) |
| **Potrditveno besedilo** | Prikaz | Besedilo s potrditvenim kvadratkom za potrditev |
| **Polje za vnos** | Vnos | Besedilno vnosno polje za prosti vnos |
| **Potrditveno polje (da)** | Vnos | Eno potrditveno polje (označeno / neoznačeno) |
| **Dvojno potrditveno polje (da/ne)** | Vnos | Par polj Da / Ne za binarno izbiro |
| **Slika** | Vnos | Nalaganje slike z izbiro širine |
| **Podpis** | Vnos | Podpis s prstom oziroma miško |
| **Ločilo** | Prikaz | Vodoravna črta med vsebinskimi sklopi |
| **Prelom strani** | Prikaz | Začne novo stran PDF izpisa |

### Spremenljivke v besedilu elementov

V besedilu elementov obrazca lahko uporabite vgrajene spremenljivke. V urejevalniku elementa je pod poljem **Tekst elementa** razdelek **Zamenljivke** – klik na spremenljivko jo vstavi na mesto kazalke.

| Spremenljivka | Opis |
|---------------|------|
| `${cName}` | Naziv stranke |
| `${cAddress}`, `${cZip}`, `${cCity}` | Naslov, poštna številka in kraj stranke |
| `${cBusCode}`, `${cBusCodeName}` | Šifra in naziv poslovne enote |
| `${cTax}` | Davčna številka stranke |
| `${locName}`, `${locAddress}`, `${locZip}`, `${locCity}` | Podatki lokacije oziroma objekta |
| `${uName}`, `${acron}`, `${expTitle}` | Izvajalec, akronim in naziv delovnega mesta |
| `${name}` | Naziv objekta pregleda |
| `${dateTest}` | Datum pregleda |
| `${mntValid}` | Trajanje veljavnosti (meseci) |
| `${descr}` | Opis |
| `${result}` | Rezultat pregleda |

**Primer uporabe:**
```
Izvajalec pregleda za stranko: ${cName}, ${cAddress}
```

!!! tip "Nasvet"
    Spremenljivke se vnesejo v besedilo elementa in se ob izpolnjevanju obrazca zamenjajo s podatki izbrane stranke oziroma objekta. Če v seznamu **Zamenljivke** katere ni, jo lahko vnesete ročno – neznane spremenljivke ostanejo v izpisu nespremenjene.

---

## E-poštne predloge

**Dostop:** Sistem → Predloge → zavihek **E-poštne predloge**

E-poštne predloge določajo **zadevo in telo** sporočila. Pošiljateljski račun, naslov From in Reply-To niso del predloge – ti podatki se določijo v [E-poštnih računih](sistemske-nastavitve.md#e-postni-racuni).

Predloge uporabljajo samodejna obvestila, e-test vabila in opomniki ter CRM kampanje. Brez aktivnega SMTP računa se sporočila ne pošljejo, tudi če je predloga aktivna.

!!! info "Glava kampanjskega sporočila"
    Pri CRM kampanjah glavo sporočila (logotip, naziv, slogan, naslov in kontaktni podatki) določa **znamka e-pošte**, izbrana na kampanji. Znamke upravljate v **Seznami → Znamke e-pošte**. Predloga določa zadevo in telo sporočila, ne pa pošiljateljskega računa ali znamke.

### Moduli predlog

| Modul | Uporaba |
|-------|---------|
| **Kampanje** | E-poštne kampanje v CRM; predlogo izberete na kampanji. |
| **E-test / izobraževanja** | Vabila in opomniki za e-učenje. |
| **Veljavnosti** | Periodična poročila o potekih. |
| **HRM** | Dopust, kandidati in druga kadrovska obvestila. |
| **Dokumentni tok** | Zahteve in odločitve pri odobritvah. |
| **CRM** | Naloge in dogodki v CRM. |
| **Medicina dela** | Napotitve in izvidi. |
| **ERP** | Obvestila, povezana s ponudbami in financami. |
| **Sistem** | Varnostne kopije, sinhronizacija in sistemska opozorila. |

### Polja predloge

| Polje | Opis |
|-------|------|
| **Koda** | Enolična oznaka predloge; priporočena je kratka oznaka, npr. `etest_invite_sl`. |
| **Dogodek** | Koda dogodka iz sistemskega kataloga, na katerega se predloga veže (npr. `etest.invite`, `etest.expiring`, `crm.task_created`). Začetek vnosa prikaže predloge z opisi; prazno polje pomeni splošno predlogo. Pri kampanjah polje ni prikazano. |
| **Naziv** | Naziv za skrbnike; ni del poslanega sporočila. |
| **Zadeva** | Zadeva e-pošte. |
| **Nadomestna zadeva (A/B)** | Neobvezna druga zadeva za poznejše A/B preizkuse. |
| **Telo (tekst)** | Besedilna različica sporočila; priporočena je za zanesljivo dostavo. |
| **Telo (HTML)** | Neobvezna obogatena različica. Če je prazna, se uporabi besedilna različica. |
| **Opombe** | Interne opombe, ki se ne pošljejo. |
| **Aktivna** | Neaktivna predloga se ne uporabi; sistem uporabi privzeto vsebino, če ta obstaja. |

!!! info "Jezik predloge"
    Predloga nima več ločenega polja za jezik. Sporočilo se sestavi v jeziku aplikacije oziroma uporabnika; prevod vsebine dodate tako, da za posamezni jezik ustvarite ločeno predlogo z isto kodo.

!!! info "Kako izberem dogodek"
    V polje **Dogodek** vnesite kodo iz sistemskega kataloga. Ko začnete tipkati, se prikažejo razpoložljive kode z opisom; prazno polje pomeni splošno predlogo. Če koda ni v katalogu, je shranjevanje zavrnjeno. Za kampanje izberite modul **Kampanje**; polje Dogodek je pri njih skrito, ker predlogo izbere kampanja.

### Spremenljivke

Spremenljivke vstavite v obliki `${imeSpremenljivke}`, na primer `${firstName}`. Med pošiljanjem jih sistem zamenja z dejanskimi podatki; neznane spremenljivke ostanejo vidne, da napako opazite.

Pod poljem **Telo (tekst)** je razdelek **Zamenljivke** – klik na spremenljivko jo vstavi na mesto kazalke v trenutno izbrano polje.

| Spremenljivka | Pomen |
|---------------|-------|
| `${senderName}` | Ime pošiljatelja oziroma prijavljenega uporabnika. |
| `${phone}`, `${email}`, `${website}` | Kontaktni podatki podjetja. |
| `${date}`, `${time}` | Datum in čas pošiljanja. |
| `${firstName}`, `${lastName}` | Ime in priimek prejemnika. |
| `${cName}` | Podjetje prejemnika. |
| `${sysCompany}`, `${sysTagline}`, `${sysAddress}`, `${sysEmail}`, `${sysTel}`, `${sysWeb}`, `${sysLogo}`, `${sysTax}` | Podatki izbrane znamke e-pošte pri kampanji; sicer podatki sistemskega podjetja. |
| `${course}`, `${courseStart}`, `${courseEnd}`, `${username}`, `${password}`, `${link}` | Podatki e-testa (samo modul E-test); začetek in konec tečaja oziroma potek e-testa. |
| `${expiryDate}`, `${daysLeft}` | Rok veljavnosti in število preostalih dni (e-test). |
| `${previousSubject}` | Zadeva prejšnjega sporočila (kampanje). |
| `${unsubscribeUrl}` | Povezava za odjavo. Pri kampanjah jo sistem doda samodejno, če je v sporočilu ni. |

### Glava e-pošte in znamke

Skupna glava e-pošte prikaže logotip, naziv, slogan ter naslov in kontaktne podatke znamke. Za kampanje se uporabi znamka, izbrana na kampanji oziroma privzeta znamka; za ostala sporočila se uporabi sistemska oziroma lastniška identiteta podjetja.

- Znamke dodajate in urejate v **Seznami → Znamke e-pošte**.
- Na kampanji je znamka izbrana v koraku **Predloga**.
- Predogled predloge v **Sistem → Predloge** uporabi sistemsko identiteto, ne izbrane kampanjske znamke; končno sporočilo kampanje uporabi izbrano znamko.
- Slogan je neobvezno polje znamke e-pošte in se prikaže pod nazivom; če je prazno, se vrstica ne prikaže.

### Predogled in upravljanje

1. Odprite **Sistem → Predloge → E-poštne predloge**.
2. Izberite modul in predlogo s seznama ali kliknite **Dodaj** za novo predlogo.
3. Izpolnite polja in po potrebi kliknite **Predogled** – prikazani so zamenljivi deli s primerom za izbrani modul.
4. Shranite predlogo. Izbrišete jo lahko z ikono koša; predloga, ki jo uporablja kampanja, najprej preverite.

!!! tip "Kampanjske predloge"
    Za kampanje izberite modul **Kampanje**. Predlogo nato izberete v koraku **Predloga** pri posamezni kampanji. Dogodek ni potreben, povezava za odjavo pa se doda samodejno, tudi če v predlogi ni `${unsubscribeUrl}`.

!!! note "Predloga ne določa pošiljatelja"
    Če želite spremeniti From, Reply-To ali strežnik, uredite [E-poštni račun](sistemske-nastavitve.md#e-postni-racuni). Predloga določa samo vsebino sporočila.

---

## Predloge DOCX

**Dostop:** Sistem → Predloge → zavihek **DOCX**

### Namen

Predloge DOCX se uporabljajo za generiranje **formalnih tiskovin** – dokumentov s statično postavitvijo (logotipi, stili, slike) in dinamičnim delom (spremenljivke, ki se zapolnijo s podatki ob generiranju).

Podprti tipi dokumentov:

| Tip | Opis |
|-----|------|
| **usposabljanje** | Potrdila o usposabljanju, zapisniki usposabljanj |
| **delovna oprema** | Zapisniki pregledov delovne opreme, certifikati |
| **meritve** | Poročila o meritvah (hrup, osvetljenost, kemikalije …) |
| **ocena tveganja** | Dokumenti ocene tveganja po delovnih mestih |
| **kartica stranke** (`card`) | Kartica stanja stranke na izbrani dan |
| **periodično poročilo** (`repy`) | Letno, mesečno ali obdobno poročilo za stranko |

!!! info "Poročila za stranke"
    Predlogi tipov `card` in `repy` se izbereta na zaslonu **Analitika → Poročila za stranke**. Seznam njunih spremenljivk je v [Legendi spremenljivk](variables-sl.md).

### Vrste spremenljivk

| Vrsta | Opis | Primer |
|-------|------|--------|
| **Posamezne spremenljivke** | Enkratna vrednost – zamenjana z enim podatkom | Ime stranke, datum pregleda |
| **Tabelarne spremenljivke (vrstične)** | Ponovijo se za vsako vrstico v tabeli | Seznam udeležencev usposabljanja |
| **Blok spremenljivke** | Ponavljajoči se paragrafi; vsebujejo posamezne ali tabelarne spremenljivke | Blok za vsak pregledani stroj |

### Format spremenljivk

Vse spremenljivke v DOCX datoteki sledijo isti sintaksi:

```
${imeSpremenljivke}
```

- **Posamezne** – vstavljene neposredno v besedilo ali celico
- **Tabelarne** – vstavljene v celice tabele; sistem samodejno doda vrstice za vsak zapis
- **Blok** – vstavljene znotraj označenega bloka, ki se ponovi za vsak objekt

**Primer za posamezno spremenljivko:**
```
Stranka: ${customerName}
Datum pregleda: ${inspectionDate}
```

**Primer za tabelarno spremenljivko (v vrstici tabele):**
```
| ${participantName} | ${participantRole} | ${participantSignature} |
```

### Spremenljivke za lastna polja (EAV)

Za **lastna polja** (polja po meri, dodana posamezni stranki) se uporablja posebna sintaksa z oznako polja in predpono pozicije:

| Predpona | Kontekst | Primer |
|----------|----------|--------|
| `lst` | Polje na ravni usposabljanja / pregleda | `${lst<code>}` |
| `dev` | Polje na ravni naprave / opreme | `${dev<code>}` |

Kjer je `<code>` koda lastnega polja, definirana v nastavitvah.

!!! info "Celoten seznam spremenljivk"
    Razpoložljive spremenljivke so odvisne od tipa dokumenta. Popoln seznam spremenljivk po tipih predlog je zbran v [Legendi spremenljivk (DOCX/FORM)](variables-sl.md).

---

## Dodajanje in upravljanje predlog DOCX

### Dodajanje nove predloge

1. Odprite **Sistem → Predloge → zavihek DOCX**
2. Kliknite gumb **Dodaj**
3. Izpolnite polja:

| Polje | Opis |
|-------|------|
| **Ime** | Naziv predloge (prikazano pri izbiri) |
| **Tip** | Vrsta dokumenta (`usposabljanje`, `delovna oprema`, `meritve`, `ocena tveganja`) |
| **Zaporedna številka** | Določa prioriteto; nižja številka = višja prioriteta |
| **DOCX datoteka** | Naložite pripravljeno DOCX datoteko s spremenljivkami |

4. Shranite zapis

### Prioriteta predlog

Kadar je za isti tip dokumenta na voljo **več predlog**, sistem privzeto uporabi tisto z **najnižjo zaporedno številko**.

### Izbira predloge pri generiranju

Pred generiranjem dokumenta je mogoče izbrati katero koli predlogo za ta tip dokumenta:

- V seznamu zapisov (npr. Zapisniki usposabljanj, Zapisniki delovne opreme, Meritve …) imata ikona **Dok. za stranko** (PDF) in ikona **DOCX** spustni seznam vseh predlog za ta tip dokumenta.
- Predloga, ki je bila **zadnjič uporabljena** za generiranje dokumenta tega zapisa, je v seznamu označena s kljukico ✓.
- Sistem si izbrano predlogo **zapomni** za posamezen zapis – ob naslednjem generiranju je takoj razvidno, katera predloga je bila uporabljena nazadnje.

### Generiranje dokumentov iz seznamov

Generiranje dokumentov poteka neposredno iz seznama zapisov, brez osveževanja strani:

| Ikona | Namembnost |
|-------|------------|
| **PDF (Dok. za stranko)** | Generira PDF dokument za stranko iz izbrane DOCX predloge. Če je nastavljeno digitalno podpisovanje, je dokument tudi digitalno podpisan. |
| **PDF po meri** | V istem spustnem seznamu lahko namesto generiranja naložite **lasten PDF dokument** (npr. ročno podpisan izpis). |
| **DOCX** | Generira DOCX datoteko za podpis in arhiv iz izbrane predloge. |

Ko je dokument za stranko enkrat ustvarjen, se na njegovem mestu prikažeta ikona za **prenos** in ikona za **brisanje** dokumenta. Po brisanju se ponovno prikaže spustni seznam za novo generiranje.

!!! info "Obvestila"
    Uspešno generiranje in morebitne napake sistem sporoči z obvestilom v kotu zaslona. Vneseni dokument (PDF po meri) mora biti datoteka tipa PDF in velikosti do 10 MB.

### Urejanje obstoječe predloge

1. V seznamu predlog kliknite na naziv predloge
2. Izvedite željene spremembe (zamenjava DOCX datoteke, sprememba naziva ali prioritete)
3. Shranite spremembe

!!! warning "Pozor"
    Zamenjava DOCX datoteke pri obstoječi predlogi vpliva na vse **prihodnje** generacije dokumentov. Že generirani dokumenti ostanejo nespremenjeni.

---

## Predloge PDF

**Dostop:** Sistem → Predloge → zavihek **PDF predloge**

### Namen

Predloge PDF urejajo **videz sistemsko generiranih PDF poročil** – na primer Poročila o veljavnosti. Same postavitve in podatkov ne spreminjajo: poročilo še vedno sestavi program, predloga pa določi, kaj je v glavi, kateri stolpci se izpišejo in katera besedila so nad ali pod tabelo.

Primerne so za:

- glavo z lastnim logotipom in besedilom (naziv, naslov, davčna številka),
- izbor in vrstni red stolpcev po posameznem poročilu,
- opombe, pravne navedbe ali pojasnila nad oziroma pod tabelo.

### Kaj lahko urejate

| Razdelek | Kaj določa |
|----------|------------|
| **Glava dokumenta** | Logotip (lasten ali logotip podjetja) in besedilo v glavi. |
| **Stolpci** | Za vsako poročilo posebej: kateri stolpci so vidni in v kakšnem vrstnem redu. |
| **Statična besedila** | Neobvezna besedila nad ali pod tabelo. |
| **Aktivna** | Neaktivna predloga se ne uporabi; izpiše se privzeta oblika. |
| **Različica** | Vsak shran poveča številko različice (sledljivost sprememb). |

Razdelek **Stolpci** ima gumbe s poročili (npr. *Tečaji za zaposlene*, *Pregledi delovne opreme*, *Zdravniški pregledi*) – stolpci se nastavljajo za vsako poročilo posebej. Skriti stolpec se v PDF ne izpiše, vrstni red pa določa vrstni red v tabeli.

### Spremenljivke

Spremenljivke so v obliki `${imeSpremenljivke}`. V razdelku **Zamenljivke** pod ustreznim poljem klik na spremenljivko vstavi na mesto kazalke.

| Spremenljivka | Kje velja | Pomen |
|---------------|-----------|-------|
| `${sysCompany}` | glava | Naziv podjetja |
| `${sysAddress}` | glava | Naslov podjetja |
| `${sysTel}`, `${sysEmail}`, `${sysWeb}` | glava | Kontaktni podatki |
| `${sysTax}` | glava | Davčna številka |
| `${title}` | besedila | Naziv poročila |
| `${date}` | besedila | Datum izpisa |
| `${period}` | besedila | Izbrano obdobje (če je nastavljeno) |

### Predogled

V seznamu predlog kliknite ikono **PDF** – odpre se predogled s tremi vzorčnimi vrsticami. Predogled uporabi **shranjene** nastavitve, zato ga odprite po shranjevanju.

### Pravila

- Brez shranjene predloge se uporabi **privzeta oblika** poročila.
- Izbris predloge vrne privzeto obliko; že izpisani PDF dokumenti ostanejo nespremenjeni.
- Sprememba vpliva samo na **nove** izpise.

---

## Predloga potrdila za usposabljanje (samodejno generiranje)

Predloge tipa **usposabljanje** običajno vsebujejo zapisnik in prilogo s potrdili. Sistem iz naložene predloge **samodejno izdela ločeno predlogo samo za potrdilo** (tip **Potrdilo o usposabljanju**), ki se uporablja pri tiskanju posameznih potrdil iz kartice zaposlenega.

### Kako deluje

- Zadnji del predloge usposabljanja mora vsebovati blok potrdila, označen s spremenljivkama `${cloneCert0}` in `${/cloneCert0}` – enako kot pri zapisniku.
- Ob vsakem nalaganju nove predloge tipa **usposabljanje** sistem:

    1. iz naložene datoteke izreže zadnje poglavje (blok potrdila),
    2. ga shrani kot samostojno predlogo tipa **Potrdilo o usposabljanju**,
    3. staro predlogo potrdila nadomesti z novo in jo izbriše.

- Če naložena predloga ne vsebuje bloka potrdila, sistem obdrži obstoječo predlogo potrdila in izpiše opozorilo.

### Opozorila

- Predloga potrdila se praviloma upravlja samodejno; po potrebi jo lahko ročno nadomestite z nalaganjem lastne DOCX datoteke tipa **Potrdilo o usposabljanju**.
- Že natisnjena potrdila se ob zamenjavi predloge ne spremenijo. Pri ponovnem tiskanju starejšega potrdila sistem uporabi predlogo, ki je bila shranjena ob generiranju zapisnika; če ta ne obstaja več, uporabi trenutno predlogo.
