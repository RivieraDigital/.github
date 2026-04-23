# 📋 Kontrol — Reorganizacija Planova za Planner/Worker Agente

**Sesija:** 16.04.2026
**Status:** ✅ Završena
**Izvor:** KONTROL_RENAME_PLAN.md + KONTROL_REFACTORING_PLAN.md

---

## Odluke

| # | Stavka | Odluka | Detalji |
|---|--------|--------|---------|
| 1 | Struktura output fajlova | ✅ 2 fajla | KONTROL_RENAME.md + KONTROL_BACKLOG.md u Plans/ |
| 2 | Stari plan fajlovi | ✅ Arhivirati | Premestiti u Archive/2026-04/ |
| 3 | Odluke | ✅ Idemo redom | Prolazimo odluke iz rename plana sada |
| 4 | Sales modul | ✅ Obriši | Prazan, 0 fajlova koda |
| 5 | Demo WebShop projekti | ✅ Obriši sva 3 | Libra88, BShop, FairyTreasure — pripadaju Poster repo-u |
| 6 | Flux.Demo.WASM | ✅ Zadrži + rename | Rename Flux→Mozaik, prebaci u Mozaik repo kao deo submodule stepa |
| 7 | Contracts submodule | ✅ Opcija A | Rename Contracts repo zasebno, posle Kontrol rename-a, u istom planu |
| 8 | Mozaik strategija | ✅ Git Submodule odmah | Sync iz Kontrol→Mozaik repo, obriši kopiju, dodaj submodule |
| 9 | Branch strategija | ✅ Zaseban branch | refactor/vezir-to-kontrol |
| 10 | Redosled | ✅ Security PRVO | Security quick-fixes pre rename-a (manji risk) |
| 11 | Flux.Demo.WASM rename | ✅ Da, rename + prebaci | Rename u Mozaik.Demo.WASM tokom rename faze |
| 12 | Contracts repo timing | ✅ U istom planu | Kao završni korak rename plana |

---

## Plan — Rezime

### Fajl 1: `Plans/KONTROL_RENAME.md` (worker-ready, hitan)
Sadržaj:
- **Sprint 0:** Security quick-fixes (iz refactoring plana: 1.1 + 1.4)
- **Sprint 1:** Brisanja (Sales, demos)
- **Sprint 2-8:** Inkrementalni rename Vezir→Kontrol (po redosledu iz rename plana)
- **Sprint 9:** Flux→Mozaik rename + Mozaik repo submodule setup
- **Sprint 10:** Contracts repo rename
- **Sprint 11:** Solution & root fajlovi, Dockerfiles, finalna verifikacija

### Fajl 2: `Plans/KONTROL_BACKLOG.md` (generalni backlog, planner-ready)
Sadržaj:
- Sve iz refactoring plana MINUS ono što je u rename planu
- Organizovano po prioritetu (P0-P3)
- Svaka stavka: opis, fajlovi, kompleksnost
- Bez "Saša odlučuje" — odluke su donete ili odložene

### Preostalo:
- [x] Arhivirati stare plan fajlove iz root DevNotes u Archive/2026-04/
- [x] Verifikovati oba plana sa Sašom

### Rezultat:
- `Plans/KONTROL_RENAME.md` — worker-ready, 11 sprintova, ~60 taskova
- `Plans/KONTROL_BACKLOG.md` — 24 stavke, P0-P3
- Stari fajlovi → `Archive/2026-04/`
