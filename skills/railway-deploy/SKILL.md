---
name: railway-deploy
description: "Deploy applications to Railway. Use when: deploy to Railway, Railway deployment, railway up, railway logs, railway variables, Railway service, Railway environment, Railway environment variables, push to production, deploy API, deploy webshop, deploy Blazor."
---

# Railway Deploy — Riviera Digital

Step-by-step deployment workflow for deploying Kontrol, Poster, and other Riviera Digital projects to Railway.

## Deployment Types

| Project | Service | Dockerfile | Notes |
|---------|---------|------------|-------|
| Kontrol API | `kontrol-api` | `Dockerfile.api` | Main backend |
| Kontrol Web | `kontrol-web` | (build from Web.csproj) | Blazor Server admin |
| Libra88 WebShop | `libra88` | `Dockerfile.libra88` | Blazor WASM webshop |
| Poster sites | per site | `docker/Dockerfile.poster-*` | Marketing sites |

---

## Pre-Deploy Checklist

Always run through this before deploying to production:

```
[ ] dotnet build succeeds locally
[ ] No new .csproj files missing from Dockerfile COPY list
[ ] EF Core migrations: any pending migrations for this deployment?
[ ] Railway env variables: all required vars exist in the target service?
[ ] No secrets hardcoded in appsettings or code
[ ] Health check endpoint responds locally
[ ] Working on correct branch (master → production, development → staging)
```

---

## Step-by-Step: Deploy to Railway

### 1. Verify Build
```powershell
dotnet build src/hosts/Kontrol.Api/Kontrol.Api.csproj
```

### 2. Check for Pending Migrations
```powershell
dotnet ef migrations list --project src/infrastructure/Kontrol.Infrastructure.Data.Migrations.PostgreSQL
```
If there are pending migrations — apply them to the target DB **before** deploying the new code.

### 3. Apply Migrations (if needed)
```bash
# Against Railway's PostgreSQL (via Railway CLI):
railway run --service kontrol-api -- dotnet ef database update \
  --project src/infrastructure/Kontrol.Infrastructure.Data.Migrations.PostgreSQL
```
Or set `APPLY_MIGRATIONS=true` env var if the app auto-migrates on startup.

### 4. Deploy via Railway CLI
```bash
# Link project (first time only)
railway link

# Deploy current directory
railway up --service kontrol-api

# Or deploy with Dockerfile explicitly:
railway up --service kontrol-api --dockerfile Dockerfile.api
```

### 5. Monitor Deployment
```bash
# Watch logs in real time
railway logs --service kontrol-api

# Check service status
railway status
```

### 6. Verify After Deploy
```bash
# Check health endpoint
curl https://your-service.railway.app/health

# Check Railway dashboard for:
# - Service running (green)
# - No crash loops
# - Memory/CPU normal
```

---

## Environment Variables Reference

Required Railway variables per service:

### Kontrol API
| Variable | Description | Example |
|----------|-------------|---------|
| `Database__ConnectionString` | PostgreSQL connection | `Host=...;Port=...;Database=railway;...` |
| `Jwt__Secret` | JWT signing secret | min 32 chars |
| `Jwt__Issuer` | JWT issuer | `https://api.yourdomain.com` |
| `Cloudinary__CloudName` | Cloudinary account | `your-cloud-name` |
| `Cloudinary__ApiKey` | Cloudinary key | from Cloudinary dashboard |
| `Cloudinary__ApiSecret` | Cloudinary secret | from Cloudinary dashboard |
| `ASPNETCORE_ENVIRONMENT` | Environment name | `Production` |

### Check Current Variables
```bash
railway variables --service kontrol-api
```

### Set a Variable
```bash
railway variables set MY_VAR=value --service kontrol-api
```

---

## Rollback

Railway keeps previous deployments. To rollback:
1. Open Railway dashboard → Service → Deployments
2. Find the last working deployment
3. Click "Redeploy" on that deployment

Or via CLI:
```bash
railway redeploy --deployment <deployment-id>
```

---

## Troubleshooting

| Symptom | Check |
|---------|-------|
| Build fails in Railway | Run `docker build` locally with same Dockerfile to reproduce |
| App starts then crashes | `railway logs` — look for startup exceptions |
| 502 Bad Gateway | Health check failing, or app not listening on port 8080 |
| DB connection error | Check `Database__ConnectionString` Railway variable |
| Missing env var error | Run `railway variables` and compare to required list above |
| Old code running | Check deployment ID in logs — Railway might be using cached image |

---

## Aiven PostgreSQL (Production DB)

Railway services connect to Aiven PostgreSQL. Connection string format:
```
Host=<host>.aivencloud.com;Port=<port>;Database=defaultdb;Username=avnadmin;Password=<password>;SslMode=Require
```

Get connection details from: Aiven Console → Service → Connection Information
