# 🛒 WEBSHOP CONFIG - TopWearShop

## Status
| Polje | Vrednost |
|-------|----------|
| **Distributer** | FF Programming (Miloš Ilić) |
| **Datum** | Januar 2026 |
| **Status** | � Frontend Kompletiran |
| **Tip** | E-commerce WebShop sa Kontrol CMS-om |
| **Stil** | Street Wear / Urban Fashion |

---

## 🚀 Development Progress

### ✅ Završeno (Januar 20, 2026)

| Komponenta | Status | Napomena |
|------------|--------|----------|
| **Specifikacija** | ✅ | Kompletna |
| **Projekat kreiran** | ✅ | `Vezir.Demo.Poster.TopWearShop` |
| **Blazor WASM setup** | ✅ | .NET 10, standalone SPA |
| **Layout** | ✅ | Header, Footer, MainLayout |
| **Routing** | ✅ | App.razor sa NotFound |
| **Lokalizacija** | ✅ | sr-Latn, en - JSON fajlovi |
| **Sve stranice** | ✅ | 15+ stranica |
| **Korpa (Cart)** | ✅ | localStorage + CartService |
| **Wishlist** | ✅ | localStorage + WishlistService |
| **Demo podaci** | ✅ | 8 proizvoda sa slikama |
| **CSS/Styling** | ✅ | Crno/crvena tema, responsive |

### ⏳ U toku

| Komponenta | Status | Napomena |
|------------|--------|----------|
| **Kontrol API integracija** | ⏳ | Sledeći korak |
| **Auth (Identity)** | ⏳ | Backend potreban |
| **Sultan email** | ⏳ | Za order confirmations |

### 📋 TODO

- [ ] Povezati sa Kontrol CMS API za prave proizvode
- [ ] Implementirati Auth sa Vezir Identity
- [ ] Integrisati Sultan email za narudžbine
- [ ] Zakupiti domen (topwearshop.rs?)
- [ ] Deploy na Azure
- [ ] Dodati pravi logo (SVG placeholder trenutno)
- [ ] SEO optimizacija
- [ ] PWA setup

---

## 📁 Projekat Struktura

```
Vezir.Demo.Poster.TopWearShop/
├── Layout/
│   ├── MainLayout.razor      ✅ Sa loading state
│   ├── Header.razor          ✅ Nav + actions
│   └── Footer.razor          ✅ Links + newsletter
├── Pages/
│   ├── Home.razor            ✅ Hero + kategorije + proizvodi
│   ├── Shop.razor            ✅ Grid + filteri + paginacija
│   ├── ProductDetail.razor   ✅ Galerija + add to cart
│   ├── Cart.razor            ✅ Quantities + promo code
│   ├── Checkout.razor        ✅ Multi-step checkout
│   ├── Wishlist.razor        ✅ Grid view
│   ├── NotFound.razor        ✅ 404 stranica
│   ├── Account/
│   │   ├── Login.razor       ✅
│   │   ├── Register.razor    ✅
│   │   ├── Profile.razor     ✅
│   │   └── Orders.razor      ✅
│   └── Info/
│       ├── FAQ.razor         ✅
│       ├── SizeGuide.razor   ✅
│       ├── Contact.razor     ✅
│       └── ReturnPolicy.razor ✅
├── Shared/
│   ├── ProductCard.razor     ✅ Reusable component
│   ├── MiniCart.razor        ✅ Slide-out panel
│   └── QuickViewModal.razor  ✅ Product preview
├── Models/
│   ├── Product.cs            ✅ Sa aliases za kompatibilnost
│   ├── Cart.cs               ✅ CartItem, WishlistItem
│   ├── Order.cs              ✅ Order, OrderItem, Address
│   └── User.cs               ✅ User, LoginModel, RegisterModel
├── Services/
│   ├── ProductService.cs     ✅ Demo data (8 proizvoda)
│   ├── CartService.cs        ✅ localStorage persistence
│   ├── WishlistService.cs    ✅ localStorage persistence
│   ├── AuthService.cs        ✅ Demo auth
│   ├── OrderService.cs       ✅ Order management
│   └── LocalizationService.cs ✅ Multi-language support
└── wwwroot/
    ├── css/app.css           ✅ 1200+ linija CSS
    ├── index.html            ✅ GA4 + FB Pixel ready
    ├── images/logo.svg       ✅ SVG placeholder
    └── locales/
        ├── sr-Latn.json      ✅ Srpski prevodi
        └── en.json           ✅ Engleski prevodi
```

---

## 📋 Osnovni podaci

| Polje | Vrednost |
|-------|----------|
| **Firma** | TopWearShop |
| **Delatnost** | Online prodaja muške odeće |
| **Lokacija** | Novi Sad, Srbija (Online) |
| **Kontakt osoba** | Vule (Milošev brat) |
| **Telefon** | *TBD* |
| **Email** | *TBD - čeka se domen* |
| **Website** | *TBD - čeka se domen* |
| **Facebook** | *Nema* |
| **Instagram** | https://www.instagram.com/_topwearshop__/ |

---

## 🎨 Branding

### Boje (izvučene iz loga)
| Boja | Hex | RGB | Upotreba |
|------|-----|-----|----------|
| **Crna** | `#1A1A1A` | 26, 26, 26 | Pozadina, header, footer |
| **Crvena (Accent)** | `#E53935` | 229, 57, 53 | CTA dugmad, highlights, sale |
| **Bela** | `#FFFFFF` | 255, 255, 255 | Tekst na tamnoj pozadini |
| **Svetlo siva** | `#F5F5F5` | 245, 245, 245 | Kartice, sekcije |
| **Tamno siva** | `#333333` | 51, 51, 51 | Body tekst |

### Logo
- **Fajl:** `wwwroot/images/logo.png`
- **Opis:** Crni krug sa "Top Wear Shop" tekstom - belo/crveni brush efekat
- **Verzije potrebne:** 
  - [x] logo.png (primary - dobijen)
  - [ ] logo-white.png (za tamne pozadine - isti)
  - [ ] favicon.ico
  - [ ] logo-192x192.png (PWA)
  - [ ] logo-512x512.png (PWA)

### Stil
- **Kategorija:** Street Wear / Urban Fashion
- **Vibe:** Moderan, urban, muževan, dinamičan
- **Inspiracija:** ASOS, Zara Men, Urban Outfitters

### Font
- **Naslovi:** Oswald Bold ili Bebas Neue (urban feel)
- **Body:** Roboto ili Open Sans

---

## 👕 Proizvodi & Katalog

### Asortiman
| Polje | Vrednost |
|-------|----------|
| **Kategorija** | Muška odeća |
| **Broj proizvoda** | ~50 (početno) |
| **Izvor podataka** | Vezir Kontrol CMS API |
| **Veličine** | XS, S, M, L, XL, XXL |
| **Valuta** | RSD (zakonska obaveza) |

### Predložene kategorije (za Kontrol)
1. Majice (T-shirts)
2. Duksevi (Hoodies & Sweatshirts)
3. Jakne (Jackets)
4. Pantalone (Pants)
5. Šortsevi (Shorts)
6. Aksesoari (Accessories)

### Cene
- ✅ Prikazuju se na sajtu
- ✅ Sale/Snižene cene (precrtana stara + nova cena)
- ✅ Valuta: RSD

---

## 🛍️ WebShop Funkcionalnosti

### Korpa & Checkout
| Funkcionalnost | Status | Napomena |
|----------------|:------:|----------|
| Korpa (Cart) | ✅ | localStorage + sync sa API |
| Wishlist/Favorites | ✅ | localStorage |
| Quick View | ✅ | Modal bez otvaranja stranice |
| Guest Checkout | ✅ | Opciono bez registracije |
| Registracija | ✅ | Opciona tokom checkout-a |

### Filteri & Pretraga
| Filter | Status |
|--------|:------:|
| Po kategoriji | ✅ |
| Po ceni (range) | ✅ |
| Po veličini | ✅ |
| Po boji | ✅ |
| Po proizvođaču | ✅ |
| Sortiranje (cena, novo, popularno) | ✅ |
| Pretraga (search) | ✅ |

### Plaćanje
| Metoda | Status | Napomena |
|--------|:------:|----------|
| Pouzeće (Cash on Delivery) | ✅ | Jedina opcija za sada |
| Online plaćanje | ❌ | Faza 2 - PaySpot/NestPay |
| Virman | ❌ | Nije potrebno |

### Dostava
| Opcija | Status | Napomena |
|--------|:------:|----------|
| PostExpress | ✅ | Kurir servis |
| Lično preuzimanje | ✅ | Samo Novi Sad |
| Besplatna dostava | ✅ | Za 2+ artikla |

> **📝 TODO za Kontrol:** Dodati opciju "Besplatna dostava za X+ artikala" u CMS settings

---

## 📄 Stranice sajta

### Glavne stranice
| # | Stranica | Ruta | Opis |
|---|----------|------|------|
| 1 | **Početna** | `/` | Hero + Featured + New + Sale |
| 2 | **Shop/Katalog** | `/shop` | Grid svih proizvoda + filteri |
| 3 | **Kategorija** | `/shop/{category}` | Proizvodi po kategoriji |
| 4 | **Proizvod** | `/product/{id}` | Detalji + galerija + add to cart |
| 5 | **Korpa** | `/cart` | Pregled korpe |
| 6 | **Checkout** | `/checkout` | Forma za narudžbinu |
| 7 | **Potvrda** | `/order-confirmation` | Thank you stranica |
| 8 | **Kontakt** | `/contact` | Forma + info |

### User Account stranice
| # | Stranica | Ruta | Opis |
|---|----------|------|------|
| 9 | **Login** | `/login` | Prijava |
| 10 | **Register** | `/register` | Registracija |
| 11 | **Forgot Password** | `/forgot-password` | Reset lozinke |
| 12 | **Reset Password** | `/reset-password` | Nova lozinka |
| 13 | **Profil** | `/account` | Korisnički podaci |
| 14 | **Istorija narudžbina** | `/account/orders` | Lista narudžbina |
| 15 | **Detalj narudžbine** | `/account/orders/{id}` | Status narudžbine |

### Info stranice
| # | Stranica | Ruta | Opis |
|---|----------|------|------|
| 16 | **FAQ** | `/faq` | Često postavljana pitanja |
| 17 | **Size Guide** | `/size-guide` | Tabela veličina |
| 18 | **Politika povraćaja** | `/return-policy` | Uslovi povraćaja |
| 19 | **Politika privatnosti** | `/privacy-policy` | GDPR |
| 20 | **Uslovi korišćenja** | `/terms` | Terms of Service |

---

## 🏠 Početna stranica (`/`)

### Sekcije
1. **Hero Banner**
   - Full-width slika/video
   - Naslov: "STREET STYLE. YOUR RULES."
   - Podnaslov: "Nova kolekcija muške odeće"
   - CTA: "SHOP NOW" → `/shop`

2. **Kategorije (Quick Links)**
   - 4-6 kategorija sa slikama
   - Hover efekat

3. **🔥 Najnovije (New Arrivals)**
   - Slider/Grid 4-8 proizvoda
   - Badge: "NEW"

4. **💰 Sale/Sniženja**
   - Banner + proizvodi na akciji
   - Badge: "-XX%"

5. **⭐ Najprodavanije (Best Sellers)**
   - Grid 4-8 proizvoda

6. **Newsletter Signup**
   - Email input + CTA
   - "Prijavi se za 10% popusta na prvu narudžbinu"

7. **Instagram Feed** (opciono)
   - Link ka IG profilu

---

## 🛒 Shop stranica (`/shop`)

### Layout
```
┌─────────────────────────────────────────────┐
│ BREADCRUMB: Home > Shop                     │
├─────────────────────────────────────────────┤
│ FILTERS (sidebar)  │  PRODUCT GRID          │
│                    │                         │
│ □ Kategorije       │  [Sort: Newest ▼]      │
│ □ Veličine         │                         │
│ □ Boje             │  ┌───┐ ┌───┐ ┌───┐    │
│ □ Proizvođači      │  │   │ │   │ │   │    │
│ □ Cena (slider)    │  └───┘ └───┘ └───┘    │
│                    │  ┌───┐ ┌───┐ ┌───┐    │
│ [Clear Filters]    │  │   │ │   │ │   │    │
│                    │  └───┘ └───┘ └───┘    │
│                    │                         │
│                    │  [Load More / Pagination]│
└─────────────────────────────────────────────┘
```

### Product Card
- Slika (hover: druga slika)
- Naziv
- Cena (stara precrtana + nova ako je sale)
- Quick View button
- Add to Wishlist (heart icon)
- Badges: NEW, SALE, OUT OF STOCK

---

## 📦 Stranica proizvoda (`/product/{id}`)

### Sadržaj
1. **Galerija slika** (main + thumbnails, zoom on hover)
2. **Info sekcija:**
   - Naziv proizvoda
   - Cena (sa popustom ako je sale)
   - Kratak opis
   - Veličina selector + Size Guide link
   - Boja selector (ako ima varijante)
   - Količina (+/-)
   - **ADD TO CART** button (crveni, prominent)
   - Add to Wishlist
3. **Tabs:**
   - Opis
   - Specifikacije
   - Dostava info
4. **Related Products** (You may also like)

---

## 🛒 Korpa (`/cart`)

### Sadržaj
| Kolona | Opis |
|--------|------|
| Slika | Thumbnail proizvoda |
| Naziv | Ime + veličina + boja |
| Cena | Pojedinačna cena |
| Količina | +/- kontrole |
| Ukupno | Cena × količina |
| Ukloni | X button |

### Summary
- Subtotal
- Dostava (izračunava se)
- **UKUPNO**
- Promo code input
- [CHECKOUT] button

---

## 💳 Checkout (`/checkout`)

### Koraci
1. **Informacije** - Email, telefon
2. **Dostava** - Adresa ili lično preuzimanje
3. **Plaćanje** - Pouzeće (jedina opcija)
4. **Pregled** - Summary pre potvrde
5. **Potvrda** - Thank you + order number

### Forma
```
KONTAKT INFORMACIJE
├── Email *
├── Telefon *
└── [ ] Kreiraj nalog (opciono)
    ├── Lozinka
    └── Potvrda lozinke

DOSTAVA
├── ( ) PostExpress dostava
│   ├── Ime i prezime *
│   ├── Adresa *
│   ├── Grad *
│   ├── Poštanski broj *
│   └── Napomena (opciono)
└── ( ) Lično preuzimanje - Novi Sad

PLAĆANJE
└── (•) Plaćanje pouzećem

NAPOMENA
└── Textarea (opciono)

[ ] Prihvatam uslove korišćenja *

[PORUČI]
```

---

## 👤 User Account

### Registracija
- Email *
- Lozinka *
- Ime *
- Prezime *
- Telefon (opciono)
- [ ] Newsletter signup

### Login
- Email
- Lozinka
- [ ] Zapamti me
- Forgot password link

### Profil (`/account`)
- Izmena ličnih podataka
- Izmena lozinke
- Adrese (saved addresses)
- Newsletter preferences

### Istorija narudžbina (`/account/orders`)
| Kolona | Opis |
|--------|------|
| # Narudžbine | Order ID |
| Datum | Datum naručivanja |
| Status | Pending, Processing, Shipped, Delivered |
| Ukupno | Cena |
| Detalji | Link |

---

## 🌍 Jezici

| Kod | Jezik | Status |
|-----|-------|--------|
| `sr-Latn` | Srpski (Latinica) | ✅ Primary |
| `en` | Engleski | ✅ |

### Implementacija
- JSON locale fajlovi
- Language switcher u header-u
- URL prefix: `/en/shop`, `/shop`

---

## 📧 Email notifikacije (Sultan)

| Email | Trigger | Sadržaj |
|-------|---------|---------|
| Order Confirmation | Narudžbina kreirana | Detalji narudžbine |
| Shipping Notification | Status: Shipped | Tracking info |
| Welcome Email | Registracija | Dobrodošlica + promo code |
| Password Reset | Forgot password | Reset link |
| Newsletter | Manual/Scheduled | Promocije |

---

## 📊 Analytics & Tracking

| Servis | Status | Napomena |
|--------|:------:|----------|
| Google Analytics 4 | ✅ | GA4 measurement ID |
| Facebook Pixel | ✅ | Za remarketing ads |
| Google Tag Manager | 🟡 | Opciono (za lakše upravljanje) |

### E-commerce Events (GA4)
- `view_item` - Pregled proizvoda
- `add_to_cart` - Dodavanje u korpu
- `remove_from_cart` - Uklanjanje iz korpe
- `begin_checkout` - Početak checkout-a
- `purchase` - Završena kupovina

---

## 📝 Sadržaj - Predlozi

### FAQ (Dummy sadržaj)

**1. Kako mogu da naručim?**
> Izaberite proizvode, dodajte ih u korpu i pratite korake za naručivanje. Možete naručiti kao gost ili kreirati nalog.

**2. Koje metode plaćanja prihvatate?**
> Trenutno prihvatamo plaćanje pouzećem. Online plaćanje uskoro!

**3. Koliko košta dostava?**
> Dostava je besplatna za narudžbine sa 2 ili više artikala. Za jedan artikal, dostava se naplaćuje po cenovniku PostExpress-a.

**4. Koliko traje dostava?**
> Dostava traje 1-3 radna dana za teritoriju Srbije.

**5. Kako mogu da pratim narudžbinu?**
> Nakon slanja, dobićete email sa tracking brojem. Status možete pratiti i u vašem nalogu.

**6. Mogu li da promenim ili otkažem narudžbinu?**
> Kontaktirajte nas što pre putem kontakt forme. Narudžbine koje su već poslate ne mogu se otkazati.

---

### Politika povraćaja (Predlog)

```markdown
# Politika povraćaja robe

## Pravo na povraćaj
Imate pravo da vratite proizvod u roku od **14 dana** od dana prijema, bez navođenja razloga.

## Uslovi povraćaja
- Proizvod mora biti nekorišćen i u originalnom pakovanju
- Sve etikete moraju biti neoštećene
- Proizvod ne sme biti pran ili oštećen

## Kako vratiti proizvod?
1. Kontaktirajte nas putem kontakt forme ili email-a
2. Dobićete uputstva za povraćaj
3. Pošaljite proizvod na našu adresu
4. Nakon prijema i provere, refundiramo iznos u roku od 14 dana

## Troškovi povraćaja
Troškove povratne pošiljke snosi kupac, osim u slučaju:
- Pogrešno poslatog proizvoda
- Oštećenog proizvoda

## Zamena veličine
Zamena veličine je besplatna! Kontaktirajte nas i organizovaćemo zamenu.

## Kontakt
Za sva pitanja u vezi povraćaja, kontaktirajte nas putem kontakt forme.
```

---

### Size Guide (Tabela veličina)

| Veličina | Grudi (cm) | Struk (cm) | Kukovi (cm) |
|----------|------------|------------|-------------|
| XS | 86-91 | 71-76 | 86-91 |
| S | 91-96 | 76-81 | 91-96 |
| M | 96-101 | 81-86 | 96-101 |
| L | 101-106 | 86-91 | 101-106 |
| XL | 106-111 | 91-96 | 106-111 |
| XXL | 111-116 | 96-101 | 111-116 |

**Kako se meriti?**
- **Grudi:** Izmerite najširi deo grudi
- **Struk:** Izmerite najuži deo struka
- **Kukovi:** Izmerite najširi deo kukova

---

## ⚙️ Tehnički zahtevi

### Arhitektura
```
┌─────────────────────────────────────────────────────┐
│                   FRONTEND                          │
│            Vezir.Demo.Poster.TopWearShop            │
│                 (Blazor WASM)                       │
└─────────────────────┬───────────────────────────────┘
                      │ HTTP/REST
┌─────────────────────▼───────────────────────────────┐
│                   BACKEND                           │
│                  Vezir.Api                          │
│              (Kontrol CMS API)                      │
├─────────────────────────────────────────────────────┤
│ Modules:                                            │
│ - Identity (Auth, Users)                            │
│ - Catalog (Products, Categories)                    │
│ - Sales (Cart, Orders) ← NEEDS IMPLEMENTATION       │
│ - Mailing (Sultan integration)                      │
└─────────────────────┬───────────────────────────────┘
                      │
┌─────────────────────▼───────────────────────────────┐
│                  DATABASE                           │
│                 PostgreSQL                          │
└─────────────────────────────────────────────────────┘
```

### Frontend Stack
| Tehnologija | Verzija | Napomena |
|-------------|---------|----------|
| Blazor WebAssembly | .NET 10 | SPA frontend |
| CSS | Custom + Bootstrap 5 | Responsive |
| JavaScript | Vanilla | Interop za analytics |

### Funkcionalnosti po layeru

**Frontend (Blazor WASM):**
- Product listing + filters
- Cart (localStorage + state management)
- Wishlist (localStorage)
- User authentication UI
- Checkout flow
- Order history
- Multi-language

**Backend (Kontrol API):**
- Product CRUD
- Category management
- Order processing
- User management
- Email sending (Sultan)

---

## 📁 Struktura projekta

```
src/demos/Vezir.Demo.Poster.TopWearShop/
├── Components/
│   ├── App.razor
│   ├── Routes.razor
│   ├── Layout/
│   │   ├── MainLayout.razor
│   │   ├── MainLayout.razor.css
│   │   ├── Header.razor
│   │   ├── Footer.razor
│   │   ├── MiniCart.razor
│   │   └── MobileMenu.razor
│   ├── Pages/
│   │   ├── Home.razor
│   │   ├── Shop.razor
│   │   ├── ProductDetail.razor
│   │   ├── Cart.razor
│   │   ├── Checkout.razor
│   │   ├── OrderConfirmation.razor
│   │   ├── Contact.razor
│   │   ├── FAQ.razor
│   │   ├── SizeGuide.razor
│   │   ├── ReturnPolicy.razor
│   │   ├── PrivacyPolicy.razor
│   │   ├── Terms.razor
│   │   └── Account/
│   │       ├── Login.razor
│   │       ├── Register.razor
│   │       ├── ForgotPassword.razor
│   │       ├── ResetPassword.razor
│   │       ├── Profile.razor
│   │       └── Orders.razor
│   └── Shared/
│       ├── ProductCard.razor
│       ├── ProductGrid.razor
│       ├── ProductFilters.razor
│       ├── QuickViewModal.razor
│       ├── LanguageSwitcher.razor
│       ├── NewsletterSignup.razor
│       ├── Breadcrumb.razor
│       ├── Pagination.razor
│       └── LoadingSpinner.razor
├── Models/
│   ├── Product.cs
│   ├── Category.cs
│   ├── CartItem.cs
│   ├── Order.cs
│   ├── User.cs
│   └── Address.cs
├── Services/
│   ├── ProductService.cs (API calls)
│   ├── CartService.cs (localStorage + state)
│   ├── WishlistService.cs (localStorage)
│   ├── AuthService.cs (JWT)
│   ├── OrderService.cs (API calls)
│   ├── LocalizationService.cs
│   └── AnalyticsService.cs
├── State/
│   ├── CartState.cs
│   ├── AuthState.cs
│   └── AppState.cs
├── wwwroot/
│   ├── css/
│   │   ├── app.css
│   │   └── variables.css
│   ├── js/
│   │   ├── app.js
│   │   └── analytics.js
│   ├── locales/
│   │   ├── sr-Latn.json
│   │   └── en.json
│   ├── images/
│   │   ├── logo.png
│   │   ├── hero/
│   │   └── placeholders/
│   ├── favicon.ico
│   └── index.html
├── Program.cs
├── appsettings.json
└── Vezir.Demo.Poster.TopWearShop.csproj
```

---

## 🔧 Kontrol CMS - Potrebne funkcionalnosti

### Već implementirano ✅
- Product CRUD
- Category CRUD
- Image upload

### Potrebno implementirati 📋
- [ ] **Sales Module** - Orders, Order Items
- [ ] **Shipping settings** - Besplatna dostava za X+ artikala
- [ ] **Discount/Promo codes**
- [ ] **Stock management** - Količina po veličini
- [ ] **Order status workflow** - Pending → Processing → Shipped → Delivered
- [ ] **Customer management** - Lista kupaca, istorija

---

## ✅ CHECKLIST PRE POČETKA

### Materijali
- [x] Logo (dobijen)
- [ ] Hero slike
- [ ] Product slike (dolaze kroz Kontrol)
- [ ] Favicon (generisati iz loga)

### Backend
- [ ] Kontrol API radi lokalno
- [ ] Sales module implementiran
- [ ] Sultan email konfigurisan

### Konfiguracija
- [ ] Domen zakupljen
- [ ] GA4 ID
- [ ] Facebook Pixel ID
- [ ] Sultan API key

---

## 📅 TIMELINE

| Faza | Opis | Status |
|------|------|--------|
| 1. Specifikacija | Definisanje zahteva | ✅ DONE |
| 2. Backend prep | Sales module, API endpoints | ⏳ |
| 3. Frontend scaffold | Projekat + osnovne stranice | ⏳ |
| 4. Shop & Products | Listing, filters, detail | ⏳ |
| 5. Cart & Checkout | Korpa, checkout flow | ⏳ |
| 6. User accounts | Auth, profile, orders | ⏳ |
| 7. Content & Polish | FAQ, policies, styling | ⏳ |
| 8. Testing | QA, responsive, cross-browser | ⏳ |
| 9. Deploy | Production deployment | ⏳ |

---

## 💬 NAPOMENE

- Vule je glavni kontakt za TopWearShop
- Dolazi preko FF Programming (Miloš connection)
- Ovo je prvi PRAVI webshop sa Kontrol integracijom!
- Template za buduće webshop projekte (Bane, Jaksu...)
- Plaćanje pouzećem za sada, online plaćanje u fazi 2

---

*Dokument kreiran: Januar 20, 2026*  
*Poslednje ažuriranje: Januar 20, 2026*
