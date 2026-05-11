# 🧑‍💻 PORTFOLIO SITE CONFIG - Saša Kitić

## Status
| Polje | Vrednost |
|-------|----------|
| **Tip** | Portfolio / CV Website |
| **Domen** | sasakitic.rs |
| **Datum** | Januar 2026 |
| **Status** | 🟡 IN PROGRESS - Frontend 90% |
| **Cena domena** | 3,300 RSD/godišnje (plaćeno) |
| **Projekat** | `Vezir.Demo.Poster.SasaKitic` |
| **Dev Server** | http://localhost:5280 |
| **Last Build** | ✅ Januar 21, 2026 |

---

## 📋 Osnovni podaci

| Polje | Vrednost |
|-------|----------|
| **Ime** | Saša Kitić |
| **Titula** | Software Engineer |
| **Lokacija** | Novi Sad, Srbija (iz Pečinaca) |
| **Email** | sasakiticsanz@gmail.com |
| **Telefon** | +381 63 787 3897 |
| **LinkedIn** | [linkedin.com/in/sasa-kitic-925701183](https://linkedin.com/in/sasa-kitic-925701183) |
| **GitHub** | [github.com/sanz1999](https://github.com/sanz1999) |

---

## 🎨 Branding

### Boje (Modern Dark Tech Theme)
| Boja | Hex | CSS Variable | Upotreba |
|------|-----|--------------|----------|
| **Deep Navy** | `#0D1B2A` | `--bg-primary` | Pozadina, header, footer |
| **Dark Surface** | `#1B263B` | `--bg-secondary` | Kartice, sekcije |
| **Electric Cyan** | `#00D9FF` | `--accent-primary` | CTA, linkovi, highlights |
| **Soft Purple** | `#7B68EE` | `--accent-secondary` | Hover, gradijenti |
| **White** | `#FFFFFF` | `--text-primary` | Glavni tekst |
| **Light Gray** | `#94A3B8` | `--text-secondary` | Sekundarni tekst |
| **Success Green** | `#10B981` | `--success` | Skills, badges |

### Gradijent opcije
```css
/* Hero gradient */
background: linear-gradient(135deg, #0D1B2A 0%, #1B263B 50%, #0D1B2A 100%);

/* Accent gradient */
background: linear-gradient(90deg, #00D9FF 0%, #7B68EE 100%);

/* Card glow effect */
box-shadow: 0 0 20px rgba(0, 217, 255, 0.1);
```

### Logo
- **Tip**: Text-based ili custom monogram "SK"
- **Stil**: Minimalistički, tech vibe
- **Verzije potrebne**:
  - [ ] logo.svg (primary)
  - [ ] favicon.ico
  - [ ] og-image.png (1200x630 za social sharing)

### Fontovi
| Tip | Font | Weight | Upotreba |
|-----|------|--------|----------|
| **Naslovi** | Inter / Space Grotesk | 600-800 | H1-H6 |
| **Body** | Inter | 400-500 | Paragraf, liste |
| **Code** | JetBrains Mono / Fira Code | 400 | Code snippets |

### Stil inspiracija
- Moderna dark tema (GitHub dark, VS Code dark)
- Čiste linije, puno whitespace
- Subtle animacije
- Tech/Developer vibe
- Minimalistički ali impresivan

---

## 🌍 Jezici

| Kod | Jezik | Status |
|-----|-------|--------|
| `sr-Latn` | Srpski (Latinica) | ✅ Primary |
| `en` | Engleski | ✅ Secondary |
| `de` | Nemački | ✅ Tertiary |

---

## 📄 Stranice

### 1. Početna / Hero (`/`)
**Komponenta**: `Home.razor`

**Sekcije**:
| # | Sekcija | Opis | Status |
|---|---------|------|--------|
| 1 | **Hero** | Ime + titula + tagline + CTA | ⬜ |
| 2 | **Quick Stats** | Godine iskustva, projekti, tehnologije | ⬜ |
| 3 | **About Preview** | Kratko o meni + link ka About | ⬜ |
| 4 | **Skills Overview** | Top 6-8 tehnologija sa ikonama | ⬜ |
| 5 | **Featured Projects** | 3 istaknuta projekta (kartice) | ⬜ |
| 6 | **Experience Timeline** | Kratka vremenska linija | ⬜ |
| 7 | **CTA** | "Hajde da radimo zajedno" + kontakt | ⬜ |

**Hero sadržaj**:
```
Zdravo, ja sam Saša 👋
Software Engineer

Gradim moderne web aplikacije sa .NET, Blazor i PostgreSQL.
Koliko je bitno to što pravimo, toliko je bitno šta to čini za vas.

8+ godina programiranja | Novi Sad, Srbija

[Pogledaj portfolio]  [Kontaktiraj me]
```

### 2. O meni (`/about`)
**Komponenta**: `About.razor`

**Sekcije**:
| # | Sekcija | Opis | Status |
|---|---------|------|--------|
| 1 | **Page Header** | Breadcrumb | ⬜ |
| 2 | **Bio** | Detaljna priča o meni | ⬜ |
| 3 | **Philosophy** | Pristup radu, šta me pokreće | ⬜ |
| 4 | **Fun Facts** | Lične stvari, hobiji | ⬜ |
| 5 | **CV Download** | PDF download dugme | ⬜ |

**Bio tekst predlog**:
```
Software Engineer sa 8+ godina iskustva u programiranju. Trenutno radim u 
2DSoft-u na enterprise .NET aplikacijama, dok u slobodno vreme razvijam 
Vezir platformu - modularni sistem za poster sajtove i webshop rešenja.

Verujem da dobra arhitektura razdvaja dobre od loših proizvoda. Učim radeći 
na PRAVIM projektima, ne iz knjiga. Svaki minut mora da se računa.

Cilj: Software Architect
```

**Filozofija / Šta me pokreće** (PROMINENTNO NA SAJTU):
```
🔗 POVEZIVANJE JE MOJA STRAST

Najviše volim trenutak kada uspem da spojim više komplikovanih komponenti 
u jednu celinu koja funkcioniše. Ako to uspem - znači da sam sve razumeo 
kako treba. To me vozi dalje.

U firmi pravim framework u kome drugi ljudi rade. Dizajniram biblioteke i 
sisteme koji omogućavaju drugima da budu produktivniji. Kada moj kod postane 
temelj na kome drugi grade - to je najveća satisfakcija.

📦 GRADIM BIBLIOTEKE, NE SAMO APLIKACIJE

Vezir Flux, Sultan API, interni framework-i... Volim da napravim nešto što 
će drugi koristiti. Nešto što rešava problem jednom, a pomaže mnogo puta.

💼 UNAPREĐUJEM VAŠE POSLOVANJE

Koliko je bitno to što pravimo, toliko je bitno šta to čini za vas. 
Tehnologija nije cilj - cilj je da vaš posao radi bolje, brže, efikasnije.
```

### 3. Iskustvo (`/experience`)
**Komponenta**: `Experience.razor`

**Timeline sadržaj**:

| Period | Pozicija | Firma | Opis |
|--------|----------|-------|------|
| **Jul 2023 - Danas** | Software Engineer | **2DSoft** | Hotelski PMS (Hotelier), UI biblioteka (One.Shell) |
| **Jan 2023 - Apr 2023** | Team Leader | **Amida IT** | PDF NuGet package, vođenje tima |
| **Nov 2022 - Apr 2023** | Software Engineer | **Amida IT** | Web aplikacije, E2E testiranje |
| **Okt 2022 - Nov 2022** | Intern | **Amida IT** | Internship program |

**2DSoft detalji**:
```
🏨 Hotelier (~1.5 godine) - 2DSoft proizvod
- Hotelski Property Management System
- Migracija finansijskog sistema iz Delphi → WinForms
- .NET Framework 4.8.2

🍽️ Garson - 2DSoft proizvod
- Restoranski sistem
- (dodati detalje)

🎨 Interni UI Framework (~1+ godina)
- UI Component Library za interne potrebe
- Dizajn sistema i komponenti koje koriste drugi developeri
- Framework u kome kolege rade - ja postavljam temelje
- .NET Core
```

**Amida IT detalji**:
```
Brzi rast: Intern → Engineer → Team Leader za 6 meseci

Projekti:
- PDF Management NuGet Package (Team Leader)
- Order Processing Application
- Claim Processing Application  
- Resubmission Management Application

Tech: C#, ASP.NET, Cypress, NUnit, FluentAssertions
```

### 4. Portfolio / Projekti (`/projects`)
**Komponenta**: `Projects.razor`

**Kategorije projekata**:
| Kategorija | Ikona | Opis |
|------------|-------|------|
| **Enterprise** | 🏢 | 2DSoft projekti |
| **Platform** | 🚀 | Vezir ekosistem |
| **Client Work** | 👥 | Klijentski posteri/webshopovi |
| **Freelance** | 💼 | Raniji projekti |

**Projekti za prikazati**:

| Projekat | Tip | Tech Stack | Link | Status |
|----------|-----|------------|------|--------|
| **Vezir Platform** | Platform | .NET 10, Blazor, PostgreSQL | - | 🟢 Active |
| **Braća Drinić** | Poster | Blazor WASM, Sultan API | bracadrinic.sasakitic.rs | 🟡 Demo |
| **TopWearShop** | WebShop | Blazor WASM, Kontrol CMS | topwearshop.sasakitic.rs | 🟡 Demo |
| **Filip Apartmani** | Poster | Blazor WASM | filipapartmani.sasakitic.rs | 🟢 Live |
| **Libra88 AutoService** | Poster | Blazor WASM | libra88.sasakitic.rs | 🟢 Live |
| **Sultan Email API** | API | .NET, Azure | sultan.sasakitic.rs | 🟢 Live |
| **Hotelier PMS** | Enterprise | .NET Framework, WinForms | - | 🏢 2DSoft |
| **One.Shell** | UI Library | .NET Core | - | 🏢 2DSoft |
| **Queens Beauty** | Desktop | WPF, Barcode Reader | - | ✅ Delivered |

**Project Card sadržaj**:
```
[Slika/Screenshot]

Naziv Projekta
Kratak opis (1-2 rečenice)

Tech: [.NET] [Blazor] [PostgreSQL]

[View Demo] [GitHub]
```

### 5. Skills (`/skills`)
**Komponenta**: `Skills.razor`

**Kategorije skillova**:

#### Backend
| Skill | Level | Years |
|-------|-------|-------|
| C# | ██████████ Expert | 8 |
| .NET / ASP.NET | █████████░ Advanced | 6 |
| Entity Framework | ████████░░ Advanced | 5 |
| PostgreSQL | ████████░░ Advanced | 4 |
| REST APIs | █████████░ Advanced | 6 |
| SOAP / WCF | ███████░░░ Intermediate | 3 |

#### Frontend
| Skill | Level | Years |
|-------|-------|-------|
| Blazor / WASM | █████████░ Advanced | 3 |
| HTML / CSS | █████████░ Advanced | 8 |
| JavaScript | ████████░░ Advanced | 6 |
| Angular | ███████░░░ Intermediate | 2 |
| WPF / XAML | ████████░░ Advanced | 4 |
| WinForms | ████████░░ Advanced | 3 |

#### DevOps & Tools
| Skill | Level |
|-------|-------|
| Git | █████████░ Advanced |
| Azure | ███████░░░ Intermediate |
| Docker | ██████░░░░ Intermediate |
| CI/CD | ██████░░░░ Intermediate |
| VS / VS Code | ██████████ Expert |

#### Testing
| Skill | Level |
|-------|-------|
| NUnit | ████████░░ Advanced |
| Cypress | ███████░░░ Intermediate |
| FluentAssertions | ████████░░ Advanced |

#### Other
| Skill | Level |
|-------|-------|
| MSGraph API | ███████░░░ Intermediate |
| NuGet Packages | ████████░░ Advanced |
| Delphi Migration | ███████░░░ Intermediate |
| Python | ██████░░░░ Intermediate |
| C/C++ | ██████░░░░ Intermediate |

**Prikaz opcije**:
- Grid sa ikonama (devicons)
- Progress bars
- Tag cloud
- Interaktivni hover efekti

### 6. Edukacija (`/education`)
**Komponenta**: `Education.razor` (može biti deo About stranice)

| Period | Institucija | Smer | Lokacija |
|--------|-------------|------|----------|
| **2019 - 2023** | Fakultet Tehničkih Nauka | Primenjeno Softversko Inženjerstvo | Novi Sad |
| **2014 - 2018** | ETŠ "Nikola Tesla" | Računarski tehničar | Sremska Mitrovica |

### 7. Kontakt (`/contact`)
**Komponenta**: `Contact.razor`

**Sekcije**:
| # | Sekcija | Opis |
|---|---------|------|
| 1 | **Contact Info** | Email, telefon, lokacija |
| 2 | **Social Links** | LinkedIn, GitHub |
| 3 | **Contact Form** | Ime, email, poruka |
| 4 | **Availability** | Status za nove projekte |

**Kontakt forma**:
| Polje | Tip | Obavezno |
|-------|-----|----------|
| Ime | Text | ✅ |
| Email | Email | ✅ |
| Tema | Select | ❌ |
| Poruka | Textarea | ✅ |

**Teme za select**:
- Saradnja na projektu
- Konsultacije
- Zaposlenje
- Ostalo

**Availability sekcija**:
```
📊 Trenutni status: Zaposlen (2DSoft)
💼 Otvoren za: Freelance projekte, konsultacije
⏰ Response time: Obično 24-48h
```

---

## 🔗 Poddomeni (Demo projekti)

| Poddomen | Projekat | Status |
|----------|----------|--------|
| `sasakitic.rs` | Portfolio (ovaj sajt) | ⬜ Planned |
| `bracadrinic.sasakitic.rs` | Braća Drinić poster | ⬜ Deploy |
| `topwearshop.sasakitic.rs` | TopWearShop webshop | ⬜ Deploy |
| `libra88.sasakitic.rs` | Libra88 AutoService | ⬜ Deploy |
| `filipapartmani.sasakitic.rs` | Filip Apartmani | ⬜ Deploy |
| `kontrol.sasakitic.rs` | Kontrol CMS demo | ⬜ Later |
| `sultan.sasakitic.rs` | Sultan API docs | ⬜ Later |

---

## ✅ Funkcionalnosti

### Implementirano ✅
- [x] Responsive dizajn (mobile-first)
- [x] Dark theme (primary) - Glassmorphism style
- [x] Smooth scroll animacije (animate-on-scroll)
- [x] SEO optimizacija
- [x] Open Graph tagovi
- [x] Structured Data (Person schema)
- [x] Kontakt forma (Sultan API integracija)
- [x] Language switcher (sr/en/de) - 3 jezika!
- [x] Back to top button
- [x] Loading screen
- [x] 404 stranica
- [x] Sitemap.xml
- [x] Robots.txt
- [x] Manifest.json (PWA ready)
- [x] **Constellation Background** - Interaktivne čestice koje se PRIVLAČE ka mišu!
- [x] Project filtering po kategorijama

### TODO 🟡
- [ ] CV PDF download (čeka PDF)
- [ ] Lazy loading slika
- [ ] Profesionalna profilna slika (placeholder za sad)
- [ ] Project screenshots
- [ ] Light theme toggle (optional)

### Nice to have (Later)
- [ ] Typing animation u hero
- [ ] Blog sekcija
- [ ] Copy email button
- [ ] Scroll progress indicator

### Nije potrebno ❌
- [ ] CMS/Admin panel
- [ ] User auth
- [ ] Comments
- [ ] Newsletter

---

## 📧 Email (Sultan API)

| Email | Trigger | Sadržaj |
|-------|---------|---------|
| Contact Form | Form submit | Ime, email, tema, poruka |
| Auto-reply | Form submit | "Hvala na poruci, javiću se uskoro" |

**Sultan config**:
```json
{
  "EmailSettings": {
    "ApiEndpoint": "https://sultan-vezir.azurewebsites.net/api",
    "ApiKey": "",
    "RecipientEmail": "sasakiticsanz@gmail.com",
    "UseTemplates": false
  }
}
```

---

## 📊 Analytics & Tracking

| Servis | Status | Napomena |
|--------|:------:|----------|
| Google Analytics 4 | 🟡 | Opciono |
| Hotjar / Clarity | 🟡 | Opciono - heatmaps |

---

## 📁 Projekat Struktura

```
Vezir.Demo.Poster.SasaKitic/
├── Components/
│   ├── App.razor
│   ├── Routes.razor
│   ├── Layout/
│   │   ├── MainLayout.razor
│   │   ├── Header.razor          # Sticky nav + theme toggle
│   │   └── Footer.razor          # Links + social
│   ├── Pages/
│   │   ├── Home.razor            # Hero + overview
│   │   ├── About.razor           # Bio + philosophy
│   │   ├── Experience.razor      # Work timeline
│   │   ├── Projects.razor        # Portfolio grid
│   │   ├── Skills.razor          # Tech stack
│   │   ├── Contact.razor         # Form + info
│   │   └── NotFound.razor        # 404
│   └── Shared/
│       ├── ProjectCard.razor     # Reusable project card
│       ├── SkillBadge.razor      # Tech icon + name
│       ├── TimelineItem.razor    # Experience entry
│       ├── SocialLinks.razor     # GitHub, LinkedIn, etc.
│       └── LanguageSwitcher.razor
├── Models/
│   ├── Project.cs
│   ├── Experience.cs
│   ├── Skill.cs
│   └── ContactForm.cs
├── Services/
│   ├── EmailService.cs           # Sultan integration
│   └── LocalizationService.cs
├── wwwroot/
│   ├── css/
│   │   ├── app.css               # Main styles
│   │   └── variables.css         # CSS custom properties
│   ├── js/
│   │   └── app.js                # Animations, theme toggle
│   ├── locales/
│   │   ├── sr-Latn.json          # Srpski
│   │   ├── en.json               # Engleski
│   │   └── de.json               # Nemački
│   ├── images/
│   │   ├── profile.jpg           # Professional photo
│   │   ├── projects/             # Project screenshots
│   │   └── og-image.png          # Social sharing
│   ├── documents/
│   │   └── Sasa_Kitic_CV.pdf     # Downloadable CV
│   ├── favicon.ico
│   └── index.html
├── Program.cs
├── appsettings.json
└── Vezir.Demo.Poster.SasaKitic.csproj
```

---

## 🖼️ Slike - Potrebno

| Lokacija | Opis | Status |
|----------|------|--------|
| `/images/profile.jpg` | Profesionalna fotografija | ⬜ Saša pravi - placeholder za sad |
| `/images/og-image.png` | Social sharing (1200x630) | ⬜ Generisati |
| `/images/projects/*.png` | Screenshots projekata | ⬜ Napraviti |
| `/favicon.ico` | Browser tab icon | ⬜ Generisati |

**Placeholder slika**: Koristiti besplatnu placeholder sliku dok Saša ne napravi profesionalnu.

---

## 📝 SEO & Meta

### Title tag
```
Saša Kitić - Software Engineer | .NET, Blazor, C#
```

### Meta description
```
Software Engineer iz Novog Sada sa 8+ godina iskustva. Specijalizacija: 
.NET, Blazor, ASP.NET, PostgreSQL. Gradim framework-e i biblioteke.
Koliko je bitno to što pravimo, toliko je bitno šta to čini za vas.
```

### Structured Data (JSON-LD)
```json
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Saša Kitić",
  "jobTitle": "Software Engineer",
  "url": "https://sasakitic.rs",
  "sameAs": [
    "https://linkedin.com/in/sasa-kitic-925701183",
    "https://github.com/sanz1999"
  ],
  "knowsAbout": ["C#", ".NET", "Blazor", "ASP.NET", "PostgreSQL"],
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Novi Sad",
    "addressCountry": "RS"
  }
}
```

---

## 🧪 QA Checklist

### Vizuelni pregled
- [ ] Dark tema izgleda profesionalno
- [ ] Boje su konzistentne
- [ ] Fontovi su čitljivi
- [ ] Animacije su smooth (ne previše)
- [ ] Responsive na svim uređajima

### Funkcionalnost
- [ ] Navigacija radi
- [ ] Language switcher radi
- [ ] Kontakt forma šalje email
- [ ] PDF download radi
- [ ] Svi linkovi rade
- [ ] Demo projekti se učitavaju

### Performanse
- [ ] Lighthouse score > 90
- [ ] Slike optimizovane
- [ ] Lazy loading radi
- [ ] No layout shift

### SEO
- [ ] Svi meta tagovi postavljeni
- [ ] OG tagovi za social sharing
- [ ] Structured data validan
- [ ] Sitemap.xml postoji

---

## 📅 Development Plan

| Faza | Opis | Status |
|------|------|--------|
| 1. Setup | Projekat kreiranje, osnovni layout | ✅ Završeno |
| 2. Hero + Home | Landing stranica + Constellation BG | ✅ Završeno |
| 3. About + Experience | Bio i timeline | ✅ Završeno |
| 4. Projects | Portfolio grid + filter | ✅ Završeno |
| 5. Skills | Tech stack prikaz | ✅ Završeno |
| 6. Contact | Forma + Sultan | ✅ Završeno |
| 7. Polish | Animacije, responsive, SEO | 🟡 90% - Interaktivna pozadina dodata |
| 8. Content | Tekstovi, slike, CV PDF | 🟡 80% - Placeholder slike, čeka pravu foto |
| 9. Deploy | sasakitic.rs | ⬜ Čeka DNS setup |
| 10. Subdomains | Demo projekti na poddomene | ⬜ Čeka DNS setup |

---

## 💬 Napomene

- Domen sasakitic.rs već zakupljen (3,300 RSD/god)
- Portfolio služi za prikaz demo projekata mušterijama
- CV sajt treba da bude impresivan ali ne pretenciozan
- Dark tema je primarna (developer vibe)
- Sve mora biti responsive i brzo

---

*Dokument kreiran: Januar 20, 2026*  
*Poslednje ažuriranje: Januar 20, 2026*
