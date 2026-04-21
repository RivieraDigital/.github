# 🚀 Kontrol — Beta to Production Master Plan

**Datum:** 2026-04-21
**Status:** 🔄 Aktivan
**Owner:** Saša Kitić
**Lokacija:** `.github/todos` (source of truth za tim)

---

## Cilj

Dovesti Kontrol platformu do stabilnog production nivoa za aktivne klijente i omogućiti pouzdano puštanje webshop + admin tokova bez blokera.

## Scope

- Kontrol API + Kontrol admin panel
- Webshop zavisnosti (Libra88, BShop, FairyTreasure, TopWear)
- Production kritične sigurnosne i runtime stavke
- GUI funkcionalni pregled
- Post-production hardening backlog

---

## Klijenti koji čekaju

| # | Klijent | Webshop | Poster | Status |
|---|---------|---------|--------|--------|
| 1 | Libra88 | Vezir.Demo.Poster.Libra88.WebShop | libra88.rs | Deployed, nije prod-ready |
| 2 | BShop | Vezir.Demo.Poster.BShop.WebShop | - | Deployed, nije prod-ready |
| 3 | FairyTreasure | Vezir.Demo.Poster.FairyTreasure.WebShop | - | Deployed, nije prod-ready |
| 4 | TopWear | Dockerfile.webshop-topwear | - | Deployed, nije prod-ready |

---

## Status model

- ⬜ Not started
- 🔄 In progress
- ⏳ Blocked
- ✅ Done
- ❌ Dropped

## Kategorije

- 🔴 BLOCKER: ne može dalje bez fixa
- 🟡 BUG: mora pre produkcije
- 🔵 POLISH: bitno za kvalitet, nije blocker
- ⚪ NICE: može posle

---

## Team Operating Template (Planner -> Worker -> Reviewer)

### 1) Rezervacija task-a (pre rada)

Kada neko uzima stavku iz backloga, u kolonu `Napomena` ili opis stavke dodaje:

- `Owner: ime`
- `StartedAt: YYYY-MM-DD HH:mm`
- `Branch: feature/... ili fix/...`
- `PlannerSession: putanja do SESSION fajla`

Primer formata:

`Owner: Marko | StartedAt: 2026-04-21 10:30 | Branch: fix/sec-4-secrets | PlannerSession: Plans/SESSION_kontrol-sec4_2026-04-21.md`

### 2) Planner izlaz (pre Worker-a)

Svaki task paket koji ide Worker-u mora imati:

- Jasan scope (tačni ID-jevi, npr. `SEC-4`, `SEC-5`)
- Acceptance kriterijume (šta znači `✅ Done`)
- Out-of-scope listu (šta se ne dira)
- Verifikaciju (`dotnet build`, test, smoke koraci)

### 3) Worker izlaz (pre Reviewer-a)

Worker mora vratiti:

- Lista promenjenih fajlova
- Šta je završeno po svakom ID-ju
- Šta nije završeno + razlog
- Komande verifikacije i rezultat

### 4) Reviewer gate (obavezno)

Task ne ide u `✅ Done` bez reviewer potvrde.

Reviewer proverava:

- Scope usklađen sa Planner planom
- Rizike/regresije
- Build/test/smoke dokaze
- Da su status i napomene u backlogu ažurirani

### 5) Backlog update posle review-a

Posle reviewer potvrde, u stavku se dopisuje:

- `Reviewer: ime`
- `PR: link ili #broj`
- `Evidence: build/test/smoke`
- `ClosedAt: YYYY-MM-DD HH:mm`

Primer formata:

`Reviewer: Sasa | PR: #128 | Evidence: build+smoke OK | ClosedAt: 2026-04-21 14:05`

---

## Paralelni Rad (anti-conflict)

1. Jedan aktivan owner po task ID-ju.
2. Ako je task `🔄 In progress`, drugi član ga ne preuzima bez predaje owner-a.
3. Velike stavke se dele na pod-taskove sa novim ID sufiksom (`SEC-4a`, `SEC-4b`) kad treba paralelizacija.
4. Svaki branch mora mapirati konkretne backlog ID-jeve.
5. Merge ide tek nakon reviewer potvrde i backlog update-a.

---

## Operativni workflow (Live)

1. Saša + Planner prolaze stranicu po stranicu.
2. Svaki nalaz se upisuje kao task sa ID i kategorijom.
3. Trivijalan/srednji fix ide odmah u Worker mini-task.
4. Review ide dalje dok Worker radi.
5. Po završetku Worker-a status se odmah ažurira.

**Pravilo:** ne skupljamo nalaze za kasnije, rešavamo u hodu.

---

## Faza 0 — Production blockeri (pre GUI)

| ID | Opis | Kategorija | Prioritet | Status | Napomena |
|----|------|-----------|-----------|--------|----------|
| B-001 | Login ne radi posle rename-a | 🔴 BLOCKER | P0 | ⬜ | JWT/CORS/Identity config |
| SEC-1 | Hardkodovan admin password u seed-u | 🔴 BLOCKER | P0 | ⬜ | Prebaciti na env/appsettings + ukloniti logovanje plain passworda |
| SEC-2 | CORS AllowAnyOrigin -> prod whitelist | 🔴 BLOCKER | P0 | ⬜ | Env-based policy |
| SEC-3 | Rate limiting na Login/Register | 🟡 BUG | P0 | ⬜ | AspNetCore rate limiting |
| SEC-4 | Hardkodovan DB password u API appsettings | 🔴 BLOCKER | P0 | ⬜ | Secrets izvući u env/secret store |
| SEC-5 | Hardkodovan JWT SecretKey u API appsettings | 🔴 BLOCKER | P0 | ⬜ | Rotirati ključ + env only |
| SEC-6 | Hardkodovan TrendSoft ApiKey u API appsettings | 🔴 BLOCKER | P0 | ⬜ | Rotirati ključ + env only |
| SEC-7 | Komitovani Railway connection stringovi u Development configu | 🔴 BLOCKER | P0 | ⬜ | Sanitizovati fajl + uskladiti .gitignore politiku |
| SEC-8 | Health endpointi otkrivaju environment i DB status bez autorizacije | 🟡 BUG | P1 | ⬜ | Zaštititi `/database` i `/detailed` |
| SEC-9 | General image upload endpoint nema autorizaciju + folder input nije whitelist-ovan | 🟡 BUG | P1 | ⬜ | Dodati `[Authorize]` i validaciju foldera |
| RUN-2 | Blazor admin panel runtime verifikacija | 🔴 BLOCKER | P0 | ⬜ | Posle login fixa |

---

## Faza 1 — GUI review nalazi

### Auth & Layout
| ID | Stranica | Nalaz | Kategorija | Prioritet | Status |
|----|----------|-------|-----------|-----------|--------|
| F-001 | Login /login | | | P0 | ⬜ |
| F-002 | MainLayout (SideNav + TopBar) | | | P1 | ⬜ |
| F-003 | Language switcher | | | P2 | ⬜ |
| F-004 | Theme toggle | | | P2 | ⬜ |

### Dashboard
| ID | Stranica | Nalaz | Kategorija | Prioritet | Status |
|----|----------|-------|-----------|-----------|--------|
| F-010 | Dashboard / | | | P1 | ⬜ |

### Catalog
| ID | Stranica | Nalaz | Kategorija | Prioritet | Status |
|----|----------|-------|-----------|-----------|--------|
| F-020 | Products /products | | | P1 | ⬜ |
| F-021 | Product Edit (modal) | | | P1 | ⬜ |
| F-022 | Product Create | | | P1 | ⬜ |
| F-023 | Categories /categories | | | P1 | ⬜ |
| F-024 | Category Edit | | | P1 | ⬜ |
| F-025 | Manufacturers /manufacturers | | | P1 | ⬜ |
| F-026 | Manufacturer Edit | | | P1 | ⬜ |
| F-027 | Tax Rates /taxrates | | | P1 | ⬜ |
| F-028 | Tax Rate Edit | | | P1 | ⬜ |

### Partners & Users
| ID | Stranica | Nalaz | Kategorija | Prioritet | Status |
|----|----------|-------|-----------|-----------|--------|
| F-040 | Business Partners /business-partners | | | P1 | ⬜ |
| F-041 | Web Users /webusers | | | P1 | ⬜ |

### Orders
| ID | Stranica | Nalaz | Kategorija | Prioritet | Status |
|----|----------|-------|-----------|-----------|--------|
| F-050 | Orders /orders | | | P1 | ⬜ |
| F-051 | Order Details | | | P1 | ⬜ |

### Blog
| ID | Stranica | Nalaz | Kategorija | Prioritet | Status |
|----|----------|-------|-----------|-----------|--------|
| F-060 | Blog Posts /blog | | | P1 | ⬜ |
| F-061 | Blog Post Edit | | | P1 | ⬜ |
| F-062 | Publish/Unpublish | | | P1 | ⬜ |

### System
| ID | Stranica | Nalaz | Kategorija | Prioritet | Status |
|----|----------|-------|-----------|-----------|--------|
| F-070 | Users /users | | | P1 | ⬜ |
| F-071 | Settings /settings | | | P1 | ⬜ |
| F-072 | Integrations /integrations | | | P1 | ⬜ |
| F-073 | TrendSoft /integrations/trendsoft | | | P1 | ⬜ |
| F-074 | Admin Tools | | | P1 | ⬜ |

### Reports
| ID | Stranica | Nalaz | Kategorija | Prioritet | Status |
|----|----------|-------|-----------|-----------|--------|
| F-080 | Reports /reports | | | P2 | ⬜ |

---

## Faza 2 — Infrastruktura (production-critical)

| ID | Backlog Ref | Opis | Kategorija | Prioritet | Status |
|----|-------------|------|-----------|-----------|--------|
| I-001 | API-1 | Global Exception Handling Middleware (ProblemDetails) | 🟡 BUG | P1 | ⬜ |
| I-002 | API-4 | Security headers middleware | 🟡 BUG | P1 | ⬜ |
| I-003 | CLEAN-1 | Dead routes (/register, /inventory) | 🔵 POLISH | P1 | ⬜ |
| I-004 | CLEAN-2 | Contracts repo rename + submodule sync | 🔵 POLISH | P1 | ⬜ |
| I-005 | RUN-3 | Git diff review rename branch-a | 🔵 POLISH | P1 | ⬜ |
| I-006 | API-OPS-1 | OpenAPI JSON endpoint exposure policy za production | 🟡 BUG | P1 | ⬜ |
| I-007 | OPS-HEALTH-1 | Standard health endpointi (`/health`) + dependency checks | 🔵 POLISH | P2 | ⬜ |
| I-008 | OPS-NET-1 | Harden forwarded headers trust policy (proxy/IP restrikcije) | 🔵 POLISH | P2 | ⬜ |
| I-009 | OPS-HTTPS-1 | Dodati `UseHttpsRedirection()` u production pipeline | 🟡 BUG | P1 | ⬜ |
| I-010 | OPS-ERR-1 | Forsirati `IncludeErrorDetail=false` u production konfiguraciji | 🟡 BUG | P1 | ⬜ |
| I-011 | OPS-AUTH-1 | Uvesti fallback authorization policy (deny-by-default) | 🟡 BUG | P1 | ⬜ |
| I-012 | OPS-DEPLOY-1 | Migrations startup strategija: readiness/liveness + graceful failure handling | 🟡 BUG | P1 | ⬜ |
| I-013 | OPS-DOCKER-1 | Dodati Docker `HEALTHCHECK` za API kontejner | 🔵 POLISH | P2 | ⬜ |
| I-014 | OPS-RESP-1 | Uvesti response compression za API odgovore | 🔵 POLISH | P2 | ⬜ |
| I-015 | OPS-ADMIN-1 | Backup/snapshot export dodatno ograničiti u production okruženju | 🔵 POLISH | P2 | ⬜ |

---

## Faza 3 — Post-production hardening backlog

### API & platform

| ID | Ref | Opis | Prioritet | Status |
|----|-----|------|-----------|--------|
| H-001 | API-2 | ApiControllerBase helper standardizacija | P2 | ⬜ |
| H-002 | API-3 | Standardizacija HTTP status kodova | P2 | ⬜ |
| H-003 | API-5 | API versioning (/api/v1/...) | P3 | ⬜ |
| H-004 | ORG-1 | Directory.Build.props + central package mgmt | P2 | ⬜ |

### Modules

| ID | Ref | Opis | Prioritet | Status |
|----|-----|------|-----------|--------|
| H-010 | MOD-1 | Orders modul domain decoupling od Catalog-a | P2 | ⬜ |
| H-011 | MOD-2 | Typed DbContext za preostale module | P2 | ⬜ |
| H-012 | MOD-3 | CQRS standardizacija Orders + WebUsers | P2 | ⬜ |
| H-013 | MOD-4 | Base Entity klase u Shared.Domain | P2 | ⬜ |

### Blazor/UI

| ID | Ref | Opis | Prioritet | Status |
|----|-----|------|-----------|--------|
| H-020 | BLZR-1 | Prebaciti @code logiku modal view-a u ViewModel-e | P2 | ⬜ |
| H-021 | BLZR-2 | Lookup data caching (Categories/Manufacturers) | P2 | ⬜ |

### Observability & perf

| ID | Ref | Opis | Prioritet | Status |
|----|-----|------|-----------|--------|
| H-030 | LOG-1 | Structured logging + Correlation IDs | P1 | ⬜ |
| H-031 | LOG-2 | Request/Response logging middleware | P1 | ⬜ |
| H-032 | PERF-1 | Response cache headers na GET endpointima | P3 | ⬜ |
| H-033 | PERF-2 | JWT AuthorId u Blog modulu (bez hardcode) | P3 | ⬜ |
| H-034 | PERF-3 | Input validation pipeline (DA vs FluentValidation) | P3 | ⬜ |
| H-035 | SEC-IMG-1 | Validacija MIME type + magic bytes za upload fajlove | P2 | ⬜ |
| H-036 | PERF-UPL-1 | Rate limiting za image upload endpoint-e | P3 | ⬜ |
| H-037 | OPS-CI-1 | Secret scanning check u CI (pre merge u development/master) | P2 | ⬜ |

### Mozaik

| ID | Ref | Opis | Prioritet | Status |
|----|-----|------|-----------|--------|
| H-040 | MOZ-1 | Sync Mozaik projekata u Mozaik repo | P3 | ⬜ |
| H-041 | MOZ-2 | Ukloniti kopije iz Kontrol, dodati submodule | P3 | ⬜ |
| H-042 | MOZ-3 | Migracija sa submodule na NuGet pakete | P3 | ⬜ |

---

## Sprint board (za Worker handoff)

| Sprint | Fokus | Stavke | Status |
|--------|-------|--------|--------|
| Sprint 1 | Login + runtime unblock | B-001, RUN-2, smoke test | ⬜ |
| Sprint 2 | Security minimum za prod | SEC-1..SEC-9 | ⬜ |
| Sprint 3 | GUI kritični bugovi | F-001..F-080 (po prioritetu) | ⬜ |
| Sprint 4 | Infra stabilnost | I-001..I-015 | ⬜ |
| Sprint 5 | Hardening | H-001..H-042 + H-035..H-037 | ⬜ |

---

## Odluke (istorija)

| # | Tema | Odluka | Datum |
|---|------|--------|-------|
| 1 | Klijenti | Libra88, BShop, FairyTreasure, TopWear | 2026-04-17 |
| 2 | Workflow | Live walkthrough + instant fix dispatch | 2026-04-17 |
| 3 | Rename ostaci | Kod čist, ostalo localization kozmetika + contracts sync | 2026-04-17 |
| 4 | Login uzrok | Rename nije root cause | 2026-04-17 |
| 5 | Source of truth lokacija | .github/todos | 2026-04-21 |
| 6 | Merge pristup | Potpuni merge backloga u jedan plan | 2026-04-21 |
| 7 | Re-scan dopuna plana | Ubačeni dodatni security/infra gap-ovi iz koda | 2026-04-21 |
| 8 | Deep re-scan #2 | Dodati net-new security/deploy/ops stavke u master plan | 2026-04-21 |

---

## Scan 2026-04-21 — dodatna zapažanja (evidence-based)

- Potvrđeno curenje tajni kroz repo config (`Database.Password`, `Jwt.SecretKey`, `TrendSoft.ApiKey`, Railway connection stringovi).
- Potvrđeno da nema registracije rate limiting middleware-a u API startup-u.
- Potvrđeno da global exception handling i security headers middleware još nisu uvedeni u pipeline.
- Potvrđeno da API koristi custom health kontroler, bez standardnog `MapHealthChecks("/health")` endpointa.
- Potvrđeno da je `MapOpenApi()` aktivan i van development režima; treba eksplicitna production politika.
- Potvrđeno da forwarded headers konfiguracija briše known proxies/networks; potrebno ograničiti trust boundary za production.
- Potvrđeno da `UploadGeneral` endpoint nema `[Authorize]` i prima folder parametar bez whitelist kontrole.
- Potvrđeno da authorization nema fallback policy (`AddAuthorization()` bez deny-by-default podešavanja).
- Potvrđeno da middleware pipeline nema `UseHttpsRedirection()` i da Dockerfile nema `HEALTHCHECK`.

---

## Pravila održavanja

1. Svaki završen task menja status istog dana.
2. Novi nalaz se upisuje odmah sa ID-em i prioritetom.
3. Ako task menja prioritet, ostaviti kratku napomenu u opisu.
4. Jednom nedeljno uraditi cleanup: prebaciti completed u kratki archive blok.
5. Ovaj fajl je jedini operativni plan za Kontrol production readiness.
