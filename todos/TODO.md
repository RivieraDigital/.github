# TODO — Riviera Digital Platform

> Ažurirano: April 2026
> Za Kontrol detaljan backlog vidi: `KONTROL_BACKLOG.md`

---

## 🔴 Kritično (uraditi odmah)

### Security
- [ ] SEC-1 Hardkodovan admin password → env (vidi KONTROL_BACKLOG)
- [ ] SEC-2 CORS AllowAnyOrigin → env-based whitelist
- [ ] SEC-3 Rate limiting na Login/Register

### Runtime
- [ ] RUN-2 Verifikacija Blazor admin panela posle rename-a

---

## 🟡 Visok prioritet

### Kontrol CMS
- [ ] API-1 Global Exception Handling Middleware (ProblemDetails)
- [ ] API-2 ApiControllerBase sa helper metodama za OperationResult<T>
- [ ] Order management modul (checkout flow)

### Sajtovi
- [ ] SasaKitic.rs — okačiti sajt
- [ ] Braća Drinić — pratiti feedback / uplatu €450

---

## 🔵 Srednji prioritet

### Kontrol CMS
- [ ] API versioning (/api/v1/)
- [ ] Security headers middleware
- [ ] Multi-tenant arhitektura

### Riviera Digital sajt (Next.js)
- [ ] Faza 4 — Detail layer (service + case study stranice)
- [ ] Faza 5 — Expansion (How We Work, FAQ, Industries)
- [ ] Faza 6 — Polish, SEO, Docker

### Dock (multi-tenant app)
- [ ] Definisati arhitekturu i scope (naslednik Sultan email servisa)

---

## ⚪ Nice-to-have / Later

- [ ] Migracija slika sa Cloudinaryja na Railway
- [ ] Kontrol API versioning
- [ ] Reporting modul

---

## ✅ Nedavno završeno

- [x] Rename Vezir → Kontrol/Riviera namespace (apr 2026)
- [x] Git diff review rename branch-a
- [x] Contracts repo rename + submodule sync
- [x] Login fix posle rename-a
- [x] DevNotes → Notes + .github migracija (apr 2026)
- [x] Riviera Digital site (Next.js) Faze 1-3
