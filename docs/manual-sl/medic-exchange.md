# Medic Exchange – povezava z izvajalcem medicine dela

**Dostop:**

- centralna namestitev: neposredna pot `/mod-partner/medic-exchange`
  (povezava ni v glavnem stranskem meniju)
- samostojna namestitev medicine dela: **Medicina dela → Povezava z Medic
  Exchange** (`/mod-medic/sync`, samo administrator ustanove)

Medic Exchange je namenjen izmenjavi **napotnic in celotnih izvidov** med
delodajalcem in izvajalcem medicine dela. To ni Partner Sync in ni ERP
sinhronizacija.

!!! note "Samostojna namestitev ustanove"
    Po nastavitvi baze in `OP_MEDIC_STANDALONE=true` administrator zažene
    `php artisan medic:install`. Ukaz ustvari ustanovo, prvega zdravnika in
    administratorski račun ter izpiše UUID ustanove. Ročno vstavljanje v
    `medic_institution`, `medic_doctor` in `usermedic` ni potrebno.

## Kaj se prenaša

| Smer | Vsebina |
|---|---|
| Delodajalec → ustanova | napotnica: stranka, zaposleni, vrsta pregleda, datum, podatki o delovnem mestu in tveganjih |
| Ustanova → delodajalec | celoten izvid: datum pregleda in veljavnosti, ocena, omejitve, ukrepi, spričevalo, očesni podatki, prisotnost |

Priloge se za zdaj ne prenašajo. Preklic napotnice in status »ni prišel« se ne
pošiljata kot ločen dogodek; prisotnost je del izvida.

Prosta mesta terminov bodo na voljo v naslednji fazi. Trenutno Medic Exchange
prenaša napotnice in izvide, ne pa še prostih terminov.

## Povezava

Na obeh straneh je treba ustvariti povezavo z **enakima API ključem in API
skrivnostjo**.

1. Odprite stran Medic Exchange.
2. Kliknite **Nova povezava**.
3. Vnesite naziv, okolje in osnovni URL nasprotne namestitve.
4. Vnesite **UUID ustanove** (`medic_institution.uuid`). Ta mora biti na obeh
   straneh enak.
5. Vnesite API ključ in skrivnost.
6. Shranite in kliknite **Preveri povezavo**.

Osnovni URL je koren namestitve, na primer `https://medic.example.si`. Sistema
sam doda pot `/api/medic/v1/...`. Za produkcijo mora biti URL HTTPS.

API skrivnost se shrani šifrirano in se pozneje ne prikaže. Če polje pustite
prazno, obstoječa skrivnost ostane nespremenjena. Ob zamenjavi ključa je treba
novo vrednost vnesti na obeh straneh.

## Stranke v izmenjavi

Povezava velja samo za **dodeljene stranke**. Na obeh straneh v razdelku
**Stranke v izmenjavi** dodajte iste stranke.

- Stranka se na nasprotni strani poišče po UUID, pri prejemu pa je možen tudi
  rezervni način po davčni številki.
- Zaposleni se poišče po UUID in mora pripadati isti stranki.
- Če stranka ali zaposleni na nasprotni strani ne obstajata, bo prejem zavrnjen.

## Vloge

- **Centralna namestitev** ima lahko več povezav, po eno za vsako ustanovo.
- **Samostojna ustanova** ima lahko več povezav, po eno za vsakega delodajalca.
- Ena ustanova se lahko poveže z več delodajalci; vsaka kombinacija ima svojo
  povezavo in svoje ključe.

## Varnost in produkcija

- Uporabljajte HTTPS in omejite dostop do API-ja na znane naslove, če je mogoče.
- Urnika na obeh straneh morata biti približno usklajena; podpis velja pet minut.
- Povezava v produkciji se pošilja šele, ko je v nastavitvah povezave vključeno
  **Dovoli produkcijsko pošiljanje**.
- Pred produkcijo je treba urediti pravno podlago oziroma pogodbo o obdelavi
  osebnih podatkov.
- V peskovniku ne uporabljajte resničnih podatkov pacientov.

## Odpravljanje težav

| Težava | Preverite |
|---|---|
| `401 Unauthorized` | ali sta ključ in skrivnost enaka na obeh straneh, ali je povezava aktivna, ali je ura pravilna |
| `403` | ali je stranka dodeljena povezavi in ali napotnica pripada isti ustanovi |
| `409` | ali na nasprotni strani obstajata stranka in zaposleni z enakim UUID, ali je termin še prost |
| Povezava je aktivna, a se ne pošilja | okolje, `Dovoli produkcijsko pošiljanje`, urnik in dnevnik `sync` |
| Sporočilo je ostalo v čakalni vrsti | zaženite `php artisan medic:publish-outbox` in preverite `integration_outbox` |

Za diagnozo administrator preveri `integration_outbox`, `integration_inbox`,
`integration_runs` in `integration_errors`. Ne urejajte vsebine sporočil ročno;
popravite izvorni zapis in počakajte na novo sporočilo. Neuspešno sporočilo
lahko po odpravi vzroka znova sprožite z
`php artisan medic:replay-outbox <id-sporočila>`.

## Povezani dokumenti

- [Sinhronizacija med namestitvami](sinhronizacija.md)
- [ERP – Sinhronizacija z Business Central](erp-sinhronizacija.md)
- [Portal za zdravnike](portal-za-zdravnike.md)
