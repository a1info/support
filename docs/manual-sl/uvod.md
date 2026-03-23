# Uvod

Optima Prevent je EHS (Environmental Health and Safety) sistem, prilagojen zakonodaji Republike Slovenije. Upošteva aktualne mednarodne standarde in napotke (OHSAS, ISO). Namenjen je organizacijam in službam, ki se ukvarjajo z varnostjo in zdravjem pri delu, za celovito in enostavno vodenje dela ter popoln nadzor nad kompleksom procesov.

Modularna arhitektura in večplastni dizajn omogočata visoko raven prilagodljivosti za vse vrste organizacij, ne glede na velikost ali dejavnost. Aplikacija je sestavljena iz medsebojno povezanih modulov, zato so vse spremembe takoj vidne tam, kjer so relevantne.

Tehnologija EAV (Entity-Attribute-Value) omogoča dodajanje atributov po meri, kar zagotavlja fleksibilnost pri vnosu in prikazu podatkov.

Klient/strežnik arhitektura s transakcijsko SQL komunikacijo in vgrajenim mehanizmom za nadzor sočasnosti (Optimistic Locking) omogoča istočasni dostop vseh uporabnikov brez tveganja izgube ali neželenega prepisa podatkov pri sočasnem urejanju.

Razvojne tehnologije: PHP 8, MVC (Model-View-Controller) — Laravel 12.x, z Livewire/Alpine na uporabniškem vmesniku. Podatkovni sloj podpira PostgreSQL in Oracle.

Vsi sloji dostopa do podatkov so šifrirani: SQL baza, datotečni sistem, omrežni prenos (SSL/VPN). Za GDPR skladnost se sejni piškotki hranijo v šifrirani SQL bazi. Obravnava osebnih podatkov je skladna z GDPR in dokumentirana v priloženi dokumentaciji Optima Prevent.

Optima Prevent je blagovna znamka podjetja A1 Informatika d.o.o. in je registrirana pri Avtorski agenciji RS pod številko 030/19.

- **Verzija**: 5
- **Licenca**: a1-tech v2 @lic
