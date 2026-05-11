# 🚀 DROPSHIPPING WEBSHOP - BEST PRACTICES & RECOMMENDATIONS

**Za:** b-shop.hr (Jakša)  
**Priprema:** Vezir Platform  
**Datum:** Januar 26, 2026

---

## 📌 **ŠTO JE DROPSHIPPING?**

**Dropshipping** je business model gdje **ne držiš proizvode na zalihama**. Kada kupac naruči:
1. ✅ Kupac naruči na tvom webshopu (b-shop.hr)
2. ✅ Ti proslediš narudžbu dobavljaču
3. ✅ Dobavljač šalje direktno kupcu
4. ✅ Ti zarađuješ **razliku između tvoje cijene i dobavljačeve**

**Prednosti:** Nema troškova skladišta, mali rizik, brzo se skalira  
**Izazovi:** Manji kontrola kvalitete, ovisnost o dobavljaču, manje marže

---

## 🎯 **FAZE RAZVOJA - NAŠA PREPORUKA**

### **🔰 FAZA 1: MVP (2-3 tjedna) - "Test the Waters"**

**Cilj:** Dokazati da koncept funkcionira sa **1000 proizvoda**

✅ **Što implementiramo:**
- Osnovni webshop sa košaricom i checkoutom
- Plaćanje: Pouzećem + Virman (bez kartica zasad)
- **Ručno dodavanje proizvoda** ili CSV import (jednostavno)
- Admin panel za upravljanje narudžbama
- Pretraga i osnovni filteri (kategorije, cijena)
- Email potvrda narudžbi

✅ **Što NE radimo u MVP:**
- Online kartice (treba payment gateway setup, vrijeme + novac)
- Automatski sync sa dobavljačem (kompleksno, može kasnije)
- Napredne analize (ne trebaš dok nema prometa)

💰 **Investicija:** Minimalna cijena za funkcionalan webshop  
⏱️ **Vrijeme:** 2-3 tjedna  
🎯 **Rezultat:** Možeš testirati market sa pravim kupcima

---

### **🔄 FAZA 2: Skaliranje (nakon 1-2 mjeseca) - "15k proizvoda"**

**Trigger:** Kad vidiš da prodaja ide i trebaš više proizvoda

✅ **Što dodajemo:**
- **Elasticsearch** - brza pretraga za 15,000+ proizvoda
- **Ručni sync button** - klik u admin panelu za osvježavanje zaliha
- **Performance optimizacija** - brže učitavanje
- **CDN za slike** - spremaju se na brže servere
- **Napredni filteri** - više opcija za pretragu

💰 **Investicija:** Dodatni development + infrastruktura  
⏱️ **Vrijeme:** 2-3 tjedna development  
🎯 **Rezultat:** Spreman za 15,000 proizvoda bez usporavanja

---

### **🚀 FAZA 3: Automation (nakon 6-12 mjeseci) - "120k proizvoda"**

**Trigger:** Kad imaš stalan promet i trebaš automatizaciju

✅ **Što dodajemo:**
- **Online kartice** (Stripe/PayPal) - više kupaca završi kupovinu
- **Automatski sync sa dobavljačem** - dnevno osvježavanje zaliha
- **API integracija sa dostavljačima** - automatsko kreiranje shipping labela
- **Invoice generation** - automatske fakture
- **Advanced analytics** - detaljni izvještaji o prodaji

💰 **Investicija:** Značajna ali opravdana prometa  
⏱️ **Vrijeme:** 4-6 tjedana development  
🎯 **Rezultat:** Potpuno automatiziran sustav, minimalna ručna intervencija

---

## 💡 **DROPSHIPPING SUCCESS TIPS**

### **1️⃣ Proizvodi i Cijene**

✅ **Marža:** Minimum **30-40%** marža na proizvode  
❌ **Izbjegavaj:** Ultra low-margin proizvode (manje od 20%)  

**Primjer:**
- Dobavljač: 50€
- Tvoja cijena: **75€** (50% marža)
- Dobit po komadu: 25€ (minus dostava i troškovi)

✅ **Niche vs. General:**
- **Niche** (specijalizirani alati) = više marže, manje konkurencije
- **General** (svi proizvodi) = veći promet, manja marža

---

### **2️⃣ Zalihe i Dostupnost**

⚠️ **Biggest Challenge:** Proizvod nestane kod dobavljača, a ti ga još prodaješ

**Rješenje:**
- ✅ **MVP faza:** Ručno provjeravaš dostupnost 1x tjedno
- ✅ **Faza 2:** Ručni sync button u admin panelu (osvježiš kad hoćeš)
- ✅ **Faza 3:** Automatski sync svaki dan (XML/API feed)

💡 **Best Practice:** Uvijek imaj **"Out of Stock" notifikaciju** na webshopu

---

### **3️⃣ Vrijeme Isporuke**

🚨 **Kupci očekuju brzu isporuku!**

**Tipična dostava u Hrvatskoj:**
- HP (Hrvatske pošte): 2-3 dana
- GLS/DPD: 1-2 dana (express)

**Preporuka:**
- Jasno napiši **"Dostava za 2-5 radnih dana"** na webshopu
- Nikad ne obećaj brže nego što dobavljač može

---

### **4️⃣ Customer Service**

✅ **Must-have:**
- Brzo odgovaranje na pitanja (Facebook, email, telefon)
- Transparentnost o rokovima
- Jednostavan returns/refunds proces

⚠️ **Watch out:**
- Dropshipping = ne vidiš proizvod prije slanja
- Kvaliteta ovisna o dobavljaču
- Probleme rješavaš preko dobavljača

**Solution:** Ispravi **prvi put** odmah (refund/zamjena) da dobiješ dobar review

---

### **5️⃣ Marketing i Prodaja**

📊 **Gdje dolaze kupci?**
- **Google Shopping** - najviše konverzija za e-commerce
- **Facebook/Instagram Ads** - vizualni proizvodi (alat display)
- **SEO** - dugoročna strategija (treba vrijeme)

💰 **Budget preporuka za početak:**
- €200-300/mj na Facebook Ads (testiranje)
- €100-200/mj na Google Shopping
- SEO organski (besplatno, treba vrijeme)

---

## 🛠️ **TEHNIČKI SETUP - FAZE**

### **MVP (1000 proizvoda)**

| Komponenta | Rješenje | Cijena/mj |
|------------|----------|-----------|
| **Hosting** | Azure App Service Basic | ~€20-30 |
| **Database** | PostgreSQL Basic | ~€10-15 |
| **Email** | Sultan API | €10 (1000 emails) |
| **Domain** | b-shop.hr | Već imaš ✅ |
| **SSL** | Let's Encrypt | Besplatno ✅ |
| **Pretraga** | SQL Full-text | Uključeno ✅ |

**Ukupno:** ~€40-55/mj operational costs

---

### **Scaling (15k proizvoda)**

| Komponenta | Rješenje | Cijena/mj |
|------------|----------|-----------|
| **Hosting** | Azure Standard | ~€60-80 |
| **Database** | PostgreSQL Standard | ~€30-40 |
| **Elasticsearch** | Basic tier | ~€25-30 |
| **CDN** | Azure CDN | ~€15-20 |
| **Email** | Sultan API | €30 (3000 emails) |

**Ukupno:** ~€160-200/mj operational costs

---

### **Production (120k proizvoda)**

| Komponenta | Rješenje | Cijena/mj |
|------------|----------|-----------|
| **Hosting** | Azure Premium | ~€150-200 |
| **Database** | PostgreSQL Premium | ~€80-100 |
| **Elasticsearch** | Standard tier | ~€50-70 |
| **CDN** | Azure CDN Premium | ~€30-50 |
| **Email** | Sultan API | €50-100 |
| **Payment Gateway** | Stripe/PayPal | 2-3% po transakciji |

**Ukupno:** ~€360-520/mj operational costs

💡 **Ovo pokriva kad imaš 50-100 narudžbi dnevno!**

---

## 📊 **BUSINESS PROJEKCIJE - PRIMJER**

Pretpostavka: **Alati** prodaja, prosječna narudžba **100€**

### **Scenario 1: Conservative (MVP faza)**
- 2-3 narudžbe/dan
- 60-90 narudžbi/mjesec
- Promet: **€6,000-9,000/mj**
- Marža 40%: **€2,400-3,600/mj**
- Operativni troškovi: €50/mj
- Neto: **€2,350-3,550/mj**

### **Scenario 2: Moderate (Nakon 6 mjeseci)**
- 10 narudžbi/dan
- 300 narudžbi/mjesec
- Promet: **€30,000/mj**
- Marža 35%: **€10,500/mj**
- Operativni troškovi: €200/mj
- Marketing: €500/mj
- Neto: **€9,800/mj**

### **Scenario 3: Aggressive (Nakon 12 mjeseci)**
- 30 narudžbi/dan
- 900 narudžbi/mjesec
- Promet: **€90,000/mj**
- Marža 30%: **€27,000/mj**
- Operativni troškovi: €500/mj
- Marketing: €2,000/mj
- Customer support: €1,000/mj
- Neto: **€23,500/mj**

💡 **Ovo su optimistične ali realne projekcije ako marketing ide dobro!**

---

## ✅ **CHECKLIST ZA USPJEŠAN START**

### **Prije lansiranja:**
- [ ] Dogovoreni uvjeti sa dobavljačem (cijene, dostava, povrati)
- [ ] Testirana dostupnost proizvoda
- [ ] Definirane dostavljačke službe
- [ ] Spremni terms of service i privacy policy
- [ ] Testirano checkout flow od početka do kraja
- [ ] Email notifikacije testrane
- [ ] Facebook/Instagram stranice aktivne
- [ ] Google Analytics setup

### **Prvi tjedan produkcije:**
- [ ] Pratiti svaku narudžbu ručno (Quality Control)
- [ ] Odgovarati na sva pitanja u 1-2 sata
- [ ] Fiksirati male bugove (normalno je!)
- [ ] Prikupljati feedback od kupaca

### **Prvi mjesec:**
- [ ] Analizirati najprodavanije proizvode
- [ ] Ukloniti proizvode koji se ne prodaju
- [ ] Optimizirati cijene prema konkurenciji
- [ ] Testirati različite marketing kanale

---

## 🎯 **NAŠA PREPORUKA ZA b-shop.hr**

**Faza 1 (Start):**
✅ MVP sa 1000 proizvoda alata  
✅ Pouzećem + Virman  
✅ Ručni sync sa dobavljačem  
✅ Fokus na marketing i prodaju  

**Faza 2 (Nakon 2-3 mjeseca):**
✅ Proširenje na 15k proizvoda  
✅ Performance upgrade  
✅ Ručni sync button  

**Faza 3 (Nakon 6-12 mjeseci):**
✅ Automatizacija svega  
✅ Online kartice  
✅ 120k proizvoda  

---

**Pitanja?**  
**Saša Kitić**  
Email: [tvoj email]  
Tel: [tvoj telefon]

**U kopiji:** Tomislav Skulić - Riviera Digital
