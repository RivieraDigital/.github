# Service Providers — Riviera Digital Infra

> Ažurirano: April 2026

---

## Hosting & Compute

### Railway
- **Koristi se za:** PostgreSQL baze, backend (Kontrol.Api), statički deploy Poster sajtova (Libra88, Tea Ristić, itd.)
- **Status:** ✅ Primarni hosting provider
- **Napomena:** Jovan Jokić postavlja i održava
- **Potencijal:** Razmatramo da migriramo slike sa Cloudinaryja ovde

### CPanel (via superhosting.rs)
- **Koristi se za:** Domeni, legacy hosting
- **Partnerstvo:** Superhosting.rs (domena registrar)
- **Status:** ✅ Aktivno

---

## Slike

### Cloudinary
- **Koristi se za:** Upload i CDN za slike u Kontrol CMS
- **Status:** ✅ Aktivno
- **Napomena:** Razmatramo potencijalnu migraciju na Railway radi centralizacije

---

## Repo / CI-CD

### Azure DevOps
- **Koristi se za:** Git repozitorijumi, CI/CD pipeline-ovi
- **Status:** ✅ Aktivno (Kontrol, Mozaik, Poster repo)
- **Org:** SaleIT organization

---

## Stari provajderi (ukinuti)

| Provajder | Bio korišćen za | Status |
|-----------|----------------|--------|
| **Azure App Services** | Sultan API, stari hosting | ❌ Ukinut |
| **Neon.tech** | PostgreSQL | ❌ Zamenjeno sa Railway |
| **Aiven** | PostgreSQL | ❌ Nije korišćen |
