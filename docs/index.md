# Optima Prevent — Portal dokumentacije in podpore

<style>
:root{
  --op-primary:#0e3a66;     /* dark blue */
  --op-primary-2:#0a2b4d;   /* darker */
  --op-accent:#1b4f8a;      /* mid blue */
  --op-grey-0:#ffffff;
  --op-grey-1:#f5f7fa;      /* light grey */
  --op-grey-2:#e6e9ef;      /* ui border grey */
  --op-text:#1f2937;        /* neutral text */
}
.op-container{max-width:1100px;margin:0 auto;}
.op-hero{
  background:linear-gradient(180deg,var(--op-primary) 0%,var(--op-primary-2) 100%);
  color:#fff;border-radius:14px;padding:48px 28px;margin:12px 0 28px 0;text-align:center;
}
.op-hero img{height:64px;margin-bottom:12px;filter:none;}
.op-hero h2{margin:8px 0 6px 0;font-weight:700;}
.op-hero p{margin:8px auto 18px auto;max-width:800px;opacity:.95}
.op-cta{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-top:6px}
.op-btn{
  display:inline-block;padding:12px 18px;border-radius:8px;border:1px solid transparent;
  text-decoration:none;font-weight:600
}
.op-btn--primary{background:#ffffff;color:var(--op-primary)}
.op-btn--primary:hover{background:#eef3fb}
.op-btn--secondary{background:transparent;color:#ffffff;border-color:#ffffff}
.op-btn--secondary:hover{background:rgba(255,255,255,.08)}
.op-grid{
  display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:16px;margin:18px 0;
}
.op-card{
  background:var(--op-grey-1);border:1px solid var(--op-grey-2);
  border-radius:10px;padding:18px
}
.op-card h3{margin-top:0;color:var(--op-primary)}
.op-card p{margin:8px 0 12px 0}
.op-list{margin:0;padding-left:18px}
.op-section{margin:28px 0}
.op-section h2{color:var(--op-primary);margin-bottom:8px}
.op-muted{color:#4b5563}
.op-table{border-collapse:collapse;width:100%;background:var(--op-grey-0);border:1px solid var(--op-grey-2);border-radius:10px;overflow:hidden}
.op-table th,.op-table td{padding:10px 12px;border-bottom:1px solid var(--op-grey-2);text-align:left}
.op-kpis{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:12px;margin:14px 0}
.op-kpi{background:var(--op-grey-1);border:1px solid var(--op-grey-2);border-radius:10px;padding:14px}
.op-kpi strong{color:var(--op-primary)}
</style>

<div class="op-container">

<div class="op-hero">
  <img src="media/logos/op-logo.png" alt="Optima Prevent logo">
  <h2>Celovita rešitev za VZD, PV in varstvo okolja</h2>
  <p>Optima Prevent je napredni EHS sistem, prilagojen slovenski zakonodaji in mednarodnim standardom (OHSAS, ISO). Na enem mestu združuje dokumentacijo, procese in analitiko.</p>
  <div class="op-cta">
    <a class="op-btn op-btn--primary" href="#dokumentacija">Odpri dokumentacijo</a>
    <a class="op-btn op-btn--secondary" href="#podpora">Potrebujem podporo</a>
  </div>
</div>

## Dokumentacija

Vsa navodila, vodiči in referenčna vsebina na enem mestu.

<div class="op-grid">
  <div class="op-card">
    <h3>Uvod in pregled</h3>
    <p>Spoznajte glavne koncepte in arhitekturo sistema.</p>
    <ul class="op-list">
      <li><a href="sl/">Začnite tukaj</a></li>
      <li>Ključne funkcionalnosti</li>
      <li>Sistemska arhitektura</li>
    </ul>
  </div>
  <div class="op-card">
    <h3>Namestitev in konfiguracija</h3>
    <p>Tehnična navodila za vzpostavitev okolja in začetno nastavitev.</p>
    <ul class="op-list">
      <li><a href="sl/namestitev/">Navodila za namestitev</a></li>
      <li>Migracija podatkov</li>
      <li>Varnost in dostop</li>
    </ul>
  </div>
  <div class="op-card">
    <h3>Uporabniški priročnik</h3>
    <p>Podrobna navodila za delo z moduli in evidencami.</p>
    <ul class="op-list">
      <li><a href="sl/uporaba/">Priročnik za uporabo</a></li>
      <li>Upravljanje uporabnikov</li>
      <li>Analitika in poročila</li>
    </ul>
  </div>
  <div class="op-card">
    <h3>Celotni priročnik (PDF/DOCX)</h3>
    <p>Polna referenčna dokumentacija za tisk ali offline.</p>
    <ul class="op-list">
      <li><a href="manual-sl.md">Prenesi celotni priročnik</a></li>
      <li><a href="CHANGELOG.md">Dnevnik sprememb</a></li>
    </ul>
  </div>
</div>

## Podpora

Kanal za prijavo napak in predlogov ter hiter kontakt s podporo.

<div class="op-grid" id="podpora">
  <div class="op-card">
    <h3>Prijava napake</h3>
    <p>Opazili ste težavo ali napako v delovanju?</p>
    <p><a class="op-btn op-btn--primary" href="https://github.com/a1info/support/issues/new?template=bug_report.md">Odpri prijavo napake</a></p>
    <p class="op-muted">Za hitrejšo obravnavo priložite korake za ponovitev, posnetek zaslona in verzijo sistema.</p>
  </div>
  <div class="op-card">
    <h3>Predlog funkcionalnosti</h3>
    <p>Manjka vam funkcija ali izboljšava?</p>
    <p><a class="op-btn op-btn--primary" href="https://github.com/a1info/support/issues/new?template=feature_request.md">Predlagaj funkcijo</a></p>
    <p class="op-muted">Navedite poslovni primer, pričakovano vedenje in prednost.</p>
  </div>
  <div class="op-card">
    <h3>Pogosta vprašanja (FAQ)</h3>
    <p>Odgovori na najpogostejša vprašanja in reševanje težav.</p>
    <ul class="op-list">
      <li><a href="sl/podpora/">FAQ in reševanje težav</a></li>
      <li>Kontakt za podporo: <a href="mailto:podpora@a1info.si">podpora@a1info.si</a></li>
    </ul>
  </div>
</div>

## O rešitvi

Kratek pregled aplikacije, prednosti, moduli in sistemske zahteve.

### Kaj je Optima Prevent

Optima Prevent je celovita EHS platforma za varnost in zdravje pri delu (VZD), požarno varnost (PV) in varstvo okolja. Upošteva slovensko zakonodajo in mednarodne standarde (OHSAS, ISO) ter omogoča obvladovanje procesov, dokumentacije in periodike.

### Prednosti

- Prilagoditev slovenski zakonodaji in standardom (OHSAS/ISO)
- Modularna arhitektura in povezani moduli
- EAV model za polja po meri in fleksibilnost podatkov
- Transakcijski SQL, večuporabniški sočasni dostop
- Šifriranje na vseh nivojih (baza, datotečni sistem, prenos)
- Avtomatsko digitalno podpisovanje PDF (P12)
- Analitika in koledarski pregled periodike

### Moduli

Strnjeni nabor modulov za celovito upravljanje:
- Sistemske nastavitve, uporabniki, stranke, poslovne enote
- Zaposleni, usposabljanja (tečaji, zapisniki, e-test)
- Delovna oprema (evidenca, pregledi, zapisniki, QR/ROA)
- Ocene tveganj (TDM, tveganja, OTV dokumenti)
- VZD/EKO meritve (okolje, hrup, elektrika, strelovod …)
- Požarna varnost (evidence, vaje evakuacije)
- Zdravniški pregledi, osebna varovalna oprema, delovne nezgode
- Analitika (periodika, realizacija, izdani dokumenti), CRM

### Sistemske zahteve

<table class="op-table">
  <thead>
    <tr><th>Komponenta</th><th>Zahteva</th></tr>
  </thead>
  <tbody>
    <tr><td>PHP</td><td>8.0 ali novejši</td></tr>
    <tr><td>Framework</td><td>Laravel 9.x (MVC), Livewire, jQuery 2</td></tr>
    <tr><td>Podatkovna baza</td><td>PostgreSQL ali Oracle</td></tr>
    <tr><td>Varnost</td><td>SSL/VPN, šifriranje podatkov, GDPR skladnost</td></tr>
    <tr><td>Brskalnik</td><td>Posodobljeni Chrome/Edge/Firefox; min. 1024×768</td></tr>
  </tbody>
</table>

## Kontakt

<div class="op-grid">
  <div class="op-card">
    <h3>A1 Informatika d.o.o.</h3>
    <p class="op-muted">Slovenija</p>
    <p>E-pošta: <a href="mailto:svetovanje@optima-prevent.eu">svetovanje@optima-prevent.eu</a><br>
       Splet: <a href="https://optima-prevent.eu">optima-prevent.eu</a></p>
  </div>
  <div class="op-card">
    <h3>GitHub</h3>
    <p><a href="https://github.com/a1info/support">Repozitorij OP5</a></p>
    <div class="op-kpis">
      <div class="op-kpi"><strong>Podpora</strong><br><a href="https://github.com/a1info/support/issues/new?template=bug_report.md">Prijava napake</a></div>
      <div class="op-kpi"><strong>Razvoj</strong><br><a href="https://github.com/a1info/support/issues/new?template=feature_request.md">Predlog funkcije</a></div>
    </div>
  </div>
</div>

<hr>

<div class="op-muted" style="text-align:center">
  © 2025 A1 Informatika d.o.o. · Optima Prevent v5.2 · Blagovna znamka registrirana v Avtorski agenciji RS (030/19)
</div>

</div>
