# Uporabniki

Sistem loči med **sistemskimi uporabniki** (zaposleni matične družbe) in **uporabniki strank** (zunanje stranke, ki jim omogočite dostop do lastnih podatkov).

---

## Sistemski uporabniki

**Dostop:** Sistem → Nastavitve → Uporabniki

Sistemski uporabniki se delijo v vnaprej določene skupine, lahko pa ustvarite tudi lastne skupine z različnimi pravicami.

| Skupina | Pravice |
|---------|---------|
| **Uporabnik** | Dostop do lastnih in skupinskih podatkov; nima pravic nad sistemskimi nastavitvami. |
| **Operater** | Vpogled v vse podatke, možnost dela v imenu drugih uporabnikov; nima pravic nad sistemskimi nastavitvami. |
| **Administrator** | Polne pravice pregleda in urejanja vseh podatkov ter sistemskih nastavitev. |
| **Superadmin** (posebna) | Ima vse pravice administratorja ter dodatno možnost nadgradnje sistema in povratka na starejše različice. |

### Urejanje skupin (vlog)

- V glavnem seznamu uporabnikov kliknite **Uredi skupine** (ikona ključavnice) za urejanje obstoječih skupin.
- Skupini določite ime in izberite dovoljenja (permissions) s seznama.
- Privzete skupine (uporabnik, operater, administrator, superadmin) ni mogoče izbrisati, lahko pa jim spreminjate dovoljenja.

### Urejanje uporabnika

Nov uporabnik se doda s klikom na gumb **Dodaj** (+) v seznamu. Pri urejanju so na voljo naslednja polja:

| Polje | Opis |
|-------|------|
| **E‑pošta** | Uporabniško ime (obvezno, edinstveno). Po shranitvi ga ni več mogoče spremeniti. |
| **Geslo** | Za novega uporabnika obvezno. Pri obstoječem pustite prazno, če ga ne želite spremeniti. |
| **Potrditev gesla** | Ponovni vpis gesla. |
| **Skupina (vloga)** | Dodeli pravice. |
| **Ime in priimek** | Polno ime uporabnika. |
| **Strokovni naziv** | Neobvezno polje (npr. mag., inž.). |
| **Aktivno** | Potrditveno polje – če ni aktivno, se uporabnik ne more prijaviti. |
| **Povezava z zaposlenim (HRM)** | Glej poglavje *Povezava uporabnikov z zaposlenimi*. |
| **Podpis** | Možnost nalaganja slike podpisa (prikaže se v poročilih). |
| **Zadana stranka** | Stranka, ki se ob prijavi uporabnika samodejno nastavi kot aktivna. |
| **Poslovna enota** | Poslovna enota matične družbe, ki ji uporabnik pripada. |
| **Dodeljene stranke** (samo za ogled) | Seznam strank, ki so dodeljene uporabniku (ko je uporabnik skrbnik za stranko). |

Uporabnika lahko izbrišete le, če ni povezan z nobenim zapisom (pregledi, usposabljanji, naročili …). Sistem pred brisanjem preveri prisotnost povezanih podatkov.

---

## Povezava uporabnikov z zaposlenimi (HRM integracija)

Sistem omogoča samodejno povezavo uporabniškega računa s profilom zaposlenega (Custemployee). Povezava omogoča:

- Enotno upravljanje podatkov (ime, priimek, e‑pošta, aktivnost).
- Sinhronizacijo sprememb iz uporabniškega računa v HR profil (in obratno – pri dodelitvi prek izbire zaposlenega).
- Uporabo HR funkcij (evidentiranje časa, dopusti) za ta račun.

Obstajata dva načina povezave:

### 1. Povezava z obstoječim zaposlenim
Ko urejate uporabnika, v razdelku **Povezava z zaposlenim v HR** izberite zaposlenega s spustnega seznama. Prikažejo se samo zaposleni lastniške stranke (matične družbe), ki še niso povezani z nobenim uporabnikom.

Po shranitvi:
- Zaposlenemu se nastavi `user_id`.
- Vsa nadaljnja posodobitev uporabnika (ime, e‑pošta, aktivnost) se samodejno prenese na HR profil.

### 2. Samodejno ustvarjanje HR profila
Če ne izberete obstoječega zaposlenega, sistem ob shranjevanju novega uporabnika samodejno ustvari osnovni HR profil:

- Ime in priimek se razčlenita iz polnega imena uporabnika.
- E‑pošta se prepiše.
- Profil se dodeli glavni lokaciji (sedežu) lastniške stranke.
- Uporabnik postane povezan s tem novim zapisom.

Če uporabnik že ima povezanega zaposlenega (polje je zaklenjeno), se spremembe uporabnika (ime, e‑pošta, aktivnost) vedno prenesejo na HR profil.

---

## Uporabniki strank

Strankam lahko omogočite varen dostop do sistema. Njihovi uporabniki so **neodvisni od sistemskih uporabnikov** in imajo dostop le do podatkov svoje stranke.

### Ustvarjanje uporabnika stranke

**Dostop:** Stranke → [izberite stranko] → Uporabniki

Kliknite **Dodaj** in vnesite:
- **E‑pošta** (uporabniško ime)
- **Geslo** (uporabnik ga lahko kasneje spremeni)
- **Ime in priimek**
- **Modulne pravice** – izberite module (delovna oprema, zaposleni, OVO, zdravniški pregledi, delovne nezgode, naročila, požarna varnost) in zanje določite:
  - **Pregled** – uporabnik lahko le pregleduje podatke.
  - **Pregled in urejanje** – uporabnik lahko dodaja, spreminja in briše zapise v modulu.

### Prijava uporabnika stranke

Prijavna stran je ločena od glavne prijave sistemskih uporabnikov:


URL za prijavo: https://naslov_vaše_inštalacije/mod-cust  
Primer: https://demo.optima-prevent.eu/mod-cust

- Uporabniško ime: e‑poštni naslov
- Geslo: nastavljeno ob vnosu (uporabnik ga lahko po prvi prijavi spremeni v svojem profilu)

### Dostop po prijavi

Po prijavi se uporabniku prikaže prilagojena nadzorna plošča (dashboard) s hitrimi povezavami. Glede na dodeljene pravice ima dostop do:

| Meni | Vsebina |
|------|---------|
| **Dokumenti** | Izdani dokumenti, povezani s stranko. |
| **Periodika** | Koledarski pregled veljavnosti (usposabljanja, pregledi, meritve). |
| **Zaposleni** | Seznam zaposlenih stranke. |
| **Delovna mesta** | Tipična delovna mesta (če so na voljo). |
| **Delovna oprema** | Seznam opreme in pregledi. |
| **Zdravniški pregledi** | Evidence zdravstvenih pregledov. |

Prijavno stran in izgled za stranke je možno prilagoditi (CSS, logotip).

---

## Dovoljenja (Permissions)

Sistem uporablja podroben sistem dovoljenj, ki se dodeljujejo prek skupin (vlog). Za lažjo nastavitev so na voljo vnaprej pripravljena dovoljenja za ključne module, kot so:

- `view_educourse` – ogled usposabljanj
- `view_measure` – ogled meritev
- `view_custemployee` – ogled zaposlenih
- `view_mdeviceobj` – ogled delovne opreme
- `view_vpp` – ogled požarne varnosti
- `view_rass` – ogled ocen tveganj
- `view_rassl` – ogled ocen TDM
- `view_sdev` – ogled tehnične varnosti

Skrbnik lahko v nastavitvah skupin poljubno kombinir ta dovoljenja ali doda nova, če jih sistem podpira.

---

## Brisanje uporabnika

Pri brisanju uporabnika sistem preveri, ali je povezan s kakšnim zapisom (pregledi, usposabljanji, naročili ipd.). Če so takšni zapisi prisotni, brisanje ni dovoljeno – uporabnika lahko le deaktivirate. V nasprotnem primeru se izbrišejo tudi vse povezave (dodeljene vloge, dodeljene stranke, lastni podpisi) in uporabnik izgine iz sistema.
