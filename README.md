# Catedra

Aplicație pentru profesori: orarul zilei, catalog (note și absențe), structura anului școlar 2026–2027 și calendar cu practică, simulări, examene, concursuri, olimpiade, ședințe și zile libere.

Funcționează pe iPhone (instalată pe ecranul principal) și pe PC (în browser). Datele se sincronizează printr-un depozit privat GitHub, ca la Bifa.

© Paul Chirilă · cod scris împreună cu Claude

---

## 1. Publicarea aplicației (GitHub Pages)

1. Se creează pe GitHub un depozit **public** numit `catedra`.
2. Se încarcă în el toate fișierele din arhivă: `index.html`, `manifest.webmanifest`, `sw.js` și folderul `icons`.
3. În depozit: **Settings → Pages → Branch: main → / (root) → Save**.
4. După un minut, aplicația este disponibilă la `https://UTILIZATOR.github.io/catedra/`.

## 2. Depozitul de date (privat)

1. Se creează un depozit **privat** numit `catedra-date` (poate fi gol).
2. Se creează o cheie de acces: **Settings (cont) → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**
   - Repository access: *Only select repositories* → `catedra-date`
   - Permissions → Repository permissions → **Contents: Read and write**
3. Se copiază cheia (începe cu `github_pat_`).

## 3. Conectarea dispozitivelor

În aplicație: **Mai mult → Sincronizare → GitHub**
- Utilizator GitHub: numele contului
- Depozit privat: `catedra-date`
- Fișier: `catedra.json` (implicit)
- Cheie de acces: cheia de la pasul 2

Se repetă pe fiecare dispozitiv (iPhone, PC, Mac), cu aceeași cheie.

Sincronizarea are loc automat la deschidere, la revenirea în aplicație și la câteva secunde după fiecare modificare. Modificările făcute pe dispozitive diferite se combină element cu element, deci nu se pierd.

## 4. Instalarea pe iPhone

Safari → adresa aplicației → butonul **Partajare** → **Adaugă pe ecranul principal**.

---

## Ce conține

- **Azi**: ora în curs, cu numărătoare inversă până la pauză, butoanele Prezența și Notă rapidă, săptămâna de cursuri, zilele până la vacanță, programul zilei, evenimentele următoare
- **Calendar**: luna, cu vacanțele și zilele libere marcate, evenimentele colorate pe tipuri, filtre, detaliile zilei selectate
- **Catalog**: clase, filtrare pe module sau pe tot anul, media clasei, note (atingerea unei note o salvează), absențe motivate/nemotivate, prezența pe oră
- **Plus / minus** (în Catalog, pe fiecare disciplină): butoane − și + direct în lista clasei. La 3 plusuri sau 3 minusuri nefolosite, fișa elevului oferă trecerea unei note, iar cele 3 semne sunt marcate ca folosite. Dacă nota se șterge, semnele redevin active
- **Diriginție** (din Mai mult pe telefon, din meniul lateral pe PC):
  - **Adeverințe și cereri**: elevul, tipul, perioada acoperită (cu numărul de zile de curs calculat automat), data primirii, poze sau PDF atașate din telefon și bifa „motivată în catalogul electronic”. Lista „De motivat” arată ce nu a fost încă trecut, iar ecranul Azi amintește de documentele rămase
  - **Absențe importate din catalogul electronic**: tabelul se lipește de pe site sau se încarcă un fișier Excel/CSV, iar coloanele se recunosc automat și se pot corecta. Numele elevilor se potrivesc chiar dacă diferă ordinea, diacriticele sau inițiala tatălui. Fiecare import îl înlocuiește pe cel anterior. Evidența e orientativă
  - Nota la purtare **estimată** din absențele nemotivate importate (prag setabil, implicit 1 punct la 10) sau stabilită manual, ședințele cu părinții, observații pe elev
  - Pozele se micșorează automat și se salvează pe telefon. Cu sincronizarea pornită, se urcă în depozitul privat, în folderul `files/`, separat de fișierul de date
- **Orar**: pe zile (telefon) sau tabel săptămânal (PC); orele de început se calculează din setările clopoțelului
- **Mai mult**: Diriginție, profil, clase (cu lista de elevi lipită dintr-un catalog sau din Excel), an școlar editabil, vacanța mobilă (alegerea modifică automat Modulele 3 și 4), ore și pauze, temă întunecată/luminoasă, culoare de accent, copie de siguranță

## Note

- Structura anului 2026–2027 este cea oficială (Ordinul nr. 3194/2026). Vacanța mobilă diferă de la un județ la altul: săptămâna corectă se alege din **Mai mult → An școlar**.
- Clasele marcate ca **terminale** (a XII-a) nu mai apar în orar după 4 iunie 2027.
- Cheia de acces rămâne doar pe dispozitiv; nu ajunge în fișierul de date.
- Catalogul conține date personale ale elevilor; depozitul de date trebuie să rămână **privat**.
- Pentru a vedea aplicația completată, se poate folosi **Mai mult → Încarcă date de exemplu** (înlocuiește datele existente).
