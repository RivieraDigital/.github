# Railway Deployment Status
> Poslednji update: 23.04.2026.

## Projekti

| Projekat | ID | Status |
|---|---|---|
| **Kontrol - Webshop** | `c461d432-6091-4b24-a314-8879f595f156` | ✅ Aktivan |
| **Poster - Presentations** | `c11b6597-f287-43b8-b64e-038aaa6fb37a` | ✅ Kreiran, deployamenti u toku |

---

## Kontrol - Webshop (Kontrol repo, `feeling-lucky` branch)

Environment ID: `4d10cd23-6374-41d3-b816-a315184fedaa`

| Servis | ID | Status | Domen | Watch |
|---|---|---|---|---|
| BShop CMS | `be872ed3-...` | ✅ SUCCESS | `bshop-cms-production.up.railway.app` | `/src/**` |
| BShop DB | `f08842ed-...` | ✅ SUCCESS | `postgres-fmdx-production.up.railway.app` | - |
| BShop Poster | `4ff9166b-...` | ✅ SUCCESS | `bshop-poster-production.up.railway.app` | `/webshops/blazor/Vezir.Demo.Poster.BShop.WebShop/**` |
| AloeVera CMS | `13436aa9-...` | ✅ SUCCESS | `aloevera-cms-production.up.railway.app` | `/src/**` |
| AloeVera DB | `a65208fe-...` | ✅ SUCCESS | `aloevera-db-production.up.railway.app` | - |
| Demo CMS | `67dd79d6-...` | ✅ SUCCESS | `demo-cms-production.up.railway.app` | `/src/**` |
| Demo DB | `ebb24fc7-...` | ✅ SUCCESS | `demo-db-production-58cc.up.railway.app` | - |
| FairyTreasure CMS | `772c3e3e-...` | ✅ SUCCESS | `fairy-treasure-production.up.railway.app` | `/src/**` |
| FairyTreasure DB | `0d831231-...` | ✅ SUCCESS | `postgres-toei-production.up.railway.app` | - |
| FairyTreasure Poster | `dc5fd215-...` | ✅ SUCCESS | `fairytreasure-poster-production-4cd3.up.railway.app` | `/webshops/blazor/Vezir.Demo.Poster.FairyTreasure.WebShop/**` |
| Libra88 CMS | `232790de-...` | ✅ SUCCESS | (bez Railway domena) | `/src/**` |
| Libra88 DB | `6e016b7d-...` | ✅ SUCCESS | `postgres-bkpv-production.up.railway.app` | - |
| Libra 88 Poster | `bfe6210c-...` | ✅ SUCCESS | (bez Railway domena) | `/webshops/blazor/Vezir.Demo.Poster.Libra88.WebShop/**` |
| TopWear CMS | `242876ad-...` | ✅ SUCCESS | `topwear-cms-production.up.railway.app` | `/src/**` |
| TopWear DB | `d6d63628-...` | ✅ SUCCESS | `postgres-production-27d3.up.railway.app` | - |
| TopWear Poster | `79dc66d1-...` | ✅ SUCCESS | `topwear-poster-production.up.railway.app` | `/webshops/react/TopWearShop/**` |

### ⚠️ Kontrol - Nedostaje
- **Kontrol.Web** (Blazor Server admin panel) — `Dockerfile.web` postoji ali **nema Railway servisa**
  - Preskočeno na zahtev korisnika (Blazor hosted, hostuje se drugačije)

---

## Poster - Presentations (Poster repo, `development` branch)

Environment ID: `3ed1fb95-9c65-40d8-b5f7-c3eda491e5f2`

| Servis | ID | Status | Railway domen | Watch |
|---|---|---|---|---|
| filip-apartmani | `b2706061-...` | ✅ SUCCESS | `filip-apartmani-production-c56c.up.railway.app` | `presentations/blazor/Poster.FilipApartmaniPakostane/**` + Dockerfile + nginx |
| braca-drinic | `c969f577-...` | ✅ SUCCESS | `braca-drinic-production-723e.up.railway.app` | `presentations/blazor/Poster.BracaDrinic/**` + Dockerfile + nginx |
| pk-gym | `e6c7485b-...` | ✅ SUCCESS | `pk-gym-production-143b.up.railway.app` | `presentations/blazor/Poster.PkGym/**` + Dockerfile + nginx |
| innerbeauty | `bf9594d7-...` | ✅ SUCCESS | `innerbeauty-production-8df5.up.railway.app` | `presentations/blazor/Poster.Innerbeauty/**` + Dockerfile + nginx |
| sasa-kitic | `fd88ea40-...` | ✅ SUCCESS | `sasa-kitic-production-a8c3.up.railway.app` | `presentations/blazor/Poster.SasaKitic/**` + Dockerfile + nginx |
| riviera-digital | `f50179c3-...` | 🔄 IN PROGRESS | `riviera-digital-production-4168.up.railway.app` | `presentations/react/riviera-digital.com/**` |
| moja-ograda | `1458f3a8-...` | 🔄 IN PROGRESS | `moja-ograda-production-81c5.up.railway.app` | `presentations/react/moja-ograda.com/**` |

**Next.js konfiguracija:**
- `riviera-digital`: `rootDirectory = presentations/react/riviera-digital.com`, `dockerfilePath = Dockerfile`
- `moja-ograda`: `rootDirectory = presentations/react/moja-ograda.com`, `dockerfilePath = Dockerfile`

**Security fix commitovan:** `fix(security): upgrade next.js 15.3.2 -> 15.3.8 (CVE-2025-66478 critical)` — commit `a7afb2e`

---

## Custom Domeni — FairyTreasure (primer)

Urađeno: fairytreasure.rs dodat kao custom domain u Railway.

| Tip | Host | Railway target | Status |
|---|---|---|---|
| CNAME | `www` | `tvt1u6av.up.railway.app` | ✅ PROPAGATED |
| CNAME | `@` (apex) | `n1164gcj.up.railway.app` | ⚠️ REQUIRES_UPDATE |

**cPanel koraci:**
1. cPanel → Domains → Zone Editor → fairytreasure.rs → Manage
2. Obriši postojeći A zapis za `@`
3. Dodaj CNAME `@` → `n1164gcj.up.railway.app` (TTL 300)
4. Provjeri da CNAME `www` → `tvt1u6av.up.railway.app` postoji
5. Sačekaj 5–30 min propagaciju

---

## Pending — Sledeći koraci

### Poster prezentacije — custom domeni (cPanel)
Kada su deployamenti uspješni, treba za svaki sajt:
1. Dodati custom domain u Railway (API poziv)
2. Postaviti DNS u cPanel

Sajtovi sa domenima koje treba povezati:
- `riviera-digital.com` / `www.riviera-digital.com`
- `moja-ograda.com` / `www.moja-ograda.com`
- `pkgym.rs` ili slično
- `innerbeauty.rs` ili slično
- `filipapartmani.com` ili slično
- itd. (potvrditi domene sa klijentima)

### Dock projekat
- Novi Railway projekat za multitenant app
- Kreirati kad bude kod spreman

### Libra88 CMS i Libra 88 Poster
- Servisi nemaju Railway domen — treba dodati `serviceDomainCreate`
- Service IDs: Libra88 CMS `232790de-...`, Libra 88 Poster `bfe6210c-...`

---

## Korisne skripte

| Skripta | Lokacija | Opis |
|---|---|---|
| `railway-configure-presentations.ps1` | `Poster/scripts/` | Konfiguracija svih Poster servisa (connect, dockerfile, domain, watch) |

## CLI komande za nastavak

```powershell
# Refresh token (uvek pre API poziva)
$token = (Get-Content "$env:USERPROFILE\.railway\config.json" | ConvertFrom-Json).user.accessToken

# Kontrol projekat
cd "F:\Work\RivieraDigital\Kontrol"
railway status --json | ConvertFrom-Json | ...

# Poster projekat
cd "F:\Work\RivieraDigital\Poster"
railway status --json | ConvertFrom-Json | ...

# Provjera statusa Poster deploymenta
$bodyFile = "$env:TEMP\rq.json"
@{"query" = "{ project(id: `"c11b6597-f287-43b8-b64e-038aaa6fb37a`") { environments { edges { node { serviceInstances { edges { node { serviceName latestDeployment { status } } } } } } } } }" } | ConvertTo-Json | Set-Content -Encoding UTF8 $bodyFile
curl.exe -s -X POST -H "Authorization: Bearer $token" -H "Content-Type: application/json" --data-binary "@$bodyFile" https://backboard.railway.app/graphql/v2 | ConvertFrom-Json | ...
```
