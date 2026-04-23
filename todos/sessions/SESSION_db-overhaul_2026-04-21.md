# 📋 DB Overhaul Plan (Kontrol)

**Sesija:** 2026-04-21
**Status:** 🔄 U toku (domenski pretres završen, čeka implementacioni handoff)
**Izvor:** f:\Work\RivieraDigital\.github\todos\SESSION_awesome-copilot_2026-04-21.md

---

## Odluke

| # | Stavka | Odluka | Detalji |
|---|--------|--------|---------|
| 1 | Baseline sken prethodnog plana | ✅ Evidentirano | Prethodna sesija zatvorila setup agenata/skillova; nije urađen implementacioni DB plan |
| 2 | Struktura plana P0-P4 (prvi draft) | ❌ Odbačeno | Potrebna je drugačija struktura plana |
| 3 | Sledeći fokus razrade | ✅ Odobreno | Ići odmah na detaljisanje P0 i P1 |
| 4 | Novi okvir plana | ✅ Odobreno | Domain-first model |
| 5 | Nivo razrade P0/P1 | ✅ Odobreno | Task-level + complexity + dependencies |
| 6 | Status potvrde P0/P1 | 🔄 Treba još diskusije | Čeka se verifikacija da su potrebni awesome-copilot skillovi dostupni pre finalnog odobrenja |
| 7 | S1.4 raspodela uloga | ⏳ Odloženo | Ne zatvarati sada; vratiti kasnije |
| 8 | Verifikacija awesome-copilot skillova | ✅ Potvrđeno | Sva 4 ključna plugina su prisutna i vidljiva kroz `gh copilot -- plugin list` |
| 9 | Finalna potvrda P0 | ✅ Odobreno | Discovery scope usvojen bez izmena |
| 10 | Finalna potvrda P1 | ✅ Odobreno | Target schema design usvojen bez izmena |
| 11 | Sledeći fokus | ✅ Odobreno | Razraditi P2 (migration waves) detaljno |
| 12 | Finalna potvrda P2 | ✅ Odobreno | Migration strategy scope usvojen |
| 13 | Nastavak sesije | ✅ Odobreno | Razraditi P3 i P4 detaljno |
| 14 | Finalna potvrda P3/P4 | ✅ Odobreno | Validation i Cutover faze usvojene |
| 15 | Handoff u ovoj iteraciji | ⏳ Odloženo | Plan ostaje draft; nema slanja Worker-u sada |
| 16 | Domenski pretres (read-only) | ✅ Evidentirano | Završeno mapiranje tabela + programskih touchpoint-a i high-risk zona |
| 17 | Scope domenskog pretresa | ✅ Odobreno | Kontrol + Contracts |
| 18 | P0 proširenje | ✅ Odobreno | Dodati P0.6-P0.9 (Change Matrix, Impact mapa, workshop, gate) |
| 19 | Format izlaza pretresa | ✅ Odobreno | Change Matrix + Impact Heatmap |
| 20 | Q1 Discount prioritet | ✅ Odobreno | Sekvencijalno: Product discount pa BusinessPartner discount |
| 21 | Q2 Order snapshot politika | ✅ Odobreno | Hibridni model (ključna polja snapshot, ostatak reference gde ima smisla) |
| 22 | Q3 Identity strategija | ✅ Odobreno | Odvojene tabele uz federaciju kroz shared IdentityLink |
| 23 | Q4 Blog autor model | ✅ Odobreno | BlogPost.Author ide na FK ka User (zaposleni autori) |
| 24 | Q5 Category delete politika | ✅ Odobreno | Soft delete + reassignment workflow |
| 25 | Q6 StoreSettings singleton guard | ✅ Odobreno | Explicit ID=1 + DB unique guard |
| 26 | Q7 External sync standard | ✅ Odobreno | Shared SyncMetadata model za sve sync entitete |
| 27 | Q8 Product refactor model | ✅ Odobreno | Opcija 2 Pragmatic (VO + centralni pricing + Orders split) |
| 28 | Segment redosled nastavka | ✅ Odobreno | Sledeći segment je Identity + WebUser federacija |
| 29 | Identity segment model | ✅ Odobreno | Opcija C: odvojeni modeli + IdentityLink federacija |
| 30 | Customer token lifecycle | ✅ Odobreno | Uvesti refresh/revoke lifecycle i za customer auth |
| 31 | Sledeći segment | ✅ Odobreno | Settings + Integrations |
| 32 | Settings/Integrations model | ✅ Odobreno | Opcija A: generički provider model |
| 33 | Secret policy finalizacija | ✅ Odobreno | Hybrid: secret store + DB reference, uz runtime primenu bez restarta |
| 34 | Runtime osvežavanje konfiguracije | ✅ Odobreno | Manual invalidate iz admin panela |
| 35 | Status segmenta #4 | ✅ Zatvoreno | Settings + Integrations segment je zaključen |
| 36 | Order segment model | 🔄 Treba još diskusije | Potrebna finalna odluka između opcija 1/2/3 |
| 37 | Payment failure stock politika | ✅ Odobreno | Grace period pa rollback stock-a |
| 38 | Tax snapshot politika | ✅ Odobreno | Snapshot tax rate/value pri kreiranju porudžbine |
| 39 | Order model finalni put | ✅ Odobreno | Faza 1: Opcija 1, Faza 2: Opcija 3 |
| 40 | Status segmenta #2 | ✅ Zatvoreno | Order & OrderItem segment zaključen faznim pristupom |
| 41 | Blog segment policy | ✅ Odobreno | FK-author ownership + stroža moderation policy |
| 42 | Q9 Raw SQL policy | ✅ Odobreno | Threshold policy: LINQ standardno, raw SQL za >100k i teške agregacije |
| 43 | Q10 Batch policy | ✅ Odobreno | Chunk + SaveChanges + ClearChangeTracker + retry policy |
| 44 | Status domenskog pretresa | ✅ Zatvoreno | Kompletan segment-by-segment pretres završen |
| 45 | SQL pristup u ovoj fazi | ✅ Odobreno | Raw SQL se izostavlja; sve ide preko EF entiteta do daljeg |
| 46 | Worker plan kickoff | 🔄 U toku | Kreira se implementacioni plan po fazama + tabela/data triage |
| 47 | Brisanje politika (faza 1) | ✅ Odobreno | Selektivni hard delete odmah gde je jasno i bezbedno |
| 48 | Dubina pretresa | ✅ Odobreno | Kolona-po-kolona za sve tabele |
| 49 | Worker backlog trenutak | ✅ Odobreno | Ne sastavljati finalni backlog dok se ne završi detaljni triage |
| 50 | Kolona-po-kolona pretres | ✅ Evidentirano | Završeno za sve glavne tabele; definisani drop/merge/review kandidati |
| 51 | JSON strategija | ✅ Odobreno | Normalizovati odmah u posebne tabele |
| 52 | Order snapshot kolone | ✅ Odobreno | Krenuti odmah na čišćenje snapshot kolona |
| 53 | Immediate hard delete opseg | ✅ Odobreno | Samo dva secret polja odmah u fazi 1 |
| 54 | Worker backlog status | ✅ Pokrenuto | Plan prelazi u task-by-task izvršni backlog |

---

## Plan (u izradi)

## 1) Sken trenutnog plana (šta već imamo)

1. Setup faza je završena i validirana (S1-S4).
2. Scope prethodnog plana je eksplicitno bio bez migracija i bez DB izmena.
3. Potvrđen je clean-slate pravac (brisanje postojeće baze i gradnja nove strukture).
4. Potvrđena je strategija punjenja podataka: scraper gde može, seed + manual fallback gde ne može.

Zaključak: spremni smo da pređemo iz setup faze u implementacioni planning, uz jasne granice i quality gate-ove.

## 2) Kompletan DB overhaul plan (Domain-first)

### Faza D0 — Domain Scope Lock
- Cilj: zaključati granice domena i ownership pre bilo kakvog modeliranja.

#### Sprint P0 — Discovery i granice domena
- [ ] **P0.1** Scope lock po modulima i ownership mapa
	- Complexity: M
	- Dependencies: none
	- Output: lista entiteta po modulu sa owner timom
- [ ] **P0.2** As-is schema inventory (tabele, FK, indeksi, kritični constraints)
	- Complexity: H
	- Dependencies: P0.1
	- Output: as-is catalog + dependency graf
- [ ] **P0.3** Cross-module contract mapa (šta koji modul čita/piše)
	- Complexity: H
	- Dependencies: P0.1, P0.2
	- Output: contract matrix read/write
- [ ] **P0.4** NFR baseline (performanse, audit, retention, soft-delete)
	- Complexity: M
	- Dependencies: P0.2
	- Output: NFR specifikacija kao ulaz za target schema
- [ ] **P0.5** Freeze pravila i change control tokom overhaul-a
	- Complexity: M
	- Dependencies: P0.1, P0.3
	- Output: pravila šta je dozvoljeno menjati do cutover-a
- Deliverable P0: odobren scope + dependency graf + contract matrix + NFR baseline.

### Faza D1 — Target Schema Design
- Cilj: definisati clean-slate strukturu baze i standarde kvaliteta.

#### Sprint P1 — Target schema dizajn (task-level)
- [ ] **P1.1** Bounded context model i ownership tabela
	- Complexity: H
	- Dependencies: P0.1, P0.3
	- Output: target module boundaries
- [ ] **P1.2** Canonical entiteti i relacije (PK/FK/unique)
	- Complexity: H
	- Dependencies: P1.1, P0.4
	- Output: logical schema v1
- [ ] **P1.3** Naming i tipizacija standard (ID, enum, money, timestamps)
	- Complexity: M
	- Dependencies: P1.1
	- Output: data conventions dokument
- [ ] **P1.4** Audit i concurrency model (CreatedAt/UpdatedAt/Version)
	- Complexity: M
	- Dependencies: P1.2
	- Output: audit/concurrency spec
- [ ] **P1.5** Query-driven indeks strategija po modulu
	- Complexity: H
	- Dependencies: P1.2
	- Output: inicijalni indeks plan i očekivani query profile
- [ ] **P1.6** Multi-tenant, localization i soft-delete pravila gde su potrebna
	- Complexity: M
	- Dependencies: P1.2, P1.3
	- Output: policy dodatak za shared entitete
- [ ] **P1.7** Architect compliance review (manual CQRS, DTO granice, modul ownership)
	- Complexity: M
	- Dependencies: P1.1-P1.6
	- Output: approval zapisnik ili lista korekcija
- Deliverable P1: target logical/physical schema v1 + conventions + indeks plan + review zapisnik.

### Faza D2 — Data Contract i Migration Waves
#### Sprint P2 — Migraciona strategija
- [ ] **P2.1** Wave sequencing po modulima (Identity -> Catalog -> Orders -> Reporting/Integrations -> Blog/WebUsers/Settings)
	- Complexity: H
	- Dependencies: P0.2, P0.3, P1.7
	- Output: migration wave mapa sa redosledom i ownership-om
- [ ] **P2.2** Data contract matrica između stare i target šeme
	- Complexity: H
	- Dependencies: P1.2, P1.3, P2.1
	- Output: mapiranje old->new polja, transform pravila, null/default pravila
- [ ] **P2.3** Loading pipeline strategija: scraper/seed/manual po entitetu
	- Complexity: H
	- Dependencies: P2.2
	- Output: source-of-truth matrica po entitetu + fallback tok
- [ ] **P2.4** Data quality gate po talasu
	- Complexity: M
	- Dependencies: P2.2, P2.3
	- Output: checklista za kompletnost, konzistentnost, deduplikaciju
- [ ] **P2.5** Rollback model i stop-the-line triggeri
	- Complexity: H
	- Dependencies: P2.1, P2.4
	- Output: rollback decision tree i recovery playbook
- [ ] **P2.6** EF migration execution blueprint (plan i redosled, bez izvršenja)
	- Complexity: M
	- Dependencies: P1.7, P2.1
	- Output: plan skripti/migracija po wave-u i checkpoint pravila
- [ ] **P2.7** Dry-run readiness kriterijumi za staging
	- Complexity: M
	- Dependencies: P2.4, P2.5, P2.6
	- Output: minimum readiness gate za prelazak na P3
- Deliverable P2: migration wave plan + data contract matrica + loading/gate/rollback blueprint.

### Faza D3 — Validation Gates
#### Sprint P3 — Testiranje i verifikacija
- [ ] **P3.1** Test matrica po talasu: schema, integration, performance, data quality
	- Complexity: M
	- Dependencies: P2.7
	- Output: test plan po wave-u i ownership
- [ ] **P3.2** Staging dry-run orkestracija (redosled, vreme, checkpoint-i)
	- Complexity: H
	- Dependencies: P2.6, P3.1
	- Output: dry-run runbook sa expected rezultatima
- [ ] **P3.3** Verifikacija data correctness-a nakon svakog wave-a
	- Complexity: H
	- Dependencies: P2.4, P3.2
	- Output: pass/fail evidencija po entitetu i modulu
- [ ] **P3.4** Performance baseline poređenje pre/posle
	- Complexity: H
	- Dependencies: P1.5, P3.2
	- Output: benchmark izveštaj i tuning lista
- [ ] **P3.5** UAT kriterijumi i business sign-off po modulu
	- Complexity: M
	- Dependencies: P3.3
	- Output: UAT checklist i potpis vlasnika modula
- [ ] **P3.6** Finalni Go/No-Go gate
	- Complexity: M
	- Dependencies: P3.4, P3.5
	- Output: formalna odluka za ulazak u cutover
- Deliverable P3: validiran staging dry-run + UAT sign-off + Go/No-Go odluka.

### Faza D4 — Cutover i Stabilization
#### Sprint P4 — Operativni plan
- [ ] **P4.1** Cutover timeline i preflight kontrole (T-7, T-1, T0)
	- Complexity: M
	- Dependencies: P3.6
	- Output: operativni kalendar i freeze potvrde
- [ ] **P4.2** T0 execution script i owner matrica
	- Complexity: H
	- Dependencies: P4.1
	- Output: minut-po-minut runbook sa odgovornim osobama
- [ ] **P4.3** Incident playbook i rollback activation protokol
	- Complexity: H
	- Dependencies: P2.5, P4.2
	- Output: incident scenariji i rollback trigger mapa
- [ ] **P4.4** Post-cutover monitoring (T+1 do T+7)
	- Complexity: M
	- Dependencies: P4.2
	- Output: dnevna health check evidencija i KPI dashboard
- [ ] **P4.5** Stabilization sign-off i formalno zatvaranje
	- Complexity: M
	- Dependencies: P4.4
	- Output: closeout zapisnik sa otvorenim post-migration stavkama
- Deliverable P4: izvršni cutover runbook + stabilization closeout.

## 3) Rizici i mitigacije

1. Rizik: Nepotpuni scraper output.
Mitigacija: Obavezna manual import lista + data quality checkpoint pre cutover-a.
2. Rizik: Nekontrolisane među-modulske zavisnosti.
Mitigacija: Dependency mapa i obavezni review gate pre P2.
3. Rizik: Performance regresije posle prelaska.
Mitigacija: Query benchmark pre/posle + indeks tuning prozor u P3.
4. Rizik: Operativni zastoj tokom cutover-a.
Mitigacija: Precizan rollback trigger i owner matrica za incident response.

## 4) Domenski Pretres - Nalaz (read-only)

### 4.1 Pokrivenost inventara
1. Mapiran je centralni model oko jedne baze i jednog konteksta sa konfiguracijama po modulima.
2. Inventarisane su ključne tabele po domenima: Identity, Catalog, Orders, Settings, Integrations, Blog.
3. Povezani su glavni programski touchpoint-i: Services/Handlers i API kontroleri koji rade read/write.

### 4.2 High-risk zone za DB overhaul
1. Monolitni DbContext i snažno međumodulsko sprezanje.
2. Dupli discount model (Product + StoreSettings + partner defaults).
3. Delimično denormalizovan Order model (snapshot polja + reference zajedno).
4. Split identitet model (admin User i webshop WebUser).
5. Singleton settings obrasci bez striktne jedinstvenosti reda.
6. Blog Author veza bez stroge FK relacije.

### 4.3 Otvorena pitanja pre implementacije
1. Tačna discount prioritizacija i izvor istine.
2. Strategija za WebUser vs User (razdvajanje ili konvergencija).
3. Politika za denormalizovana order snapshot polja.
4. Entity-only performansna granica i kada eventualno aktivirati SQL fallback (odloženo).

### 4.4 Dodatni discovery taskovi (predlog)
- [ ] **P0.6** Tabela-po-tabela Change Matrix (Keep / Redesign / Merge / Drop)
	- Complexity: H
	- Dependencies: P0.2, P0.3
	- Output: matrica odluka za svaku tabelu
- [ ] **P0.7** Program touchpoint impact mapa (Service/Endpoint -> tabela)
	- Complexity: H
	- Dependencies: P0.3
	- Output: impact heatmap za refaktor prioritet
- [ ] **P0.8** Open-question resolution workshop (discount, identity split, order snapshot)
	- Complexity: M
	- Dependencies: P0.6, P0.7
	- Output: zaključane domenske odluke
- [ ] **P0.9** Pre-P1 architecture gate (odobrenje da P1 modeliranje može da krene)
	- Complexity: M
	- Dependencies: P0.8
	- Output: formalni GO zapisnik

### 4.5 Full Change Matrix (Kontrol + Contracts impact)

| Entitet/Tabela | Modul | Predlog | Razlog | Rizik | Prioritet |
|---|---|---|---|---|---|
| User | Identity | Keep | Stabilan admin identitet i RBAC model | L | P1 |
| Role | Identity | Keep | Standardna role matrica i ownership čist | L | P1 |
| UserRole | Identity | Keep | Junction tabela bez otvorenih problema | L | P1 |
| RefreshToken | Identity | Keep | Token lifecycle izolovan i predvidiv | L | P2 |
| WebUser | Catalog/WebUsers | Split | Domenski pripada WebUsers modulu, trenutno je coupling sa Catalog | M | P0 |
| Category | Catalog | Redesign | Self-reference pravila i delete tok zahtevaju kontrolisanu strategiju | M | P1 |
| Manufacturer | Catalog | Keep | Nizak rizik i jasan ownership | L | P2 |
| TaxRate | Catalog | Keep | Stabilan model, ali visok uticaj na obračun kroz druge module | L | P2 |
| Product | Catalog | Split + Redesign | Prevelik agregat, discount semantika i cross-module uticaj | H | P0 |
| ProductImage | Catalog | Keep | Stabilna relacija i nizak migracioni rizik | L | P1 |
| OemPartNumber | Catalog | Keep | Jednostavan prateći entitet uz Product | L | P2 |
| Order | Catalog/Orders | Split + Redesign | Kritičan domen, denormalizovani snapshot i payment/status tokovi | H | P0 |
| OrderItem | Catalog/Orders | Split | Snažna zavisnost od Product i Order; snapshot vs FK odluka | H | P0 |
| BusinessPartner | Catalog | Keep | Stabilan B2B entitet, nizak tehnički rizik | L | P1 |
| IntegrationSetting | Integrations | Merge | Ujednačiti provider model i smanjiti dupliranje konfiguracije | M | P2 |
| TrendSoftIntegrationSettings | Integrations | Merge | Konsolidacija sa IntegrationSetting radi jedinstvenog modela | M | P2 |
| StoreSettings | Settings | Redesign | Singleton obrazac bez tvrdih guard-ova i secret boundary rizik | M | P1 |
| BlogPost | Blog | Redesign | Author veza bez stroge FK validacije | M | P1 |
| BlogComment | Blog | Keep | Stabilan model sa predvidivim relacijama | L | P2 |

### 4.6 Impact Heatmap (programski dodir i lomovi)

| Entitet/Tabela | Contracts/DTO sloj | Services/Handlers | API sloj | Impact (1-5) |
|---|---|---|---|---|
| Product | Product* DTO familija | ProductService + zavisni tokovi | Products endpoints | 5 |
| Order | Order* DTO familija | OrderService / Orders tok | Orders endpoints | 5 |
| OrderItem | OrderItem DTO | OrderService (detail + totals) | Orders detail tok | 4 |
| WebUser | WebUser DTO + auth request-i | WebUserService | WebUsers + CustomerAuth | 4 |
| ProductImage | ProductImage DTO | image related servisi | Images endpoints | 4 |
| Category | Category DTO i tree tok | CategoryService | Categories endpoints | 3 |
| TaxRate | TaxRate DTO | TaxRateService | TaxRates endpoints | 3 |
| StoreSettings | StoreSettings DTO | StoreSettingsService | Settings endpoints | 3 |
| BlogPost | BlogPost DTO | BlogPostService | Blog endpoints | 3 |
| BusinessPartner | BusinessPartner DTO | BusinessPartnerService | BusinessPartners endpoints | 2 |
| Manufacturer | Manufacturer DTO | ManufacturerService | Manufacturers endpoints | 2 |
| BlogComment | BlogComment DTO | Blog tok | Blog comment tok | 2 |
| IntegrationSetting | IntegrationSetting DTO | IntegrationSettingsService | IntegrationSettings endpoints | 2 |
| TrendSoftIntegrationSettings | IntegrationSetting DTO sloj | IntegrationSettingsService | TrendSoft sync tok | 2 |
| User / Role / UserRole / RefreshToken | Identity DTO/Auth response | Identity/Auth servisi | Auth/Users endpoints | 1-2 |

### 4.7 Operativni zaključak pretresa

1. P0 blokatori su: Product, Order, OrderItem, WebUser split odluke.
2. P1 stabilizacija je: Category, StoreSettings, BlogPost i granice settings/integrations modela.
3. P2 cleanup je: integracije, sekundarni entiteti i finalna konsolidacija kontrakata.
4. Pre implementacije obavezno zaključati 10 otvorenih domen pitanja (discount, snapshot, identity split i ostalo).

## 6) Domain Policy Dokument (u izradi)

### Policy A - Pricing & Discount
1. Discount obračun je sekvencijalan: prvo Product, zatim BusinessPartner.
2. Implementacija mora imati test slučajeve za oba nivoa popusta i negativne slučajeve.

### Policy B - Order Data Semantics
1. Usvaja se hibridni model: ključna komercijalna istorija ostaje snapshot.
2. Reference ostaju gde ne ugrožavaju audit i istorijsku tačnost porudžbine.

### Policy C - Identity Boundary
1. User i WebUser ostaju odvojeni modeli.
2. Uvodi se shared IdentityLink za federaciju identiteta gde je potreban zajednički tok.

### Policy D - Blog Author Ownership
1. BlogPost autor se vezuje FK relacijom ka User entitetu.
2. Autorstvo je namenjeno zaposlenima (Kontrol korisnicima).

### Policy E - Category Lifecycle
1. Brisanje kategorije ide kroz soft delete.
2. Obavezno reassignment pravilo za proizvode i podkategorije pre finalnog gašenja.

### Policy F - StoreSettings Singleton
1. StoreSettings koristi explicit ID=1.
2. Baza mora imati unique guard da spreči više aktivnih redova.

### Policy G - External Sync Metadata
1. External sync metadata se standardizuje kroz shared model.
2. Pattern važi za sve sync entitete, ne samo jedan provider.

### Policy H - Product Core Evolution
1. Usvaja se Pragmatic put (Opcija 2) za Product segment.
2. Obavezni elementi: ProductPricing VO, centralizovan pricing service, i jasno odvajanje Product/Orders granica.

### Policy I - Federated Identity
1. User i WebUser ostaju odvojeni modeli.
2. Uvodi se IdentityLink kao federacioni most.
3. Customer auth dobija isti token lifecycle standard kao admin (refresh/revoke).

### Policy J - Secrets & Runtime Config
1. Tajne vrednosti (API keys/secrets) ne čuvaju se kao plain podaci u bazi.
2. Baza čuva reference/metapodatke, a realne tajne idu u secret store.
3. Primena promena ide kroz manual invalidate iz admin panela, bez restarta aplikacije.

### Policy K - Order Reliability Rules
1. Kod neuspelog plaćanja koristi se grace period, zatim rollback stock-a.
2. Tax se snima kao snapshot na nivou porudžbine/stavke u trenutku kreiranja.
3. Order model ide fazno: odmah Minimal Snapshot stabilizacija, zatim Two-phase inventory commit.

### Policy L - Blog Ownership & Moderation
1. Author ownership se vodi kroz FK-author pristup.
2. Moderation policy je stroža i eksplicitno definisana kroz approved-first pristup.

### Policy M - Data Access i Batch Standard
1. Standardni tok: entity-first (EF Core), bez raw SQL u trenutnoj fazi.
2. Za veće batch operacije obavezno: chunking, SaveChanges po batch-u, ClearChangeTracker i retry pravila.
3. Raw SQL ostaje odložen fallback i aktivira se tek posebnom odlukom kada EF pristup ne zadovolji zahteve.

## 7) Segment-By-Segment Program Review (nova faza)

Cilj: proći programske segmente jedan po jedan i zaključati:
1. Namenu segmenta.
2. Očekivano ponašanje.
3. Da li ostaje, menja se ili se deli.

Segmenti za review:
1. Product core (pricing, inventory, discount)
2. Order & OrderItem lifecycle
3. Identity + WebUser federacija
4. Settings + Integrations
5. Blog + Author ownership

### 7.1 Segment #1 - Product Core (pricing/inventory/discount)

Namena:
1. Centralni ecommerce agregat za cenu, zalihu, katalog prikaz i prodajne tokove.
2. Ključni input za Orders i Reporting.

Trenutno stanje:
1. Product nosi veliki broj polja i više poslovnih poddomena u jednom entitetu.
2. Pricing kalkulacije su rasute kroz Domain, Service i UI sloj.
3. OrderItem čuva snapshot podatke, ali pravilo snapshot-vs-reference nije formalno zaključano za sve scenarije.

Gap:
1. Ne postoji jedinstven pricing engine i jasna discount strategija kroz sve nivoe.
2. Kohezija Product modela je niska zbog mešanja pricing/inventory/SEO/sync detalja.
3. Modul granice Product-Orders su tehnički i domenski previše spojene.

Predlog promena (iz analize):
1. Opcija 1 Minimal: lokalno sređivanje bez dubljeg razdvajanja.
2. Opcija 2 Pragmatic: ProductPricing Value Object + centralni pricing service + Orders split + modularni DbContext pristup.
3. Opcija 3 Enterprise: pun aggregate overhaul sa širim opsegom i većim rizikom.

Preporuka:
1. Opcija 2 (Pragmatic) kao najbolji odnos rizik/dobit za trenutni overhaul.

### 7.2 Segment #3 - Identity + WebUser Federacija

Namena:
1. Razdvojeni korisnički svetovi: zaposleni (admin) i webshop kupci.
2. Potrebna kontrolisana federacija bez rušenja postojećeg sistema.

Trenutno stanje:
1. Admin auth koristi pun token lifecycle (access + refresh + revoke tok).
2. Customer auth je odvojen i jednostavniji tok (ad-hoc JWT, bez refresh token lifecycle-a).
3. User i WebUser su odvojeni modeli bez formalnog link mehanizma.

Gap:
1. Asimetričan auth model povećava operativni i security dug.
2. Nema formalne veze za scenario "ista osoba je i zaposleni i kupac".
3. Uloga kupca je tvrdo kodirana u token toku.

Predlog promena (iz analize):
1. A: minimalna standardizacija bez federacije.
2. B: potpuna unifikacija u jedan account model.
3. C: odvojeni modeli + IdentityLink federacija (inkrementalni put).

Preporuka:
1. Opcija C kao kontrolisan put: odvojene tabele ostaju, uvodi se IdentityLink i postepena auth standardizacija.

### 7.3 Segment #4 - Settings + Integrations

Namena:
1. Settings drži poslovnu konfiguraciju webshopa.
2. Integrations upravlja eksternim provider-ima i sync tokovima.

Trenutno stanje:
1. StoreSettings nosi i business i tehničke podatke, uključujući tajne vrednosti.
2. Integrations ima dualnost modela (specifičan TrendSoft model + generički model).
3. Provider tok nije potpuno standardizovan i teško je skalirati na više provajdera.

Gap:
1. Security rizik zbog secret podataka u modelima i API projekcijama.
2. Dupliranje konfiguracionih obrazaca i provider-specifična logika.
3. Nedovoljno jasno razdvajanje šta je business setting a šta infra secret/config.

Predlog promena (iz analize):
1. A: generički provider model kao primarni obrazac.
2. B: koegzistencija modela uz postepenu migraciju.
3. C: minimalni hotfix bez strukturne konsolidacije.

Preporuka:
1. Opcija A uz fazni rollout (najbolja dugoročna skalabilnost i čist security boundary).

### 7.4 Segment #2 - Order & OrderItem Lifecycle

Namena:
1. End-to-end tok porudžbine: kreiranje, statusi, plaćanje, isporuka i izveštavanje.
2. Finansijski i operativni centar webshop poslovanja.

Trenutno stanje:
1. OrderItem koristi mešavinu snapshot + reference podataka.
2. Inventory deduction postoji, ali ključne zaštite i rollback scenariji nisu dosledno zatvoreni.
3. Tax/discound tok nije kompletno standardizovan u kreiranju porudžbine.

Gap:
1. Potencijal za negativan stock i nekonzistentnost pri neuspelom plaćanju.
2. Nedovoljno eksplicitna politika šta je immutable snapshot, a šta live referenca.
3. Potreban jači transakcioni boundary između order write i inventory update toka.

Predlog promena (iz analize):
1. Opcija 1: Minimal Snapshot (preporučeno za brži i bezbedan pomak).
2. Opcija 2: Event/Saga pristup (kompleksnije, jače dugoročno).
3. Opcija 3: Two-phase inventory commit model.

Preporuka:
1. Opcija 1 kao početni rollout za Libra88, uz obavezne guard-ove i transakcije.

### 7.5 Segment #5 - Blog + Author Ownership

Namena:
1. Upravljanje sadržajem i komentarima uz moderaciju.
2. Jasno autorstvo i auditabilan sadržajni tok.

Trenutno stanje:
1. Author veza je fleksibilna, ali ownership integritet nije najjače definisan.
2. Komentari imaju osnovni moderation tok, uz prostor za strožu lifecycle kontrolu.

Gap:
1. Potrebna dosledna author ownership politika kroz ceo tok.
2. Potrebno jasnije definisati comment visibility/moderation pravila.

Predlog:
1. Ojačati author ownership model u skladu sa ranije odobrenim FK smerom.
2. Formalizovati comment moderation policy (approved-only vidljivost, soft-delete pravila gde je potrebno).

### 7.6 Cross-Cutting - Raw SQL i Batch Operacije

Namena:
1. Stabilne performanse za velike eksport/sync tokove.
2. Kontrolisano upravljanje memorijom i transakcijama pri batch obradi.

Trenutno stanje:
1. Batch pattern postoji, ali policy nije formalno zaključan po volumenu.
2. Raw SQL je izostavljen iz trenutnog scope-a radi smanjenja kompleksnosti.

Gap:
1. Potrebna jasna EF-only granica performansi i prag za eventualni kasniji fallback.
2. Nedostaje standard batch/memory playbook za velike setove podataka.

Predlog:
1. Definisati EF-only policy (LINQ + batch), bez SQL putanje u ovoj fazi.
2. Zaključati ChangeTracker cleanup i retry pravila po batch scenarijima.

## 8) Worker Handoff Plan (EF-Only Execution)

Cilj: plan spreman za Worker implementaciju bez SQL putanje, sa jasnim fazama i checkpoint-ovima.

### Faza W0 - Safety Baseline
- [ ] W0.1 Zaključati scope i freeze pravila po modulima.
- [ ] W0.2 Definisati backup/restore proceduru pre bilo kakvih EF migracija.
- [ ] W0.3 Potvrditi test gate: build + kritični integration testovi pre/posle svakog većeg koraka.
- Deliverable: sigurnosni gate i operativna spremnost.

### Faza W1 - Domain Skeleton Cleanup
- [ ] W1.1 WebUser izdvajanje ownership-a prema WebUsers granici.
- [ ] W1.2 Order/OrderItem ownership finalizacija prema Orders granici.
- [ ] W1.3 Product core refactor skeleton (VO granice bez API lomova).
- Deliverable: jasno razdvojene domenske granice pre dubljih migracija.

### Faza W2 - Data Model Triage (Keep/Redesign/Merge)
- [ ] W2.1 Keep tabele: potvrditi da ostaju bez strukturnog loma.
- [ ] W2.2 Redesign tabele: definisati ciljnu strukturu i migraciona pravila.
- [ ] W2.3 Merge tabele: definisati source->target mapiranje i fallback.
- Deliverable: zaključana tabela/data matrica za implementaciju.

### Faza W3 - Reliability Rules Implementation
- [ ] W3.1 Pricing engine centralizacija (entity-first).
- [ ] W3.2 Order reliability: stock guard + grace rollback + tax snapshot.
- [ ] W3.3 Identity federacija i token lifecycle parity.
- Deliverable: stabilni poslovni tokovi bez SQL intervencija.

### Faza W4 - Settings/Integrations Hardening
- [ ] W4.1 Secret boundary: secret store + DB reference model.
- [ ] W4.2 Integration provider model konsolidacija (generički provider).
- [ ] W4.3 Manual invalidate runtime config tok kroz admin panel.
- Deliverable: sigurna i operativno fleksibilna konfiguracija.

### Faza W5 - Validation, Dry-Run, Handoff Gate
- [ ] W5.1 Test matrix execution po modulima.
- [ ] W5.2 Dry-run checklista i rollback simulacija.
- [ ] W5.3 Finalni Worker handoff paket i redosled taskova.
- Deliverable: implementacioni paket spreman za izvršenje.

## 9) Tabela/Data Triage Matrica (radna verzija)

Legenda:
1. Keep = ostaje uz minimalne izmene.
2. Redesign = menja se struktura/politika.
3. Merge = konsolidacija u drugi model.

### 9.1 Identity
| Tabela | Akcija | Buduca namena | Status odluke |
|---|---|---|---|
| User | Keep | Zaposleni/admin identitet | ✅ |
| Role | Keep | RBAC | ✅ |
| UserRole | Keep | RBAC veza | ✅ |
| RefreshToken | Keep | Token lifecycle | ✅ |

### 9.2 Catalog / Core
| Tabela | Akcija | Buduca namena | Status odluke |
|---|---|---|---|
| Product | Redesign | Product core sa jasnim pricing/inventory granicama | ✅ |
| ProductImage | Keep | Media galerija proizvoda | ✅ |
| OemPartNumber | Keep | OEM reference | ✅ |
| Category | Redesign | Hijerarhija + soft delete + reassignment | ✅ |
| Manufacturer | Keep | Brand metadata | ✅ |
| TaxRate | Keep | Poreske stope | ✅ |
| BusinessPartner | Keep | B2B partner profil | ✅ |

### 9.3 Orders
| Tabela | Akcija | Buduca namena | Status odluke |
|---|---|---|---|
| Order | Redesign | Pouzdan lifecycle + snapshot/tax/rollback pravila | ✅ |
| OrderItem | Redesign | Snapshot + controlled references | ✅ |

### 9.4 WebUsers / Federacija
| Tabela | Akcija | Buduca namena | Status odluke |
|---|---|---|---|
| WebUser | Redesign | Customer identitet + federacija sa User | ✅ |
| IdentityLink (nova) | Add | Federacioni most User <-> WebUser | ✅ |

### 9.5 Settings / Integrations
| Tabela | Akcija | Buduca namena | Status odluke |
|---|---|---|---|
| StoreSettings | Redesign | Business settings bez plain secrets | ✅ |
| TrendSoftIntegrationSettings | Merge | Konsolidacija u generički provider model | ✅ |
| IntegrationSetting | Redesign/Merge Target | Primarni provider model | ✅ |

### 9.6 Blog
| Tabela | Akcija | Buduca namena | Status odluke |
|---|---|---|---|
| BlogPost | Redesign | FK author ownership + publishing policy | ✅ |
| BlogComment | Keep/Policy Update | Moderation i visibility pravila | ✅ |

### 9.7 Candidate za uklanjanje (tek posle stabilizacije)
| Stavka | Tip | Uslov za uklanjanje |
|---|---|---|
| Legacy TrendSoft specifična polja/tabela | Merge ostatak | Tek kada generic provider radi produkciono stabilno |
| Duplirane snapshot/reference kolone u Order tokovima | Refactor cleanup | Tek nakon potvrde audit potreba i regresionih testova |

## 10) Kolona-By-Kolona Pretres (operativni sažetak)

### 10.1 Opšti zaključak
1. Većina kolona ostaje (Keep) uz policy promene.
2. Najveći rizici su security tajne, legacy duplikati i JSON polja bez jasne šeme.
3. Triage je spreman da se prevede u Worker taskove po fazama.

### 10.2 Kandidati za hard delete odmah (faza 1)
1. StoreSettings.CloudinaryApiSecret: izbaciti iz baze nakon migracije na secret store.
2. TrendSoftIntegrationSettings.ApiKey: izbaciti iz baze nakon migracije na secret store.

Napomena:
1. Obe stavke se brišu tek kada aplikacija potvrđeno čita tajne iz secret store-a u svim tokovima.

### 10.3 Kandidati za hard delete kasnije
1. Product.Brand: uklanjanje nakon mapiranja na Manufacturer.
2. Legacy JSON kolone (Category.AttributeTemplate, Product.AdditionalAttributes): odluka posle validacije da li ostaju JSON ili idu u normalizovane tabele.

### 10.4 Merge/Rename kandidati
1. TrendSoftIntegrationSettings -> IntegrationSetting (postepena konsolidacija).
2. Standardizacija sync i audit obrazaca kroz zajedničke modele/metapodatke.

### 10.5 REVIEW stavke pre finalne odluke
1. Category.AttributeTemplate (JSON strategija).
2. Product.AdditionalAttributes (JSON strategija).
3. Order snapshot/reference granica po koloni (šta ostaje immutable).

### 10.6 Obavezne data transformacije pre cleanup-a
1. Product.Brand -> Manufacturer mapiranje.
2. Slug deduplikacija (Category/Manufacturer gde je potrebno).
3. Validacija enum i referentnih vrednosti pre striktnih ograničenja.

## 11) Worker Backlog (Task-by-Task, EF-Only)

### Sprint WB1 - Security i trenutni cleanup
- [ ] **WB1.1** Izvući `StoreSettings.CloudinaryApiSecret` u secret store i ukloniti polje iz modela/migracija.
- [ ] **WB1.2** Izvući `TrendSoftIntegrationSettings.ApiKey` u secret store i ukloniti polje iz modela/migracija.
- [ ] **WB1.3** Dodati verifikacioni test da nijedan secret ne izlazi kroz DTO/API.

### Sprint WB2 - JSON normalizacija (odmah)
- [ ] **WB2.1** Uvesti tabelu za category attribute definicije (normalizacija `Category.AttributeTemplate`).
- [ ] **WB2.2** Uvesti tabelu za product attribute vrednosti (normalizacija `Product.AdditionalAttributes`).
- [ ] **WB2.3** Napisati migracioni mapper iz postojećeg JSON modela u nove entitete.
- [ ] **WB2.4** Ukloniti legacy JSON kolone iz entiteta nakon uspešne migracije i verifikacije.

### Sprint WB3 - Order snapshot cleanup (odmah)
- [ ] **WB3.1** Definisati novu target strukturu OrderItem bez legacy snapshot kolona.
- [ ] **WB3.2** Migrirati postojeće podatke iz snapshot polja u ciljnu strukturu po odobrenoj policy logici.
- [ ] **WB3.3** Ažurirati service/DTO tokove koji trenutno zavise od snapshot kolona.
- [ ] **WB3.4** Ukloniti snapshot kolone iz modela nakon integracionih testova.

### Sprint WB4 - Product i relacije cleanup
- [ ] **WB4.1** Migrirati `Product.Brand` vrednosti na `Manufacturer` relaciju.
- [ ] **WB4.2** Ukloniti `Product.Brand` nakon mapiranja i data quality potvrde.
- [ ] **WB4.3** Proći sve Product query/projekcije da koriste novu normalizovanu strukturu atributa.

### Sprint WB5 - Integrations konsolidacija
- [ ] **WB5.1** Konsolidovati TrendSoft specifičnu konfiguraciju u generički IntegrationSetting model.
- [ ] **WB5.2** Uvesti tipizovanu validaciju konfiguracije po provider-u.
- [ ] **WB5.3** Očistiti legacy putanje nakon produkcione stabilizacije.

### Sprint WB6 - Završna validacija i gate
- [ ] **WB6.1** End-to-end test matrix (Catalog/Orders/Identity/Settings/Blog).
- [ ] **WB6.2** Data consistency audit posle svih migracija.
- [ ] **WB6.3** Finalni handoff paket za Worker izvršenje po redosledu WB1->WB6.

## 5) Predlog odluka za potvrdu

1. Da li ovaj okvir sprintova P0-P4 usvajamo kao zvaničan skeleton plana?
2. Da li želiš da prioritetno razradimo prvo P0 i P1 do task-level detalja (sa kompleksnostima i zavisnostima)?
3. Da li S1.4 (raspodela uloga) iz prethodnog plana sada zatvaramo u ovoj sesiji kao deo P0.4?
