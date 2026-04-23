# Client Onboarding Checklist

**Verzija:** 2.0
**Ažurirano:** Januar 2026

---

## 📋 POSTER SITE (Prezentacioni sajt)

> Tipično vreme: 2-5 radnih dana
> Cena: €150-300 jednokratno + €50/god hosting

### 1. Pre-Start
- [ ] Potvrđena saradnja (email/poruka)
- [ ] Definisan rok isporuke
- [ ] Primljen avans (opciono za distributere)

### 2. Prikupljanje Materijala
**Od klijenta:**
- [ ] Logo (PNG/SVG, pozadina transparentna)
- [ ] Boje brenda (ili dozvoliti da mi predložimo)
- [ ] Tekstovi za sekcije (ili "napišite vi")
- [ ] Slike (galerija, hero, tim) - ili stock
- [ ] Kontakt podaci (adresa, telefon, email)
- [ ] Social media linkovi (ako imaju)

**Za Poster config:**
- [ ] Naziv projekta (folder name)
- [ ] Domen (subdomena ili custom)
- [ ] Ključne sekcije sajta

### 3. Development
- [ ] Kreiran projekat (kopiraj template)
- [ ] Konfigurisan `PosterSettings.cs`
- [ ] Primenjen branding (boje, logo)
- [ ] Uneti tekstovi i slike
- [ ] Responsive test (mobile/tablet/desktop)

### 4. Deployment
- [ ] Railway ili CPanel hosting konfigurisan
- [ ] Build & Deploy uspešan
- [ ] Custom domen konfigurisan (ako ima)
- [ ] SSL aktivan
- [ ] Smoke test na produkciji

### 5. Predaja
- [ ] Link poslat klijentu
- [ ] Feedback primljen i ispravke
- [ ] Finalna potvrda od klijenta
- [ ] Faktura poslata
- [ ] Dodat u portfolio

---

## 🛒 WEBSHOP (Kontrol CMS)

> Tipično vreme: 2-4 nedelje
> Cena: €500-1500 setup + €30-50/mes

### 1. Pre-Sales
- [ ] Uvodni sastanak/poziv
- [ ] Identifikovane potrebe (broj proizvoda, kategorije, plaćanje)
- [ ] Poslata ponuda sa paketom
- [ ] Potpisan ugovor (ili email potvrda)
- [ ] Primljen avans (50%)

### 2. Prikupljanje Materijala

**Brending:**
- [ ] Logo (PNG, SVG)
- [ ] Brand colors (hex)
- [ ] Favicon

**Kontakt & Pravno:**
- [ ] Naziv firme
- [ ] Adresa, telefon, email
- [ ] PIB, matični broj
- [ ] Tekst: Uslovi korišćenja
- [ ] Tekst: Politika privatnosti
- [ ] Tekst: Povrat robe

**Proizvodi:**
- [ ] Lista proizvoda (Excel/CSV)
  - Naziv, šifra, opis, cena, kategorija
- [ ] Slike proizvoda (min 800x800px)
- [ ] Struktura kategorija

**Logistika:**
- [ ] Metode dostave + cene
- [ ] Prag za besplatnu dostavu
- [ ] Metode plaćanja

**Tehnički:**
- [ ] Domen (postojeći ili registrovati)
- [ ] DNS pristup (za custom domen)

### 3. Setup

**Azure resursi:**
- [ ] Resource Group kreiran
- [ ] App Service (B1 tier ~€13/mes)
- [ ] PostgreSQL (Flexible, Burstable ~€15/mes)
- [ ] Storage Account (slike)
- [ ] Environment variables

**Aplikacija:**
- [ ] Kontrol instance konfigurisan
- [ ] Branding primenjen
- [ ] Kontakt podaci uneti
- [ ] Pravni tekstovi uneti
- [ ] Dostava konfigurisana
- [ ] Email notifikacije (Sultan)

**Sadržaj:**
- [ ] Kategorije kreirane
- [ ] Proizvodi importovani
- [ ] Slike uploadovane
- [ ] Homepage sadržaj
- [ ] O nama stranica
- [ ] Kontakt stranica

### 4. Testing
- [ ] Mobile test
- [ ] Desktop test
- [ ] Pretraga proizvoda
- [ ] Dodaj u korpu
- [ ] Checkout flow (do kraja)
- [ ] Admin panel - CRUD proizvodi
- [ ] Email notifikacije (test porudžbina)

### 5. Launch

**Pre-launch:**
- [ ] Review sa klijentom
- [ ] Ispravke po feedback-u
- [ ] DNS konfigurisan
- [ ] SSL aktivan
- [ ] Google Analytics (opciono)

**Go-live:**
- [ ] Final deploy
- [ ] DNS propagacija OK
- [ ] Smoke test na produkciji
- [ ] Email klijentu: LIVE!

**Post-launch:**
- [ ] Obuka klijenta (30-60 min screen share)
- [ ] Poslato uputstvo (PDF/video)
- [ ] Faktura za ostatak (50%)

### 6. Zatvaranje
- [ ] Klijent potvrdio prijem
- [ ] Kompletna uplata primljena
- [ ] Ugovor o održavanju (opciono)
- [ ] Dodato u reference/portfolio
- [ ] Zamoljen za review/preporuku

---

## 💰 COST BREAKDOWN (Za Tomislava)

### Poster Site - Naši Troškovi
| Stavka | Mesečno | Godišnje |
|--------|---------|----------|
| Azure Static Web App | FREE | FREE |
| Custom domen (opciono) | - | ~€12 |
| **UKUPNO** | ~€0-1 | ~€12 |

### Poster Site - Naplata Klijentu
| Stavka | Cena |
|--------|------|
| Izrada sajta | €150-300 |
| Hosting (godišnje) | €50 |
| **Profit margin** | **~95%** |

---

### WebShop - Naši Troškovi
| Stavka | Mesečno |
|--------|---------|
| Azure App Service (B1) | ~€13 |
| PostgreSQL Flexible | ~€15 |
| Storage (slike) | ~€2-5 |
| Sultan Email | ~€3 |
| **UKUPNO** | **~€33-36/mes** |

### WebShop - Naplata Klijentu
| Stavka | Cena |
|--------|------|
| Setup (jednokratno) | €500-1500 |
| Hosting + Održavanje (mesečno) | €50-80 |
| **Profit margin na hosting** | **~40-60%** |

---

## 📊 ROI Primer - Poster Sites

**10 klijenata godišnje:**
- Prihod od izrade: 10 × €200 = €2,000
- Prihod od hostinga: 10 × €50 = €500/god
- Naši troškovi: ~€120/god (domeni)
- **Godišnji profit: ~€2,380**

**Vreme uloženo:** ~30-40 sati (za 10 sajtova)
**Satnica:** ~€60-80/sat

---

## 📝 Napomene

- Za FF Programming klijente - oni naplaćuju svoju maržu
- Za Riviera klijente - isti model, samo faktura na hrvatskom
- Poster Sites su profitabilniji per-hour nego WebShop
- WebShop ima recurring revenue ali i recurring troškove

---

*Izvor: Adaptirano iz originalnog CLIENT-ONBOARDING-CHECKLIST.md*
