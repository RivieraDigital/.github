# 🔗 TRENDSOFT INTEGRATION - REFERENCE DOKUMENTACIJA

> **Datum:** 2.2.2026  
> **Status:** Analiza završena - Ready za portovanje u Kontrol  
> **Projekat:** Libra88 WebShop → Vezir.Kontrol CMS

---

## 📍 LOKACIJE

### **Stari Projekat (SaleIT):**
```
F:\Work\SaleIT\Libra88WebShop\
├── docs/Libra88 TrendSoft/API specifikacija Libra88.pdf
└── src/Server/Libra88WebShop.Server.Business/
    └── Services/Integration/Import/Domain/Trendsoft/
```

### **Novi Projekat (Kontrol):**
```
F:\Work\VEZIR ROOT\Vezir\src\modules\
└── Vezir.Modules.Integrations.TrendSoft/ (← Kreirati!)
```

---

## 🔐 API CREDENTIALS (Bane)

```json
{
  "TrendsoftApi": {
    "BaseUrl": "http://servislibra88.com/api/",
    "Credentials": {
      "Header": "X-API-TOKEN",
      "Value": "CHoVN25XRFytep"
    }
  }
}
```

**Test Endpoint:**
```bash
curl -H "X-API-TOKEN: CHoVN25XRFytep" http://servislibra88.com/api/products?page=1
```

---

## 📦 POSTOJEĆI KOD (SaleIT Projekat)

### **1. TrendsoftHttpService.cs**
```csharp
public class TrendsoftHttpService : HttpService, ITrendsoftHttpService
{
    private static HttpClient? client;
    protected override string ClientName => HttpClientNamesConsts.TrendsoftApi;
    
    // IHttpClientFactory setup sa BaseUrl i header
}
```

### **2. TrendsoftHttpHandler.cs** (Auth)
```csharp
public class TrendsoftHttpHandler : DelegatingHandler
{
    protected override async Task<HttpResponseMessage> SendAsync(...)
    {
        // Dodaje X-API-TOKEN header automatski
        request.Headers.Add(options.Credentials.Header, options.Credentials.Value);
        return await base.SendAsync(request, cancellationToken);
    }
}
```

### **3. TrendsoftImportService<TEntity, TDto>** (Base)
```csharp
public abstract class TrendsoftImportService<TEntity, TDto> 
    where TEntity : IIntegratedEntity
    where TDto : class
{
    protected abstract string RequestUrl { get; }
    
    public virtual async IAsyncEnumerable<TEntity> ImportFromTrendsoftApi(...)
    {
        // Pagination support
        do {
            var response = await trendsoftHttpService.GetAsync<TrendsoftApiResponse<TDto>>(...);
            foreach (var entity in response.Data.Data.Select(mapper.Map<TEntity>))
                yield return entity;
                
            requestUri = response.Data.NextPageUrl;
        } while (!cancellationToken.IsCancellationRequested);
    }
}
```

### **4. ProductsTrendsoftImportService.cs**
```csharp
public class ProductsTrendsoftImportService 
    : TrendsoftImportService<ProductEntity, ProductLDTO>
{
    protected override string RequestUrl => integrationOptions.RequestUrl;
    // "products" endpoint
}
```

### **5. ProductLDTO.cs** (TrendSoft Response Model)
```csharp
public class ProductLDTO
{
    [JsonPropertyName("sifra")]
    public required int Id { get; set; }

    [JsonPropertyName("naziv")]
    public required string Name { get; set; }

    [JsonPropertyName("j_mere")]
    public string Unit { get; set; }

    [JsonPropertyName("p_cena")]
    public string? _Price { get; set; }
    
    public decimal? Price => decimal.TryParse(_Price, out var price) ? price : default;

    [JsonPropertyName("kataloski_broj")]
    public string? CatalogNumber { get; set; }

    [JsonPropertyName("bar_cod")]
    public string Barcode { get; set; }

    [JsonPropertyName("tip")]
    public required int ProductGroupId { get; set; }

    [JsonPropertyName("proizvodjaci_id")]
    public int? ManufacturerId { get; set; }

    [JsonPropertyName("opis")]
    public string? Description { get; set; }

    [JsonPropertyName("info")]
    public string? Info { get; set; }
}
```

### **6. TrendsoftApiResponse<T>** (Pagination)
```csharp
public class TrendsoftApiResponse<TEntity> where TEntity : class
{
    [JsonPropertyName("current_page")]
    public int CurrentPage { get; set; }

    [JsonPropertyName("data")]
    public IEnumerable<TEntity> Data { get; set; } = [];

    [JsonPropertyName("next_page_url")]
    public string? NextPageUrl { get; set; }

    [JsonPropertyName("total")]
    public int Total { get; set; }
}
```

### **7. AutoMapper Profile**
```csharp
CreateMap<ProductLDTO, ProductEntity>()
    .ForMember(dest => dest.Id, exp => exp.MapFrom(src => 0))
    .ForMember(dest => dest.TrendsoftEntityId, exp => exp.MapFrom(src => src.Id))
    .ForMember(dest => dest.GroupId, exp => exp.MapFrom(src => src.ProductGroupId))
    .ForMember(dest => dest.Name, exp => exp.MapFrom(src => src.Description ?? src.Name))
    .ForMember(dest => dest.Description, exp => exp.MapFrom(src => src.Name));
```

### **8. API Controller Endpoints**
```csharp
[Route("api/integration/trendsoft-libra")]
public class TrendsoftLibraApiController : BaseController
{
    [HttpGet("import/products")]
    public async Task<ActionResult<GeneralResponse>> ImportProduct(...)
    
    [HttpGet("import/product-groups")]
    public async Task<ActionResult<GeneralResponse>> ImportProductGroups(...)
    
    [HttpGet("import/manufacturers")]
    public async Task<ActionResult<GeneralResponse>> ImportManufacturers(...)
    
    [HttpGet("import/tariff-rates")]
    public async Task<ActionResult<GeneralResponse>> ImportTariffRates(...)
    
    [HttpGet("import/business-partners")]
    public async Task<ActionResult<GeneralResponse>> ImportBusinessPartners(...)
}
```

### **9. Entity Interface**
```csharp
public interface ITrendsoftEntity<T> where T : IEquatable<T>
{
    /// <summary>
    /// Id in Trendsoft Api db.
    /// </summary>
    public T TrendsoftEntityId { get; set; }
}

public interface IIntegratedEntity : IEntity, ITrendsoftEntity<int>
{
}
```

---

## 🗺️ PORTOVANJE → KONTROL

### **ŠTA TREBA ADAPTIRATI:**

| SaleIT Projekat | Kontrol Target | Napomena |
|-----------------|----------------|----------|
| `ProductEntity` | `Product` (Vezir.Modules.Catalog) | Domain model |
| `ProductGroupEntity` | `Category` | Renamed |
| `ManufacturerEntity` | `Manufacturer` ili `Brand` | Check Kontrol schema |
| `TariffRateEntity` | Možda nije potrebno | Check biznis logika |
| `BusinessPartnerEntity` | Možda nije potrebno | Check use case |

### **NOVI MODUL STRUKTURA:**

```
Vezir.Modules.Integrations.TrendSoft/
│
├── Core/
│   ├── TrendsoftClient.cs              (Port: TrendsoftHttpService)
│   ├── TrendsoftAuthHandler.cs         (Port: TrendsoftHttpHandler)
│   └── TrendsoftMapper.cs              (Port: IntegrationProfile)
│
├── Services/
│   ├── TrendsoftImportService<T>.cs    (Port: Base class)
│   ├── ProductSyncService.cs           (Port: ProductsTrendsoftImportService)
│   ├── CategorySyncService.cs          (Port: ProductGroupsTrendsoftImportService)
│   └── ManufacturerSyncService.cs      (Port: ManufacturersTrendsoftImportService)
│
├── Models/
│   ├── TrendsoftProduct.cs             (Port: ProductLDTO)
│   ├── TrendsoftCategory.cs            (Port: ProductGroupsLDTO)
│   ├── TrendsoftManufacturer.cs        (Port: ManufacturerLDTO)
│   └── TrendsoftApiResponse.cs         (Port: TrendsoftApiResponse<T>)
│
├── Configuration/
│   ├── TrendsoftSettings.cs            (Port: TrendsoftApiOptions)
│   └── TrendsoftServiceExtensions.cs   (DI registration)
│
└── Controllers/
    └── TrendsoftIntegrationController.cs (Port: TrendsoftLibraApiController)
```

---

## 🎯 BUSINESS IMPACT

| Metrika | Vrednost |
|---------|----------|
| **Libra88 (Bane)** | MVP klijent - €1,100 dug poništen |
| **TrendSoft korisnici** | 20+ potencijalnih trgovaca |
| **Godišnji potencijal** | €36,000+ (20 × €1,800) |
| **Recurring revenue** | +€2,000-3,000/god hosting |
| **Konkurentska prednost** | JEDINI out-of-box TrendSoft integration |

**Strategija:** TrendSoft integracija = flagship feature za Kontrol CMS!

---

## ⏱️ PROCENA POSLA

| Faza | Vreme | Opis |
|------|-------|------|
| **Port Integration Code** | 4-6h | Adapt servisa, DTOs, mapper |
| **Database Setup** | 2-3h | Local PostgreSQL + migrations |
| **API Test** | 1-2h | Verify connection, pull test data |
| **Bulk Import** | 2-3h | 300 artikala import |
| **Libra88 API Integration** | 3-4h | Replace mock data |
| **MVP Deploy** | 4-6h | Production hosting + DNS |
| **TOTAL** | **16-24h** | ~3-4 dana full-time |

---

## 📋 CHECKLIST - PORT PROCEDURE

**Pre nego što počneš:**
- [ ] Backup SaleIT projekta
- [ ] Kreirati Vezir.Modules.Integrations.TrendSoft folder
- [ ] Setup test PostgreSQL database
- [ ] Pripremiti Kontrol Domain modele (Product, Category)

**Tokom portovanja:**
- [ ] Copy-paste fajl po fajl sa adaptacijom
- [ ] Rename namespaces (Libra88WebShop → Vezir)
- [ ] Update Entity references (ProductEntity → Product)
- [ ] Test svaki servis pojedinačno
- [ ] Verify JSON serialization radi

**Posle portovanja:**
- [ ] Integration test sa real TrendSoft API
- [ ] Bulk import test (10-20 artikala prvo)
- [ ] Performance test (300+ artikala)
- [ ] Error handling validation
- [ ] Admin panel UI dodaj

---

## 🚨 NAPOMENE

**Što radi trenutno u SaleIT:**
✅ HTTP client sa auth  
✅ Pagination support  
✅ Generic import service  
✅ AutoMapper profili  
✅ Error handling  
✅ Async/await patterns  

**Što treba dodati u Kontrol:**
- [ ] Admin UI za manual sync
- [ ] Sync history/logs (database table)
- [ ] Scheduled background jobs (Hangfire ili Quartz)
- [ ] Webhook support (ako TrendSoft ima)
- [ ] Image sync (ako TrendSoft ima image URLs)
- [ ] Stock level real-time update

---

## 📚 DODATNI RESURSI

**PDF Dokumentacija:** `F:\Work\SaleIT\Libra88WebShop\docs\Libra88 TrendSoft\API specifikacija Libra88.pdf`

**Programer kontakt:** Programer TrendSoft tima (potvrdio da se API nije menjaо)

**Existing credentials:** Validni (testovano ranije)

---

**Last Updated:** 2.2.2026 23:50  
**Next Step:** Port integration module → Kontrol  
**Status:** Ready to start! 🚀
