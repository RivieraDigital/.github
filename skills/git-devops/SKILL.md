---
name: git-devops
description: "Git workflow for DevOps: conventional commits, branching, release tagging, hotfix flow. Use when: git commit message, conventional commit, branch strategy, git flow, release branch, hotfix, merge to master, tag release, git devops workflow."
argument-hint: "What git operation do you need help with?"
---

# Git DevOps Workflow — Riviera Digital

Adapted from the awesome-copilot `conventional-commit` and `git-flow-branch-creator` community skills.

## Branch Model

```
master          → production (auto-deploys to Railway)
development     → active development (staging)
feature/...     → new features
fix/...         → bug fixes
hotfix/...      → urgent production fixes
release/...     → release preparation (optional)
```

**Flow:** `feature/*` or `fix/*` → `development` → `master`

---

## Conventional Commits

Format: `type(scope): short description`

### Types
| Type | When |
|------|------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `chore` | Build, tooling, dependencies |
| `refactor` | Code change, no new feature or bug fix |
| `test` | Adding or fixing tests |
| `style` | Formatting, whitespace (no logic change) |
| `perf` | Performance improvement |
| `ci` | CI/CD configuration changes |
| `build` | Docker, build system changes |

### Scopes (Riviera Digital)
`catalog`, `orders`, `identity`, `blog`, `integrations`, `reporting`, `settings`, `webusers`, `api`, `web`, `deploy`, `docker`, `db`

### Examples
```
feat(catalog): add product image upload endpoint
fix(orders): correct tax calculation for HR locale
chore(docker): update Kontrol.Api Dockerfile to .NET 10
ci: add Railway deployment health check
build(api): add missing Module.csproj to Dockerfile
docs: update deploy instructions in README
refactor(identity): extract token generation to service
perf(catalog): add database index on ProductSku
```

---

## Workflow Procedures

### Start a New Feature
```bash
git checkout development
git pull origin development
git checkout -b feature/short-description
# ... work ...
git add .
git commit -m "feat(scope): description"
git push origin feature/short-description
# Create PR: feature/... → development
```

### Bug Fix
```bash
git checkout development
git pull origin development
git checkout -b fix/issue-description
# ... fix ...
git commit -m "fix(scope): what was fixed"
git push origin fix/issue-description
# Create PR: fix/... → development
```

### Deploy to Production
```bash
# Merge development → master
git checkout master
git pull origin master
git merge development --no-ff -m "chore: release to production"
git tag v<version>
git push origin master --tags
# Railway auto-deploys from master (or trigger manually)
```

### Hotfix (urgent production fix)
```bash
git checkout master
git pull origin master
git checkout -b hotfix/critical-issue
# ... fix ...
git commit -m "fix(scope): critical description"
# Merge to both master AND development
git checkout master && git merge hotfix/critical-issue --no-ff
git checkout development && git merge hotfix/critical-issue --no-ff
git push origin master development
git branch -d hotfix/critical-issue
```

---

## Pre-Commit Checklist

Before every commit:
- [ ] `dotnet build` passes (no compile errors)
- [ ] No secrets/connection strings in changed files
- [ ] Commit message follows conventional format
- [ ] Only changes for THIS logical unit (no mixed concerns)

---

## Generating a Commit Message

Run these steps to auto-generate a commit:

```bash
# 1. Check what changed
git status
git diff --staged

# 2. Generate message based on changes
# (Ask devops agent: "suggest a commit message for these changes")

# 3. Commit
git commit -m "type(scope): description"
```
