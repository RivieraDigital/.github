---
name: dockerfile-review
description: "Audit, review, and improve Dockerfiles for ASP.NET Core (.NET 10) projects. Use when: reviewing Dockerfile, improving Docker build, multi-stage Dockerfile, container optimization, Docker best practices, containerize, Dockerfile for Railway, .NET Docker, security in container."
---

# Dockerfile Review & Improvement — .NET 10 / ASP.NET Core

Adapted from the awesome-copilot `multi-stage-dockerfile` and `containerize-aspnetcore` community skills, tuned for Riviera Digital's Railway-hosted .NET 10 stack.

## When to Use
- Creating a new Dockerfile for an ASP.NET Core project
- Reviewing or improving an existing Dockerfile
- Optimizing build time via layer caching
- Hardening a container for production on Railway

---

## Review Checklist

Read the existing Dockerfile first, then evaluate each point:

### ✅ Structure
- [ ] Multi-stage build: `sdk` for build, `aspnet` for runtime
- [ ] SDK image used: `mcr.microsoft.com/dotnet/sdk:10.0`
- [ ] Runtime image used: `mcr.microsoft.com/dotnet/aspnet:10.0`
- [ ] Specific tag (not `latest`) on all `FROM` statements
- [ ] `WORKDIR /src` set in build stage, `WORKDIR /app` in runtime stage

### ✅ Layer Caching
- [ ] `.csproj` files are copied BEFORE source code
- [ ] `dotnet restore` runs right after `.csproj` copy (before `COPY . .`)
- [ ] Source code copied AFTER restore (so restore is cached unless deps change)
- [ ] `nuget.config` copied alongside `.csproj` files (if present)

### ✅ Security
- [ ] Non-root user: `USER $APP_UID` or explicit non-root user in runtime stage
- [ ] No secrets, passwords, or connection strings hardcoded
- [ ] No `.env` files or `appsettings.*.json` with secrets copied in
- [ ] `.dockerignore` exists and excludes: `bin/`, `obj/`, `.git/`, `*.user`, `appsettings.*.json`

### ✅ Railway Compatibility
- [ ] `ENV ASPNETCORE_URLS=http://+:8080`
- [ ] `EXPOSE 8080`
- [ ] No HTTPS setup (Railway handles TLS externally)
- [ ] No hardcoded connection strings (use Railway env variables)

### ✅ Optional but Recommended
- [ ] Health check: `HEALTHCHECK --interval=30s --timeout=3s CMD curl -f http://localhost:8080/health || exit 1`
- [ ] `curl` installed in runtime stage for health checks: `RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*`

---

## Ideal Dockerfile Pattern for Riviera Digital

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
WORKDIR /src

# 1. Copy project files first (enables layer caching for restore)
COPY nuget.config .                            # if exists
COPY src/hosts/MyProject/MyProject.csproj src/hosts/MyProject/
COPY src/modules/Module1/Module1.csproj src/modules/Module1/
# ... all .csproj files ...

# 2. Restore (cached unless .csproj files change)
RUN dotnet restore src/hosts/MyProject/MyProject.csproj

# 3. Copy source and build
COPY . .
RUN dotnet publish src/hosts/MyProject/MyProject.csproj \
    -c Release \
    -o /app/publish \
    --no-restore

# Runtime stage — no SDK, minimal image
FROM mcr.microsoft.com/dotnet/aspnet:10.0 AS runtime
WORKDIR /app

# Install curl for health checks
RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

COPY --from=build /app/publish .

ENV ASPNETCORE_URLS=http://+:8080
ENV ASPNETCORE_ENVIRONMENT=Production

EXPOSE 8080

HEALTHCHECK --interval=30s --timeout=3s --start-period=10s --retries=3 \
    CMD curl -f http://localhost:8080/health || exit 1

# Non-root user
USER $APP_UID

ENTRYPOINT ["dotnet", "MyProject.dll"]
```

---

## Common Problems & Fixes

| Problem | Fix |
|---------|-----|
| `COPY . .` before `dotnet restore` | Restore is never cached — move `.csproj` copy + restore before `COPY . .` |
| Missing `.csproj` in COPY list | Build fails after adding a new project to the solution — add the new `.csproj` |
| `latest` tag on base image | Pin to `10.0` or `10.0-bookworm-slim` for reproducibility |
| Running as root | Add `USER $APP_UID` before `ENTRYPOINT` |
| HTTPS configured in container | Railway terminates TLS — remove HTTPS setup, use `http://+:8080` only |
| No `.dockerignore` | Bloated build context, slow builds — create `.dockerignore` |

---

## .dockerignore Template

```
bin/
obj/
.git/
.github/
.vs/
.vscode/
**/node_modules/
*.user
*.suo
**/.DS_Store
**/Thumbs.db
appsettings.Development.json
appsettings.Staging.json
docker/
docs/
Plans/
TODO.md
```
