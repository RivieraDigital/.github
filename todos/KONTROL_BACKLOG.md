# 🔧 Kontrol — Generalni Backlog

**Datum:** 17.04.2026
**Status:** 📋 Aktivan backlog
**Napomena:** KONTROL_RENAME.md plan je zatvoren (17.04.2026). Nedovršene stavke iz rename plana su prebačene ovde.

---

## Prioriteti

| Oznaka | Značenje | Kada |
|--------|----------|------|
| P0 🔴 | Kritično — pre produkcije | Odmah posle rename-a |
| P1 🟡 | Važno — beta kvalitet | Pre klijenata |
| P2 🔵 | Korisno — production polish | Kad dođe vreme |
| P3 ⚪ | Nice-to-have | Ako bude vremena |

---

## P0 🔴 — Security & Kritično (posle rename-a)

- [ ] **SEC-1** Hardkodovan admin password u seed-u → čitati iz env/appsettings
  - `src/infrastructure/Kontrol.Infrastructure.Data/Seed/IdentitySeedModule.cs`
  - Kompleksnost: niska

- [ ] **SEC-2** CORS AllowAnyOrigin → environment-based whitelist (dev=any, prod=lista domena)
  - `src/hosts/Kontrol.Api/Configuration/CorsExtensions.cs`
  - Kompleksnost: niska

- [ ] **SEC-3** Rate limiting na Login/Register endpointima
  - `Microsoft.AspNetCore.RateLimiting` middleware
  - Kompleksnost: srednja

---

## P0 🔴 — Post-Rename Runtime Fix

- [x] **RUN-1** ~~Login puca posle rename-a~~ — **ZAVRŠENO**

- [ ] **RUN-2** Blazor admin panel verifikacija
  - Proveriti da se panel učitava posle rename-a
  - Kompleksnost: niska
  - ⚠️ Iz KONTROL_RENAME.md — Sprint 11.4

- [x] **RUN-3** ~~Git diff review rename branch-a~~ — **ZAVRŠENO**

---

## P1 🟡 — API Infrastruktura

- [ ] **API-1** Global Exception Handling Middleware (`ProblemDetails` format)
  - Kreirati `src/hosts/Kontrol.Api/Middleware/ExceptionHandlingMiddleware.cs`
  - Kompleksnost: srednja

- [ ] **API-2** `ApiControllerBase` sa helper metodama (`OkResult`, `FailResult`, `CreatedResult`, `NoContentResult`)
  - Standardizovati SVE kontrolere na `OperationResult<T>` pattern
  - Kompleksnost: srednja (menja sve kontrolere)

- [ ] **API-3** Standardizovati HTTP status codes
  - GET=200, POST=201, PUT=200, DELETE=204, Validation=400, NotFound=404
  - Kompleksnost: niska (ali mnogo fajlova)

- [ ] **API-4** Security headers middleware
  - X-Content-Type-Options, X-Frame-Options, CSP
  - Kompleksnost: niska

- [ ] **API-5** API versioning (`/api/v1/...`)
  - `Asp.Versioning.Http` paket
  - Kompleksnost: srednja
  - ⚠️ Razmisliti da li je potrebno za beta

---

## P1 🟡 — Čišćenje

- [ ] **CLEAN-1** Ukloniti dead routes (`/register`, `/inventory` u Routes.cs)
  - Kompleksnost: trivijalna

- [x] **CLEAN-2** ~~Contracts repo rename + submodule sync~~ — **ZAVRŠENO**

---

## P1-P2 — Module Konzistentnost

- [ ] **MOD-1** Orders modul refaktor — kreirati sopstveni domain (Order, OrderItem), Commands/Queries, IOrdersDbContext, Mapper
  - Trenutno koristi `Catalog.Domain.Order` — tight coupling
  - Kompleksnost: visoka
  - Template: Catalog modul

- [ ] **MOD-2** Typed DbContext za preostale module
  - Kreirati: IOrdersDbContext, IWebUsersDbContext, ISettingsDbContext, IIdentityDbContext, IReportingDbContext, IIntegrationsDbContext
  - Implementirati ih u KontrolDbContext
  - Kompleksnost: srednja

- [ ] **MOD-3** CQRS za Orders + WebUsers
  - Orders: CreateOrderCommand, GetOrdersPagedQuery, itd.
  - WebUsers: Search logika
  - ⚠️ Settings/Reporting — overkill, samo Get/Update
  - Kompleksnost: visoka

- [ ] **MOD-4** Base Entity klase u Shared.Domain
  - `EntityBase { Id }`, `AuditableEntity : EntityBase { CreatedAt, UpdatedAt }`
  - Kompleksnost: niska (ali treba ažurirati sve entitete koji naslede)

---

## P2 🔵 — Solution Organizacija

- [ ] **ORG-1** Directory.Build.props + Central Package Management
  - Zajedničke PropertyGroup (TargetFramework, Nullable, ImplicitUsings)
  - Centralne verzije NuGet paketa
  - Kompleksnost: srednja

---

## P2 🔵 — Blazor Poboljšanja

- [ ] **BLZR-1** Prebaciti @code blokove iz 7 modal views u ViewModele
  - Tab state, handler logika → EditViewModeli
  - Izuzetak: ImageUpload.razor (JS interop mora da ostane)
  - Kompleksnost: srednja

- [ ] **BLZR-2** Lookup data caching (Categories/Manufacturers)
  - Keširati u scoped servisu umesto učitavanja svaki put
  - Kompleksnost: niska

---

## P2 🔵 — Logging & Observability

- [ ] **LOG-1** Structured logging + Correlation IDs
  - Middleware koji generiše RequestId i propagira kroz logove
  - Kompleksnost: srednja

- [ ] **LOG-2** Request/Response logging middleware
  - Sa opt-out za health check endpoint
  - Kompleksnost: niska

---

## P3 ⚪ — Performance & Polish

- [ ] **PERF-1** Response Caching Headers
  - `[ResponseCache]` atributi na GET endpointima (lookup data, statični podaci)
  - Kompleksnost: niska

- [ ] **PERF-2** JWT AuthorId iz tokena u Blog modulu
  - Umesto hardkodovanog "system"
  - `Kontrol.Web.UI/ViewModels/.../BlogPostEditViewModel.cs:194`
  - Kompleksnost: niska

- [ ] **PERF-3** Input validacija pipeline
  - DataAnnotations na Request DTOs + ModelState validation
  - ILI FluentValidation u Application layeru
  - Kompleksnost: srednja
  - ⚠️ Treba odluka: DataAnnotations vs FluentValidation

---

## Mozaik Backlog (nakon submodule setup-a)

- [ ] **MOZ-1** Sync Mozaik projekti u Mozaik repo
  - Kopiraj renamed sadržaj (Mozaik.*) iz Kontrol `src/external projects/` → Mozaik repo (`f:\Work\RivieraDigital\Mozaik`)
  - Verifikuj da Mozaik repo builduje samostalno
  - ⚠️ Iz KONTROL_RENAME.md — Sprint 6.6

- [ ] **MOZ-2** Obriši Mozaik kopije iz Kontrol + dodaj kao submodule
  - Obriši `src/external projects/Mozaik*` iz Kontrol
  - `git submodule add <mozaik-repo-url> src/external projects/Mozaik`
  - Update ProjectReference putanje u Kontrol projektima ka submodule lokaciji
  - `dotnet build` verifikacija
  - ⚠️ Iz KONTROL_RENAME.md — Sprint 6.7/6.8

- [ ] **MOZ-3** Dugoročno: migracija ka NuGet paketima
  - Publish Mozaik kao NuGet, zameni submodule sa package reference
  - Kad Mozaik bude stabilan

---

## 📊 Sumarni Pregled

| Prioritet | Stavki | Kompleksnost |
|-----------|--------|-------------|
| P0 🔴 Security | 3 | Niska |
| P0 🔴 Runtime | 3 | Niska-Srednja |
| P1 🟡 | 7 | Srednja |
| P1-P2 | 4 | Visoka |
| P2 🔵 | 5 | Srednja |
| P3 ⚪ | 3 | Niska-Srednja |
| Mozaik | 3 | - |
| **UKUPNO** | **28** | |

---

## Napomene

- Catalog modul je **template** za sve ostale — svaki refaktor prati njegov pattern
- Refaktori se rade **modul po modul**, bez big-bang pristupa
- Prioritet je **monetizacija** (klijenti) — backlog ne sme da blokira delivery
- Worker agent radi po sprintovima koje planner definiše iz ovog backloga
