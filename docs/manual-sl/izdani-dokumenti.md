# Izdani dokumenti in različice

Stran **Izdani dokumenti** je osrednji arhiv vseh dokumentov, ki jih sistem ustvari iz zapisnikov, meritev, ponudb, pogodb in drugih evidence. Prikazuje datoteke, njihove različice, status potrditve in vidnost za stranko.

!!! info "Kratek povzetek"
    Za stranko se objavijo samo **potrjene, aktivne PDF datoteke**. Datoteke DOCX so namenjene internemu delu in se v portalu za stranke ne prikazujejo.

---

## Dostop in pravice

**Glavni meni → Poročila → Izdani dokumenti**

Stran je na voljo uporabnikom z vlogo **admin** ali **superadmin** ter uporabnikom z dovoljenjem `view_erp_finance` ali `manage_erp_finance`.

| Dejanje | Potrebna pravica |
|---------|------------------|
| Ogled seznama in prenos datotek | admin/superadmin, `view_erp_finance` ali `manage_erp_finance` |
| Aktivna različica, vidnost za stranko, nalaganje nove različice | admin/superadmin ali `manage_erp_finance` |

Uporabnikom brez teh pravic se povezava v meniju ne prikaže.

---

## Pregled tabele

Vsaka vrstica predstavlja eno datoteko oziroma različico dokumenta.

| Stolpec | Pomen |
|---------|-------|
| **Št. dokumenta** | Številka dokumenta, naziv in povezava na izvorni zapisnik (če je na voljo). |
| **Stranka** | Stranka, poslovna enota in morebitni prejemnik (npr. udeleženec usposabljanja). |
| **Vrsta** | Vrsta poročila (npr. delovna oprema, usposabljanje, ponudba, pogodba) in format datoteke. |
| **Revizija** | Različica datoteke ter oznaka **Manjka**, če fizična datoteka ni na voljo. |
| **Status** | Status potrditve dokumenta v dokumentnem toku. |
| **Vidno stranki** | Ali je datoteka objavljena v portalu za stranke. |
| **Datum** | Datum in ura nastanka ter uporabnik, ki je dokument izdal. |
| **Datoteka** | Ime datoteke. |
| **Opravila** | Dejanja z datoteko. |

### Filtri

- **Iskanje** po imenu datoteke, številki dokumenta, nazivu, izvorni kodi ali stranki.
- **Prejemnik** — iskanje po imenu ali priimku prejemnika (uporabno predvsem pri potrdilih o usposabljanju).
- **Vrsta dokumenta** — omeji seznam na posamezno vrsto poročila.
- **Status** — osnutek, v potrjevanju, v popravku, potrjeno ali zavrnjeno.
- **Format** — PDF ali DOCX.
- **Vidno stranki** — da/ne.
- **Datum od / do** — datum dokumenta.
- **Vse različice** — privzeto so prikazane samo aktivne različice; obkljukajte za prikaz celotne zgodovine.

!!! tip "Aktivna različica"
    Privzeto je prikazana samo trenutno aktivna različica. Za pregled starejših datotek vklopite **Vse različice**.

---

## Različice dokumentov

- Vsak dokument ima lahko več različic iste vrste in formata.
- Aktivna je samo ena različica za posamezno kombinacijo dokumenta, vrste poročila in formata. Pri potrdilih se različice ločijo tudi po prejemniku.
- Starejše različice se ne izbrišejo; ostanejo v zgodovini in so dostopne prek **Vse različice**.
- Ob nalaganju nove različice se prejšnja aktivna različica samodejno označi kot nadomeščena.
- Datoteke, ki ob migraciji niso več obstajale na strežniku, se v novo evidenco ne prenesejo.

---

## Dejanja

| Ikona / dejanje | Opis |
|-----------------|------|
| **Prenesi** | Prenese datoteko. Dokumente DOCX lahko prenesejo samo pooblaščeni interni uporabniki. |
| **Aktivna različica** | Izbere različico kot aktivno. Prejšnja aktivna različica se nadomesti. |
| **Vidno stranki** | Objavi ali umakne **PDF** iz portala za stranke. Dejanje je na voljo samo za potrjene dokumente. |
| **Nova verzija** | Naloži novo datoteko PDF ali DOCX. Za objavo stranki mora biti nova datoteka PDF in dokument potrjen. |
| **Odpri izvorni dokument** | Odpre izvirni zapisnik, iz katerega je bil dokument ustvarjen. |

### Pravila za objavo stranki

1. Dokument mora biti **potrjen**.
2. Datoteka mora biti **PDF** in aktivna različica.
3. Datoteka mora pripadati stranki, ki je prijavljena v portal.
4. Uporabnik stranke mora imeti dostop do dokumentov; prenos poteka prek zaščitene povezave v portalu.

**DOCX se stranki ne objavi.** Datoteko DOCX je po prenosu mogoče urejati v Wordu, zato je namenjena samo internemu delu. Za stranko uporabite PDF; obstoječe digitalno podpisane PDF datoteke omogočajo tudi preverjanje morebitnih sprememb.

---

## Povezava z dokumentnim tokom in Finance

- Dokument nastane ob shranjevanju zapisnika oziroma izvozu dokumenta.
- Če ima stranka za modul aktiven dokumentni tok, je treba dokument poslati v potrditev. Podrobnosti so v poglavju [Dokumentni tok in potrjevanje](dokumentni-tok.md).
- Po potrditvi se dokument prikaže v **ERP → Finance**, kjer ga finančna ekipa pregleda in označi status.
- Ob zavrnitvi ali vrnitvi v popravek se objavljene datoteke umaknejo iz portala; po ponovni potrditvi se ponovno objavijo.
- Če za stranko ni aktivnega dokumentnega toka, se dokument ob shranitvi samodejno potrdi.

---

## Nadgradnja in migracija

- Stara tabela `docissue` je opuščena. Ob nadgradnji se obstoječe datoteke prenesejo v novo evidenco `document_files`.
- Migracija se izvede samodejno ob nadgradnji na različico **5.312** oziroma ob zagonu `php artisan migrate`.
- Migracija je varna za ponovni zagon: že prenesene vrstice se prepoznajo po starem ID-ju in se ne podvojijo.
- Če fizična datoteka iz stare evidence ne obstaja, se v novo tabelo **ne vnese**; v dnevniku ostane opozorilo.
- Če posamezne vrstice ni mogoče pretvoriti, se zabeleži v dnevnik, nadgradnja pa se nadaljuje. Preverite `storage/logs/laravel.log`, če po nadgradnji opazite manjkajoče dokumente.
- Izvorne datoteke, ki so še prisotne v `public/eMreports`, se prenesejo skupaj z osnovnimi podatki dokumenta, stranke in različice.
- Za varnost naj bodo datoteke v produkciji zaščitene pred neposrednim javnim dostopom; aplikacija uporablja nadzorovane povezave za stranke in interno osebje.

!!! warning "Če se nadgradnja ustavi pri migraciji"
    Pri različici 5.312 je migracija prilagojena tako, da posamezna neveljavna vrstica ne prekine celotne transakcije. Po namestitvi posodobljene različice znova zaženite nadgradnjo oziroma `php artisan migrate --force`. Če je prišlo do delnega prenosa, se migracija nadaljuje brez podvajanja. Pri nadgradnji prek spletnega vmesnika naj bo `max_execution_time` nastavljen na vsaj 1800 sekund; za velike migracije je zanesljivejši zagon `php artisan migrate --force` v ukazni vrstici.

---

## Pogosta vprašanja

### Zakaj dokumenta ne vidim v portalu za stranko?
Preverite, ali je dokument **potrjen**, ali je datoteka **PDF**, ali je aktivna različica in ali je vklopljena možnost **Vidno stranki**.

### Zakaj ne morem objaviti DOCX?
DOCX je namenjen internemu urejanju in ga stranka ne sme prejemati kot uradni dokument. Naložite PDF različico.

### Zakaj je v tabeli več različic istega dokumenta?
Sistem hrani zgodovino. Aktivna je ena različica; za prikaz vseh vklopite **Vse različice**.

### Kdo lahko upravlja različice?
Uporabniki z vlogo **admin**/**superadmin** ali dovoljenjem `manage_erp_finance`.
