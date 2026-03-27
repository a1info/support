# Uporabniki

Sistem loči med **sistemskimi uporabniki** (zaposleni matične družbe) in **uporabniki strank** (zunanje stranke, ki jim omogočite dostop do lastnih podatkov). Oba tipa sta popolnoma neodvisna in imata ločene prijavne strani ter nabore pravic.

---

## 1. Sistemski uporabniki

**Dostop:** Sistem → Nastavitve → Uporabniki

Sistemski uporabniki se delijo v vnaprej določene skupine, poleg tega pa lahko ustvarite lastne skupino z natančno določenimi pravicami. Vsaka skupina (vloga) določa, do katerih modulov in funkcij ima uporabnik dostop.

### Pregled skupin in njihovih pravic

| Skupina | Pravice |
|---------|---------|
| **Uporabnik** | Dostop do lastnih in skupinskih podatkov. Nima pravic nad sistemskimi nastavitvami. |
| **Operater** | Vpogled v vse podatke; možnost dela v imenu drugih uporabnikov. Nima pravic nad sistemskimi nastavitvami. |
| **Administrator** | Polne pravice pregleda in urejanja vseh podatkov ter sistemskih nastavitev. |
| **Superadmin** | Vse pravice administratorja, poleg tega možnost nadgradnje sistema in povratka na starejše različice. |

!!! info "Privzete skupine"
    Privzetih skupin (uporabnik, operater, administrator, superadmin) **ni mogoče izbrisati**, lahko pa jim kadar koli spremenite dodeljena dovoljenja.

---

### Urejanje skupin (vlog)

1. V glavnem seznamu uporabnikov kliknite gumb **Uredi skupine** (ikona ključavnice).
2. Za vsako skupino določite:
   - **Ime** skupine,
   - **Dovoljenja** – izberite s seznama razpoložljivih dovoljenj.
3. Shranite spremembe.

!!! tip "Ustvarjanje lastnih skupin"
    Za specifične potrebe (npr. skupina »Varnostni inženir« z dostopom samo do ocen tveganj) ustvarite novo skupino in ji dodelite natančno ta dovoljenja, ki jih potrebujete.

---

### Dodajanje in urejanje uporabnika

Nov uporabnik se doda s klikom na gumb **Dodaj** (+) v seznamu sistemskih uporabnikov. Obrazec za urejanje vsebuje naslednja polja:

| Polje | Obvezno | Opis |
|-------|---------|------|
| **E-pošta** | ✅ | Uporabniško ime za prijavo. Mora biti edinstveno. **Po prvi shranitvi ga ni mogoče spremeniti.** |
| **Geslo** | ✅ (novi) | Za novega uporabnika obvezno. Pri obstoječem pustite prazno, da geslo ostane nespremenjeno. |
| **Potrditev gesla** | ✅ (novi) | Ponovni vpis gesla za preverjanje. |
| **Skupina (vloga)** | ✅ | Določa pravice uporabnika v sistemu. |
| **Ime in priimek** | — | Polno ime, ki se prikazuje v sistemu in poročilih. |
| **Strokovni naziv** | — | Neobvezno (npr. mag., inž., dr.). Prikazuje se v podpisu poročil. |
| **Aktivno** | — | Če potrditveno polje ni označeno, se uporabnik **ne more prijaviti**. |
| **Povezava z zaposlenim (HRM)** | — | Poveže račun s HR profilom zaposlenega. Glej razdelek [HRM integracija](#2-povezava-uporabnikov-z-zaposlenimi-hrm-integracija). |
| **Podpis** | — | Naložite sliko podpisa (prikazuje se v izpisanih poročilih). |
| **Zadana stranka** | — | Stranka, ki se ob prijavi samodejno nastavi kot aktivna. |
| **Poslovna enota** | — | Poslovna enota matične družbe, ki ji uporabnik pripada. |
| **Dodeljene stranke** | 🔒 samo za ogled | Seznam strank, dodeljenih temu uporabniku kot skrbniku (ne urejate tukaj). |

!!! warning "E-pošta kot uporabniško ime"
    E-poštni naslov je hkrati uporabniško ime za prijavo. Po prvi shranitvi ga **ni mogoče spremeniti** – v primeru napake morate ustvariti novega uporabnika.

---

### Brisanje sistemskega uporabnika

Sistem pred brisanjem avtomatično preveri, ali je uporabnik povezan s katerim koli zapisom (pregledi, usposabljanja, naročila, ocene tveganj ipd.).

- **Zapisi obstajajo** → brisanje ni dovoljeno. Uporabnika lahko le **deaktivirate** (odznačite polje *Aktivno*).
- **Ni povezanih zapisov** → sistem izbriše uporabnika in vse njegove povezave: dodeljene vloge, dodeljene stranke in shranjene podpise.

!!! danger "Deaktivacija namesto brisanja"
    V večini primerov priporočamo deaktivacijo namesto brisanja. Deaktiviran uporabnik ostane v zgodovini zapisov, kar je pomembno za revizijsko sled.

---

## 2. Povezava uporabnikov z zaposlenimi (HRM integracija)

Sistem omogoča samodejno povezavo uporabniškega računa s profilom zaposlenega v modulu HR. Povezava prinaša naslednje prednosti:

- Enotno upravljanje podatkov (ime, priimek, e-pošta, aktivnost).
- Sinhronizacija sprememb iz uporabniškega računa v HR profil.
- Dostop do HR funkcij (evidentiranje prisotnosti, dopusti) za ta račun.

Obstajata dva načina vzpostavitve povezave:

### Način 1 – Povezava z obstoječim zaposlenim

Pri urejanju uporabnika izberite zaposlenega iz spustnega seznama v razdelku **Povezava z zaposlenim v HR**.

!!! note "Kateri zaposleni se prikažejo?"
    Prikazujejo se samo zaposleni **lastniške stranke** (matične družbe), ki še **niso** bili povezani z nobenim uporabniškim računom.

Po shranitvi se zgodi naslednje:

- Zaposlenemu se nastavi vrednost `user_id`.
- Vsa nadaljnja posodabljanja uporabnika (ime, e-pošta, aktivnost) se samodejno prenesejo na HR profil.

### Način 2 – Samodejno ustvarjanje HR profila

Če pri shranjevanju novega uporabnika **ne izberete** obstoječega zaposlenega, sistem samodejno ustvari osnovni HR profil:

| Polje HR profila | Vrednost |
|-----------------|---------|
| Ime | Razčlenjeno iz polnega imena uporabnika |
| Priimek | Razčlenjeno iz polnega imena uporabnika |
| E-pošta | Prenesena iz uporabniškega računa |
| Lokacija | Dodeljena glavni lokaciji (sedežu) lastniške stranke |

!!! tip "Preverjanje povezave"
    Ko je uporabnik že povezan z zaposlenim, je polje za izbiro zaklenjeno. Vse nadaljnje spremembe (ime, e-pošta, aktivnost) se samodejno prenesejo v HR profil.

---

## 3. Uporabniki strank

Strankam lahko zagotovite varen, omejen dostop do njihovih lastnih podatkov. Uporabniki strank so **popolnoma ločeni od sistemskih uporabnikov** in nimajo dostopa do podatkov drugih strank.

### Ustvarjanje uporabnika stranke

**Dostop:** Stranke → [izberite stranko] → Uporabniki

Kliknite **Dodaj** (+) in izpolnite obrazec:

| Polje | Opis |
|-------|------|
| **E-pošta** | Uporabniško ime za prijavo. |
| **Geslo** | Začetno geslo (uporabnik ga lahko pozneje sam spremeni). |
| **Ime in priimek** | Polno ime kontaktne osebe stranke. |
| **Modulne pravice** | Za vsak modul posebej izberite raven dostopa (glej spodnjo tabelo). |

#### Modulne pravice

Za vsak modul izberite eno od dveh ravni dostopa:

| Raven | Opis |
|-------|------|
| **Pregled** | Uporabnik lahko samo pregleduje podatke (samo za branje). |
| **Pregled in urejanje** | Uporabnik lahko dodaja, ureja in briše zapise v modulu. |

Razpoložljivi moduli:

- Delovna oprema
- Zaposleni
- OVO (osebna varovalna oprema)
- Zdravniški pregledi
- Delovne nezgode
- Naročila
- Požarna varnost

### Prijava uporabnika stranke

Prijavna stran za stranke je **ločena** od glavne prijavne strani sistemskih uporabnikov:

```
https://[naslov_vaše_instalacije]/mod-cust
Primer: https://demo.optima-prevent.eu/mod-cust
```

- **Uporabniško ime:** e-poštni naslov
- **Geslo:** nastavljeno ob ustvarjanju računa

### Dostop po prijavi

Po uspešni prijavi se prikaže prilagojena nadzorna plošča s hitrimi povezavami. Razpoložljivi elementi menija so odvisni od dodeljenih pravic:

| Meni | Vsebina |
|------|---------|
| **Dokumenti** | Izdani dokumenti in poročila, povezana s stranko. |
| **Periodika** | Koledarski pregled veljavnosti (usposabljanja, pregledi, meritve). |
| **Zaposleni** | Seznam zaposlenih stranke. |
| **Delovna mesta** | Tipična delovna mesta (če so konfigurirana). |
| **Delovna oprema** | Seznam opreme in pregledi. |
| **Zdravniški pregledi** | Evidence zdravstvenih pregledov. |

!!! tip "Prilagoditev izgleda"
    Prijavno stran in celoten videz portala za stranke je mogoče prilagoditi z lastnim CSS in logotipom stranke.

---

## 4. Dovoljenja (Permissions)

Sistem uporablja podroben sistem dovoljenj, ki se dodeljujejo prek skupin (vlog). Dovoljenja določajo, kateri moduli in funkcije so dostopni posameznemu uporabniku.

### Predefinirana dovoljenja modulov

| Dovoljenje | Opis |
|-----------|------|
| `view_educourse` | Ogled usposabljanj in tečajev |
| `view_measure` | Ogled meritev |
| `view_custemployee` | Ogled zaposlenih strank |
| `view_mdeviceobj` | Ogled delovne opreme |
| `view_vpp` | Ogled požarne varnosti |
| `view_rass` | Ogled ocen tveganj |
| `view_rassl` | Ogled ocen tveganj TDM |
| `view_sdev` | Ogled tehnične varnosti (naprave) |

!!! info "Kombiniranje dovoljenj"
    Administrator lahko v nastavitvah skupin poljubno kombinira dovoljenja ali doda nova, če jih sistem podpira. S tem je mogoče natančno prilagoditi dostop za vsako vlogo v organizaciji.

---

## 5. Brisanje uporabnika

| Pogoj | Dejanje |
|-------|---------|
| Uporabnik **je** povezan z zapisi (pregledi, usposabljanja, naročila …) | Brisanje ni dovoljeno. Uporabnika **deaktivirajte**. |
| Uporabnik **ni** povezan z nobenim zapisom | Sistem izbriše uporabnika in vse povezave: vloge, dodeljene stranke, shranjene podpise. |

!!! warning "Kdaj izbrisati, kdaj deaktivirati?"
    Priporočamo **deaktivacijo** v vsakem primeru, ko uporabnik ne bo več aktivno delal v sistemu, a so njegovi zapisi (poročila, pregledi) del revizijske sledi. Pravo brisanje je namenjeno samo za testne ali napačno ustvarjene račune brez kakršnih koli zapisov.
