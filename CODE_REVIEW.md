# Code Review – Observații și backlog recomandat

## Ce este bun în proiect
- Designul este consistent între pagini (aceeași tipografie, paletă cromatică și componente vizuale reutilizate).
- Structura paginilor este clară și ușor de urmărit (hero, conținut principal, footer).
- Navigația principală este simplă și predictibilă pentru utilizator.
- Copy-ul comercial este bine orientat către beneficii și public țintă.

## Ce ar trebui îmbunătățit (pe scurt)
- Corectitudinea structurală HTML (există markup invalid în `services.html`).
- Consistența conținutului între pagini (branding și mesaje de footer diferite).
- Claritatea comentariilor din cod (unele comentarii nu mai reflectă realitatea din fișier).
- Introducerea unor verificări automate minime pentru a preveni regresii de structură/conținut.

## Sarcini propuse

### 1) Sarcină pentru corectarea unei greșeli de scriere
**Titlu:** Standardizează termenul „SaaS” în toate textele publice.

**Context:** În `services.html`, cardul de pachet folosește forma „SAAS”, deși forma standard uzuală este „SaaS”.

**Acțiuni:**
- Înlocuiește „SAAS” cu „SaaS” în heading-uri, texte și eventuale etichete similare.
- Rulează o căutare în toate fișierele HTML pentru variantele inconsistente ale termenului.

**Criterii de acceptanță:**
- Nu mai există apariții „SAAS” în paginile site-ului.
- Toate aparițiile sunt „SaaS”, cu capitalizare consecventă.

---

### 2) Sarcină pentru corectarea unei erori
**Titlu:** Repară structura HTML invalidă din secțiunea pachetelor (`services.html`).

**Context:** În `services.html`, secțiunea „Service Packages” este deschisă, apoi este introdusă o a doua secțiune „Infrastructure Costs”, dar secțiunea externă nu este închisă explicit înainte de footer.

**Acțiuni:**
- Închide corect secțiunea „Service Packages” înainte de a începe secțiunea următoare sau restructurează ierarhia secțiunilor fără imbricare incorectă.
- Verifică validitatea HTML după modificare.

**Criterii de acceptanță:**
- Structura paginii trece validarea HTML (fără tag-uri de secțiune neînchise/imbricate greșit).
- Footer-ul este în afara secțiunilor de conținut.

---

### 3) Sarcină pentru corectarea unui comentariu sau a unei discrepanțe de documentație
**Titlu:** Corectează comentariul „NAV (IDENTIC)” și aliniază descrierea cu implementarea reală.

**Context:** În `contact.html`, comentariul „NAV (IDENTIC)” sugerează că navbar-ul este identic cu celelalte pagini, dar stilurile active și butonul de contact diferă între pagini.

**Acțiuni:**
- Actualizează comentariul la un text factual (ex: „NAV”).
- Opțional, adaugă o convenție documentată despre cum se marchează linkul activ în navbar pentru consistență.

**Criterii de acceptanță:**
- Comentariul nu mai induce în eroare.
- Există consistență între comentariu și implementarea actuală.

---

### 4) Sarcină pentru îmbunătățirea unui test
**Titlu:** Adaugă un test automat de validare HTML + verificări de consistență UI.

**Context:** Proiectul nu are verificări automate; erori de structură (ex. tag-uri neînchise) pot ajunge ușor în producție.

**Acțiuni:**
- Adaugă un script de verificare (ex: `htmlhint` sau validator similar) pentru `index.html`, `services.html`, `projects.html`, `contact.html`.
- Adaugă un test simplu (Playwright sau script Node) care verifică existența navbar-ului și a footer-ului pe toate paginile.
- Rulează testele în pipeline CI la fiecare push.

**Criterii de acceptanță:**
- Build-ul eșuează dacă HTML-ul este invalid.
- Build-ul eșuează dacă lipsește navbar-ul sau footer-ul pe una dintre pagini.
- Există instrucțiuni clare în README pentru rularea testelor local.

## Ce altceva poți adăuga (next level)

### 1) Pagina „About / Process”
- O pagină scurtă cu metodologia ta: Discovery → Design logică business → Implementare → Testare → Deploy.
- Ajută clienții să înțeleagă **cum lucrezi**, nu doar ce livrezi.

### 2) Studii de caz pe proiecte
- Pentru fiecare proiect: problemă inițială, soluție, stack, rezultat măsurabil.
- Include 2-3 KPI simpli (ex: timp economisit, reducere erori, conversie).

### 3) Testimoniale + proof points
- Secțiune cu recenzii, logo-uri clienți, capturi dashboard (anonimizate).
- Crește încrederea și reduce fricțiunea în etapa de contact.

### 4) CTA-uri mai puternice
- Buton „Book a 30-min discovery call”.
- Formular scurt de calificare (tip proiect, buget, deadline, industrie).

### 5) SEO de bază
- Meta description unică pe fiecare pagină.
- Open Graph / Twitter cards pentru share.
- Date structurate `Person`/`ProfessionalService`.

### 6) Performanță
- Optimizează `hero.jpeg` (WebP/AVIF + variantă responsive).
- Adaugă `loading="lazy"` pentru imagini non-critice.

### 7) i18n RO/EN
- Variantă bilingvă (română + engleză), utilă pentru clienți locali și externi.
- Poți începe simplu: două versiuni statice ale paginilor.

### 8) Mini blog tehnic (opțional)
- 3-5 articole scurte: automatizare procese, arhitectură Django, QA/BDD.
- Te poziționează ca expert și aduce trafic organic.
