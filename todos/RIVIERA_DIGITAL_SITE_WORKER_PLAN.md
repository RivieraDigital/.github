# 📋 Riviera Digital Site — Worker Plan

**Status:** ✅ Faze 1-3 završene | 🔄 Faza 4 u toku
**Namena:** Handoff dokument za `worker` agenta
**Repo:** `Poster`
**Target folder:** `presentations/react/riviera-digital.com`

## Kako koristiti ovaj fajl

Ovaj dokument više nije samo brainstorming plan. Ovo je radni handoff za `worker` agenta koji treba da uradi kompletan prvi prolaz sajta.

`Worker` treba da:

- pročita ovaj fajl kao glavni izvor istine
- sprovede plan fazu po fazu
- ne zaustavlja se na scaffold-u ili parcijalnom layout-u
- isporuči kompletan prvi release koji može da se pokrene i pregleda
- samostalno donese neblokirajuće odluke u smeru premium flagship sajta

---

## 1. Glavni cilj

Napraviti novi `Riviera Digital` flagship sajt koji izgleda profesionalno, premium i marketinški zrelo, tako da može da postane glavni javni sajt firme za prodaju usluga, predstavljanje proizvoda i buduće marketing aktivnosti.

Ovo ne sme da ispadne još jedan demo ili generičan agency template. Sajt mora da deluje kao ozbiljan, pažljivo dizajniran digital studio/software company sa jasnom hijerarhijom sadržaja, dobrim SEO osnovama i dovoljno jakim vizuelnim identitetom da odmah ostavi dobar utisak.

---

## 2. Potvrđene odluke

- Stack: `Next.js` (`App Router`)
- Rešenje mora biti pogodno za `Docker` deployment
- Sajt je `high-end showcase`, ne brzi MVP
- Pozicioniranje je `hybrid`: usluge + proizvodi/platforme
- Homepage mora biti jak lead-generation entry point
- CTA model je kombinovan, ne jedan linearni funnel za sve korisnike
- Struktura treba da podrži više jezika kasnije, ali prvi release može ići sa jednim jezikom
- Startni jezik prvog release-a je `Croatian`
- Primarna publika je kombinacija lokalnih klijenata i ozbiljnijih B2B leadova
- Vizuelni smer naginje ka `creative studio` izrazu
- Prvi utisak treba da bude `moderan i tehnološki jak`
- Kolorni smer ide ka `toplom mediteranskom premium` izrazu
- Tipografski karakter ide ka `studio expressive` pristupu
- Nivo smelosti treba da bude `odmereno smelo`
- Vizuelni materijal treba da se oslanja na apstraktne oblike, svetlo/teksturne slojeve i stvarne prikaze rada
- Layout treba da koristi `editorial asymmetry` pristup
- Najistaknutije usluge su business websites, webshops, custom software, branding/digital presence, maintenance/growth support i automations/integrations
- Tone of voice treba da bude pristupačan i ljudski
- Glavna poruka sajta treba da se vrti oko sajtova i sustava koji ozbiljno predstavljaju i pokreću biznis
- `Products` ostaje posebna stavka u glavnoj navigaciji
- Proof sloj treba da bude `case study first`, bez fake brojki i naduvavanja
- Najistaknutiji projekti u prvom sloju su `Libra88`, `Filip Apartmani` i `Braća Drinić`
- U `Products` fokusu za prvi release su `Kontrol`, `Poster` i `Mozaik / Flux`
- Kontakt funnel treba da vodi i na upit za projekt i na zakazivanje konsultacija
- Postojeći Blazor Riviera sajt je samo referenca za sadržaj i teme, ne dizajn za kopiranje

---

## 3. Obavezni kriterijumi kvaliteta

Worker treba da napravi sajt koji ispunjava sledeće kriterijume:

- Vizuelno deluje premium i namerno dizajnirano
- Nema demo/template osećaj
- SEO osnova je dobra od prvog dana
- Animacije postoje, ali ne ubijaju performanse
- Responsive ponašanje je kvalitetno i na desktopu i na mobilnom
- Arhitektura je čista i pogodna za dalje širenje
- Sajt može da se pokrene i proveri lokalno nakon završetka
- Sve treba da bude spremno da se kasnije dorađuje stranicu po stranicu bez menjanja osnove

### Zabranjeno

- Kopirati postojeći Blazor sajt 1:1
- Koristiti generičan AI agency layout bez karaktera
- Izmišljati lažne metrike, testimonials, klijente ili rezultate
- Puniti sajt placeholder copy-jem koji zvuči prazno i generički
- Praviti “wow” animacije koje kvare UX ili usporavaju sajt

---

## 4. Poslovni cilj sajta

Sajt treba da radi tri stvari istovremeno:

1. Da generiše upite za usluge
2. Da pokaže dubinu kroz proizvode i sistemska rešenja
3. Da izgradi poverenje kroz radove, pristup i profesionalni identitet

To znači da sajt ne treba da bude ni čist product sajt, ni klasičan agency landing. Treba da spoji oba sveta, ali tako da prodaja i kredibilitet ostanu jasni.

---

## 5. Predlog informacione arhitekture

Ovo je trenutni radni predlog za prvi ozbiljan release:

### Core strane
- `Home`
- `Services`
- `Work`
- `Products`
- `About`
- `Contact`

### Dodatne strane za prvi release
- detaljne service strane
- case study detalji
- `How We Work` / process strana
- industry / niche strane
- `FAQ` / pricing-direction strana

Napomena: prvi release treba da bude širi od običnog “home + nekoliko podstrana” pristupa, ali prioritet završnosti mora biti pametno raspoređen.

## 5.1. Preporučeni sitemap v1

Ovo je preporučeni sadržajni opseg prvog worker prolaza:

### P0 stranice
- `Home`
- `Services`
- `Work`
- `Contact`
- 2 ključne detaljne service strane
- 1 do 2 ključna case study detalja

### P1 stranice
- `Products`
- `About`
- `How We Work`
- `FAQ` / pricing-direction
- preostale service detail strane

### P2 stranice
- `Industries` overview
- 2 do 3 industry detail strane
- dodatni case study template sistem

### Preporučeni detail fokus za prvi prolaz

#### Service detail prioritet
- `Business Websites`
- `Webshops / E-commerce`
- `Custom Software`
- `Automations / Integrations`

#### Case study prioritet
- `Libra88`
- `Filip Apartmani`
- `Braća Drinić`

#### Product fokus
- `Kontrol`
- `Poster`
- `Mozaik / Flux`

---

## 6. Prioritetni model za prvi worker prolaz

Worker treba da koristi `hybrid flagship` pristup:

### P0 — Najviši nivo završnosti
- `Home`
- `Services`
- `Work`
- `Contact`
- 2 ključne detaljne service strane
- 1 do 2 ključna case study detalja

### P1 — Jaka baza
- `Products`
- `About`
- `How We Work`
- `FAQ` / pricing-direction
- preostale service detail strane

### P2 — Dobra osnova za dalju iteraciju
- industry / niche overview
- 2 do 3 industry detail strane
- dodatni case study template sistem

Poenta: `worker` treba da uradi ceo prvi prolaz sajta, ali mora da zna koje stranice moraju izgledati najzrelije i najzavršenije već u prvoj verziji.

---

## 7. Faze rada za worker

## Faza 1 — Foundation ✅ ZAVRŠENA

### Cilj
Postaviti kvalitetnu osnovu projekta, layout sistem i vizuelni smer sajta.

### Worker treba da uradi
- inicijalizuje `Next.js` projekat u target folderu
- postavi folder strukturu koja podržava više strana i dalje širenje
- definiše globalni layout, header, footer i navigaciju
- postavi osnovni design system (`colors`, `type scale`, spacing, buttons, cards, section patterns)
- postavi osnovne motion/animation primitives
- pripremi metadata osnovu i SEO strukturu
- pripremi projekat za Docker pakovanje

### Očekivani rezultat
Jasna i kvalitetna osnova sajta na koju sve ostalo može da se gradi bez haosa.

## Faza 2 — Homepage i core conversion sloj ✅ ZAVRŠENA

### Cilj
Napraviti homepage koji odmah deluje ozbiljno i vodi korisnika kroz jasnu priču.

### Home treba da ima
- jak hero sa jasnom vrednošću
- proof / trust sloj bez lažnih brojki
- izdvojene usluge
- izdvojene projekte / radove
- products/platform capability blok
- kratak process snapshot
- CTA sekcije na više mesta
- završni strong conversion blok

### Napomena
Home ne sme da bude prenatrpan. Treba da deluje fokusirano i premium.

## Faza 3 — Core stranice ✅ ZAVRŠENA

### Cilj
Napraviti glavne stranice koje nose prodaju i kredibilitet.

### Obuhvat
- `Services`
- `Work`
- `Contact`
- `Products`
- `About`

### Očekivanje
Svaka strana mora imati jasan razlog postojanja. Nema filler sekcija samo da “popune sajt”.

## Faza 4 — Detail layer 🔄 U TOKU

### Cilj
Dodati dubinu kroz detaljne service i case study stranice.

### Obuhvat
- najmanje 2 detaljne service strane sa vrhunskim nivoom završnosti
- najmanje 1 do 2 case study strane sa kvalitetnom naracijom problema, rešenja i ishoda
- ostale detail strane mogu biti nešto lakše, ali moraju imati dobru bazu

## Faza 5 — Expansion layer

### Cilj
Dodati SEO i sadržajnu širinu bez rušenja fokusa.

### Obuhvat
- `How We Work`
- `FAQ` / pricing-direction
- industry overview
- industry detail strane

### Napomena
Ovo ne sme da deluje kao naknadno nalepljen sadržaj. Mora ostati deo jedinstvenog sistema sajta.

## Faza 6 — Polish i verifikacija

### Cilj
Završiti prvi release tako da može da se pokrene i pregleda kao celina.

### Worker treba da uradi
- responsive polishing
- motion tuning
- SEO metadata tuning po stranicama
- osnovni accessibility sanity check
- local run proveru
- Docker proveru ako je realno izvodljivo u tom prolazu

---

## 7.1. Očekivani deliverable-i

Na kraju prvog worker prolaza treba da postoje sledeći deliverable-i:

- kompletan `Next.js` projekat u `Poster/presentations/react/riviera-digital.com`
- višestranična struktura sajta, ne samo landing page
- jasan globalni layout sistem
- premium homepage sa jakom hijerarhijom i CTA logikom
- core stranice sa smislenim sadržajem i dizajnom
- najmanje 2 jaka service detail prikaza
- najmanje 1 do 2 jaka case study prikaza
- `Products` sloj sa fokusom na `Kontrol`, `Poster`, `Mozaik / Flux`
- SEO osnova po stranicama
- responsive ponašanje i motion sloj
- Docker osnova za kasnije pokretanje/deployment
- dokaz da projekat može da se build-uje i lokalno pokrene

## 7.2. Odobrena projektna struktura v1

Ovo je preporučena struktura za `presentations/react/riviera-digital.com`.

Cilj je da routing, sadržaj, sekcije, design sistem i assets budu jasno odvojeni, bez nepotrebnog over-engineeringa.

```text
presentations/react/riviera-digital.com/
├─ app/
│  ├─ (marketing)/
│  │  ├─ page.tsx
│  │  ├─ services/
│  │  │  ├─ page.tsx
│  │  │  └─ [slug]/page.tsx
│  │  ├─ work/
│  │  │  ├─ page.tsx
│  │  │  └─ [slug]/page.tsx
│  │  ├─ products/
│  │  │  └─ page.tsx
│  │  ├─ about/
│  │  │  └─ page.tsx
│  │  ├─ contact/
│  │  │  └─ page.tsx
│  │  ├─ how-we-work/
│  │  │  └─ page.tsx
│  │  ├─ faq/
│  │  │  └─ page.tsx
│  │  └─ industries/
│  │     ├─ page.tsx
│  │     └─ [slug]/page.tsx
│  ├─ api/
│  │  └─ contact/
│  │     └─ route.ts
│  ├─ globals.css
│  ├─ layout.tsx
│  ├─ robots.ts
│  └─ sitemap.ts
├─ components/
│  ├─ layout/
│  ├─ navigation/
│  ├─ sections/
│  │  ├─ home/
│  │  ├─ services/
│  │  ├─ work/
│  │  ├─ products/
│  │  ├─ about/
│  │  ├─ contact/
│  │  ├─ process/
│  │  └─ shared/
│  ├─ case-studies/
│  ├─ cards/
│  └─ ui/
├─ content/
│  └─ hr/
│     ├─ site.ts
│     ├─ navigation.ts
│     ├─ home.ts
│     ├─ services.ts
│     ├─ work.ts
│     ├─ products.ts
│     ├─ about.ts
│     ├─ contact.ts
│     ├─ faq.ts
│     ├─ how-we-work.ts
│     ├─ industries.ts
│     ├─ service-details/
│     ├─ case-studies/
│     └─ product-details/
├─ lib/
│  ├─ seo/
│  ├─ motion/
│  ├─ utils/
│  └─ constants/
├─ styles/
│  ├─ tokens.css
│  ├─ theme.css
│  └─ utilities.css
├─ public/
│  ├─ images/
│  │  ├─ brand/
│  │  ├─ work/
│  │  ├─ products/
│  │  ├─ textures/
│  │  └─ og/
│  └─ icons/
├─ Dockerfile
├─ .dockerignore
├─ next.config.mjs
├─ package.json
└─ tsconfig.json
```

### Pravila ove strukture

- `app/` sadrži routing, page composition i metadata entry points
- `components/` sadrži reusable UI i section blokove, ali ne i sav copy
- `content/hr/` odvaja sadržaj od komponenti i priprema teren za budući i18n
- `lib/` čuva SEO helper-e, motion helper-e i opšte util funkcije
- `styles/` drži design tokens i globalni stil sistem
- `public/images/` treba organizovati po nameni, ne kao jedan nepregledan folder

### Napomena

Ne treba preterati sa dubinom foldera. Ako neka oblast ostane mala, struktura može ostati plića dok ne poraste.

---

## 8. Šta treba da se nalazi na sajtu

Ovo je trenutni radni sadržajni okvir koji worker treba da prati.

## Home

### Uloga
Prvi utisak, pozicioniranje i usmeravanje korisnika dalje.

### Glavna poruka
Riviera Digital gradi sajtove i sustave koji ozbiljno predstavljaju i pokreću biznis.

### Sekcije
- hero
- credibility / proof strip
- services preview
- selected work
- products/platform depth block
- process snapshot
- industry relevance block
- CTA block

## Services

### Uloga
Jasno objasniti šta Riviera Digital radi i za koga.

### Treba da sadrži
- pregled glavnih usluga
- razlikovanje tipova usluga
- idealne klijente ili probleme koje rešavamo
- CTA prema kontaktu, konsultacijama ili ponudi

### Kandidati za detaljne service strane
- business websites
- e-commerce / webshops
- custom software / internal systems
- branding / digital presence / growth support
- maintenance / growth support
- automations / integrations

## Work

### Uloga
Da pokaže realan rad i ulije poverenje.

### Treba da sadrži
- pregled izdvojenih projekata
- filter ili grupisanje po tipu projekta ako ima smisla
- jasan prelaz ka detaljnim case study stranama

### Kandidati za case study fokus
- `Libra88`
- `Filip Apartmani`
- `Braća Drinić`
- `InnerBeauty`
- `SasaKitic`

### Prioritet za prvi proof sloj
- `Libra88`
- `Filip Apartmani`
- `Braća Drinić`

## Products

### Uloga
Da pokaže da Riviera ne nudi samo “uslugu”, nego ima i proizvodnu dubinu.

### Navigacija
`Products` treba da postoji kao posebna stavka u glavnom meniju.

### Treba da sadrži
- pregled platformi/proizvoda
- objašnjenje gde oni pomažu klijentima
- razliku između custom rada i productized delova sistema

### Kandidati
- `Kontrol`
- `Poster`
- `Porto`
- eventualno drugi interni sistemi ako imaju smisla za javni prikaz

### Prioritet za prvi release
- `Kontrol`
- `Poster`
- `Mozaik / Flux`

## About

### Uloga
Da da ljudski i profesionalni identitet firmi.

### Treba da sadrži
- ko je Riviera Digital
- pristup radu
- zašto postoji firma
- ko stoji iza nje / partnerstvo / način saradnje

## Contact

### Uloga
Glavna conversion tačka.

### Treba da sadrži
- jasan kontakt CTA
- više opcija za javljanje
- kratko objašnjenje šta korisnik dobija kada se javi
- forma koja ne deluje predugačko ili naporno

### Glavni ishodi
- upit za projekt
- zakazivanje konsultacija

## How We Work

### Uloga
Da smanji neizvesnost kod klijenta i objasni proces saradnje.

### Treba da sadrži
- korake saradnje
- kako izgleda projekat od ideje do isporuke
- kako komuniciramo
- šta klijent može da očekuje

## FAQ / Pricing Direction

### Uloga
Da rastereti prodajni razgovor bez zaključavanja u fiksan cenovnik ako to nije poželjno.

### Treba da sadrži
- kako prilazimo proceni projekta
- okvirne razlike između tipova angažmana
- najčešća pitanja
- CTA prema razgovoru ili proceni

## Industry / Niche strane

### Uloga
Da pomognu SEO-u i da pokažu da razumeš konkretne tipove biznisa.

### Kandidati
- građevina
- lokalni biznisi
- beauty / lifestyle
- uslužne delatnosti

---

## 9. CTA model

CTA ne treba da bude samo jedan.

Worker treba da gradi kombinovani CTA sistem:

- `Javite se` za opšti kontakt
- `Zakažite konsultacije` za ozbiljnije leadove
- `Pogledajte radove` za korisnike kojima prvo treba dokaz
- `Istražite usluge` za korisnike koji još nisu sigurni šta im treba
- `Pogledajte proizvode` za korisnike koje zanima dubina sistema

Poenta je da CTA prati nameru korisnika, a ne da svi dobiju isti slepi funnel.

## 9.1. Proof model

Poverenje treba graditi pre svega kroz:

- konkretne projekte
- case study logiku
- jasno objašnjene usluge i procese

Ne oslanjati se na lažne statistike, naduvane rezultate ili dekorativni social proof bez stvarne osnove.

---

## 10. SEO i sadržajna pravila

Worker treba da vodi računa o sledećem:

- svaka glavna strana treba da ima jasan SEO ugao
- metadata ne sme biti generička
- naslovi i podnaslovi treba da budu prirodni, ne keyword-spam
- treba postaviti osnovu za kasnije širenje sadržaja
- copy mora delovati zrelo, jasno i prodajno, bez praznih buzzword rečenica
- tone of voice treba da ostane ljudski i pristupačan, bez gubitka profesionalne težine

## 10.1. Copy pravila za worker-a

Copy treba da bude:

- na hrvatskom jeziku
- jasan, konkretan i prodajno inteligentan
- profesionalan bez korporativne ukočenosti
- pristupačan bez banalnosti
- fokusiran na probleme koje rešavamo i vrednost koju donosimo

Copy ne treba da bude:

- generičan agency filler
- pun praznih buzzword formulacija
- previše tehnički tamo gde korisnik traži jasnoću
- marketinški naduvan bez stvarnog oslonca u radu i projektima

---

## 11. Vizuelni smer

Vizuelni pravac još nije finalno zaključan, ali worker treba da pođe od sledećih smernica:

- moderan i premium
- topliji mediteranski premium ton, ali bez turističkog/hospitality osećaja
- kreativniji studio izraz, ali sa ozbiljnom business kontrolom
- tehnološki jak prvi utisak
- ozbiljan, ali ne sterilan
- izražen karakter, bez generičnog startup/template izgleda
- pažljivo korišćene animacije i transitions
- jaka i ekspresivnija tipografska hijerarhija
- odmereno smeo, ali upečatljiv art direction
- vizuelni materijal kroz apstraktne oblike, teksture i stvarne screenshot-ove rada
- editorial asymmetry kompozicija umesto previše pravilnog corporate grida

Worker može da predloži jači vizuelni koncept, ali mora ostati u okviru premium business sajta koji prodaje poverenje i kvalitet.

## 11.1. Vizuelni identitet v1 — radni draft

Ovo je radni art direction koji `worker` treba da koristi kao polazni sistem.

### Brand osećaj
- premium
- mediteranski topao, ali ne turistički
- studio karakter
- tehnološki kredibilan
- odmereno smeo

### Kolorni sistem — smer
- tamna `ink` baza za ozbiljnost i dubinu
- svetliji `stone` / `sand` tonovi za prostor i premium kontrast
- topli `copper` / `terracotta` akcenti za identitet i energiju
- po potrebi jedan hladniji `adriatic` ili `teal` signal za tehnološki balans

### Tipografski sistem — smer
- izražen display stil za hero i glavne naslove
- čitljiv, ozbiljan sans za body copy
- mogući tehnički akcent kroz mono ili uski utility stil u malim detaljima
- izbeći default corporate font osećaj

### Layout sistem — smer
- editorial asymmetry
- jaka sekcijska hijerarhija
- kombinacija širokih mirnih zona i vizuelno napetijih blokova
- ritam koji vodi kroz priču, a ne samo niz kartica jednake težine

### Vizuelni materijal — smer
- manje stock fotografija
- više stvarnih UI/screenshot prikaza gde imaju smisla
- apstraktni oblici, svetlosni slojevi, fine teksture i kontrolisani gradijenti
- systems/structure vizuelni motivi umesto generičnih tech ilustracija

### Komponente i površine
- velike hero površine sa jakom tipografijom
- kartice koristiti selektivno, ne kao dominantan sistem svuda
- kontrast između “premium editorial” sekcija i “technical proof” sekcija
- vizuelne separacije između usluga, rada i proizvoda moraju biti jasne

### Motion smer
- koristiti promišljene reveal animacije i sekcijski pacing
- hover interakcije treba da daju osećaj dubine i kvaliteta
- transitions treba da deluju precizno i premium, ne “flashy radi flashy”
- izbeći napadne efekte koji ruše čitljivost ili performanse

## 11.2. Odobreni palette i font sistem v1

Ovo je prvi konkretniji predlog za palette i tipografski sistem.

### Palette draft

- `Ink 950` — `#0F1316`
- `Ink 800` — `#1B2328`
- `Stone 100` — `#E9E1D6`
- `Sand 200` — `#D8C6A8`
- `Copper 500` — `#B86D47`
- `Terracotta 500` — `#C96B52`
- `Adriatic 600` — `#0F5F63`
- `Mist 50` — `#F7F3ED`

### Uloga boja

- `Ink` tonovi nose ozbiljnost, dubinu i tehnološki kredibilitet
- `Stone`, `Sand` i `Mist` daju premium vazduh i toplinu
- `Copper` i `Terracotta` daju identitet, energiju i editorial karakter
- `Adriatic` služi kao hladniji balans kada treba pojačati sistemski / tech signal

### Tipografski draft

- Display: `Syne`
- Body: `Instrument Sans`
- Utility / meta / microcopy akcent: `IBM Plex Mono`

### Zašto ovaj font sistem ima smisla

- `Syne` daje kreativniji studio potpis i dovoljno karaktera za hero i velike naslove
- `Instrument Sans` čuva čitljivost, ozbiljnost i dobar digitalni ritam za body copy
- `IBM Plex Mono` daje tehnički akcent u malim dozama bez preuzimanja celog identiteta

### Pravila za korišćenje tipografije

- display font koristiti selektivno, za hero, velike naslove i ključne editorial momente
- body font treba da nosi većinu copy-ja i navigacije
- mono koristiti samo za male labele, tehničke detalje, meta elemente i sitne proof akcente
- ne praviti sajt gde svaka sekcija viče istom snagom; tipografija mora da gradi ritam

### Napomena

Ako `Syne` ispadne previše glasan u praksi, rezervna sigurnija varijanta može biti `Sora`, ali polazna preporuka ostaje `Syne`.

---

## 12. Otvorene stvari za kasnije iteracije

Ovo ne blokira prvi worker prolaz, ali ostaje otvoreno za kasnije dorade:

- konačan izbor projekata za case studies
- finalni visual identity detalji
- kontakt forma backend / integracija
- dodatne industrijske strane
- finalna pricing komunikacija

---

## 13. Definicija uspeha prvog prolaza

Prvi worker prolaz je uspešan ako:

- postoji kompletan i pokrenut novi sajt
- sajt deluje kao ozbiljna osnova za flagship brend prezentaciju
- homepage i ključne strane ostavljaju profesionalan utisak
- informacijska arhitektura je jasna
- postoji dovoljan nivo sadržajne dubine da možemo dalje iterirati bez restartovanja projekta

---

## 14. Napomena za worker-a

Ako naiđeš na otvorene odluke koje nisu blokirajuće, izaberi najjači profesionalni smer koji podržava cilj premium flagship sajta. Ne vraćaj se na demo-logiku, ne pojednostavljuj bez potrebe i ne optimizuj za “što brže gotovo” ako to ruši kvalitet.

---

## 15. Izvršni brief za worker-a

Ispod je stroži izvršni brief. Ovo je deo koji `worker` treba direktno da prati.

### Zadatak

Napraviti kompletan prvi release novog `Riviera Digital` flagship sajta u `Poster` repou, u folderu `presentations/react/riviera-digital.com`, koristeći `Next.js` `App Router` pristup.

Ovo nije zadatak za izradu demo landing stranice niti za pravljenje čistog skeleton-a. Cilj je da se isporuči ozbiljna prva verzija javnog sajta koja već izgleda kao pravi premium business/creative studio sajt spreman za dalje fino doterivanje.

### Obavezni tehnički smer

- koristiti `Next.js`
- arhitektura mora biti pogodna za `Docker` deployment
- styling mora podržati high-end art direction bez oslanjanja na generičan UI framework izgled
- preferirati pristup koji omogućava jasan SEO po stranicama
- projekat mora imati jasnu osnovu za lokalni run i build verifikaciju
- strukturu projekta organizovati po odvojenim slojevima `app`, `components`, `content`, `lib`, `styles` i `public`
- `content/hr/` koristiti kao početni sadržajni sloj kako bi budući i18n bio moguć bez kasnijeg raspada strukture

### Obavezni poslovni smer

- sajt mora prodavati i usluge i dubinu kroz proizvode
- homepage mora biti jak lead-generation ulaz
- `Products` mora ostati posebna stavka u navigaciji
- copy mora biti na hrvatskom jeziku
- tone of voice mora biti ljudski, pristupačan i profesionalan
- trust treba graditi kroz realne projekte i case study logiku, ne kroz fake statistike ili izmišljene testimonials

### Obavezan vizuelni smer

- sajt mora delovati moderno i tehnološki jako u prve 3 sekunde
- vizuelni identitet treba da naginje ka `creative studio` izrazu sa business kontrolom
- izbeći sterilan corporate template izgled
- izbeći generičan AI-agency layout
- koristiti animacije promišljeno i sa merom
- koristiti topao mediteranski premium kolorni smer uz tehnološki balans
- koristiti ekspresivniji tipografski sistem i editorial asymmetry layout
- osloniti se na apstraktne oblike, teksture i stvarne screenshot-ove rada
- početni palette sistem treba da prati `Ink`, `Stone`, `Sand`, `Copper`, `Terracotta`, `Adriatic` i `Mist` logiku iz odobrenog v1 sistema
- početni font sistem treba da koristi `Syne` za display, `Instrument Sans` za body i `IBM Plex Mono` za utility/meta akcente

### Obavezan scope prvog prolaza

`Worker` treba da isporuči ceo prvi release, ne samo deo. Fokus završnosti rasporediti ovako:

#### Najviši nivo završnosti
- `Home`
- `Services`
- `Work`
- `Contact`
- 2 ključne service detail strane
- 1 do 2 ključna case study prikaza

#### Jaka baza
- `Products`
- `About`
- `How We Work`
- `FAQ` / pricing-direction
- preostale service detail strane

#### Dobra osnova
- `Industries` overview
- 2 do 3 industry detail strane
- dodatni case study template sistem

### Obavezni sadržajni akcenti

#### Najistaknutije usluge
- business websites
- webshops / e-commerce
- custom software
- branding / digital presence
- maintenance / growth support
- automations / integrations

#### Proof prioritet
- `Libra88`
- `Filip Apartmani`
- `Braća Drinić`

#### Products prioritet
- `Kontrol`
- `Poster`
- `Mozaik / Flux`

### Pravila izvođenja

- ne kopirati postojeći Blazor Riviera sajt 1:1
- koristiti postojeći Blazor sajt samo kao referencu za teme, sadržaj i polazni kontekst
- ne zaustavljati rad nakon setup-a, layout-a ili home stranice
- ne koristiti placeholder copy koji zvuči prazno ili generički
- ne izmišljati poslovne rezultate, statistike ili izjave klijenata
- samostalno rešavati neblokirajuće odluke u smeru premium flagship kvaliteta

### Validacija pre završetka

Pre završetka rada proveriti i prijaviti:

- da projekat build-uje
- da glavni tok sajta može lokalno da se pokrene i pregleda
- da nema očigledno polomljenih ruta ili praznih ključnih strana
- da `Home` i ključne P0 strane ostavljaju ubedljivo jači utisak od starog demo sajta
- da Docker osnova postoji ili je jasno objašnjeno šta još treba da bi bila završena

### Očekivani završni izveštaj worker-a

Na kraju rada `worker` treba da vrati:

- kratak sažetak šta je napravljeno
- listu glavnih stranica i detail stranica koje su implementirane
- glavne dizajnerske i arhitekturne odluke
- koje komande su korišćene za verifikaciju
- šta je ostalo kao najvažniji sledeći polish sloj

### Finalni handoff prompt v1

Radiš kao izvršni agent na `Poster` repou. Tvoj zadatak je da napraviš kompletan prvi release novog `Riviera Digital` sajta u folderu `presentations/react/riviera-digital.com` koristeći `Next.js App Router`. Ne pravi demo landing stranicu i ne zaustavljaj se na scaffold-u. Isporuči ozbiljnu prvu verziju višestraničnog flagship sajta koja već može da se pokrene i pregleda kao celina.

Sajt mora biti premium, moderan, vizuelno jak i marketinški zreo. Treba da izgleda kao ozbiljan creative studio / software partner sajt, ne kao generičan AI agency template. Fokus je na kombinaciji usluga i proizvoda, sa jakim homepage-om koji vodi ka leadovima, jasnim `Products` slojem, realnim proof modelom kroz projekte i case studies, i hrvatskim copy-jem koji je pristupačan, ljudski i profesionalan.

Vizuelni identitet treba da prati sledeći smer: topao mediteranski premium ton, ali bez turističkog osećaja; studio-expressive tipografija; editorial asymmetry raspored; apstraktni oblici, teksture i svetlosni slojevi uz stvarne screenshot-ove rada; promišljene i premium animacije koje pojačavaju iskustvo bez narušavanja performansi. Sajt treba da deluje odmereno smelo, sa jakim karakterom i tehnološki ozbiljnim utiskom već u prvim sekundama.

Kao početni dizajn sistem koristi odobreni v1 palette i font paket iz ovog dokumenta: `Syne` za display, `Instrument Sans` za body, `IBM Plex Mono` za utility/meta detalje, uz kolorni sistem zasnovan na `Ink`, `Stone`, `Sand`, `Copper`, `Terracotta`, `Adriatic` i `Mist` tokenima.

Kao početnu tehničku organizaciju koristi odobrenu projektnu strukturu iz ovog dokumenta, sa jasnim odvajanjem route layer-a, components layer-a, content layer-a i design token sloja.

Prioritet završnosti daj za `Home`, `Services`, `Work`, `Contact`, 2 ključne service detail strane i 1-2 case study strane. Zatim postavi jaku bazu za `Products`, `About`, `How We Work`, `FAQ` i preostale detail strane. Kao dodatni sloj postavi dobru osnovu za `Industries` i dalje SEO širenje.

Najvažniji proof projekti su `Libra88`, `Filip Apartmani` i `Braća Drinić`. Najvažniji product elementi su `Kontrol`, `Poster` i `Mozaik / Flux`. Nemoj izmišljati statistike, testimonials ili rezultate. Ako neka odluka nije blokirajuća, preseci je sam u smeru jačeg premium flagship kvaliteta.

Na kraju obavezno proveri build, lokalni run i osnovnu spremnost za Docker, pa vrati jasan sažetak implementacije, glavne odluke, verifikaciju i sledeće važne polish tačke.

Minimum očekivanja pre zatvaranja zadatka:

- postoji realan višestranični sajt, ne samo skeleton
- `Home` izgleda kao flagship ulazna strana, ne template hero + par kartica
- postoji jasan `Services`, `Work`, `Products`, `About` i `Contact` sloj
- postoje najmanje 2 ozbiljne service detail strane
- postoji najmanje 1-2 konkretna case study prikaza
- vizuelni identitet je konzistentan kroz više strana
- projekat može da se build-uje i pokrene lokalno

---

## 16. Handoff Summary

### Šta worker treba da napravi
- kompletan prvi release novog `Riviera Digital` sajta
- `Next.js App Router` projekat u `presentations/react/riviera-digital.com`
- višestranični flagship marketing sajt, ne demo landing page
- premium vizuelni identitet sa toplim mediteranskim premium smerom
- jasan spoj usluga, proizvoda i case-study proof modela

### Najvažniji prioriteti
- vrhunski `Home`
- jaki `Services`, `Work` i `Contact`
- najmanje 2 ozbiljne service detail strane
- najmanje 1-2 case study strane
- dobra baza za `Products`, `About`, `How We Work`, `FAQ` i `Industries`

### Obavezni sistemi
- odobrena projektna struktura v1
- odobreni palette i font sistem v1
- hrvatski copy
- kombinovani CTA model
- Docker-ready smer
- SEO-ready višestranična arhitektura

### Najvažniji proof i product fokus
- proof: `Libra88`, `Filip Apartmani`, `Braća Drinić`
- products: `Kontrol`, `Poster`, `Mozaik / Flux`

### Šta worker ne sme da uradi
- da isporuči samo skeleton ili samo jednu stranu
- da kopira stari Blazor sajt 1:1
- da koristi generičan AI agency template izgled
- da izmišlja metrike, testimonials ili rezultate

### Šta worker treba da vrati na kraju
- šta je implementirano
- koje su stranice završene
- koje su glavne dizajnerske i arhitekturne odluke
- kako je verifikovan build / run
- šta je ostalo kao sledeći polish sloj

---

## 17. Copy-ready handoff block

Ako želiš da ovo pošalješ workeru bez dodatnog objašnjavanja, koristi ovaj blok zajedno sa celim dokumentom iznad:

Pokreni implementaciju po planu iz ovog fajla i tretiraj ga kao glavni izvor istine za prvi release sajta. Radiš na `Poster` repou i praviš novi `Riviera Digital` flagship sajt u `presentations/react/riviera-digital.com` koristeći `Next.js App Router`. Ne zaustavljaj se na scaffold-u, layout-u ili jednoj landing strani. Isporuči kompletan prvi prolaz višestraničnog sajta sa fokusom na `Home`, `Services`, `Work`, `Contact`, ključne service detail strane i ključne case study prikaze. Koristi odobrenu projektnu strukturu, odobren palette/font sistem, hrvatski copy i premium creative-studio art direction iz ovog dokumenta. Na kraju obavezno prijavi šta je završeno, kako je verifikovan build/run i šta ostaje kao sledeći polish sloj.
