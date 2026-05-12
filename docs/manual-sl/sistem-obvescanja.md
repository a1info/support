# Sistem obveščanja

Sistem Optima Prevent omogoča napredno avtomatizirano obveščanje strank in zaposlenih preko e-pošte. Obvestila pokrivajo opomnike o poteku veljavnosti (pregledi opreme, usposabljanja), pošiljanje dostopnih podatkov za e-učenje in sistemska opozorila.

!!! warning "Predpogoj: Nastavitev SMTP strežnika"
    Za uspešno delovanje celotnega sistema obveščanja mora biti predhodno pravilno nastavljen vaš lastni SMTP strežnik. 
    Navodila za nastavitev najdete v poglavju [Sistemske nastavitve](sistemske-nastavitve.md#e-postna-konfiguracija-smtp).

---

## 1. Pravila obveščanja strank (Veljavnosti)

Sistem omogoča prožno nastavljanje avtomatiziranih e-poštnih opomnikov za stranke. Tako ste vi in vaše stranke pravočasno obveščeni o izteku veljavnosti zapisnikov, pregledov opreme ali zdravniških spričeval.

**Dostop:** Nastavitve → Obveščanje (Notifications)

### Ustvarjanje pravila

Kliknite na gumb za dodajanje (**+**) in izpolnite naslednje parametre:

| Polje | Opis |
|-------|------|
| **Stranka** | Izbira stranke, na katero se obvestilo nanaša. |
| **E-pošta** | E-poštni naslov prejemnika (lahko je kontakt pri stranki ali vaš skrbnik). |
| **Tip obvestila** | Kategorija, ki se preverja (npr. poteki pregledov delovne opreme, poteki usposabljanj). |
| **Periodika** | Kako pogosto naj se obvestilo pošlje (npr. mesečno). |
| **Dan v mesecu** | Točen dan v mesecu (1-28), ko se obvestilo zgenerira in pošlje. |
| **Dni pred potekom** | Koliko dni vnaprej naj sistem opozori na potek (npr. 30 dni). |
| **Dni po poteku** | Opozorilo za postavke, ki so že potekle in še niso bile rešene (npr. 15 dni). |
| **Status** | Pravilo lahko začasno deaktivirate brez brisanja (Aktivno / Neaktivno). |

!!! tip "Več prejemnikov"
    Če želite isto obvestilo poslati več osebam (npr. direktorju stranke in vašemu skrbniku za to stranko), preprosto ustvarite dve ločeni pravili z različnima e-poštnima naslovoma.

---

## 2. Obveščanje zaposlenih (eUsposabljanje / eTest)

Modul za usposabljanja vsebuje lasten sistem obveščanja, ki skrbi za neposredno komunikacijo z zaposlenimi pri izvajanju spletnih tečajev (e-izobraževanj).

### Pošiljanje dostopnih podatkov

Ko ustvarite nov tečaj usposabljanja z omogočenim **e-testom**, mora sistem udeležencem poslati unikatne dostopne podatke.

1. Zaposleni mora imeti v svojem profilu **vpisan e-poštni naslov**.
2. Pri ustvarjanju tečaja (zapisnika) morate obvezno **obkljukati možnost za pošiljanje e-pošte** s pristopnimi podatki.
3. Sistem bo udeležencu samodejno poslal e-poštno sporočilo, ki vsebuje:
    - Povezavo (URL) do portala za reševanje testa,
    - Uporabniško ime,
    - Geslo za enkratno prijavo.

### Opomniki pred iztekom e-testa

E-testi imajo običajno določen rok za reševanje (npr. 7 ali 14 dni). Če zaposleni testa ne reši takoj, sistem spremlja njegovo aktivnost.
Nekaj dni pred iztekom roka za reševanje bo sistem **samodejno poslal opomnitveno e-pošto**, da zaposlenega spomni na neopravljeno obveznost.

---

## 3. Sledenje e-pošti in diagnostika (Email Log)

Ker je dostavljivost e-pošte ključnega pomena, ima sistem vgrajeno orodje za sledenje in diagnostiko odhodne pošte. Tukaj lahko preverite, ali je bil mail dejansko poslan in odkrijete morebitne napake (npr. napačno vnesen e-mail stranke, napaka na SMTP strežniku).

**Dostop:** Nastavitve → Dnevnik dejavnosti (System log) → zavihek **Email log**

### Uporaba dnevnika

- **Prikaz terminala:** Dnevnik je prikazan v obliki temnega terminalskega okna, ki prikazuje surovo komunikacijo med sistemom in vašim SMTP strežnikom.
- **Filtriranje:** Na vrhu lahko določite število vrstic za prikaz (Lines) in uporabite polje **Filter** za iskanje specifičnega e-poštnega naslova (npr. iskanje `janez.novak@stranka.si`, da vidite, ali je dobil povabilo na e-test).

!!! note "Kaj pomenijo napake v dnevniku?"
    Če pri določenem e-mailu vidite napako (pogosto obarvano ali označeno z *Exception*), to najpogosteje pomeni:
    
    - Vaš SMTP strežnik je zavrnil povezavo (napačno geslo v sistemskih nastavitvah).
    - E-poštni predal prejemnika je poln ali ne obstaja.
    - Vaš ponudnik gostovanja je blokiral pošiljanje zaradi prekoračitve dnevne omejitve.

---

## 4. Obveščanje znotraj Portala za stranke

Poleg e-pošte sistem podpira tudi t.i. *in-app* obveščanje za vaše naročnike. 

Stranke imajo omogočen dostop do lastnega spletnega portala, kjer lahko pregledujejo svojo opremo, zaposlene, ocene tveganja in dokumente. **Kadarkoli v sistemu za stranko ustvarite in objavite nov dokument**, se na njihovem portalu samodejno ustvari obvestilo o novem dokumentu.

!!! info "Več informacij o portalu"
    Podrobna navodila o dodeljevanju dostopov strankam in upravljanju portala za stranke so opisana v ločenem poglavju **Portal za stranke** .