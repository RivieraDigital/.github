# 📋 Kontrol — Login Fix + Full GUI Test Plan

**Sesija:** 17.04.2026
**Status:** 🔄 U toku
**Izvor:** KONTROL_BACKLOG.md (RUN-1, RUN-2, RUN-3, SEC-1, SEC-2, CLEAN-1)

---

## Odluke

| # | Stavka | Odluka | Detalji |
|---|--------|--------|---------|
| | | | |

---

## Plan (u izradi)

_Popunjava se tokom sesije..._

---

## Scope — Kompletna GUI Test Matrica

### Faza 0: Login Fix (Blocker)
- [ ] **T-0.1** Dijagnostika login problema (JWT? CORS? Config mismatch?)
- [ ] **T-0.2** Fix login — API auth endpoint radi
- [ ] **T-0.3** Fix login — Blazor WASM prima token, čuva u localStorage, redirectuje na Dashboard

### Faza 1: Layout & Navigacija
- [ ] **T-1.1** MainLayout učitavanje (SideNav + TopBar rendlovani)
- [ ] **T-1.2** SideNav — svi linkovi klikabilni, navigacija radi
- [ ] **T-1.3** TopBar — profil meni (logout, change password)
- [ ] **T-1.4** Language switcher (ako postoji)
- [ ] **T-1.5** Theme toggle (dark/light)

### Faza 2: Dashboard (`/`)
- [ ] **T-2.1** Dashboard statistika — API poziv radi, podaci se prikazuju
- [ ] **T-2.2** Welcome state za neulogovane korisnike

### Faza 3: Catalog — Products (`/products`)
- [ ] **T-3.1** Lista proizvoda — tabela se učitava
- [ ] **T-3.2** Pretraga proizvoda (search)
- [ ] **T-3.3** Filter po kategoriji
- [ ] **T-3.4** Kreiranje novog proizvoda (Create)
- [ ] **T-3.5** Edit proizvoda (double-click otvara modal/view)
- [ ] **T-3.6** Brisanje proizvoda
- [ ] **T-3.7** Context menu na row click
- [ ] **T-3.8** Image upload za proizvod

### Faza 4: Catalog — Categories (`/categories`)
- [ ] **T-4.1** Tree prikaz kategorija
- [ ] **T-4.2** Kreiranje kategorije
- [ ] **T-4.3** Edit kategorije
- [ ] **T-4.4** Brisanje kategorije
- [ ] **T-4.5** Image upload za kategoriju

### Faza 5: Catalog — Manufacturers (`/manufacturers`)
- [ ] **T-5.1** Lista proizvođača
- [ ] **T-5.2** Kreiranje proizvođača
- [ ] **T-5.3** Edit proizvođača
- [ ] **T-5.4** Brisanje proizvođača (sa transfer dijalogom za proizvode)

### Faza 6: Catalog — Tax Rates (`/taxrates`)
- [ ] **T-6.1** Lista poreskih stopa
- [ ] **T-6.2** Kreiranje poreske stope
- [ ] **T-6.3** Edit poreske stope
- [ ] **T-6.4** Brisanje poreske stope

### Faza 7: Orders (`/orders`)
- [ ] **T-7.1** Lista narudžbina
- [ ] **T-7.2** Pregled detalja narudžbine
- [ ] **T-7.3** Edit narudžbine (status, stavke)
- [ ] **T-7.4** Product lookup unutar order edit-a

### Faza 8: Business Partners (`/business-partners`)
- [ ] **T-8.1** Lista poslovnih partnera
- [ ] **T-8.2** Kreiranje partnera
- [ ] **T-8.3** Edit partnera
- [ ] **T-8.4** Brisanje partnera

### Faza 9: Web Users (`/webusers`)
- [ ] **T-9.1** Lista web korisnika
- [ ] **T-9.2** Pretraga/filter web korisnika

### Faza 10: Blog (`/blog`)
- [ ] **T-10.1** Lista blog postova
- [ ] **T-10.2** Kreiranje blog posta
- [ ] **T-10.3** Edit blog posta
- [ ] **T-10.4** Publish/Unpublish toggle
- [ ] **T-10.5** Brisanje blog posta

### Faza 11: Reports (`/reports`)
- [ ] **T-11.1** Reports stranica se učitava
- [ ] **T-11.2** Grafikon/podaci prikazani

### Faza 12: System — Users (`/users`)
- [ ] **T-12.1** Lista admin korisnika
- [ ] **T-12.2** Kreiranje korisnika
- [ ] **T-12.3** Edit korisnika
- [ ] **T-12.4** Change password

### Faza 13: System — Settings (`/settings`)
- [ ] **T-13.1** Settings forma se učitava sa podacima
- [ ] **T-13.2** Izmena i Save settings

### Faza 14: System — Integrations (`/integrations`)
- [ ] **T-14.1** Lista integracija

### Faza 15: Admin Tools
- [ ] **T-15.1** Backup funkcija
- [ ] **T-15.2** Snapshot Export
- [ ] **T-15.3** Snapshot Import
- [ ] **T-15.4** Admin Stats

---

## Backlog stavke pokrivene ovim planom

Sledeće stavke iz KONTROL_BACKLOG.md se rešavaju/testiraju u ovom planu:
- **RUN-1** Login puca posle rename-a → Faza 0
- **RUN-2** Blazor admin panel verifikacija → Faze 1-15
- **SEC-1** Hardkodovan admin password → proveriti tokom login fix-a
- **SEC-2** CORS → ispliva tokom testiranja
- **CLEAN-1** Dead routes → proveriti tokom navigacije

---

## Napomene

_Dodaju se tokom sesije..._
