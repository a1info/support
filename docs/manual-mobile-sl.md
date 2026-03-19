# Navodila za uporabo — Optima Prevent Mobilna aplikacija

## Uvod
Mobilna aplikacija Optima Prevent je terensko orodje, ki deluje v povezavi s spletnim EHS sistemom Optima Prevent. Omogoča hiter dostop do informacij o delovni opremi, izvajanje pregledov na terenu, reševanje e-testov in beleženje prihodov/odhodov zaposlenih prek NFC tehnologije.

Aplikacija je na voljo za operacijska sistema Android in iOS ter je posebej prilagojena za hitro in enostavno uporabo neposredno na delovnem mestu.

---

## Prijava in izbira vloge
Ob zagonu aplikacije morate izbrati svojo vlogo. Na voljo so trije glavni moduli dostopa:

1. **Zaposleni (E-Testi)**
   * Namenjeno zaposlenim, ki morajo opraviti usposabljanje ali preverjanje znanja.
   * Prijava poteka z uporabniškim imenom in geslom, ki ga zaposleni prejme na "E-Test kartici" (ali po e-pošti).

2. **Inšpektor / Skrbnik (Pregledi)**
   * Namenjeno strokovnim sodelavcem, ki na terenu pregledujejo delovno opremo, gasilnike in vnašajo nove zapise.
   * Prijava poteka z e-poštnim naslovom in geslom vašega glavnega uporabniškega računa v spletni aplikaciji Optima Prevent.

3. **Kadrovska evidenca (HRM - Kiosk način)**
   * Namenjeno postavitvi naprave (telefona ali tablice) na vhod v podjetje kot "registrator delovnega časa".
   * Za delovanje mora biti na napravi omogočen NFC in aktivna internetna povezava.

---

## Modul: Zaposleni (E-test)
Sistem zaposlenemu omogoča reševanje dodeljenih vprašalnikov za področje VZD in PV.

* **Prikaz gradiva:** Pred začetkom testa se na zaslonu prikaže študijsko gradivo (PDF dokument ali MP4 video). Gradivo morate pregledati in potrditi, da ste se z njim seznanili.
* **Reševanje testa:** Po potrditvi gradiva se prikažejo vprašanja. Izberete enega izmed ponujenih odgovorov (A, B ali C).
* **Časovna omejitev:** Če je v spletnem sistemu za določen test nastavljena časovna omejitev, se na vrhu zaslona prikazuje odštevalnik. Če čas poteče, se test samodejno zaključi.
* **Konec testa:** Po zadnjem vprašanju potrdite oddajo testa. Rezultat in potrdilo se samodejno generirata in shranita v centralno bazo Optima Prevent.

---

## Modul: Inšpektor / Skrbnik (QR Skeniranje in Pregledi)
Ta modul omogoča hiter dostop do podatkov z branjem QR kod, ki so nalepljene na delovni opremi.

### Skeniranje QR kod
* Za uporabo skenerja morate aplikaciji dovoliti dostop do kamere.
* Kamero usmerite v QR kodo na nalepki opreme.
* Sistem bo samodejno zaznal tip kode in vas preusmeril na ustrezno kartico:
  * **Zaposleni:** Prikaže osnovne podatke o zaposlenem, pretekle e-teste in zdravniške preglede.
  * **Gasilni aparat:** Prikaže evidenco in zgodovino pregledov gasilnika.
  * **Delovna oprema:** Prikaže podatke o opremi, njeno lokacijo in zadnji opravljen pregled.

### Izvajanje novih pregledov
Če med skeniranjem delovne opreme ugotovite, da je potreben nov pregled (npr. periodični letni pregled):
1. Na zaslonu s podrobnostmi opreme kliknite gumb **"NOV PREGLED"**.
2. Odpre se obrazec, kjer označite uspešnost pregleda (Ustrezno / Neustrezno).
3. Določite datum pregleda in preverite/uredite novo točno lokacijo opreme (če je bila oprema premaknjena, se bo lokacija posodobila tudi v glavni bazi).
4. Vpišite morebitne opombe.
5. Če ima oprema nastavljene **kontrolne točke** (dinamična matrika iz spletnega sistema), se bodo te točke prikazale kot seznam. Vsako točko preverite in označite.
6. Kliknite **"SHRANI PREGLED"**.

Sistem ob shranjevanju prebere vaše **GPS koordinate** in jih shrani skupaj z zapisnikom v glavno bazo, kar zagotavlja sledljivost opravljenega terenskega dela.

---

## Modul: Kadrovska evidenca (HRM Terminal)
V tem načinu naprava deluje kot pametni registrator prisotnosti. 

### Uporaba NFC terminala
1. Inšpektor ali skrbnik se mora najprej prijaviti v modul "Inšpektor / Skrbnik", da aplikacija prevzame nastavitve URL-ja in varnostne žetone.
2. Nato na začetnem zaslonu izberete **"Kadrovska evidenca"**.
3. Na zaslonu se prikaže utripajoča ikona NFC.
4. Zaposleni prisloni svojo **NFC kartico** ali **NFC obesek** na hrbtno stran naprave (na mesto, kjer se nahaja NFC čitalec).
5. Sistem samodejno prepozna kartico in v zlomku sekunde zabeleži dogodek na serverju.
6. Na zaslonu se prikaže ime zaposlenega in zabeležena akcija (zelena barva za PRIHOD, oranžna barva za ODHOD).
7. Po nekaj sekundah se zaslon samodejno ponastavi in je pripravljen na naslednjega zaposlenega.

*Opomba: Aplikacija mora imeti dostop do interneta, da se podatki o prisotnosti sinhronizirajo z modulom HRM v spletni aplikaciji.*