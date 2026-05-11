# DROPSHIPPING POSLOVNI MODEL: PREPORUKE I STRATEGIJA

**Klijent:** b-shop.hr (Jakša)  
**Priprema:** Saša Kitić, Riviera Digital (Vezir Platform)  
**Datum:** 26. januar 2026.  

---

## 1. DEFINICIJA MODELA POSLOVANJA

**Dropshipping** je model e-trgovine u kojem prodavac ne skladišti robu na sopstvenim zalihama. Logistički proces teče na sledeći način:

1. **Porudžbina:** Kupac vrši kupovinu na platformi b-shop.hr.
2. **Procesuiranje:** Informacije o porudžbini se prosleđuju dobavljaču.
3. **Logistika:** Dobavljač šalje proizvod direktno na adresu kupca.
4. **Dobit:** Zarada se ostvaruje kao razlika između prodajne cene i nabavne cene dobavljača.

**Ključne prednosti:** Eliminacija troškova skladištenja, minimalan početni kapital i visoka skalabilnost.  
**Izazovi:** Zavisnost od logistike dobavljača i potreba za preciznom sinhronizacijom zaliha.

---

## 2. FAZE TEHNIČKOG RAZVOJA

### Faza 1: MVP (Minimum Viable Product)
* **Cilj:** Validacija tržišta sa portfolijom od **1.000 artikala**.
* **Implementacija:** Osnovni checkout proces, plaćanje pouzećem i virmanom, ručni uvoz artikala.
* **Fokus:** Brzina lansiranja i stabilnost osnovnih funkcija.

### Faza 2: Skaliranje (15.000+ artikala)
* **Cilj:** Upravljanje širim asortimanom bez degradacije performansi.
* **Implementacija:** Elasticsearch (napredna pretraga), CDN za optimizaciju vizuelnih sadržaja, ručna sinhronizacija zaliha putem admin panela.

### Faza 3: Automatizacija (120.000+ artikala)
* **Cilj:** Potpuna automatizacija procesa uz minimalnu manuelnu intervenciju.
* **Implementacija:** Automatski API sync sa dobavljačem, online kartično plaćanje (Stripe/PayPal), automatsko generisanje transportnih dokumenata.

---

## 3. FINANSIJSKA STRUKTURA I OPERATIVNI TROŠKOVI

Proračun dobiti se vrši prema sledećoj formuli:
$$Dobit = (Promet \times Marža) - (Operativni\_Troškovi + Marketing)$$

### Projekcija operativnih troškova (Azure + Sultan API)

| Infrastruktura | Faza 1 (MVP) | Faza 2 (Scaling) | Faza 3 (Production) |
| :--- | :--- | :--- | :--- |
| **Hosting (Azure)** | €20 - €30 | €60 - €80 | €150 - €200 |
| **Baza podataka** | €10 - €15 | €30 - €40 | €80 - €100 |
| **Search Engine** | Integrisano | €25 - €30 | €50 - €70 |
| **Email (Sultan)** | €10 | €30 | €50 - €100 |
| **Ukupno (mjesečno)** | **~€40 - €55** | **~€160 - €200** | **~€360 - €520** |

---

## 4. POSLOVNE PROJEKCIJE (PRODAJA ALATA)

*Pretpostavka: Prosečna vrednost korpe iznosi 100€.*

| Parametar | Konzervativni (MVP) | Umereni (6 meseci) | Agresivni (12 meseci) |
| :--- | :--- | :--- | :--- |
| **Narudžbe / dan** | 2 - 3 | 10 | 30 |
| **Mesečni promet** | €6,000 - €9,000 | €30,000 | €90,000 |
| **Marža (prosek)** | 40% | 35% | 30% |
| **Marketing budžet** | €200 | €500 | €2,000 |
| **Neto dobit (mj.)** | **€2,350 - €3,550** | **€9,800** | **€23,500** |

---

## 5. OPERATIVNI SAVETI ZA USPEH

1. **Strategija marži:** Preporučena marža za niche alate je minimum **30-40%**. Izbegavati artikle sa maržom ispod 20% zbog troškova akvizicije kupca.
2. **Upravljanje zalihama:** U MVP fazi vršiti ručnu proveru dostupnosti najprodavanijih artikala. U kasnijim fazama obavezan je automatizovani XML/API feed.
3. **Korisnička podrška:** Brzina odgovora na upite unutar 2 sata direktno utiče na stopu konverzije i poverenje kupaca.
4. **Transparentnost isporuke:** Jasno komunicirati rok isporuke (2-5 radnih dana) na stranici svakog proizvoda.

---

## 6. CHECKLIST ZA IMPLEMENTACIJU

- [ ] Definisanje komercijalnih uslova sa dobavljačem (povrati i reklamacije).
- [ ] Izrada i testiranje Checkout toka (Order pipeline).
- [ ] Konfiguracija email notifikacija (Sultan API).
- [ ] Setup Google Analytics i Facebook Pixel-a.
- [ ] Finalno testiranje prikaza na mobilnim uređajima.

---

**Pripremio:** Saša Kitić  
Riviera Digital / Vezir Platform