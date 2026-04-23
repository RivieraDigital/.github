# 📋 Kontrol Production Master Plan

**Sesija:** 2026-04-21
**Status:** 🔄 U toku
**Izvor:** [Plans/KONTROL_BETA_TO_PRODUCTION.md](Plans/KONTROL_BETA_TO_PRODUCTION.md) + nova sesija

---

## Odluke

| # | Stavka | Odluka | Detalji |
|---|--------|--------|---------|
| 1 | Lokacija master plana | Odobreno | `.github/todos` je glavni source of truth |
| 2 | Naziv master fajla | Odobreno | `KONTROL_BETA_TO_PRODUCTION.md` |
| 3 | Backlog merge pristup | Odobreno | Potpuni merge u jedan master plan |
| 4 | Stari plan handling | Odobreno | Premešten u Archive + redirect ostavljen |
| 5 | Re-scan opseg dopune | Odobreno | Uključiti sve nalaze P0-P3 u master plan |
| 6 | Deep re-scan #2 opseg | Odobreno | Dodati još net-new nalaze u još jednom request-u |
| 7 | Commit master backloga | Završen | `.github` commit `da110a7` |
| 8 | Team workflow template | Završen | Dodat Planner->Worker->Reviewer SOP u master backlog |

---

## Plan (u izradi)

### Trenutno stanje (scan)

- Izvor 1: KONTROL_BETA_TO_PRODUCTION.md (operativni production flow + live walkthrough model)
- Izvor 2: KONTROL_BACKLOG.md (širi tehnički backlog sa prioritetima P0-P3)
- Preklapanje: SEC-1, SEC-2, SEC-3, API-1, API-4, CLEAN-1, RUN-3
- Rizik: dupliranje i razilaženje statusa između dva plana

### Predlog konsolidacije

1. Jedan master fajl u .github/todos kao source of truth za tim
2. Jasna podela: Production Critical, GUI Findings, Infrastructure, Post-Production
3. Jedinstven status model i owner polja po tasku
4. Nedeljni ritam ažuriranja + instant update kada se task završi

### Implementirano u ovoj sesiji

- Kreiran master plan: `.github/todos/KONTROL_BETA_TO_PRODUCTION.md`
- Urađen potpuni merge sadržaja iz:
	- `Plans/KONTROL_BETA_TO_PRODUCTION.md`
	- `Plans/KONTROL_BACKLOG.md`
- Definisan status model, faze, sprint board i pravila održavanja
- Urađen re-scan aplikacije i dopunjen master plan sa novim gap-ovima:
	- SEC-4..SEC-7 (secrets/config exposure)
	- I-006..I-008 (OpenAPI policy, health endpoint standard, forwarded headers trust)
	- Prioritet logging stavki podignut na P1
- Urađen deep re-scan #2 i dopunjen plan sa dodatnim stavkama:
	- SEC-8..SEC-9 (health endpoint exposure + upload auth/folder validation)
	- I-009..I-015 (HTTPS redirection, error detail policy, fallback auth, migration strategy, Docker healthcheck, response compression, admin export guard)
	- H-035..H-037 (MIME/magic-byte validation, upload throttling, CI secret scanning)
- Master backlog je komitovan u `.github` repo (`da110a7`).
- Dodat operativni template za timski rad (rezervacija taska, handoff, reviewer gate, backlog update, anti-conflict pravila).

### Otvorene odluke

- Da li odmah formirati Sprint 2A (SEC-4..SEC-9) kao poseban worker handoff
