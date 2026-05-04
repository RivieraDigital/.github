# Kontrol CMS — Features & Status

> Ažurirano: April 2026
> Za detaljan backlog vidi: `todos/KONTROL_BACKLOG.md`

---

## Arhitektura

- **Pattern:** Modular Clean Architecture + Manual CQRS
- **Stack:** .NET 10, ASP.NET Core, Blazor Server (admin), EF Core, PostgreSQL
- **Hosting:** Railway

---

## Moduli

| Modul | Status | Napomena |
|-------|--------|----------|
| **Identity** | ✅ Aktivan | JWT auth, ASP.NET Identity |
| **Catalog** | ✅ Aktivan | Proizvodi, kategorije |
| **Orders** | 🔥 U razvoju | Checkout, narudžbine |
| **Blog** | ⚙️ Osnova | |
| **WebUsers** | ✅ Aktivan | |
| **Integrations** | 🔥 U razvoju | Eksterne integracije |
| **Reporting** | 📋 Planirano | |
| **Settings** | ⚙️ Osnova | |

---

## Ključne funkcionalnosti

| Feature | Status |
|---------|--------|
| JWT autentifikacija | ✅ |
| Admin panel (Blazor) | ✅ Verifikacija pending (RUN-2) |
| Catalog CRUD | ✅ |
| Order management | 🔥 U razvoju |
| WebShop frontend (Blazor WASM) | ✅ Osnova |
| Image upload (Cloudinary) | ✅ |
| Multi-tenant podrška | 📋 Planirano |

---

## Otvorena P0 security pitanja

- [ ] **SEC-1** Hardkodovan admin password u seed-u → env/appsettings
- [ ] **SEC-2** CORS AllowAnyOrigin → environment-based whitelist
- [ ] **SEC-3** Rate limiting na Login/Register

---

## Poznati klijenti

| Klijent | Status deploy-a |
|---------|----------------|
| Libra88 | 🔥 U razvoju |
| B-Shop | ✅ |
| Tea Ristić | ✅ |
