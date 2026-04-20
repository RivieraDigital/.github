# Riviera Digital — Organization Coding Standards

These instructions apply to ALL Riviera Digital repositories. Individual repos may have additional repo-specific instructions.

---

## 1. Coding Standards

### Language & Framework
- .NET 10.0, C#, ASP.NET Core
- Blazor (Server and WebAssembly)
- PostgreSQL + Entity Framework Core

### Naming Conventions
- **PascalCase**: public members, types, methods, properties
- **camelCase**: local variables, parameters, private fields
- **I-prefix**: interfaces (`IProductService`, `IOrderRepository`)
- **Suffix patterns**: `*Request`, `*Response`, `*Command`, `*Query`, `*Handler`, `*Validator`, `*ViewModel`

### Architecture Patterns
- **OperationResult\<T\>** for all service return types — never throw exceptions for business logic
- **Manual CQRS** — Command + Handler, Query + Handler. NO MediatR
- **Thin controllers** — delegate to Application layer services
- **DTOs in Contracts** — never expose Domain entities to API
- **Dependency Injection** for all services
- **async/await everywhere** — never use `.Result`, `.Wait()`, or `Task.Run()` for async operations
- **MVVM for Blazor** — ViewModels in `.UI` projects (clean .NET, no Blazor dependencies), Razor components separate

### Task Tokens
Use in code comments for VS Task List tracking:
- `// TODO:` — implementation needed
- `// FIXME:` — broken, needs fix
- `// BUG:` — known bug
- `// HACK:` — temporary workaround
- `// REVIEW:` — needs review
- `// OPTIMIZE:` — performance opportunity

---

## 2. Git Workflow

### Branching Model
- **`master`** — production branch (deployed to Railway)
- **`development`** — active development branch
- Feature branches: `feature/short-description`
- Bugfix branches: `fix/short-description`
- Flow: `feature/*` → `development` → `master`

### Commit Convention — Conventional Commits
```
type(scope): short description

feat:     New feature
fix:      Bug fix
docs:     Documentation only
chore:    Build, tooling, dependencies
refactor: Code change that neither fixes nor adds
test:     Adding or fixing tests
style:    Formatting, whitespace (no logic change)
perf:     Performance improvement
```

Examples:
- `feat(catalog): add product search endpoint`
- `fix(orders): correct tax calculation for HR`
- `docs: update README with deploy instructions`

### Rules
- Write clear, descriptive commit messages
- One logical change per commit
- Never commit secrets, connection strings, or API keys

---

## 3. Language Policy

- **Code**: English — variable names, function names, class names, comments
- **UI text / labels**: Serbian (Latin script) — buttons, messages, form labels
- **Documentation**: Serbian for business docs, English for technical docs and READMEs
- **Framework terms stay English**: ViewModel, Service, Controller, Repository, Handler

---

## 4. Security

### OWASP Top 10 Awareness
- **Input validation** at system boundaries (Application layer)
- **Parameterized queries** — never concatenate SQL strings
- **Authentication/Authorization** on all API endpoints — no anonymous access to business data
- **HTTPS** enforced in production
- **CORS** configured explicitly — no wildcard origins in production

### Secrets Management
- **Never** commit secrets, API keys, or connection strings to source control
- Use environment variables or user-secrets for local development
- Use platform-specific secret management in production (Railway variables, Azure Key Vault)
- `.gitignore` must exclude `appsettings.*.json` (except base `appsettings.json`)

### Code Safety
- Validate all external input (API requests, file uploads, query parameters)
- Sanitize output to prevent XSS
- Use `[Authorize]` attributes — opt-out (allow anonymous) rather than opt-in
- Log security events (failed logins, authorization failures)

---

## 5. AI Usage Guidelines

### What AI Can Do Freely
- Read and analyze code
- Search the codebase for context
- Make small, contained code changes (single file, clear intent)
- Run build commands (`dotnet build`, `dotnet test`)
- Update documentation and plan files

### What AI Must Ask Before Doing
- Changes affecting more than 3 files
- Deleting files or folders
- Database migrations
- Git operations (push, force push, reset)
- Deploying or affecting production systems
- Architectural decisions or pattern changes
- Creating new projects or solutions

### AI Best Practices
- Always read existing code before modifying
- Run `dotnet build` after every code change to verify
- Follow existing patterns in the codebase — don't introduce new ones without discussion
- Keep changes minimal — do exactly what was asked, no extra "improvements"
- When uncertain between approaches, present options and let the developer choose
