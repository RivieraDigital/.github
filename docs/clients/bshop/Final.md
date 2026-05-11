# TEHNIČKA SPECIFIKACIJA I PREGLED OPCIJA: b-shop.hr

**Klijent:** Jakša, b-shop.hr  
**Izvođač:** Saša Kitić, Riviera Digital (Vezir Platform)  
**Cc:** Tomislav Skulić, Riviera Digital  
**Datum:** 26. januar 2026.  

---

## 1. UVOD
Ovaj dokument služi kao zvanični pregled funkcionalnosti i opcija za razvoj platforme **b-shop.hr**. Na osnovu planiranog dropshipping modela (prodaja alata) i hibridnog skladištenja, definisane su osnovne i napredne komponente sistema.

---

## 2. STANDARDNA FUNKCIONALNOST (UKLJUČENO)

Ove komponente čine osnovu sistema i uključene su u inicijalnu fazu razvoja (MVP).

### Korisnički interfejs (Frontend)
* **Naslovna strana:** Hero banner sa istaknutim artiklima i kategorijama.
* **Katalog i pretraga:** Pregled svih proizvoda sa paginacijom i osnovnim filtriranjem.
* **Detaljan prikaz:** Galerija slika, tehnički opis, specifikacije i cena.
* **Sistem korpe:** Dodavanje, uklanjanje i modifikacija količine proizvoda.
* **Responzivnost:** Potpuna optimizacija za mobilne uređaje i tablete.

### Administratorski panel (Backend)
* **Upravljanje katalogom:** Ručni unos, izmena i organizacija kategorija.
* **Multimedija:** Sistem za upload i optimizaciju fotografija proizvoda.
* **Lager lista:** Osnovno praćenje dostupnosti (Stock tracking).
* **Menadžment narudžbi:** Centralizovan pregled svih pristiglih porudžbina.

---

## 3. KLJUČNI PARAMETRI ZA KONFIGURACIJU

*Molimo klijenta da definiše sledeće stavke radi pravilnog podešavanja sistema:*

| Kategorija | Opcije | Odgovor klijenta |
| :--- | :--- | :--- |
| **Metode plaćanja** | Pouzećem, Virman, Kartice, PayPal | ____________________ |
| **Dostavne službe** | HP, GLS, DPD, Overseas, Drugo | ____________________ |
| **Logika dostave** | Besplatno iznad [X] iznosa ili fiksno | ____________________ |
| **Korisnički nalozi** | Samo Guest, Registracija, ili oba | ____________________ |
| **Email notifikacije** | Potvrda narudžbe, Status update | ____________________ |

---

## 4. NAPREDNE OPCIJE I SKALABILNOST (VEZIR FRAMEWORK)

Ove opcije se aktiviraju prema fazama razvoja definisanim u dokumentu o strategiji.

### Pretraga i filtriranje (Kritično za 1.000+ artikala)
* **Full-text Search:** Instant rezultati pretrage po nazivu i opisu (Vezir Search).
* **Dinamički filteri:** Filtriranje po brendu (npr. Makita, Bosch), ceni i tehničkim karakteristikama.

### Automatizacija i Dropshipping
* **Masovni import (CSV/Excel):** Neophodno za inicijalno punjenje baze (1.000+ artikala).
* **Automatski Sync (Faza 2/3):** Direktno povezivanje sa XML/API feed-om dobavljača.
* **Email Automatizacija:** Korišćenje **Sultan API** servisa za visoku stopu isporuke obaveštenja klijentima.

---

## 5. DIZAJN I VIZUELNI IDENTITET

Za implementaciju **Flux UI** biblioteke potrebni su sledeći podaci:

* **Primarna boja (Brand):** ____________________
* **Sekundarna boja:** ____________________
* **Logotip:** Dostaviti u vektorskom formatu (SVG) ili visokoj rezoluciji.
* **Stil:** [ ] Industrijski (Alati) | [ ] Minimalistički | [ ] Moderan

---

## 6. FINANSIJSKI MODEL I DINAMIKA PLAĆANJA

Razvoj se odvija u fazama (MVP, Scaling, Production).

* **Način plaćanja:** Bez avansnih sredstava (uz garanciju partnera).
* **Finalna uplata:** Nakon uspešnog postavljanja sistema u produkciono okruženje.
* **Garancija kvaliteta:** Fokus na stabilnost koda i brzinu učitavanja (Vezir Platform standard).

---

## 7. AKCIONI PLAN ZA KLIJENTA (ACTION ITEMS)

Molimo klijenta da pripremi i dostavi odgovore na sledeće tačke:

1. **Definicija plaćanja i dostave** (koje službe i koji uslovi).
2. **Kontakt podaci i lokacije** (za stranicu "O nama" i zaglavlje).
3. **Linkovi društvenih mreža** (Facebook, Instagram).
4. **Informacije o dobavljaču** (format u kojem dobavljač šalje podatke o proizvodima).
5. **Model lagera** (isključivo dropshipping ili mešovito).

---

**Saša Kitić** Senior .NET Developer, Riviera-Digital  
Web: riviera-digital.com  
Email: [sasa.kitic@riviera-digital.com]

---