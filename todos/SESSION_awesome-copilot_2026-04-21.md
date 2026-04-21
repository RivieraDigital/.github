# 📋 Awesome Copilot + Kontrol DB Planning

**Sesija:** 2026-04-21
**Status:** ✅ Setup spreman (S1.4 odloženo)
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

## Veliki Plan (Master + Runbook)

### 0) Scope i granice
- Ova sesija radi samo setup sprintove S1-S4.
- Nema implementacije migracija, nema izmena baze, nema DB reset koraka.
- Fokus je: instalacija, aktivacija, validacija workflow-a i handoff priprema.

### 1) Target ishod sesije
1. Potrebni skillovi/agenti su dostupni i provereni.
2. Architect -> Worker dry-run je potvrđen na read-only mini zadatku.
3. Spreman kickoff paket za posebnu migracionu sesiju.
4. Reviewer approval zabeležen na samom kraju setup faze.

### 2) Master Plan po sprintovima

#### Sprint S1 — Readiness i odluke (P0)
- [x] S1.1 Provera Copilot preuslova (Copilot + Chat + CLI) ✅ (21.04. — CLI potvrđen, bez daljih code CLI provera)
- [x] S1.2 Registracija awesome-copilot marketplace-a ✅ (21.04. — awesome-copilot potvrđen kao default marketplace)
- [x] S1.3 Finalna lista setup skillova ✅ (21.04. — EF Core, PostgreSQL Code Review, SQL Code Review, Create Implementation Plan, DevOps Rollout Plan)
- [ ] S1.4 Raspodela uloga (odloženo) ⚠️ (21.04. — biće odlučeno kasnije)
- Deliverable: Setup readiness checklist + potvrđen scope

#### Sprint S2 — Install i aktivacija skillova (P0)
- [x] S2.1 Instalacija prioritetnih skillova ✅ (21.04. — 5/5 pluginova instalirano)
- [x] S2.2 Provera dostupnosti skillova u sesiji ✅ (21.04. — finalno 4 plugina aktivna; mapiranje pokrivenosti potvrđeno)
- [x] S2.3 Test Architect prompta na read-only mini zadatku ✅ (21.04. — dry-run analiza uspešna, bez izmena fajlova)
- [x] S2.4 Test Worker mini toka bez izmene baze ✅ (21.04. — dry-run uspešan; prvi unchecked task detektovan i plan vraćen)
- Deliverable: Potvrđen agent+skill setup

#### Sprint S3 — Validacija workflow-a (P0)
- [x] S3.1 Simulacija punog toka Architect -> Worker (bez Reviewer faze) ✅ (21.04. — read-only dry-run uspešno potvrđen)
- [x] S3.2 Provera usklađenosti izlaza sa Kontrol pravilima ✅ (21.04. — pass, bez kršenja setup-only pravila)
- [x] S3.3 Lista korekcija promptova/instrukcija ✅ (21.04. — korekcije definisane i upisane)
- [x] S3.4 Finalni ready-gate za migracioni planning (interni, bez Reviewer approval-a) ✅ (21.04. — GO)
- Deliverable: Workflow validation report

#### Sprint S4 — Kickoff paket za sledeću sesiju (P1)
- [x] S4.1 Zaključavanje setup artefakata (skill set + agent tok) ✅ (21.04. — finalni artefakti zaključani)
- [x] S4.2 Priprema ulaza za posebni migracioni plan ✅ (21.04. — ulazni paket definisan)
- [x] S4.3 Definisanje tačnog obima migracione sesije (bez implementacije) ✅ (21.04. — scope zaključan)
- Deliverable: Migration planning kickoff paket

### 3) Operativni Runbook (izvršenje korak po korak)

#### R1. S2 install tok
1. Update marketplace kataloga.
2. Browse awesome-copilot i mapiranje tačnih plugin identifikatora za 5 potvrđenih skill oblasti.
3. Install svakog plugin-a pojedinačno.
4. Posle svakog install koraka prijava: radi/ne radi.
5. Ako instalacija padne: retry jednom; ako i dalje pada, fallback na najbliži skill i beleženje gap-a.

#### R2. S2 aktivacija tok
1. List installed plugins.
2. Potvrda da su skillovi vidljivi/pozivi dostupni u sesiji.
3. Read-only mini test za Architect prompt.
4. Read-only mini test za Worker tok.
5. Evidencija izlaza i status po testu: radi/ne radi.

#### R3. S3 validacija workflow-a
1. Pokretanje simulacije punog toka Architect -> Worker (bez Reviewer faze).
2. Upoređivanje izlaza sa Kontrol pravilima (manual CQRS, bez DB implementacije, setup-only scope).
3. Evidentiranje odstupanja i predlog korekcija promptova.
4. Re-test nakon korekcija (ako potrebno).
5. Interni go/no-go zaključak i priprema za završni Reviewer gate u S4.

#### R4. S4 handoff paket
1. Finalna lista skillova i njihovih namena.
2. Finalni agent tok i checkpoint pravila.
3. Risk lista za sledeću migracionu sesiju.
4. Jasno odvojen scope: sledeća sesija planira migraciju, ne izvršava je.

### 4) Kontrolne tačke i quality gate
1. Posle svakog koraka mora status: radi/ne radi.
2. Ako nešto padne, prvo se popravlja setup pa se nastavlja dalje.
3. Bez prelaska u sledeći sprint dok current sprint nema minimalni deliverable.
4. Reviewer approval je obavezan samo na kraju setup faze (posle S4).

### 5) Prompt paket za setup verifikaciju

#### Prompt A — Setup audit
Proveri da li su svi potrebni agenti i skillovi dostupni za Kontrol DB redesign workflow. Vrati sta je OK, sta nedostaje i prioritet korekcija.

#### Prompt B — Dry-run workflow
Simuliraj Architect -> Worker tok na read-only zadatku i pokazi gde moze da zapne pre realnog rada na bazi.

#### Prompt C — Skill coverage
Mapiraj izabrane skillove na konkretne korake buduceg DB projekta i oznaci praznine koje treba dopuniti.

#### Prompt D — Ready gate
Napravi go/no-go checklistu za start sledece sesije u kojoj se pravi poseban migracioni plan.

### 5.1 Korekcije promptova/instrukcija (S3.3)
1. U svim setup promptovima eksplicitno navesti: read-only, bez izmene fajlova i bez DB migracija.
2. Ukloniti Reviewer iz S3 simulacija; koristiti Architect -> Worker tok, Reviewer samo finalni gate.
3. Za plugin install promptove obavezno koristiti format `<plugin-id>@awesome-copilot`.
4. Zabraniti `code` CLI provere u ovoj sesiji; koristiti samo `gh copilot` i terminal output verifikaciju.
5. U svakom promptu tražiti jasan izlaz: `radi/ne radi` + kratko obrazloženje.

### 6) Rizici i fallback
1. Plugin nije dostupan: koristi najblizi skill i evidentiraj gap.
2. Verzijski problem CLI alata: uradi update, pa re-test.
3. Nejasna raspodela uloga: ostavi S1.4 otvoren i ne blokiraj S2-S4 setup validaciju.
4. Dry-run neuspeh: korekcija prompta/instrukcija pa ponovni dry-run.

### 7) Exit criteria (setup sesije)
1. Potrebni skillovi/agenti dostupni i provereni.
2. Architect -> Worker dry-run uspešno potvrđen.
3. Kickoff paket za posebnu migracionu sesiju spreman.
4. Reviewer approval potvrđen na završnom gate-u.

### 8) Handoff sadržaj za narednu sesiju
1. Ovaj plan fajl sa statusima S1-S4.
2. Potvrđena lista skillova + eventualni gap-ovi.
3. Validiran workflow i korekcije promptova.
4. Kickoff ulaz za migracioni planning (bez implementacije).

### 8.1 Zaključani setup artefakti (S4.1)
1. Finalni aktivni plugin set:
	- database-data-management@awesome-copilot
	- openapi-to-application-csharp-dotnet@awesome-copilot
	- project-planning@awesome-copilot
	- devops-oncall@awesome-copilot
2. Finalni setup tok u ovoj sesiji:
	- Architect -> Worker (read-only) za S3 validacije
	- Reviewer uključenje tek na završnom gate-u posle S4
3. Zabranjeno u setup sesiji:
	- DB migracije
	- izmene baze
	- code/file izmene van plana

### 8.2 Ulaz za posebnu migracionu sesiju (S4.2)
1. Potvrđeni setup preuslovi:
	- Copilot CLI aktivan
	- awesome-copilot marketplace aktivan
	- finalni plugin set instaliran
2. Potvrđeni workflow preuslovi:
	- Architect -> Worker dry-run validiran
	- prompt korekcije primenjene (sekcija 5.1)
3. Obavezni input dokument za narednu sesiju:
	- ovaj fajl kao baseline status + pravila
4. Obavezna ulazna pitanja za migracioni planning:
	- ciljna schema granice po modulima
	- data migration policy (scraper/seed/manual)
	- rollback strategija
	- redosled sprintova za implementaciju

### 8.3 Tačan obim migracione sesije (S4.3)
1. U scope ulazi:
	- izrada migracionog plana po sprintovima
	- target schema dizajn i dependency mapa
	- migraciona strategija (redosled, rizici, rollback)
	- test/validacioni kriterijumi za implementaciju
2. Van scope-a (strogo zabranjeno):
	- pokretanje EF migracija
	- izmena postojece baze
	- implementacija koda za migraciju
3. Ocekivani izlaz naredne sesije:
	- odobren pisani migracioni plan spreman za Worker implementaciju
