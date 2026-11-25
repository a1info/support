# Sistemske nastavitve

**Dostop:** Sistem → Nastavitve

V tem razdelku upravljate osnovne podatke podjetja, aktivacijo modulov, nastavitve za pošiljanje e‑pošte in e‑poštne predloge, nadgradnjo sistema in digitalno podpisovanje dokumentov.

---

## Podjetje (Company)

### Osnovni podatki

| Polje | Opis |
|-------|------|
| **Ime podjetja** | Polno ime matične družbe |
| **DDV številka** | Identifikacijska številka za DDV |
| **Matična številka** | Registrska številka podjetja |
| **Naslov** | Naslov sedeža podjetja |
| **Kraj** | Mesto / poštna številka sedeža |
| **Telefon** | Stacionarna telefonska številka |
| **Mobilni** | Mobilna telefonska številka |
| **E‑pošta** | Javni kontaktni e-poštni naslov |
| **Spletna stran** | URL spletnega mesta podjetja |
| **Odgovorna oseba** | Ime in priimek odgovorne osebe |

### Logotip in podpis

- **Logotip** – naloži se slikovna datoteka (PNG/JPG); prikaže se v poročilih in na prijavnem zaslonu aplikacije.
- **Podpis** – slikovna datoteka podpisa odgovorne osebe; uporablja se pri digitalnem podpisovanju dokumentov (skupaj s certifikatom P12).

### Poslovne enote (Business Units)

Tabela prikazuje vse poslovne enote matične družbe. Vsaka enota ima svoje ime, naslov in kontaktne podatke.

!!! note "Opomba"
    Dodajanje in brisanje poslovnih enot je omejeno, kadar je sistem aktivno povezan z osrednjo licenčno storitvijo in obstaja lastniška stranka. Poslovne enote se navezujejo na obveščanje in poročila po enotah.

## E-poštni računi

**Dostop:** Sistem → Nastavitve → zavihek **E-poštni računi**

E-poštni računi so ločeni od osnovnih podatkov podjetja. V zavihku **Podjetje** ni več polj SMTP; vsa pošiljanja se nastavijo tukaj. Vsak račun določa pošiljatelja, način pošiljanja, naslov za odgovore in privzeto identiteto.

Sistem za samodejno pošto uporabi **privzeti aktivni SMTP račun**. Brez aktivnega SMTP računa se samodejna pošta ne pošilja: periodična in dogodkovna obvestila ter e-test vabila in opomniki se preskočijo, ročni gumb **Pošlji zdaj** pa prikaže opozorilo.

### Upravljanje računov

- **Dodaj račun** – odpre obrazec za nov pošiljateljski račun.
- **Uredi** – spremenite podatke obstoječega računa. Prazno polje za geslo ali API ključ ohrani obstoječo skrivnost.
- **Privzeto** – račun postane privzeti pošiljatelj. Privzet je lahko samo eden; račun mora biti aktiven in vrste SMTP.
- **Test** – pošlje testno sporočilo; prejemnik je privzeto prijavljeni uporabnik, naslov pa lahko spremenite. Ob uspehu sta prikazana tudi dejanski **From** in **Reply-To**.
- **Izbriši** – računa ni mogoče izbrisati, če je edini; ob brisanju privzetega računa sistem izbere naslednji aktivni SMTP račun.
- **Aktiven** – neaktivni račun se ne uporablja za pošiljanje.
- **Privzet** – privzeti račun se uporabi, kadar za posamezni scenarij ni drugega pravila.

Administratorji lahko račune dodajajo in urejajo. Samo **superadmin** lahko s gumbom **Pokaži** razkrije shranjeno geslo ali API ključ.

### Polja računa

| Polje | Opis |
|-------|------|
| **Ime računa** | Naziv, ki ga vidijo skrbniki (npr. *Splošni pošiljatelj*). |
| **Koda** | Kratka enolična oznaka; če je prazna, se ustvari iz imena. |
| **Način pošiljanja** | `SMTP` za dejansko pošiljanje. `MailerSend API` je za zdaj samo shranjevanje ključa za prihodnjo uporabo. |
| **Strežnik (host)** | Naslov SMTP strežnika; privzeto `smtp.mailersend.net`. |
| **Vrata** | Privzeto `587` za TLS; `465` za SSL. |
| **Šifriranje** | `TLS`, `SSL` ali brez. |
| **Uporabniško ime** | Uporabniško ime za SMTP prijavo. |
| **Geslo** | SMTP geslo. Shranjeno je šifrirano; ob urejanju ga prazno polje ne spremeni. |
| **MailerSend API ključ** | Neobvezno za prihodnje API pošiljanje; shranjeno je šifrirano. |
| **Pošiljatelj (e-pošta)** | Naslov v polju From. Domena mora biti verificirana pri ponudniku pošte. |
| **Ime pošiljatelja** | Prikazno ime pošiljatelja. |
| **Odgovori na** | Naslov Reply-To; če je prazen, se uporabi pošiljateljev naslov. |
| **Povratna pot** | Neobvezna povratna pot (Return-Path). |
| **Dnevna omejitev** | Zgornja meja dnevnega pošiljanja (privzeto 30). Uporablja se pri CRM kampanjah; preflight upošteva nižjo od omejitve kampanje in tega računa. |
| **Aktiven** | Vklopi ali izklopi račun. |
| **Privzet** | Označi privzeti račun. |

### MailerSend in lastni SMTP

Privzete vrednosti za MailerSend so:

| Ponudnik | Strežnik | Vrata | Šifriranje |
|----------|----------|-------|------------|
| MailerSend | `smtp.mailersend.net` | `587` | `tls` |
| Lastni SMTP (cPanel) | `mail.vasadomena.si` | `587` | `tls` |
| Brevo | `smtp-relay.brevo.com` | `587` | `tls` |

Za pošiljanje iz druge domene dodajte ločen račun in domeno najprej verificirajte pri ponudniku. Naslov v polju **Pošiljatelj** mora biti dovoljen za ta račun; sistema ne omejujemo na vnaprej določeno domeno.

!!! warning "MailerSend API še ni aktiven"
    Polje **MailerSend API ključ** je pripravljeno za kasnejšo integracijo, vendar API pošiljanje v tej različici ni omogočeno. Račun z načinom `MailerSend API` ne more biti privzet in testno pošiljanje ne bo uspelo. Za produkcijsko pošiljanje uporabite `SMTP`.

!!! warning "Microsoft 365 in Google Workspace"
    Ponudniki poslovne e-pošte zaradi omejitev osnovne avtentikacije in 2FA pogosto ne dovoljujejo neposrednega SMTP pošiljanja. Za sistemsko pošto uporabite namenski SMTP ali MailerSend.

### Scenariji in privzeti račun

Sistem ima rezervirane scenarije pošiljanja: `system`, `transactional`, `campaign`, `etest`, `notification`, `invoice`, `support` in `test`. Ob nadgradnji so vsi scenariji vezani na privzeti račun; upravljanje posameznih scenarijev v uporabniškem vmesniku še ni na voljo. Pri posamezni CRM kampanji lahko izberete drug poštni račun; če ga ne izberete, se uporabi scenarij `campaign` oziroma privzeti račun.

### Varnost in razkritje skrivnosti

Geslo SMTP in API ključ sta shranjena z reverzibilnim šifriranjem, ker ju SMTP oziroma API potrebuje za dejansko prijavo. Enosmerni hash (na primer bcrypt) za to ni primeren, ker bi onemogočil pošiljanje. Skrivnosti se ne izpisujejo v dnevnikih; razkrije jih lahko samo superadmin.

## E-poštne predloge

Vsebino e-poštnih sporočil urejate v **Sistem → Predloge → E-poštne predloge**. Predloge ne določajo pošiljateljskega računa – ta je vedno izbran v **E-poštni računi** – določajo pa zadevo in telo sporočila. Kampanje uporabljajo predloge iz modula **Kampanje** in izbrani poštni račun; potek pošiljanja je opisan v poglavju [CRM → Kampanje](crm.md#kampanje).

Podrobnosti o poljih, spremenljivkah in predogledu so v poglavju [Urejanje predlog → E-poštne predloge](urejanje-podlog.md#e-postne-predloge).

---

## Moduli

### Pregled aktivnih modulov

Na zavihku **Moduli** je prikazan seznam vseh modulov, ki jih sistem podpira. Za vsak modul so prikazani:

| Stolpec | Opis |
|---------|------|
| **Ime modula** | Naziv in kratek opis funkcionalnosti |
| **Status** | Aktiven / Neaktiven (pogojeno z licenco) |
| **Nastavitve** | Gumb z ikono zobnika – prikaže se le za module s konfiguracijo |

### Stanje licence

V zgornjem delu zavihka so prikazani podatki o licenci:

| Podatek | Opis |
|---------|------|
| **Trenutni paket / načrt** | Naziv aktivnega licenčnega paketa |
| **Datum poteka licence** | Datum izteka (prazno = neomejena licenca) |
| **Zadnja sinhronizacija** | Datum in čas zadnje uspešne sinhronizacije z licenčnim strežnikom |

Gumb **Sinhroniziraj licenco** ročno sproži preverjanje stanja licence pri osrednjega strežnika Optima Prevent. To je koristno po nakupu novega modula ali podaljšanju licence.

### Konfiguracija modulov

Klik na gumb **Nastavitve** (ikona zobnika ⚙) pri posameznem aktivnem modulu odpre modalno okno z nastavitvami, specifičnimi za ta modul.

**Primer – modul Ocene tveganj (Rass):**

V nastavitvah modula Rass je mogoče konfigurirati **dinamično formulo** za izračun ocene tveganja. Skrbnik vnese matematično formulo, ki se aplicira na vrednosti parametrov tveganja (verjetnost, pogostost, resnost ipd.). Rezultat je numerična vrednost, ki se prikaže v poročilih ocene tveganja.

---

## Nadgradnja sistema

**Dostop:** Sistem → Nastavitve → zavihek Nadgradnja

Na tem zaslonu spremljate različico sistema in izvajate posodobitve.

### Prikaz različic

| Element | Opis |
|---------|------|
| **Nameščena različica** | Trenutna verzija, nameščena na strežniku (pridobljena iz baze) |
| **Razpoložljiva različica** | Najnovejša različica na centralnem strežniku Optima Prevent |
| **Gumb Posodobi** | Prikaže se, ko je na voljo novejša različica ALI ko superadmin želi znova namestiti trenutno verzijo |
| **Gumb Revert to …** | Prikaže se le superadminu, kadar je lokalna različica novejša od strežniške |
| **Dnevnik sprememb** | Na desni strani zaslona – seznam novosti in popravkov za vse objavljene različice |

### Postopek samodejne nadgradnje

Ko kliknete **Posodobi**, sistem samodejno izvede naslednje korake:

1. **Prenos paketa** z osrednjega strežnika Optima Prevent
2. **Odstranitev zastarelih datotek**, ki so bile opredeljene v paketu za nadgradnjo
3. **Razširitev nove kode** na strežnik
4. **Izvedba odvisnosti in migracij** – `composer update` ter Artisan ukazi (`migrate`, `cache:clear`, `config:cache` …)
5. **Posodobitev različice** v podatkovni bazi

!!! warning "Varnostno opozorilo"
    Pred vsako nadgradnjo naredite **varnostno kopijo podatkovne baze in datotek**. Nadgradnja je enosmerna – sistem po nadgradnji ne more samodejno povrniti prejšnje različice.

    Možnost povrnitve (**Revert to …**) je dostopna le superadminu in se **ne priporoča** v produkcijskem okolju.

---

## Digitalno podpisovanje dokumentov

**Dostop:** Nastavitve → Potrdila / Akreditacije

Sistem OP5 podpira samodejno digitalno podpisovanje vseh generiranih PDF dokumentov (zapisniki, poročila, potrdila) s pomočjo osebnega certifikata v formatu P12.

### Postopek nastavitve

1. Odprite **Nastavitve → Potrdila / Akreditacije**
2. Kliknite **Dodaj nov zapis**
3. V polju **Tip** izberite `digitalni podpis`
4. Naložite datoteko **P12** (osebni certifikat)
5. Vnesite **geslo** certifikata
6. Shranite zapis

Po uspešni shranitvi bo sistem ob vsakem generiranju PDF dokumenta le-tega **samodejno digitalno podpisal**.

### Prepoznavanje podpisanih dokumentov

Digitalno podpisani dokumenti so prepoznavni po:

- Vrstici **"DIGITALLY SIGNED"** v dokumentu
- Podatkih o podpisniku (ime, datum in čas podpisa, podatki certifikata)

!!! info "Dostop za stranke"
    Podpisani dokumenti so uporabnikom strank vidni po prijavi v modulu **Izdani dokumenti**, kjer si jih lahko prenesejo in preverijo veljavnost digitalnega podpisa.

---

## Številčenje dokumentov

**Dostop:** Sistem → Številčenje

Modul za samodejno številčenje omogoča definiranje pravil oštevilčevanja za vsako vrsto dokumenta posebej. To je referenčno mesto za nastavitev števcev, ki jih pred prvo produkcijsko uporabo samo preverite še v okviru [začetne nastavitve](zacetna-nastavitev.md#avtomaticno-stevilcenje-dokumentov).

!!! note "ERP in CRM številčenje"
    Ponudbe, pogodbe, projekti in delovni nalogi se številčijo samodejno v svojih modulih in niso del tega seznama. Ponudbe in pogodbe dobijo `PON-YYYY-NNNNN` oziroma `POG-YYYY-NNNNN` ob shranjevanju, projekti `PR-YYYY-NNNNN`, delovni nalogi pa `DN-YYYY-NNNNN` v CRM.

### Parametri oštevilčevanja

| Parameter | Opis |
|-----------|------|
| **Leto** | Vključi letnico v številko dokumenta (npr. `2024`) |
| **Stranka** | Vključi kratico ali šifro stranke |
| **Tip dokumenta** | Vključi oznako tipa dokumenta |
| **Zaporedna številka** | Samodejno naraščajoče zaporedje znotraj parametrov |

### Dokumenti s samodejnim številčenjem

- Delovna oprema in certifikati delovne opreme
- Zapisniki pregledov delovne opreme
- Zapisniki pregledov varnostne opreme
- Skupine tečajev in potrdila udeležencev
- Meritve
- Dokumenti ocen tveganj
- Pregledi SAPZ
- Zapisniki VPP pregledov
- Evakuacijske vaje

V seznamu so samo števci, ki jih moduli dejansko uporabljajo. Opuščeni števci so odstranjeni iz sistema.
