# 📋 Poster Repo — Čišćenje Vezir Imenovanja

**Sesija:** 2026-04-20
**Status:** ✅ Završeno — commitovano na feature branch-ove
**Izvor:** Poster repo analiza + .github agent setup za Milana

---

## Kontekst

Milan je preuzeo .github repo sa planner/worker agentima. Saša je odradio rename Vezir → Poster za 8 projekata. RivieraDigital duplikati odloženi.

---

## Odluke

| # | Stavka | Odluka | Detalji |
|---|--------|--------|---------|
| 1 | Novo ime | `Poster.*` | Kraće i čistije od Riviera.Poster.* |
| 2 | Scope | Sve odjednom | 8 projekata (5 presentations + 3 webshops) |
| 3 | Contracts zavisnosti | Riviera.* | Univerzalno ime za platformu — ne po proizvodu |
| 4 | NuGet paketi (Vezir.Flux) | Ignorišemo | To je Mozaik posao |
| 5 | Anomalije | Samo rename | FilipApartmani mismatch i duplikat se ne diraju |
| 6 | RivieraDigital duplikati | Odloženo | Oba ostaju netaknuta za sada |
| 7 | VezirEmailClient | Odloženo | Shared servis — ne dira se u ovom prolazu |

---

## Urađeno

### Preimenovani projekti (✅ Build OK)

| # | Staro ime | Novo ime | Tip | Build |
|---|-----------|----------|-----|-------|
| 1 | Vezir.Demo.Poster.Libra88.WebShop | Poster.Libra88.WebShop | WebShop | ✅ |
| 2 | Vezir.Demo.Poster.BShop.WebShop | Poster.BShop.WebShop | WebShop | ✅ |
| 3 | Vezir.Demo.Poster.FairyTreasure.WebShop | Poster.FairyTreasure.WebShop | WebShop | ✅ |
| 4 | Vezir.Demo.Poster.BracaDrinic | Poster.BracaDrinic | Presentation | ✅ |
| 5 | Vezir.Demo.Poster.FilipApartmaniPakostane | Poster.FilipApartmaniPakostane | Presentation | ✅ |
| 6 | Vezir.Demo.Poster.Innerbeauty | Poster.Innerbeauty | Presentation | ✅ |
| 7 | Vezir.Demo.Poster.PkGym | Poster.PkGym | Presentation | ✅ |
| 8 | Vezir.Demo.Poster.SasaKitic | Poster.SasaKitic | Presentation | ✅ |

### Nepreimenovano (odloženo)
- Vezir.Demo.Poster.Riviera-Digital (starija verzija)
- Vezir.Demo.Poster.RivieraDigital/RivieraDigital1 (produkciona verzija)

### Šta je sve promenjeno
1. **Folderi** — 8 foldera preimenovano
2. **Csproj fajlovi** — 8 .csproj fajlova preimenovano
3. **Namespace-ovi** — svi .cs fajlovi (31+ po projektu) ažurirani
4. **@using direktive** — svi .razor i _Imports.razor fajlovi ažurirani
5. **Solution fajlovi** — Posters.slnx (preimenovan iz Vezir.Posters.slnx), webshops-blazor.slnx, presentations-blazor.sln
6. **Docker fajlovi** — svi Dockerfile.* u docker/ folderu
7. **Kontrol tasks.json** — start-libra88 task putanja ažurirana
8. **Kontrol Dockerfile.libra88** — putanje ažurirane
9. **Contracts using-ovi** — ažurirani na Riviera.* (univerzalan namespace)

### Git Status
- **Contracts submodule**: `feature/rename-to-riviera` branch, 1 commit
- **Poster repo**: `feature/rename-vezir-to-poster` branch, 1 commit  
- **Kontrol repo**: `feature/rename-poster-refs` branch, 1 commit
- **Ništa nije push-ovano** — samo lokalni commitovi

### Šta NIJE dirano
- Contracts submodule (shared/contracts/) — folderi i fajlovi ostaju Vezir.*
- NuGet paketi Vezir.Flux.* — Mozaik posao
- VezirEmailClient klasa u prezentacijama
- DevNotes dokumentacija
- RivieraDigital duplikati

---

## Za Milana (taskovi)

Milan može da radi na:
- Čišćenje koda u pojedinačnim prezentacijama
- SEO optimizacija
- Tailwind CSS refactoring
- Contact form popravke (Porto integracija)
- React migracija novih sajtova
