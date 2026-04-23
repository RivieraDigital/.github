# 📋 Poster React Presentation Rewamp

**Sesija:** 2026-04-21
**Status:** ✅ Završen
**Izvor:** nova sesija

---

## Odluke

| # | Stavka | Odluka | Detalji |
|---|--------|--------|---------|
| 1 | Scope | ✅ Odobreno | Full site systematic rewamp za ceo React presentation sajt |
| 2 | Visual direction | ✅ Odobreno | Editorial luxury kao glavni premium smer |
| 3 | Execution style | ✅ Odobreno | Odmah full homepage + shared layout, pa rollout na ostale stranice |
| 4 | GSAP depth | ✅ Odobreno | Cinematic motion umesto samo restrained reveal-a |
| 5 | Rollout priority | ✅ Odobreno | Posle homepage prioritet imaju Services, Work, Contact, About, Industries i Products |
| 6 | Handoff style | ✅ Odobreno | Bez worker handoff-a; plan ostaje u sesiji kao ručni execution plan za sledeći chat |
| 7 | Next artifact | ✅ Odobreno | Pripremiti gotov prompt za drugi chat koji izvršava samo Sprint 1 |

---

## Plan (u izradi)

### Tehnički baseline

- Target aplikacija: Poster presentations React app `riviera-digital.com`
- Stack: Next 15 + React 19 + TypeScript
- GSAP core je već u dependency listi, ali React integracija još nije sistematizovana
- Prema GSAP React smernicama, motion foundation treba graditi preko `@gsap/react` + `useGSAP()` u client komponentama, uz `gsap.registerPlugin(useGSAP)` i `ScrollTrigger` tamo gde zaista treba
- Trenutni vizuelni smer je dobar, ali je UI i dalje dosta `boxed` kroz `container-wide`, `surface` i kartičnu hijerarhiju
- Trenutne animacije su CSS `reveal-up` + inline `animationDelay`, što nije dovoljno za cinematic premium osećaj
- Shared shell je centralizovan kroz `SiteShell`, `SiteHeader` i `SiteFooter`, pa shared rewamp treba krenuti odatle pre page rollout-a

### Predlog smera

1. Proširiti layout sistem tako da ključne sekcije mogu da dišu edge-to-edge bez gubitka čitljivosti
2. Podići premium osećaj kroz jaču art direkciju: veći kontrast sekcija, luksuzniji rhythm, pažljivije kompozicije i manje generičnih kartica
3. Uvesti GSAP kao zajednički motion sloj za hero, section transitions, parallax detalje i scroll reveal, ne kao dodatni efekat preko postojećeg CSS reveal-a
4. Raditi rewamp sistemski, ne samo hero sekciju, da ceo sajt deluje kao jedna nova verzija

### Glavni problemi koje rewamp mora da reši

1. Previše sekcija koristi isti ritam: `SectionHeading` + grid + kartica + CTA red
2. `surface` tretman je skoro svuda isti, pa premium delovi nemaju dovoljno ekskluzivan kontrast
3. Header trenutno izgleda kao izolovana kapsula umesto kao premium chrome za ceo sajt
4. Hero je najjači deo sajta, ali ostatak stranice ne nastavlja isti nivo art direkcije
5. Motion nema zajedničku režiju: postoji samo `reveal-up`, bez scrollytelling sloja i bez scene orchestration-a

### Dizajn principi za izvršavanje

1. Svaka top-level stranica mora imati makar jednu stvarno široku, edge-to-edge kompoziciju
2. Ne koristiti isti grid/card pattern u dve uzastopne sekcije bez jasnog razloga
3. Premium osećaj graditi kroz spacing, tipografsku hijerarhiju, tonalne prelaze i pažljivo kadriranje, ne kroz gomilanje efekata
4. GSAP koristiti kao režiju pogleda: entrance, emphasis, continuity, parallax detalji; ne animirati sve što se pojavi na ekranu
5. Reduced-motion fallback mora biti deo foundation sloja, ne naknadni patch

### Draft faze

### Sprint 1 — Shared foundation + homepage flagship
- [x] **1.1** Proširiti width sistem novim container nivoima za reading/editorial/full-bleed layout → `styles/tokens.css`, `styles/utilities.css`
- [x] **1.2** Prebaciti premium atmosphere sa izolovanih panela na ceo shell kroz layered background, noise, rings i section contrast pravila → `app/globals.css`, `components/layout/site-shell.tsx`
- [x] **1.3** Rewamp header i footer da deluju kao premium chrome sajta, a ne kao standardni capsule/card elementi → `components/navigation/site-header.tsx`, `components/layout/site-footer.tsx`, `app/globals.css`
- [x] **1.4** Uvesti GSAP React foundation: dodati `@gsap/react`, registrovati `useGSAP`, pripremiti shared reveal/scene helpers i reduced-motion guard → `package.json`, `lib/motion/reveal.ts`, eventualno novi helper u `lib/motion/*`
- [x] **1.5** Režirati homepage hero kao flagship full-bleed scene sa staged headline ulazom, floating aside akcentima i controlled parallax detaljima → `components/sections/home/home-hero.tsx`
- [x] **1.6** Razbiti uniformni homepage ritam tako da sekcije dobiju različite kompozicije umesto istog heading + grid obrasca → `components/sections/home/featured-services.tsx`, `components/sections/home/selected-work.tsx`, `components/sections/home/products-depth.tsx`, `components/sections/home/process-snapshot.tsx`, `components/sections/home/industries-focus.tsx`, `components/sections/shared/cta-panel.tsx`
- [x] **1.7** Smanjiti oslanjanje na generične kartice i podići editorial feel kroz asimetriju, veće slike, jači whitespace i manje ponavljanja `surface` tretmana → `components/cards/*`, `components/ui/section-heading.tsx`

### Sprint 2 — Sales-critical page rollout
- [x] **2.1** Services listing prevesti iz običnog kataloga u premium capability narrative sa wide bands, process proof i manje kartične monotonije → `app/(marketing)/services/page.tsx`, `components/sections/services/*`, `components/cards/service-card.tsx`
- [x] **2.2** Service detail template podići na nivo mini sales page-a sa motion chapter prelazima, proof blokovima i jačim CTA ritmom → `app/(marketing)/services/[slug]/page.tsx`, `components/sections/services/service-detail-page.tsx`
- [x] **2.3** Work listing i case study experience pretvoriti u showcase sa većim imagery fokusom, editorial pacing-om i GSAP section transitions → `app/(marketing)/work/page.tsx`, `app/(marketing)/work/[slug]/page.tsx`, `components/case-studies/*`, `components/cards/project-card.tsx`
- [x] **2.4** Contact page tretirati kao premium conversion endpoint sa manje forme-first osećaja i više trust/proof/intent vođenja → `app/(marketing)/contact/page.tsx`, `components/sections/contact/contact-form.tsx`

### Sprint 3 — Brand depth rollout
- [x] **3.1** About stranicu pretvoriti u studio narrative sa stronger founder/studio framing-om i manje generičnih info blokova → `app/(marketing)/about/page.tsx`
- [x] **3.2** Industries overview i detail stranice postaviti kao positioning layer sa punim sekcijama i specifičnim proof framing-om po niši → `app/(marketing)/industries/page.tsx`, `app/(marketing)/industries/[slug]/page.tsx`
- [x] **3.3** Products pregled podići iz liste proizvoda u product story layer koji povezuje Kontrol, Poster i Mozaik u ozbiljniji ekosistem narativ → `app/(marketing)/products/page.tsx`, `components/cards/product-card.tsx`
- [x] **3.4** How We Work i FAQ uskladiti sa premium vizuelnim jezikom da ne ostanu kao stari template ostaci → `app/(marketing)/how-we-work/page.tsx`, `app/(marketing)/faq/page.tsx`, `components/sections/shared/faq-list.tsx`

### Sprint 4 — Final polish i guardrails
- [x] **4.1** Responsive cleanup za široke sekcije, breakpoint compositing i mobile fallback gde full-bleed ne sme da razbije čitljivost
- [x] **4.2** Reduced-motion fallback i accessibility tuning za GSAP scene, posebno za hero i scroll-triggered sekcije
- [x] **4.3** Performance pregled animacija, slika, blur/gradient slojeva i layout paint cost-a
- [x] **4.4** Final content consistency pass da premium vizuelni smer prati i verbalni ton kroz ključne CTA i section naslove

### Definition of done

1. Homepage i sve glavne prodajne stranice više ne deluju kao niz sličnih kartičnih sekcija u istom width režimu
2. Shared shell ostavlja premium utisak i kada korisnik samo scroll-uje kroz više različitih stranica
3. GSAP je uveden kao pravi motion system preko React-friendly setup-a, bez oslanjanja na stari CSS `reveal-up`
4. Najmanje hero, selected work, service detail i contact experience imaju jasno režirane motion scene
5. Responsive i reduced-motion ponašanje ostaju uredni, bez lomljenja layout-a i bez napadnih animacija na mobile-u

### Preporučeni redosled izvršavanja

1. Završiti shared foundation pre nego što se krene u page-by-page rollout
2. Odraditi homepage do kraja kao referentni vizuelni standard
3. Posle toga širiti isti jezik na Services, Work i Contact kao prodajno najbitnije stranice
4. Tek onda zatvarati About, Industries, Products, How We Work i FAQ

### Prompt za sledeći chat — Sprint 1 only

Koristi ovaj prompt u novom chatu:

Radi samo Sprint 1 iz plana za React presentation rewamp u Poster projektu. Nemoj da praviš handoff, nemoj da pišeš novi plan, nego direktno implementiraj promene u kodu i proveri da build/typecheck prođu ako je moguće.

Kontekst:
- Projekat je Next 15 + React 19 + TypeScript app u `f:\Work\RivieraDigital\Poster\presentations\react\riviera-digital.com`
- Vizuelni cilj je premium editorial luxury, sa širim layout-om preko celog sajta i manje boxed/card osećaja
- Za animacije želim GSAP prema zvaničnim smernicama, sa React integracijom preko `@gsap/react` i `useGSAP()` u client komponentama gde ima smisla
- Nemoj raditi Sprint 2, 3 ili 4 osim ako je nešto minimalno neophodno da Sprint 1 radi ispravno

Scope za implementaciju je isključivo ovaj:

1. Shared foundation
- Proširi width sistem u `styles/tokens.css` i `styles/utilities.css` tako da postoje jasni nivoi za reading/editorial/full-bleed layout
- U `app/globals.css` i po potrebi `components/layout/site-shell.tsx` pomeri premium atmosphere sa izolovanih panela na ceo sajt: layered backgrounds, tonal contrast između sekcija, noise/rings gde pomažu, ali bez kiča
- Rewampuj `components/navigation/site-header.tsx` i `components/layout/site-footer.tsx` da deluju kao premium frame sajta, ne kao standardne capsule/card komponente

2. GSAP foundation
- Proveri dependency setup i dodaj `@gsap/react` ako nedostaje
- Uvedi React-friendly GSAP foundation umesto postojećeg CSS-only reveal pristupa iz `lib/motion/reveal.ts`
- Koristi `useGSAP()` u client komponentama, sa urednim cleanup-om i reduced-motion fallback-om
- Ako koristiš `ScrollTrigger`, registruj ga samo tamo gde zaista donosi vrednost
- Nemoj praviti motion spam; koristi GSAP kao cinematic orchestration layer

3. Homepage flagship
- Režiraj `components/sections/home/home-hero.tsx` kao full-bleed flagship hero sa jačim premium kompozicionim osećajem
- Hero treba da ima staged entrance za headline/copy/actions i kontrolisane dekorativne pokrete za aside elemente, bez prenatrpanosti
- Razbij uniformni ritam na homepage-u kroz sledeće fajlove:
	`components/sections/home/featured-services.tsx`
	`components/sections/home/selected-work.tsx`
	`components/sections/home/products-depth.tsx`
	`components/sections/home/process-snapshot.tsx`
	`components/sections/home/industries-focus.tsx`
	`components/sections/shared/cta-panel.tsx`
- Cilj je da sekcije više ne deluju kao isti pattern: heading + grid + cards + CTA row

4. Card/UI cleanup unutar Sprint 1
- Po potrebi prilagodi `components/cards/*` i `components/ui/section-heading.tsx`
- Smanji oslanjanje na isti `surface` tretman i generične kartice
- Zadrži postojeći content model; fokus je na layout-u, art direction-u i motion-u, ne na content rewrite-u

Obavezna pravila:
- Menjaj samo ono što je potrebno za Sprint 1
- Ne uvodi nepotrebne biblioteke osim `@gsap/react` ako treba
- Sačuvaj postojeći tech stack i idiome projekta
- Dizajn mora da izgleda namerno, široko i premium, ne kao generičan AI landing page
- Mobile i tablet moraju ostati uredni
- Reduced motion mora biti podržan

Na kraju:
- Sažmi šta je promenjeno
- Napiši koje si fajlove menjao
- Reci da li su build/typecheck prošli
- Ako nešto nisi mogao da završiš bez dodatne odluke, jasno navedi šta je ostalo otvoreno
