# 🎯 POSTER CONFIG - Braća Drinić

## Status
| Polje | Vrednost |
|-------|----------|
| **Distributer** | FF Programming (Miloš Ilić) |
| **Datum** | Januar 2026 |
| **Status** | ✅ Sajt okačen, ⏳ Čeka feedback / uplata €450 |
| **Tip** | Korporativni sajt (extended poster) |
| **Referenca** | mas-promet.com (bez webshop funkcionalnosti) |
| **Photography** | 🤝 **Luka Stupar** - stovarište i proizvodi (50€ paket) |

---

## 🚀 Development Progress

### ✅ Završeno (Januar 20, 2026) - Sesija 2

| Komponenta | Status | Napomena |
|------------|--------|----------|
| **Slike organizovane** | ✅ | Sve iz dump/ prebačeno u wwwroot/images/ |
| **Folder struktura** | ✅ | hero/, products/, gallery/, branding/, services/, projects/ |
| **Putanje ažurirane** | ✅ | NavBar, Footer, Home, About, Services, Projects |
| **JSON data fajlovi** | ✅ | categories, projects, services, products |
| **Lokalizacija kategorija** | ✅ | 4 jezika (sr-Latn, sr-Cyrl, en, ru) |
| **Scroll animacije** | ✅ | AOS-like sa Intersection Observer |
| **CSS animacije** | ✅ | fade-up, fade-left, fade-right, zoom-in |
| **Gallery layout** | ✅ | CSS Grid sa masonry efektom |
| **Logo integracija** | ✅ | NavBar + Footer + Favicon |
| **PWA manifest** | ✅ | Ažurirano sa logo ikonama |

### ✅ Završeno (Januar 19, 2026) - Sesija 1

| Komponenta | Status | Napomena |
|------------|--------|----------|
| **Projekat kreiran** | ✅ | `Vezir.Demo.Poster.BracaDrinic` |
| **Program.cs** | ✅ | Blazor WASM setup |
| **App.razor** | ✅ | Router + Layout |
| **MainLayout.razor** | ✅ | Responsive layout + NavMenu + Footer |
| **Home.razor** | ✅ | Hero, Stats, Services preview, CTA |
| **About.razor** | ✅ | Timeline, Values, Gallery |
| **Services.razor** | ✅ | 6 usluga sa ikonama |
| **Products.razor** | ✅ | Katalog kategorija |
| **ProductCategory.razor** | ✅ | Lista proizvoda po kategoriji |
| **ProductDetail.razor** | ✅ | Detalji proizvoda + galerija |
| **Projects.razor** | ✅ | Portfolio sa filterom |
| **Contact.razor** | ✅ | Forma + mapa + info |
| **LocalizationService** | ✅ | 4 jezika (sr-Latn, sr-Cyrl, en, ru) |
| **ProductService** | ✅ | Kategorije + proizvodi |
| **ProjectService** | ✅ | Projekti sa statusom |
| **CSS Styling** | ✅ | Navy/Cyan tema, responsive |
| **Lokalizacija** | ✅ | Sva 4 JSON fajla |
| **appsettings.json** | ✅ | Sultan email config |
| **Build & Run** | ✅ | Testiran, radi! |

### ⏳ U toku

| Zadatak | Status | Napomena |
|---------|--------|----------|
| **Kontakt podaci** | 🟡 | Čekaju se od klijenta |
| **SEO fajlovi** | 🟡 | robots.txt, sitemap.xml |

### 📋 TODO

- [ ] Dobiti kontakt podatke od klijenta (telefon, email, adresa)
- [ ] Testirati Sultan email integraciju
- [ ] SEO fajlovi (robots.txt, sitemap.xml)
- [ ] Deployment na Azure

---

## Osnovni podaci

| Polje | Vrednost |
|-------|----------|
| **Firma** | Braća Drinić |
| **Delatnost** | Stovarište građevinskog materijala |
| **Lokacija** | Novi Sad, Srbija |
| **Istorija** | 30+ godina poslovanja |
| **Telefon** | *TBD - čeka se od klijenta* |
| **Email** | *TBD - čeka se od klijenta* |
| **Adresa** | *TBD - čeka se od klijenta* |
| **Facebook** | *TBD* |
| **Instagram** | *TBD* |
| **Radno vreme** | *TBD* |

---

## Branding

### Boje
| Boja | Hex | RGB | Upotreba |
|------|-----|-----|----------|
| **Navy (Tamno plava)** | `#2E3192` | 46, 49, 146 | Primarni tekst, levi deo loga |
| **Cyan (Svetlo plava)** | `#00AEEF` | 0, 174, 239 | Akcenti, desni deo loga, linkovi |
| **Bela** | `#FFFFFF` | 255, 255, 255 | Pozadina |
| **Tamno siva** | `#333333` | 51, 51, 51 | Body tekst |
| **Svetlo siva** | `#F5F5F5` | 245, 245, 245 | Sekcije, kartice |

### Logo
- **Fajl:** `dump/braca drinic/logo.png`
- **Opis:** Dva srca/strelice koje se prepliću (braća, partnerstvo)
- **Verzije potrebne:**
  - [ ] logo.svg (vektorski)
  - [ ] logo-white.svg (za tamne pozadine)
  - [ ] favicon.ico
  - [ ] logo-192x192.png (PWA)
  - [ ] logo-512x512.png (PWA)

### Font
- **Naslovi:** Montserrat Bold ili Poppins Bold
- **Body:** Open Sans ili Roboto

---

## Struktura sajta

### 📄 Stranice

| # | Stranica | Ruta | Opis |
|---|----------|------|------|
| 1 | **Početna** | `/` | Hero + pregled svih sekcija + CTA |
| 2 | **O nama** | `/o-nama` | Istorija, vrednosti, galerija firme |
| 3 | **Usluge** | `/usluge` | Lista svih usluga |
| 4 | **Proizvodi** | `/proizvodi` | Katalog bez cena |
| 5 | **Projekti** | `/projekti` | Portfolio sa filterom |
| 6 | **Kontakt** | `/kontakt` | Forma + mapa + info |

---

### 🏠 Početna (`/`)

**Sekcije:**
1. **Hero** - Ko smo i čime se bavimo
   - Naslov: "Braća Drinić - Vaš partner u građevini od 1995."
   - Podnaslov: "Stovarište građevinskog materijala | Novi Sad"
   - CTA: "Kontaktirajte nas" / "Pogledajte proizvode"

2. **Statistike** (brojevi)
   - 30+ godina iskustva
   - 1000+ realizovanih projekata
   - 500+ proizvoda u ponudi
   - 100% posvećenost kvalitetu

3. **Pregled oblasti poslovanja**
   - Kartica: Usluge → link
   - Kartica: Proizvodi → link
   - Kartica: Projekti → link

4. **Izdvojene kategorije proizvoda** (katalog preview)
   - 6 glavnih kategorija sa slikama

5. **Izdvojeni projekti** (3 najnovija)

6. **Kontakt sekcija** (footer CTA)
   - Adresa, telefon, poziv na kontakt

---

### 📖 O nama (`/o-nama`)

**Najvažnija stranica za poverenje!**

**Sekcije:**
1. **Istorija firme**
   - Timeline: 1995 → danas
   - Ključni milestones

2. **Naše vrednosti**
   - Kvalitet
   - Pouzdanost
   - Iskustvo
   - Partnerski odnos

3. **Brojevi koji govore**
   - Godine poslovanja
   - Zadovoljni klijenti
   - Realizovani projekti

4. **Galerija**
   - Stovarište
   - Objekti
   - Tim (opciono)

---

### 🔧 Usluge (`/usluge`)

**Sve na jednoj stranici, bez podstranica.**

Predložene usluge (TBD - potrebna potvrda od klijenta):
1. Prodaja građevinskog materijala
2. Dostava materijala
3. Konsultacije za gradnju
4. Izrada ponuda
5. Tehnička podrška
6. Veleprodaja

Za svaku uslugu:
- Ikona
- Naziv
- Kratak opis (2-3 rečenice)

---

### 📦 Proizvodi (`/proizvodi`)

**Katalog BEZ CENA i bez online kupovine!**

**Struktura:**
```
/proizvodi                    → Lista kategorija
/proizvodi/[kategorija]       → Lista proizvoda u kategoriji
/proizvodi/[kategorija]/[id]  → Pojedinačni proizvod
```

**Predložene kategorije** (TBD):
1. Cement i veziva
2. Cigla i blokovi
3. Armatura i čelik
4. Izolacija
5. Krovni materijali
6. Keramika i pločice
7. Boje i lakovi
8. Alati i pribor

**Stranica proizvoda sadrži:**
- Naziv
- Opis
- Tehničke specifikacije
- Galerija slika
- ⚠️ "Cena i dostupnost na upit" - CTA za kontakt

---

### 🏗️ Projekti (`/projekti`)

**Portfolio realizovanih i aktuelnih projekata.**

**Filter po statusu:**
- ✅ Završeni
- 🔨 U toku
- 📋 U najavi

**Svaki projekat ima:**
- Naziv
- Status (badge)
- Kratak opis
- Galerija slika
- Godina realizacije

---

### 📞 Kontakt (`/kontakt`)

**Sekcije:**
1. **Info blok**
   - Adresa sa ikonom
   - Telefon(i)
   - Email
   - Radno vreme

2. **Google Mapa**
   - Embed lokacije stovarišta

3. **Kontakt forma**
   - Ime *
   - Email *
   - Telefon (opciono)
   - Poruka *
   - Submit → Sultan API

4. **Success message**
   - "Vaša poruka je uspešno poslata. Kontaktiraćemo vas u najkraćem roku."

---

## Tehnički zahtevi

### ✅ POTVRĐENE FUNKCIONALNOSTI

#### Osnovno
| # | Funkcionalnost | Status |
|---|----------------|--------|
| 1 | Mobile responsive | ✅ DA |
| 2 | SEO optimizacija (meta, sitemap, robots.txt, structured data) | ✅ DA |
| 3 | SSL/HTTPS | ✅ DA (Azure auto) |
| 4 | Lazy loading slika | ✅ DA |

#### Jezici (4 locale fajla)
| Kod | Jezik | Pismo |
|-----|-------|-------|
| `sr-Latn` | Srpski | Latinica |
| `sr-Cyrl` | Srpski | Ćirilica |
| `en` | Engleski | Latinica |
| `ru` | Ruski | Ćirilica |

#### Kontakt forma
| # | Funkcionalnost | Status |
|---|----------------|--------|
| 7 | Kontakt forma (ime, email, poruka) | ✅ DA |
| 8 | Sultan email integracija | ✅ DA |
| 9 | Telefon polje (opciono) | ✅ DA |
| 10 | Dropdown tip upita | ✅ DA |

#### Mapa & Social
| # | Funkcionalnost | Status |
|---|----------------|--------|
| 11 | Google Maps embed | ✅ DA |
| 12 | Više lokacija | ❌ NE |
| 13 | Facebook link | ✅ DA |
| 14 | Instagram link | ✅ DA |
| 15 | Viber/WhatsApp | ❌ NE |

#### Proizvodi (Katalog)
| # | Funkcionalnost | Status |
|---|----------------|--------|
| 16 | Pretraga proizvoda | ❌ NE |
| 17 | Filter po kategoriji | ✅ DA |
| 18 | Galerija slika (lightbox) | ✅ DA |
| 19 | "Pošalji upit" button | ❌ NE |
| 20 | PDF katalog download | 🟡 MOŽDA (later) |

#### Projekti
| # | Funkcionalnost | Status |
|---|----------------|--------|
| 21 | Filter po statusu | ❌ NE |
| 22 | Galerija slika (lightbox) | ✅ DA |
| 23 | Godina projekta | ✅ DA |

#### UI/UX
| # | Funkcionalnost | Status |
|---|----------------|--------|
| 24 | Dark/Light mode | ❌ NE |
| 25 | AOS animacije (scroll) | ✅ DA |
| 26 | Sticky navbar | ✅ DA |
| 27 | Back to top button | ✅ DA |
| 28 | Loading skeleton | ✅ DA |

#### Pravno & Praćenje
| # | Funkcionalnost | Status |
|---|----------------|--------|
| 29 | Cookie consent (GDPR) | ✅ DA |
| 30 | Google Analytics | ❌ NE |
| 31 | Facebook Pixel | ❌ NE |
| 32 | PWA | ❌ NE |
| 33 | Radno vreme u footeru | ✅ DA |
| 34 | Floating call button | ❌ NE |

---

## Šta se NE RADI

- ❌ Online prodaja / Korpa / Plaćanje
- ❌ Prikaz cena / lagera
- ❌ CMS/Admin panel
- ❌ Google Analytics / Facebook Pixel
- ❌ PWA
- ❌ Dark mode
- ❌ Pretraga proizvoda
- ❌ Filter projekata po statusu
- ❌ Viber/WhatsApp integracija

---

## Sadržaj - Status

| Sekcija | Status | Napomena |
|---------|--------|----------|
| Logo | ✅ Ima | PNG u dump folderu, treba integrisati |
| Boje | ✅ Implementirano | Navy #2E3192 + Cyan #00AEEF |
| Tekstovi | ✅ Placeholder | Implementirani placeholder tekstovi |
| Slike | 🟡 Placeholder | Koriste se placeholder URL-ovi |
| Kontakt info | ✅ Placeholder | Čeka se od klijenta |
| Proizvodi | ✅ Demo | 8 kategorija, demo proizvodi |
| Projekti | ✅ Demo | 6 demo projekata |

---

## Placeholder podaci (dok ne stignu pravi)

```
Adresa: Bulevar oslobođenja 100, Novi Sad
Telefon: +381 21 123 456
Email: info@bracadrinic.rs
Radno vreme: Pon-Pet 07:00-17:00, Sub 07:00-14:00
```

---

## Fajlovi projekta

```
src/demos/Vezir.Demo.Poster.BracaDrinic/
├── Components/
│   ├── App.razor
│   ├── Layout/
│   │   ├── MainLayout.razor
│   │   ├── MainLayout.razor.css
│   │   ├── NavMenu.razor
│   │   ├── Footer.razor
│   │   └── CookieConsent.razor
│   ├── Pages/
│   │   ├── Home.razor
│   │   ├── About.razor
│   │   ├── Services.razor
│   │   ├── Products.razor
│   │   ├── ProductCategory.razor
│   │   ├── ProductDetail.razor
│   │   ├── Projects.razor
│   │   └── Contact.razor
│   └── Shared/
│       ├── LanguageSwitcher.razor
│       ├── BackToTop.razor
│       ├── LoadingSkeleton.razor
│       └── ImageGallery.razor (lightbox)
├── Models/
│   ├── Product.cs
│   ├── Category.cs
│   ├── Project.cs
│   └── Service.cs
├── Services/
│   ├── LocalizationService.cs
│   ├── ProductService.cs
│   ├── ProjectService.cs
│   └── EmailService.cs (Sultan integration)
├── wwwroot/
│   ├── css/
│   │   ├── app.css
│   │   └── aos.css
│   ├── js/
│   │   ├── app.js
│   │   └── aos.js
│   ├── locales/
│   │   ├── sr-Latn.json
│   │   ├── sr-Cyrl.json
│   │   ├── en.json
│   │   └── ru.json
│   ├── images/
│   │   ├── logo.png
│   │   ├── logo-white.png
│   │   ├── hero/
│   │   ├── products/
│   │   ├── projects/
│   │   └── gallery/
│   ├── favicon.ico
│   └── index.html
├── Program.cs
├── appsettings.json
└── Vezir.Demo.Poster.BracaDrinic.csproj
```

---

*Dokument kreiran: Januar 2026*
*Poslednje ažuriranje: Januar 19, 2026 - Projekat kreiran i funkcionalan!*
