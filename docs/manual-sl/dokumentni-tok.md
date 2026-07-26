# Dokumentni tok in potrjevanje

Dokumentni tok *(Document Flow)* omogoča večnivojsko potrjevanje zapisnikov znotraj modulov (npr. Delovna oprema, Požarna varnost). Pregledi, ki jih vnese tajništvo na podlagi terenskih zapisov, gredo skozi enega ali več potrjevalcev, preden so dokončno potrjeni in pripravljeni za izdajo poročil ali ERP ponudb.

---

## Kako deluje

1. **Tajništvo** vnese podatke pregleda in shrani zapisnik kot **osnutek**.
2. S klikom na **Pošlji v potrditev** se zapisnik pošlje vsem določenim potrjevalcem hkrati *(vzporedno potrjevanje)*.
3. Vsak potrjevalec pregleda podatke in zapisnik **potrdi** ali **zavrne** s komentarjem.
4. Ko vsi potrjevalci potrdijo, zapisnik preide v stanje **Potrjeno**. Če kdorkoli zavrne, gre zapisnik nazaj v popravo.
5. Potrjeni zapisniki so na voljo za nadaljnjo obdelavo (npr. izdaja ponudb v ERP modulu).

---

## Nastavitev dokumentnega toka

Dokumentni tok se nastavi za vsako **podjetje** posebej, po **modulih**.

**Dostop:** Seznam zapisnikov (npr. Delovna oprema → Pregledi) → ikona zobnika ⚙️ v desnem kotu

### Obrazec za nastavitev

| Polje | Obvezno | Opis |
|-------|---------|------|
| **Naziv** | ✅ | Ime predloge (npr. *Standardni 2‑nivojski*). |
| **Podjetje** | ✅ | Za katero podjetje velja ta konfiguracija. |
| **Potrjevalci** | ✅ | Seznam vlog, ki morajo potrditi zapisnik. |

Vsak potrjevalec ima:
- **Vloga** — izbira iz seznama vlog (npr. *inspector*, *director*). Uporabnik lahko ima dodeljenih več vlog.
- **Naziv** — prikazano ime na kartici potrjevanja (npr. *Strokovni pregled*, *Končna potrditev*).

### Tabela konfiguracij

V tabeli so prikazane vse shranjene predloge za izbrano podjetje. Vsako predlogo lahko:

| Dejanje | Opis |
|---------|------|
| **Aktiviraj / deaktiviraj** | Stikalo za vklop ali izklop predloge. |
| **Uredi** | Svinčnik — odpre obrazec s podatki predloge. |
| **Izbriši** | Koš — izbriše predlogo (zahteva potrditev). |

---

## Uporaba — potrjevanje zapisnika

Pladenj za potrjevanje se prikaže na desni strani obrazca zapisnika (npr. pri urejanju pregleda delovne opreme).

### Stanja zapisnika

| Stanje | Barva | Pomen |
|--------|-------|-------|
| **Osnutek** | Siva | Zapisnik je shranjen, vendar še ni poslan v potrditev. |
| **V potrjevanju** | Oranžna | Zapisnik čaka na potrditve vseh določenih potrjevalcev. |
| **Potrjeno** | Zelena | Vsi potrjevalci so zapisnik potrdili. |
| **Zavrnjeno** | Rdeča | Eden od potrjevalcev je zapisnik zavrnil — potrebna je poprava. |

### Dejanja na pladnju

**Osnutek:**
- Gumb **Pošlji v potrditev** — sproži postopek. Zapisnik preide v stanje *V potrjevanju*.

**V potrjevanju:**
- Vsak potrjevalec, ki ima ustrezno vlogo, vidi svojo kartico z gumboma **Potrdi** in **Zavrni**.
- **Potrdi** — prikaže potrditveno okno. Po potrditvi se zabeleži uporabnik, datum in ura.
- **Zavrni** — odpre polje za obvezen komentar. Po zavrnitvi gre zapisnik v stanje *Zavrnjeno*.
- Če uporabnik nima nobene zahtevane vloge, se prikaže obvestilo *"Nimate ustreznih pravic za potrjevanje"*.

**Potrjeno:**
- Prikazan je seznam vseh, ki so potrdili, z datumi.

**Zavrnjeno:**
- Prikazan je razlog zavrnitve in gumb **Pošlji ponovno**, ki ponovno sproži postopek.

---

## Pogosta vprašanja

### Kdo lahko nastavi dokumentni tok?
Uporabniki z vlogo **admin** ali **superadmin**.

### Ali lahko uporabnik potrdi kot več vlog?
Da. Če ima uporabnik dodeljenih več vlog (npr. *inspector* in *director*), lahko potrdi kartice za vsako vlogo posebej.

### Kaj se zgodi, če spremenim podjetje v obrazcu?
Seznam konfiguracij se osveži — prikažejo se predloge za izbrano podjetje. Obrazec za nov vnos se ponastavi.

### Ali dokumentni tok deluje tudi za druge module?
Da. Pladenj za potrjevanje je pripravljen za vse module, ki imajo stolpec `approval_status` (Delovna oprema, Požarna varnost, Usposabljanje, …). Nastavitev toka se izvede ločeno za vsak modul.

---

## Tehnične opombe

- Potrjevanje je **vzporedno** — vsi potrjevalci dobijo zapisnik hkrati, ne čakajo drug na drugega.
- Vsaka **zavrnitev** zahteva obvezen komentar.
- Potrjeni zapisniki so samodejno na voljo v ERP modulu za kreiranje ponudb.
- Konfiguracija se hrani v tabeli `document_flow_configs`, posamezne potrditve pa v `document_approvals`.
