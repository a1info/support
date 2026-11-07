# CRM (Organizacija nalog in projektov)

Modul **CRM** omogoča pregled in organizacijo dela z naročniki prek skupnega koledarja, projektov in nalog.

---

## Pregled modula

CRM modul je osrednje mesto za upravljanje delovnih nalog, projektov in komunikacije s strankami.

### Dostop

**Glavni meni → CRM**

### Ključne funkcionalnosti

- Vizualni pregled nalog v mesecu in tednu, z urami dogodkov
- Osebni, skupni in deljeni koledarji ter zunanji (ICS) koledarji
- Iskanje in filtriranje nalog po uporabniku, koledarju in statusu
- Barvno ločevanje: projekt (ozadje) in izvajalec (leva črta)
- Naročnina na koledar (ICS) za Google Koledar in Outlook
- Sledenje statusom nalog
- Izpis delovnih nalogov (PDF)
- Samodejno generiranje periodičnih opomnikov

---

## Naloge (Tasks)

Naloga je osnovna delovna enota v modulu CRM.

### Prikaz in dostop

- Naloge so prikazane v **koledarskem pogledu** (mesec/teden) in kot seznam.
- Odprte naloge so vidne tudi na **uporabniškem Dashboardu** (začetni strani).

### Pravice

| Vloga | Vidnost in urejanje nalog |
|-------|---------------------------|
| **Administrator / Superadmin** | Vidi in ureja vse naloge; naloge lahko dodeljuje kateremu koli uporabniku. |
| **Navadni uporabnik** | Privzeto vidi svoje naloge. Z filtrom lahko doda druge uporabnike ali koledarje, če so mu vidni. Ureja lahko svoje naloge in naloge, kjer je naveden kot izvajalec storitve. |

!!! info "Vidnost koledarjev"
    Naloge v **skupnem koledarju** so vidne vsem uporabnikom. Naloge v **osebnem koledarju** vidijo lastnik in uporabniki, ki jim je lastnik dodelil dovoljenje.

### Polja naloge

| Polje | Opis |
|-------|------|
| **Naziv** | Kratek opis naloge ali naročila. |
| **Začetek** | Datum in ura začetka naloge. |
| **Konec** | Datum in ura zaključka naloge. |
| **Status** | Trenutno stanje naloge (npr. Odprt, V teku, Zaključen). |
| **Dodeljen uporabnik** | Izvajalec naloge. |
| **Stranka** | Naročnik, za katerega se naloga izvaja. |
| **Koledar / Projekt** | Razvrstitev v ustrezni koledar ali projekt. |
| **Seznam storitev in odgovornih oseb** | Podrobnejši opis storitev, ki jih naloga vključuje, ter odgovorne osebe. |

!!! info "Upravljanje storitev"
    Seznam storitev, ki so na voljo pri nalogah, upravljajo administratorji prek **Nastavitve → Storitve**.

### Povezava s ponudbami (ERP)

Naloga je lahko povezana s ponudbo iz modula **ERP**:

- Nalogo ustvarite neposredno **iz ponudbe** z gumbom *Ustvari nalogo* (glejte poglavje *ERP — Ponudbe in pogodbe*); sistem samodejno poveže nalogo s ponudbo ter predizpolni stranko in naziv naloge.
- Povezava je vidna v obrazcu naloge (**Povezan objekt** s povezavo na ponudbo).
- Na seznamu nalog se pod nazivom naloge izpiše modra značka s **številko ponudbe**; klik nanjo odpre ponudbo.

---

## Koledarji

Naloge so razvrščene v koledarje. Vsak koledar ima **lastnika**, **barvo** in **tip**.

### Vrste koledarjev

| Tip | Namen |
|-----|-------|
| **Skupni (Naročila)** | Sistemski skupni koledar, viden vsem. Vanj se shranijo naloge, če uporabnik ne izbere drugega. Ni ga mogoče izbrisati. |
| **Osebni** | Vsak uporabnik ga dobi samodejno ob ustvaritvi računa. Vidi ga lastnik in uporabniki z dovoljenjem. |
| **Deljeni** | Skupni koledar brez lastnika; dostop je urejen prek dovoljenj. Ustvari ga superadmin. |
| **Zunanji (ICS)** | Povezan Google/Outlook koledar. Dogodki so **samo za branje** in se sinhronizirajo vsakih 15 minut. |

### Osebni koledar

- Ob ustvaritvi uporabnika sistem samodejno ustvari njegov osebni koledar z imenom uporabnika.
- Uporabnik lahko v **CRM → Koledarji** ustvari dodatne koledarje ali uredi svojega.
- Lastnik lahko koledar deli z uporabniki ali skupinami prek ikone **Dovoljenja**.

!!! tip "Skupni koledar kot privzeta izbira"
    Podjetja, ki delo organizirajo v enem skupnem koledarju, lahko še naprej uporabljajo **Naročila**: novi nalogi se samodejno dodeli ta koledar, uporabnik pa ga lahko v obrazcu zamenja.

### Dovoljenja

| Dovoljenje | Opis |
|------------|------|
| **Lastnik** | Upravlja koledar, dovoljenja in brisanje. |
| **Urejanje** | Ureja koledar in njegove naloge; ne more brisati koledarja ali spreminjati dovoljenj. |
| **Vpogled** | Vidi koledar in njegove naloge. |
| **Brez** | Koledarja ne vidi. |

### Barve

- **Ozadje dogodka** = barva projekta.
- **Leva črta** = barva izvajalca (generirana iz uporabnikovega ID-ja).
- **Pika pred imenom** v seznamu nalog = barva izvajalca.
- Naloge brez projekta imajo nevtralno ozadje, tako da je izvajalec še vedno razviden.

### Iskanje in filtri

- **Iskalno polje** nad seznamom išče po nazivu naloge, stranki in lokaciji.
- **Filtri** (uporabnik, koledar, status) so v zgornji vrstici; izbrani filtri so prikazani kot **čipi**, ki jih odstranite s klikom na ×.
- **Počisti filtre** vrne privzeti pogled (vsi uporabniki, vsi statusi).
- **Mesečni/tedenski pogled**: dogodke lahko **premaknete** (sprememba datuma) ali **raztegnete** (sprememba konca); spremembe se shranijo takoj.

### Naročnina na koledar (ICS)

Uporabnik lahko svoj CRM koledar naroči v Google Koledar, Outlook ali drug ICS odjemalec.

1. Odprite **CRM → Koledarji**.
2. V kartici **Naročnina na koledar (ICS)** kliknite **Ustvari povezavo**.
3. Kopirajte prikazani naslov in ga dodajte v svoj koledar:
   - **Google Koledar**: *Drugi koledarji → Iz URL-ja*.
   - **Outlook**: *Dodaj koledar → Naročnina iz spleta*.
4. Povezava je **osebna** – ne delite je. Z gumbom **Nova povezava** jo prekličete in ustvarite novo; z **Prekliči** onemogočite dostop.

!!! warning "Zasebnost povezave"
    Naslov vsebuje skrivni žeton. Kdor ima povezavo, lahko bere naloge, ki so vidne temu uporabniku. Ob sumu uhajanja povezavo takoj zamenjajte.

### Zunanji koledarji (Google/Outlook → CRM)

1. Odprite **CRM → Koledarji** in kliknite **+**.
2. Izberite tip **Zunanji (ICS)**.
3. Prilepite **skrivni naslov iCal**:
   - **Google Koledar**: *Nastavitve → Nastavitve koledarja → Skrivni naslov v obliki iCal*.
   - **Outlook**: *Objavi koledar → Povezava ICS*.
4. Shranite. Sinhronizacijo lahko takoj sprožite z gumbom **Sinhroniziraj**, sicer se izvede samodejno vsakih 15 minut.
5. Na obrazcu sta prikazana **zadnja sinhronizacija** in morebitna **napaka**.

Zunanji dogodki:

- so prikazani v glavnem koledarju nalog z barvo zunanjega koledarja,
- so **samo za branje** (ni jih mogoče urejati, premikati ali brisati),
- se **ne** prikazujejo v seznamu nalog, Excel izvozu ali na portalu za stranke,
- podpirajo osnovno ponavljanje (dnevno, tedensko, mesečno, letno); izjeme ponavljanja (EXDATE) niso podprte.

!!! info "Varnost povezave"
    Dovoljena je samo povezava **https**. Naslovi, ki kažejo na lokalno omrežje ali zasebne strežnike, so zavrnjeni.

### Periodika in veljavnosti

Opomniki iz evidenc z veljavnostjo (usposabljanja, pregledi, meritve) **niso** del koledarjev CRM. Prikazujejo se v ločenem pregledu **Poročila → Veljavnosti** in so namenjeni samo branju. Ne urejajte jih ročno – ob naslednji posodobitvi se prepišejo.

---

## Projekti

Projekt združuje naloge, datoteke in komentarje v enotnem kronološkem pogledu.

### Dostop

**CRM → Projekti → Ogled**

### Struktura projekta

| Element | Opis |
|---------|------|
| **Naloge** | Vse naloge, ki so dodeljene temu projektu. |
| **Datoteke** | Priponke in dokumenti, vezani na projekt. |
| **Komentarji** | Komunikacija med člani ekipe znotraj projekta. |

### Pravice dostopa

| Nastavitev | Opis |
|-----------|------|
| **Privzeto** | Projekt je dostopen vsem uporabnikom sistema. |
| **Omejeno** | Ogled in urejanje projekta se omeji na točno določene uporabnike. |

!!! tip
    Projekte uporabite za večje naročniške pogodbe ali ponavljajoče se sklope del, kjer želite vse naloge, dokumentacijo in komunikacijo hraniti na enem mestu.

---

## Delovni nalog

Delovni nalog je tiskani (PDF) dokument, ki potrjuje opravljeno delo pri stranki.

### Generiranje

Na **seznamu nalog** ali znotraj posamezne naloge kliknite ikono za **tisk delovnega naloga**.

### Vsebina delovnega naloga

- Glava z nazivom, naslovom, registrsko številko, e-pošto, spletno stranjo in logotipom vašega podjetja (iz nastavitev podjetja — stranka s kategorijo *OWN*)
- Podatki o stranki in naslovu
- Datum in čas opravljenega dela
- Opis opravljenih storitev
- Ime izvajalca
- Prostor za **podpis stranke** (potrdi sprejem opravljenega dela)

### Prilagoditev

Oblika in vsebina delovnega naloga sta prilagodljivi prek **predlog za tisk**. Predloge ureja administrator v nastavitvah sistema.

!!! info
    Delovni nalog služi kot uradna potrditev opravljenega dela in se priporoča za vsak terenski obisk pri stranki.
