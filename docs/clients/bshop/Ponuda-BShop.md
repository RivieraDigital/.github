# PROJEKTNA DOKUMENTACIJA I TEHNIČKA SPECIFIKACIJA: b-shop.hr

**Predmet:** Strategija razvoja, finansijski okvir i konfiguracioni upitnik
**Izvođač:** Saša Kitić, Riviera Digital (Vezir Platform)
**Klijent:** Jakša, b-shop.hr
**Datum:** 26. januar 2026.

---

## 1. STRATEGIJA RAZVOJA (ROADMAP)

Razvoj platforme b-shop.hr podeljen je u tri faze kako bi se osigurala tehnička stabilnost i postepeno skaliranje sistema u skladu sa rastom broja proizvoda.

### Faza 1: MVP (Minimum Viable Product)
* **Cilj:** Lansiranje funkcionalne prodavnice za inicijalno testiranje tržišta.
* **Obim:** Katalog do 1.000 artikala (ručni ili CSV uvoz).
* **Tehnološki stack:** .NET 10 Blazor WebAssembly, PostgreSQL baza, Sultan API za email notifikacije.
* **Status:** Fokus na osnovni checkout proces i stabilnost sistema.

### Faza 2: Skaliranje sistema
* **Cilj:** Optimizacija za veći broj poseta i artikala.
* **Obim:** Katalog do 15.000 artikala.
* **Unapređenja:** Implementacija Elasticsearch servisa za pretragu u realnom vremenu i CDN optimizacija slika.

### Faza 3: Puna automatizacija
* **Cilj:** Potpuno automatizovan dropshipping sistem.
* **Obim:** Katalog do 120.000 artikala.
* **Unapređenja:** API sinhronizacija zaliha sa dobavljačem, integracija kartičnog plaćanja i automatizacija naloga za dostavu.

---

## 2. FINANSIJSKE PROJEKCIJE

Proračun dobiti zasniva se na modelu dropshipping poslovanja uz optimizaciju operativnih troškova.

$$Dobit = (Promet \times Marža) - (Operativni\_Troškovi + Marketing)$$

| Scenario | Procenjeni mesečni promet | Procenjena neto dobit |
| :--- | :--- | :--- |
| **Konzervativni (Faza 1)** | €6,000 - €9,000 | **€2,350 - €3,550** |
| **Umereni (Faza 2)** | €30,000 | **€9,800** |
| **Agresivni (Faza 3)** | €90,000 | **€23,500** |

---

## 3. KONFIGURACIONI UPITNIK ZA KLIJENTA

*Molimo klijenta da popuni sledeća polja radi definisanja parametara produkcionog okruženja.*

### 3.1. Podaci o poslovnom subjektu
| Polje | Odgovor klijenta |
| :--- | :--- |
| **Puni naziv firme** | b-shop |
| **Sedište i adresa** | ____________________________________ |
| **Poštanski broj** | ____________________________________ |
| **Kontakt telefon** | ____________________________________ |
| **Email za korisnike** | ____________________________________ |

### 3.2. Plaćanje i Logistika
**Metode plaćanja:**
- [ ] Pouzećem (Gotovina)
- [ ] Virman (Uplata na račun po ponudi)
- [ ] Kartično plaćanje (Planirano za Fazu 3)

**Dostava:**
- [ ] Hrvatska pošta (HP)
- [ ] GLS / DPD / Overseas
- **Besplatna dostava iznad:** _______ €

### 3.3. Vizuelni identitet
- **Primarna boja (Hex kod):** ____________________
- **Sekundarna boja (Hex kod):** ____________________
- **Stil dizajna:** [ ] Minimalistički | [ ] Industrijski (Alati) | [ ] Elegantan

---

## 4. FUNKCIONALNE SPECIFIKACIJE

### Korisnički interfejs (Flux UI)
* **Napredna pretraga:** Filtriranje artikala po brendu (npr. Makita, Bosch, DeWalt) i cenovnom rangu.
* **Checkout proces:** Optimizovan za Guest korisnike (brza kupovina) uz opciju registracije naloga.
* **Responsiveness:** Potpuna podrška za mobilne uređaje i tablete (PWA standard).

### Administracija (Vezir Framework)
* **Import podataka:** Podrška za masovni import artikala putem CSV/XML fajlova.
* **Upravljanje zalihama:** Integrisan modul za praćenje stanja zaliha dobavljača u MVP fazi.

---

## 5. ZAKLJUČAK I NAREDNI KORACI

Po prijemu popunjenog upitnika, razvojni tim Riviera Digital će pristupiti sledećim koracima:
1. Konfiguracija Azure resursa i baze podataka.
2. Implementacija vizuelnog identiteta klijenta.
3. Testiranje Sultan API servisa za email automatizaciju.
4. Deployment MVP verzije na produkcioni domen.

---

**Izvođač radova:**
Saša Kitić, sasa.kitic@riviera-digital.com
Senior .NET Developer, Riviera Digital