# 📋 Awesome Copilot + Kontrol DB Planning

**Sesija:** 2026-04-21
**Status:** 🔄 U toku
**Izvor:** nova sesija

---

## Odluke

| # | Stavka | Odluka | Detalji |
|---|--------|--------|---------|
| 1 | Pristup za novu strukturu baze | ✅ Odobreno | Architect-first: prvo dizajn/rizici, pa implementacija kroz sprintove |
| 2 | Paket za start | ✅ Odobreno | Pripremiti i Architect prompt paket i DB migration blueprint |
| 3 | Fokus skillova | ✅ Odobreno | EF Core modeliranje i migracije + PostgreSQL schema/review + planiranje/rollout |
| 4 | Traženi ishod sesije | ✅ Odobreno | Napraviti veliki plan + setup vodič za skillove/agente + priprema za Worker izvršenje |
| 5 | Handoff status | 🔄 Treba još diskusije | Sačekati sa predajom, plan ide na dodatne izmene pre Worker starta |
| 6 | Tehnički model promene baze | ✅ Odobreno | Clean-slate reset: postojeća baza se briše i radi se nova struktura od nule |
| 7 | Strategija punjenja podataka | ✅ Odobreno | Primarno scraper punjenje gde je moguće, uz seed skripte za obavezne sistemske podatke |
| 8 | Scraper fallback strategija | ✅ Odobreno | Seed + manual import lista za entitete koje scraper ne može pouzdano da popuni |
| 9 | Scope ove sesije | ✅ Odobreno | Samo setup agenata i skillova; poseban migracioni plan ide u narednoj sesiji |
| 10 | Setup handoff | ✅ Odobreno | Pripremiti finalni handoff paket koji Mane direktno prosleđuje Worker-u |
| 11 | Lokacija tim planova ubuduće | ✅ Odobreno | Svi planovi idu u .github/todos da Mane može jednostavno da syncuje preko git-a |

---

## Plan (final draft)

### 0) Cilj
- Završiti setup agenata i skillova za rad na Kontrol bazi.
- Pripremiti Mane + Worker izvršni tok za setup verifikaciju.
- Odvojiti migracioni plan u posebnu sledeću sesiju kada setup bude potvrđen.

### 1) Setup skillova i agenata (isti dan)

#### 1.1 Preuslovi
- GitHub Copilot + GitHub Copilot Chat aktivni u VS Code.
- Copilot CLI instaliran.

#### 1.2 Marketplace i plugin install
1. Provera marketplace-a:
copilot plugin marketplace add github/awesome-copilot
2. Install ciljane grupe pluginova/skillova (preko awesome-copilot kataloga):
copilot plugin install <plugin-name>@awesome-copilot

#### 1.3 Minimalni skill stack za DB redesign
1. Ef Core
2. Postgresql Code Review
3. Sql Code Review
4. Create Implementation Plan
5. Devops Rollout Plan

#### 1.4 Uloge agenata
1. Architect:
- radi analizu postojećeg modela
- predlaže target schema i migracionu strategiju
- mapira rizike i rollback tačke
2. Worker:
- implementira sprint taskove redom
- radi male inkremente i validacije posle svakog koraka

### 2) Setup-only operativni plan (za tebe + Mane + Worker)

#### Sprint S1 — Alati i pristupi (P0)
- [ ] S1.1 Provera Copilot preuslova (Copilot + Chat + CLI)
- [ ] S1.2 Registracija awesome-copilot marketplace-a
- [ ] S1.3 Dogovor oko liste pluginova/skillova za instalaciju
- [ ] S1.4 Definisanje ko šta radi: ti, Mane, Worker, Reviewer
- Deliverable: Setup readiness checklist

#### Sprint S2 — Install i aktivacija (P0)
- [ ] S2.1 Instalacija prioritetnih skillova (EF Core, PostgreSQL review, SQL review, planning)
- [ ] S2.2 Provera da su skillovi dostupni u sesiji
- [ ] S2.3 Test poziv Architect prompta nad malim read-only zadatkom
- [ ] S2.4 Test poziv Worker toka na mini tasku bez menjanja baze
- Deliverable: potvrđen agent+skill setup

#### Sprint S3 — Validacija workflow-a (P0)
- [ ] S3.1 Simulacija punog toka: Architect -> Worker -> Reviewer
- [ ] S3.2 Check da su izlazi konzistentni sa Kontrol pravilima
- [ ] S3.3 Lista korekcija u promptovima/instrukcijama
- [ ] S3.4 Finalna potvrda da je tim spreman za migracioni planning
- Deliverable: Workflow validation report

#### Sprint S4 — Handoff za narednu sesiju (P1)
- [ ] S4.1 Zaključavanje setup artefakata (koji skillovi, koji agent tok)
- [ ] S4.2 Priprema ulaza za posebni migracioni plan
- [ ] S4.3 Definisanje tačnog obima migracione sesije (bez implementacije)
- Deliverable: Migration planning kickoff paket

### 3) Prompt paket za setup verifikaciju (copy-ready)

#### Prompt A — Setup audit
Proveri da li su svi potrebni agenti i skillovi dostupni za Kontrol DB redesign workflow. Vrati šta je OK, šta nedostaje i prioritet korekcija.

#### Prompt B — Dry-run workflow
Simuliraj Architect -> Worker -> Reviewer tok na read-only zadatku i pokaži gde može da zapne pre realnog rada na bazi.

#### Prompt C — Skill coverage
Mapiraj izabrane skillove na konkretne korake budućeg DB projekta i označi praznine koje treba dopuniti.

#### Prompt D — Ready gate
Napravi go/no-go checklistu za start sledeće sesije u kojoj se pravi poseban migracioni plan.

### 4) Worker execution pravila za Mane
1. Worker radi samo setup sprintove S1-S4.
2. Nema rada na migraciji baze u ovoj sesiji.
3. Posle svakog setup koraka obavezna je kratka validacija (radi/ne radi).
4. Ako setup test padne, prvo se ispravlja setup; ne ide se dalje.
5. Reviewer approval je obavezan pre otvaranja posebne migracione sesije.

### 5) Definition of Done
1. Potrebni agenti i skillovi su instalirani i provereni.
2. Architect -> Worker -> Reviewer tok je testiran na dry-run primeru.
3. Postoji jasno mapiran setup za budući DB projekat.
4. Migration planning kickoff paket je spreman.
5. Migracioni plan nije još izvršavan u ovoj sesiji (svesno odloženo).

### 6) Handoff paket za Mane
- Plan fajl ove sesije
- Sprint backlog (S1-S4)
- Setup prompt paket (A-D)
- Pravila izvršenja Worker + Reviewer gate
- Napomena: migracioni plan ide u posebnoj sledećoj sesiji
