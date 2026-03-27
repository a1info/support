# Požarna varnost

Modul **Požarna varnost** omogoča celovito vodenje evidenc požarne varnosti v skladu z načrtom požarne varnosti posameznega objekta.

---

## 1. Pregled modula

Modul pokriva vse ključne evidence, ki jih zahteva zakonodaja s področja varstva pred požarom:

- evidence aktivne požarne zaščite (APZ),
- ročne gasilnike,
- usposabljanja zaposlenih,
- vaje evakuacije,
- kurilne in dimne naprave,
- strelovode,
- elektro naprave,
- odgovorne osebe,
- hidrantne liste,
- evidenco požarov in eksplozij.

### Dostop

**Glavni meni → Požarna varnost → Seznam objektov**

!!! info "Aktivna stranka"
    Prikazani objekti so odvisni od trenutno izbrane stranke. Pred pregledom ali vnosom preverite, da imate v orodni vrstici izbrano ustrezno stranko.

---

## 2. Objekti požarne varnosti

Vsaka stranka ima lahko enega ali več objektov požarne varnosti. Vsak objekt je osnovna enota, na katero se navezujejo vse evidence.

### Dodajanje novega objekta

Kliknite gumb **Dodaj objekt** na seznamu objektov.

### Polja pri vnosu objekta

| Polje | Opis |
|-------|------|
| **Stranka / PE** | Izberite stranko in poslovno enoto, ki ji objekt pripada. |
| **Naziv objekta** | Opisno ime objekta (npr. »Skladišče – Kranj«). |
| **Ocena požarne ogroženosti** | Numerična ocena (1–4) glede na zakonodajne kriterije. |
| **Število oseb** | Največje število oseb, ki so hkrati prisotne v objektu. |
| **Veljavnost (meseci)** | Določite, čez koliko mesecev je vnos potrebno obnoviti; to se upošteva v modulu **Periodika**. |
| **Priponke** | Priložite načrt evakuacije, požarni red ali druge dokumente. |
| **Ostali podatki** | Naslov, kontaktna oseba za PV, dodatne opombe. |

!!! warning "Samodejni prikaz vaj evakuacije"
    Kadar je **ocena požarne ogroženosti ≥ 3** IN **število oseb ≥ 100**, se v okviru objekta samodejno prikaže zavihek **Vaje evakuacije**. Evidence letnih vaj evakuacije so v tem primeru obvezne.

---

## 3. Evidence v okviru objekta

Ko odprete posamezni objekt, imate na voljo naslednje zavihke z evidencami:

| Evidenca | Opis |
|----------|------|
| **Aktivna požarna zaščita (APZ)** | Sistemi aktivne požarne zaščite (javljalniki, sprinklerji itd.). Tipi APZ se upravljajo v **Požarna varnost → Tip APZ**. |
| **Ročni gasilniki** | Seznam prenosnih in prevoznih gasilnikov z datumi pregledov. Na voljo je uvoz iz datoteke CSV. |
| **Usposabljanje zaposlenih** | Evidenca usposabljanj za začetno gašenje in evakuacijo. Povezano z glavnim modulom Usposabljanja – izberite tip tečaja v nastavitvah objekta. |
| **Vaje evakuacije** | Prikazano samo kadar ogroženost ≥ 3 IN število oseb ≥ 100. Evidenca letnih vaj z datumom, opisom in priponkami. |
| **Kurilne in dimne naprave** | Kotli, peči in dimne naprave z datumi čiščenja in pregledov. |
| **Strelovodi** | Inštalacije za zaščito pred strelo z datumi meritev in pregledov. |
| **Elektro naprave** | Električne inštalacije. Povezano z modulom **EKO/VZD – Meritve** za pregled meritev. |
| **Odgovorne osebe za PV** | Seznam oseb, ki so odgovorne za požarno varnost v objektu (ime, kontakt, vloga). |
| **Hidrantni list** | Evidence hidrantnega omrežja in hidrantnih pregledov. |
| **Požari in eksplozije** | Zapis vseh incidentov v objektu z datumom, opisom in škodo. |

!!! tip "Veljavnost in Periodika"
    Vsaki evidenci (npr. pregled gasilnikov, meritev strelovoda) določite veljavnost v mesecih. Ko veljavnost poteče, se vnos samodejno pojavi v modulu **Analitika → Periodika** in v **CRM → Periodika** koledarju.

---

## 4. Tipi APZ

Preden dodate sisteme aktivne požarne zaščite k objektu, morate definirati tipe APZ.

### Dostop

**Požarna varnost → Tip APZ**

### Upravljanje tipov

- Dodajte nove tipe (npr. »Avtomatski javljalnik dima«, »Sprinkler sistem«, »Plinsko gašenje«).
- Vsak tip ima naziv in opcijski opis.
- Tipi se nato izbirajo pri vnosu APZ evidence znotraj objekta.

!!! info
    Tipi APZ so skupni za vse objekte in stranke v sistemu. Priporočamo poenoteno poimenovanje.

---

## 5. Izvozi in tisk

### PDF izvoz

Na vsakem seznamu evidenc (gasilniki, APZ, strelovodi itd.) je na voljo gumb za **izvoz v PDF**. Izpis vsebuje vse ključne podatke zapisov ter glavo z imenom objekta in stranke.

### Usposabljanja – potrdila

Potrdila in zapisniki usposabljanj za požarno varnost se generirajo v **glavnem modulu Usposabljanja**, ne neposredno iz tega modula. Evidenca v požarni varnosti je le referenca na opravljeno usposabljanje.

---

## 6. Povezava z modulom Usposabljanja

Usposabljanje zaposlenih za gašenje začetnih požarov in evakuacijo je tesno integrirano z modulom **Usposabljanja**.

### Nastavitev

1. Odprite objekt požarne varnosti.
2. V razdelku **Usposabljanje zaposlenih** izberite **tip tečaja** iz glavnega modula usposabljanj.
3. Ko se usposabljanje opravi prek modula Usposabljanja, se podatki samodejno zrcalijo v evidenco objekta.

### Potrdila in zapisniki

- Potrdila o usposabljanju in zapisniki skupin se generirajo izključno v **modulu Usposabljanja**.
- Iz evidence požarne varnosti lahko dostopate do povezanega zapisa v usposabljanjih s klikom na ikono povezave.

!!! tip
    Za celovit nadzor usposobljenosti zaposlenih za PV redno preverjajte **Analitika → Periodika → Usposabljanja**, kjer so prikazani poteki veljavnosti.
