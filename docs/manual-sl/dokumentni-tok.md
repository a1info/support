# Dokumentni tok in potrjevanje

Dokumentni tok *(Document Flow)* omogoča večnivojsko potrjevanje zapisnikov znotraj modulov, kot so **Delovna oprema**, **Usposabljanje** in **ERP** (ponudbe in pogodbe). Vsak zapisnik dobi en sam dokument, ki ga potrjujejo izbrani potrjevalci. Ko je dokument potrjen, se prikaže v **ERP → Finance**, kjer je na voljo za nadaljnjo obdelavo.

---

## Kako deluje

1. Ob shranitvi zapisnika sistem ustvari **dokument** in ga poveže z zapisnikom.
2. Če ima stranka za ta modul **aktivno nastavljen dokumentni tok**, je dokument v stanju **Osnutek**. Pripravljavec ga pošlje v potrditev.
3. Potrjevalci prejmejo dokument hkrati. Vsak lahko dokument **potrdi**, **zavrne** ali **vrne v popravek**; ob tem lahko doda komentar.
4. Ko so vsi potrjevalci potrdili (ali zadostuje eden, če je način nastavljen tako), dokument preide v stanje **Potrjeno** in dobi finančni status **Odprto**.
5. Potrjen dokument se prikaže v **ERP → Finance**. Če stranka za ta modul **nima aktivnega toka**, se dokument **samodejno potrdi** in takoj prikaže v Finance.

!!! info "Brez dokumentnega toka ni čakanja"
    Če za stranko in modul ni aktivne konfiguracije dokumentnega toka, dokumenta ni mogoče potrjevati. V tem primeru se dokument ob shranitvi samodejno potrdi. To velja tudi za obstoječe zapisnike, ki so bili ob nadgradnji brez aktivnega toka.

---

## Nastavitev dokumentnega toka

Dokumentni tok se nastavi za vsako **podjetje** posebej, po **modulih**.

**Dostop:** Seznam zapisnikov (npr. Delovna oprema → Pregledi) → ikona zobnika ⚙️ v desnem kotu

### Obrazec za nastavitev

| Polje | Obvezno | Opis |
|-------|---------|------|
| **Naziv** | ✅ | Ime predloge (npr. *Standardni 2‑nivojski*). |
| **Podjetje** | ✅ | Za katero podjetje velja ta konfiguracija. |
| **Način potrjevanja** | ✅ | **Vsi potrjevalci** ali **zadostuje eden**. |
| **Potrjevalci** | ✅ | Seznam skupin (vlog) ali posameznih uporabnikov, ki sodelujejo pri potrjevanju. |

Vsak potrjevalec ima:
- **Vrsto** — skupina (vloga) ali posamezen uporabnik.
- **Skupino / uporabnika** — izbira iz seznama.
- **Naziv** — prikazano ime na kartici potrjevanja (npr. *Strokovni pregled*, *Končna potrditev*).

### Tabela konfiguracij

V tabeli so prikazane vse shranjene predloge za ta modul. Stolpec **Podjetje** pove, za katero podjetje velja posamezna predloga. Vsako predlogo lahko:

| Dejanje | Opis |
|---------|------|
| **Aktiviraj / deaktiviraj** | Stikalo za vklop ali izklop predloge. |
| **Uredi** | Svinčnik — odpre obrazec s podatki predloge. |
| **Izbriši** | Koš — izbriše predlogo (zahteva potrditev). |

!!! warning "Neaktivna predloga pomeni samodejno potrjevanje"
    Če je predloga deaktivirana ali za stranko/modul ne obstaja aktivna predloga, dokument nima potrjevalcev. Ob shranitvi se zato samodejno potrdi in prikaže v Finance.

---

## Uporaba — potrjevanje dokumenta

Pladenj za potrjevanje se prikaže na desni strani obrazca zapisnika (npr. pri urejanju pregleda delovne opreme). Gumbi so zaradi ozkega prostora zloženi navpično.

### Stanja dokumenta

| Stanje | Barva | Pomen |
|--------|-------|-------|
| **Osnutek** | Siva | Dokument je shranjen, vendar še ni poslan v potrditev. |
| **V potrjevanju** | Oranžna | Dokument čaka na potrditve določenih potrjevalcev. |
| **Potrjeno** | Zelena | Dokument je potrjen; prikazan je v Finance. |
| **Zavrnjeno** | Rdeča | Eden od potrjevalcev je dokument zavrnil — potrebna je poprava. |
| **V popravku** | Modra | Dokument je vrnjen v popravek; pripravljavec ga mora dopolniti in ponovno poslati. |

Dokument, potrjen brez aktivnega toka, je v stanju **Potrjeno** in ima dodatno oznako **Samodejno potrjeno**.

### Dejanja na pladnju

**Osnutek:**
- Gumb **Pošlji v potrditev** — sproži postopek. Dokument preide v stanje *V potrjevanju*.

**V potrjevanju:**
- Vsak potrjevalec, ki ima ustrezno vlogo, vidi svojo kartico z gumbi **Potrdi**, **Vrni v popravek** in **Zavrni**.
- **Potrdi** — prikaže potrditveno okno. Po potrditvi se zabeleži uporabnik, datum in ura.
- **Vrni v popravek** — odpre polje za obvezen komentar. Dokument gre v stanje *V popravku*.
- **Zavrni** — odpre polje za obvezen komentar. Dokument gre v stanje *Zavrnjeno*.
- Če uporabnik nima nobene zahtevane vloge, se prikaže obvestilo *"Nimate ustreznih pravic za potrjevanje"*.

**Potrjeno:**
- Prikazan je seznam vseh, ki so potrdili, z datumi.
- Če je dokument potrjen samodejno, je prikazano obvestilo **Samodejno potrjeno** in razlog (ni dokumentnega toka).

**Zavrnjeno / V popravku:**
- Prikazan je razlog in gumb **Pošlji ponovno**, ki ponovno sproži postopek.

### Komentarji in pripombe

- Komentarje je mogoče dodati na celoten dokument ali na posamezno vrstico (tečaj, kos opreme, pregled).
- Vsak komentar ima status **Odprto**, **Narejeno** ali **Preklicano**.
- Pripravljavec ali pregledovalec lahko komentar označi kot **Narejeno**; potrjevalec ga lahko ponovno odpre, če popravek ni ustrezen.
- **Odprti komentarji ne blokirajo potrditve** — potrjevalec lahko dokument potrdi tudi ob odprtih pripombah. Pripombe so vidne v Finance in v dokumentu.

### Urejanje potrjenega dokumenta

- Če je za stranko aktiven dokumentni tok in je dokument že potrjen, **shranjevanje sprememb dokument vrne v Osnutek**. Potrebna je ponovna potrditev.
- Če dokument nima aktivnega toka, ostane samodejno potrjen tudi po urejanju.
- Ob ponovnem pošiljanju se poveča **revizija** dokumenta.

---

## Finance — pregled potrjenih dokumentov

**Dostop:** [ERP → Finance](erp.md#finance)

Finance prikazuje dokumente, ki so potrjeni in pripravljeni za finančno obdelavo.

- Privzeto so prikazani **samo potrjeni dokumenti**.
- Filter **Prikaži vse dokumente** je privzeto **izklopljen**. Ko ga vklopite, se prikažejo tudi osnutki, dokumenti v potrjevanju in zavrnjeni dokumenti.
- Filtrirate lahko po modulu in statusu financ; iščete po številki dokumenta, nazivu, izvorni kodi ali stranki.
- V podrobnostih dokumenta so zavihki:
  - **Vsebina dokumenta** — celotna vsebina zapisnika (tečaji, udeleženci, datumi; oprema, pregledi, datumi in statusi; postavke ponudbe/pogodbe).
  - **Komentarji** — vse pripombe z statusi in možnostjo označitve kot Narejeno.
  - **Dokumentni tok** — potrjevalci, odločitve, komentarji in datum potrditve.
- Prikazano je tudi **število pregledov** (delovna oprema), **število udeležencev** (usposabljanje) oziroma **število postavk** (ERP).
- Statusi financ so **Odprto**, **Narejeno** in **Preklicano**.
- Dokumenti, potrjeni brez aktivnega toka, imajo oznako **Samodejno potrjeno**.
- **Izdelava računov v tej različici še ni vključena** — Finance je pregled potrjenih dokumentov in njihovega statusa.

---

## Številčenje dokumentov

- Usposabljanje: `leto-številka_zapisnika-EDU` (npr. `2026-32-EDU`).
- Delovna oprema: `leto-številka_zapisnika-DEV` (npr. `2026-32-DEV`).
- ERP ponudbe in pogodbe uporabljajo svojo številko ponudbe oziroma pogodbe.
- `številka_zapisnika` je interna številka zapisnika (`cust_nr_rep`), ki jo sistem dodeli ob shranitvi. Če številke ni, se uporabi ID zapisa.

---

## Pogosta vprašanja

### Kdo lahko nastavi dokumentni tok?
Uporabniki z vlogo **admin** ali **superadmin**.

### Ali lahko uporabnik potrdi kot več vlog?
Da. Če ima uporabnik dodeljenih več vlog (npr. *inspector* in *director*), lahko potrdi kartice za vsako vlogo posebej.

### Kaj se zgodi, če spremenim podjetje v obrazcu?
Izbrano podjetje velja za novo predlogo; tabela prikazuje vse predloge modula. Pri urejanju obstoječe predloge podjetja ni mogoče spremeniti. Če za izbrano podjetje ni aktivnega toka, bo dokument ob shranitvi samodejno potrjen.

### Ali dokumentni tok deluje tudi za druge module?
Trenutno je povezan z moduli **Delovna oprema**, **Usposabljanje** in **ERP** (ponudbe in pogodbe). Meritve (VZD/EKO) zaenkrat niso vključene.

### Zakaj dokumenta ne vidim v Finance?
- Preverite, ali je dokument **potrjen**. Če je v osnutku ali v potrjevanju, ga privzeti pogled ne prikaže.
- Vklopite filter **Prikaži vse dokumente**, da preverite tudi osnutke in dokumente v potrjevanju.
- Če dokument ni bil poslan v potrditev in je za stranko aktiven tok, ga morate najprej poslati v potrditev.
- Če za stranko ni aktivnega toka, bi moral biti dokument samodejno potrjen; osvežite stran ali preverite nastavitve.

### Ali odprti komentarji blokirajo potrditev?
Ne. Potrjevalec lahko dokument potrdi tudi ob odprtih komentarjih. Pripombe ostanejo vidne v Finance.

### Ali Finance izda račun?
V trenutni različici ne. Finance prikazuje potrjene dokumente in omogoča označevanje statusa (**Odprto / Narejeno / Preklicano**). Izdelava računov je predvidena v naslednji fazi.

### Kdo lahko vidi Finance?
Uporabniki z dovoljenjem `view_erp_finance` ali administratorji. Za urejanje statusa financ je potrebno dovoljenje `manage_erp_finance` (ali vloga **admin**/**superadmin**).

---

## Tehnične opombe

- Dokumenti se hranijo v tabeli **`document`** (ednina).
- Potrditve so v tabeli **`document_approvals`**; glavna povezava na dokument je `document_id`.
- Izvorne tabele (`educoursegrp`, `mdevicegrp`, `erp_offer`, `erp_contract`) nimajo več lastnega polja `approval_status`; status je samo na dokumentu.
- Komentarji uporabljajo obstoječo tabelo `comment`:
  - dokument: `table_obj = 'document'`, `id_obj = document.id`;
  - vrstica: obstoječe sidro (`educourse`, `mdevice` ipd.).
- Ob nadgradnji se pravice za Finance dodajo samodejno prek `UserpermSeeder` (brez podvajanja).
- Dokumenti brez aktivnega toka se ob shranitvi samodejno potrdijo; to velja tudi za obstoječe zapisnike ob nadgradnji.
