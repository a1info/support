# Zaposleni

## Pregled modula

Modul **Zaposleni** je namenjen upravljanju evidenc delavcev vaših strank. Zagotavlja centralno mesto za vodenje osebnih podatkov zaposlenih, njihovih delovnih mest in organizacijske umestitve.

Modul je **tesno povezan z ostalimi moduli** sistema OP5:

| Modul | Povezava |
|---|---|
| Usposabljanja | Zaposleni so udeleženci usposabljanj; generirajo se zapisniki in potrdila |
| OVO (Osebna varovalna oprema) | Evidenca izdane opreme posameznemu delavcu |
| Delovna oprema | Zadolževanje zaposlenih z delovno opremo (orodje, stroji, službena vozila) |
| Zdravniški pregledi | Sledenje veljavnosti zdravniških spričeval |
| Delovne nezgode | Zaposleni nastopajo kot ponesrečenci ali priče |
| Ocene tveganja | Tipična delovna mesta zaposlenih so osnova za OT |

**Dostop:** Glavni meni → Zaposleni

---

## Seznam zaposlenih

Ko je v zgornjem meniju izbrana **aktivna stranka**, seznam prikazuje samo zaposlene te stranke. Brez izbire aktivne stranke so prikazani zaposleni vseh strank.

### Elementi seznama

- **Tabela zaposlenih** — priimek, ime, delovno mesto, poslovna enota, status (aktiven/neaktiven)
- **Desni panel** — gumbi za akcije in možnosti filtriranja

### Možnosti filtriranja

| Filter | Opis |
|---|---|
| Aktivni / neaktivni | Prikaz samo aktivnih, samo neaktivnih ali vseh zaposlenih |
| Poslovna enota | Filtrirajte zaposlene po določeni lokaciji stranke |
| Delovno mesto | Prikaz po vrsti delovnega mesta |
| Iskanje po imenu | Hitro iskanje po priimku ali imenu |

---

## Dodajanje zaposlenega

**Dostop:** Zaposleni → gumb »Dodaj novega« ali »+«

### Polja obrazca

| Polje | Tip | Obvezno | Opis |
|---|---|---|---|
| Ime | Besedilo | Da | Osebno ime |
| Priimek | Besedilo | Da | Priimek |
| Datum rojstva | Datum | Ne | Rojstni datum (za izračun starosti in dokumentacijo) |
| Spol | Izbor | Ne | Moški / Ženski |
| Naslov | Besedilo | Ne | Stalno bivališče |
| E-pošta | Besedilo | Ne | Elektronski naslov (za obvestila) |
| Telefon | Besedilo | Ne | Kontaktna telefonska številka |
| Delovno mesto | Izbor | Da | Tipično delovno mesto (TDM) — osnova za ocene tveganja |
| Poslovna enota | Izbor | Da | Lokacija oz. enota, kjer je zaposleni razporejen |
| Aktiven | Da/Ne | — | Status zaposlenega; privzeto: Da |

### Delovno mesto (TDM)

Polje **Delovno mesto** poveže zaposlenega s **tipičnim delovnim mestom (TDM)**. TDM je standardiziran profil delovnega mesta, ki določa:

- tveganja in nevarnosti,
- zahtevana usposabljanja,
- predpisane zdravniške preglede,
- potrebno osebno varovalno opremo.

!!! info "Pomembno"
    Pravilna dodelitev delovnega mesta je ključna za avtomatsko predlaganje usposabljanj in zdravniških pregledov pri posameznemu zaposlenemu.

### Preverjanje podvojenih zapisov

Sistem OP5 **samodejno preverja podvojene zapise** na podlagi kombinacije ime + priimek + datum rojstva. Pred dokončnim shranjevanjem preverite opozorilo o morebitnem duplikatu.

!!! warning "Duplikati"
    Kljub avtomatskemu preverjanju pred vnosom sami preverite, ali zaposleni že obstaja v sistemu — zlasti pri strankah z večjim številom zaposlenih ali pri ponovnem uvajanju.

---

## Upravljanje zaposlenih

### Urejanje zapisa

- Kliknite na **ime zaposlenega** v seznamu ali na ikono za urejanje (svinčnik).
- Odpre se obrazec z vsemi polji — spremenite željene podatke in shranite.

### Zadolževanje opreme (Delovna oprema)

Zaposlenemu lahko dodelite v uporabo delovno opremo (npr. orodje, merilnike, službeno vozilo). Več zaposlenih lahko souporablja isto opremo, hkrati pa lahko določite, kdo izmed njih je **odgovorna oseba** za to opremo.

**Postopek zadolžitve:**
1. V seznamu kliknite na ime zaposlenega, da odprete **Kartoteko zaposlenega (Ogled)**.
2. Izberite zavihek **Zadolžena oprema**.
3. Kliknite gumb **»+ Zadolži«**.
4. Odpre se iskalno okno, kjer lahko poiščete opremo (po nazivu, serijski ali inventarni številki). Prikazana je le oprema podjetja, v katerem je delavec zaposlen.
5. Izpolnite polja (označite ali je zaposleni odgovoren, vpišite datum zadolžitve in morebitno opombo).
6. Shranite.

*Opomba: Ko zaposleni vrne opremo, v urejanju zadolžitve vnesite »Datum vračila«. S tem se ohrani sledljivost, oprema pa ni več aktivno na delavcu.*

### Deaktivacija zaposlenega

Zaposlenih z obstoječo zgodovino **ni mogoče izbrisati** (če imajo na primer opravljene preglede, usposabljanja ali zadolženo opremo) — evidenca preteklih usposabljanj in dokumentov mora ostati nespremenjena.

Namesto brisanja zaposlene **deaktivirajte**:

1. Odprite zapis zaposlenega.
2. Odznačite polje **Aktiven**.
3. Shranite.

Deaktiviran zaposleni:

- se ne prikazuje v operativnih pregledih in izbirah,
- ohrani vse zgodovinske zapise,
- ga je mogoče kadar koli **ponovno aktivirati**.

### PDF poročilo zaposlenega

Za vsakega zaposlenega je možno generirati **PDF poročilo z zgodovino** — pregled vseh povezanih evidenc:

- opravljenih usposabljanj in veljavnih potrdil,
- zdravniških pregledov,
- zadolžene delovne opreme in OVO,
- delovnih nezgod (kot ponesrečenec ali priča).

**Dostop:** Kliknite na zaposlenega → gumb »PDF poročilo« ali ikona za tiskanje.

---

## Povezava z IT računom

Sistem OP5 omogoča hitro **povezavo evidence zaposlenega z IT uporabniškim računom** za dostop do aplikacije.

### Postopek

1. Odprite zapis zaposlenega (zavihek Dodatno).
2. Obkljukajte gumb **»Ustvari uporabniški račun (Login)«**.
3. Sistem samodejno ustvari račun, kjer kot prijavno ime nastavi e-pošto zaposlenega.

### Prednosti povezave

- **Avtomatska sinhronizacija podatkov** — spremembe v evidenci zaposlenega se odrazijo na uporabniškem računu.
- **Dostop do HRM orodij** — omogoča zaposlenemu prijavo v portale za:
    - evidenco prisotnosti in delovnega časa,
    - vlogo za dopust in odsotnosti,
    - vpogled v lastna potrdila in dokumente.

!!! info "Podrobnosti"
    Za nastavitev pravic in vlog IT računov glejte razdelek **Uporabniki** v sistemski dokumentaciji.

---

## Uvoz zaposlenih iz Excel datoteke

Za masovni vnos zaposlenih (npr. pri novi stranki) uporabite **uvoz iz Excel datoteke**.

**Predloga:** `tplImportCustemployee.xlsx` — dostopna na vnosni maski Zaposleni.

### Postopek uvoza


    - Prenesite predlogo tplImportCustemployee.xlsx,
    . Odprite v LibreOffice Calc (priporočeno),
    - Vnesite ali prilepite podatke pod naslovno vrstico,
    - Preverite, da naslovna vrstica ostane nespremenjena,
    - Shranite datoteko v formatu UTF-8,
    - V OP5 izberite aktivno stranko (zgornji meni),
    - Pojdite na Zaposleni → ikona za uvoz (ob gumbu Dodaj),
    - Naložite datoteko in potrdite uvoz,
    - Preglejte rezultat (uspešno / neuspešno uvožene vrstice)


!!! important "UTF-8 kodiranje"
    Datoteko vedno shranite s kodiranjem **UTF-8**, da zagotovite pravilen prikaz šumnikov (č, š, ž). V LibreOffice izberite: Datoteka → Shrani kot → Format: CSV (UTF-8) ali ustrezni Excel format.

!!! tip "Testni uvoz"
    Pred uvozom celotnega seznama najprej uvozite 3–5 testnih vrstic in preverite rezultat. Tako hitro odkrijete morebitne napake v strukturi datoteke.

!!! note "Aktivna stranka"
    Pred uvozom preverite, da je v zgornjem meniju izbrana **pravilna aktivna stranka**. Uvoženi zaposleni bodo dodeljeni izbrani stranki in izbrani poslovni enoti.