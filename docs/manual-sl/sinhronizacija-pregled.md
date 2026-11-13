# Sinhronizacija – kako deluje

Optima Prevent ima dve ločeni vrsti povezav:

| Povezava | S kom | Namen |
|---|---|---|
| **Partner Sync** | druga namestitev Optima Prevent | izmenjava EHS podatkov z zunanjimi izvajalci |
| **ERP Sync** | Microsoft Dynamics 365 Business Central | prenos ponudb in pogodb v prodajna naročila ter vračanje finančnih referenc |

Povezavi uporabljata skupno varno jedro za sporočila, ponovne poskuse in
revizijsko sled, vendar ostaneta poslovno ločeni. ERP sinhronizacija ne pošilja
zdravstvenih podatkov, Partner Sync pa ne ustvarja finančnih dokumentov.

---

## Partner Sync

Partner Sync povezuje dve namestitvi Optima Prevent. Uporablja se, ko za vaše
stranke delo izvaja zunanji izvajalec – na primer usposabljanja, preglede
delovne opreme ali EKO meritve.

- **Stranke se ne sinhronizirajo.** Obe strani morata imeti isto stranko
  vneseno po enaki davčni številki.
- **Dodelitve** določijo, kateri partner lahko za katero stranko prejema in
  pošilja posamezno storitev.
- Matični podatki potujejo od lastnika podatkov k partnerju; opravljeno delo
  potuje nazaj.
- Vsaka zahteva je podpisana s HMAC-SHA256.
- Zgodovinska sinhronizacija prenese obstoječe zapise ob prvi povezavi.

Podrobnosti: [Partner Sync](sinhronizacija.md).

---

## ERP Sync

ERP Sync povezuje Optimo z Business Central. Optima ostaja vir EHS operacije,
Business Central pa vir financ in izdanih računov.

- **Ponudbe in pogodbe:** sprejeta ponudba ali aktivna pogodba se pretvori v
  prodajno naročilo.
- **Stranke in storitve:** pred prvim prenosom jih je treba povezati v
  pregledu povezav. Sistem predlaga povezave, vendar jih ne potrdi sam.
- **Računi:** ERP Sync ne izdaja računov; prebere referenco in status iz
  Business Central.
- **Varna uvedba:** produkcijsko pošiljanje je privzeto izklopljeno in se
  vklopi šele po uspešnem sandbox testu.
- **Nadzor:** čakalna vrsta, napake, izvajanja in ponovno pošiljanje so na
  strani ERP nadzor.

Podrobnosti: [ERP Sync z Business Central](erp-sinhronizacija.md).

---

## Kaj potrebujete pred uvedbo

1. Dogovorjen obseg podatkov in odgovorne osebe.
2. Za Partner Sync: definirana partnerja in dodelitve na obeh straneh.
3. Za ERP Sync: Business Central sandbox, Azure aplikacijo in potrjene
   številke strank ter artiklov.
4. Pregled povezav strank in storitev.
5. Uspešen test enega dokumenta ter ponovitve.
6. Potrditev računovodstva in odgovornih oseb za produkcijo.

Do zaključka testov uporabljajte sandbox oziroma testne podatke.
