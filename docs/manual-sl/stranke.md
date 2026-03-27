# Stranke in poslovne enote

## Stranke

Stranke so **naročniki in prejemniki storitev** matične družbe. V sistemu OP5 vsaka stranka predstavlja pravni subjekt, za katerega se vodijo evidenca zaposlenih, delovne opreme, usposabljanj, pregledov in ostala dokumentacija s področja EHS.

Vsaka stranka in njene poslovne enote lahko vsebujeta:

- zapise zaposlenih,
- evidenco delovne opreme,
- operacije (pregledi, usposabljanja, meritve, ocene tveganja itd.),
- izdane dokumente in certifikate.

**Dostop:** Glavni meni → Stranke

---

### Obvezna polja

| Polje | Opis |
|---|---|
| Naziv | Uradno ime podjetja / organizacije |
| Naslov | Ulica in hišna številka sedeža |
| Mesto | Kraj sedeža |
| DDV številka | Davčna številka stranke (SI + 8 mestna številka) |

### Samodejni uvoz iz AJPES

Za hitrejši vnos podatkov o stranki:

1. V polje **DDV številka** vnesite davčno številko podjetja.
2. Kliknite gumb **»Najdi«**.
3. Sistem poizve v registru AJPES in samodejno izpolni naziv, naslov in ostale javne podatke.

!!! tip "Prihranek časa"
    Uvoz iz AJPES je priporočen za vse novo dodane stranke — zmanjša možnost tipkarskih napak in zagotovi, da so podatki usklajeni z uradnim registrom.

---

### Izbirna polja

| Polje | Opis |
|---|---|
| Šifra po meri | Lastna šifra stranke (npr. šifra iz računovodskega programa, za lažjo povezavo) |
| Skrbnik | Uporabnik sistema, ki je odgovoren za to stranko in prejema obvestila (npr. opozorila o veljavnosti) |
| Aktivna | Označuje, ali je stranka aktivna; neaktivne stranke se skrijejo iz operativnih pogledov, zgodovina pa se ohrani |
| Izključi iz sledenja veljavnosti | Če označeno, se stranka ne prikazuje v analitičnih pregledih veljavnosti dokumentov in opreme |

---

### Deaktivacija stranke

Stranke **ni priporočeno brisati**, ker s tem izgubite zgodovino vseh operacij, dokumentov in evidenc. Namesto tega stranko **deaktivirajte**:

- Odprite stranko → uredite zapis → odznačite polje **Aktivna**.
- Deaktivirana stranka se ne prikazuje v delovnih pogledih, vsi zgodovinski zapisi pa ostanejo dostopni.

!!! warning "Brisanje stranke"
    Brisanje je možno samo, če stranka nima nobenih povezanih zapisov. V praksi to velja le za testne stranke, dodane med uvajanjem sistema.

---

### Pregled polj stranke

| Polje | Tip | Obvezno | Opomba |
|---|---|---|---|
| Naziv | Besedilo | Da | Uradno ime |
| Naslov | Besedilo | Da | Ulica in hišna št. |
| Mesto | Besedilo | Da | Kraj |
| DDV številka | Besedilo | Da | Davčna št. |
| Šifra po meri | Besedilo | Ne | Interni kode |
| Skrbnik | Uporabnik | Ne | Prejemnik obvestil |
| Aktivna | Da/Ne | — | Privzeto: Da |
| Izključi iz sledenja veljavnosti | Da/Ne | — | Privzeto: Ne |

---

## Poslovne enote

Večje stranke imajo pogosto **več lokacij ali organizacijskih enot**. Poslovne enote v sistemu OP5 omogočajo natančno organizacijo dela po lokacijah — zaposleni in delovna oprema so razporejeni po poslovnih enotah, operacije pa so izvedene na določeni lokaciji.

**Dostop:** Na seznamu strank → kliknite gumb **»Uredi lokacije«** pri želeni stranki.

---

### Sedež kot poslovna enota

!!! important "Sedež je vedno ena izmed poslovnih enot"
    Ob kreiranju stranke sistem samodejno ustvari eno poslovno enoto — **sedež**. Te poslovne enote **ni mogoče izbrisati**. Vse ostale poslovne enote so dodatne lokacije.

---

### Dodajanje poslovne enote

1. Na seznamu strank poiščite stranko.
2. Kliknite **»Uredi lokacije«**.
3. Izberite **»Dodaj novo«** ali **»+«**.
4. Izpolnite obvezno polje **Naziv** (ime poslovne enote / lokacije).
5. Po potrebi dodajte naslov in ostale podatke.
6. Shranite.

### Polja poslovne enote

| Polje | Tip | Obvezno | Opis |
|---|---|---|---|
| Naziv | Besedilo | Da | Ime poslovne enote (npr. »Skladišče Maribor«) |
| Naslov | Besedilo | Ne | Naslov lokacije |
| Mesto | Besedilo | Ne | Kraj lokacije |
| Opomba | Besedilo | Ne | Interni komentar |

---

### Pomen poslovnih enot

Poslovne enote so ključne za:

- **Razporejanje zaposlenih** — vsak zaposleni je dodeljen določeni poslovni enoti.
- **Evidenco opreme** — oprema je vezana na lokacijo poslovne enote.
- **Filtriranje prikazov** — v operativnih pregledih je mogoče filtrirati po posamezni poslovni enoti.
- **Poročila** — analitika in izvozi so lahko segmentirani po poslovnih enotah.

---

## Aktivna stranka

Koncept **aktivne stranke** je eden najpomembnejših elementov vmesnika OP5.

### Kaj je aktivna stranka?

V zgornjem desnem kotu aplikacije se nahaja selector za izbiro **aktivne stranke**. Ko izberete aktivno stranko:

- Vsi **vnosi** so samodejno vezani na to stranko.
- Vsi **seznami** (zaposleni, oprema, dokumenti) so filtrirani samo na zapise te stranke.
- **Uvoz iz Excel** datoteke uvozi podatke v kontekstu aktivne stranke.

### Prikaz brez aktivne stranke

Če aktivna stranka **ni izbrana**, sistem prikazuje zapise vseh strank skupaj. To je primerno za globalne preglede in analitiko, ne pa za operativno delo.

!!! warning "Preverite aktivno stranko pred vnosom"
    Pred vsakim vnosom podatkov (zaposleni, oprema, dokumenti) preverite, da je v zgornjem meniju izbrana **pravilna aktivna stranka**. Napačno dodeljeni zapisi zahtevajo ročni popravek.

!!! tip "Hiter dostop"
    Aktivno stranko lahko kadar koli zamenjate — izberite drugo stranko v selektorju in pogled se takoj osveži.
