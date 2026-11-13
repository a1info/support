# API integracije

!!! warning "Mobilni REST API je umaknjen"
    Nekdanji javni mobilni API na poti `/api/mobile/v1` je bil odstranjen. Mobilna aplikacija Optima Prevent je zdaj PWA in uporablja isto sejo in poslovno logiko kot spletni vmesnik, zato ločen mobilni REST API ni potreben.

    Vsi mobilni endpointi iz prejšnjih različic – prijava, QR dostop, kontrole opreme, gasilni aparati, HRM in e-testi – **niso več na voljo**.

## Kaj uporabiti

- **Mobilna aplikacija:** namestite jo iz brskalnika in uporabite vmesnik `/mobile`. Glejte [navodila za mobilno aplikacijo](manual-mobile-sl.md).
- **Pregled obeh vrst povezav:** [Sinhronizacija – kako deluje](manual-sl/sinhronizacija-pregled.md).
- **Povezovanje med namestitvami Optima Prevent:** uporabite [Partner Sync](manual-sl/sinhronizacija.md).
- **Povezava z Business Central:** glejte [ERP Sync](manual-sl/erp-sinhronizacija.md).
- **Izmenjava napotnic in izvidov z izvajalcem medicine dela:** glejte [Medic Exchange](manual-sl/medic-exchange.md).
- **Druge integracije:** obrnite se na podporo Optima Prevent za dogovor o načinu povezave.

!!! note "Zakaj je API umaknjen?"
    PWA uporablja neposredno spletno aplikacijo in obstoječe seje, zato vzdrževanje ločenega mobilnega API-ja ni potrebno. S tem se zmanjša število vmesnikov, ki jih je treba vzdrževati in varovati.
