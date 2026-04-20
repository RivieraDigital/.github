# .github — Riviera Digital Organization Defaults

Shared AI agents, prompts, coding standards, and GitHub configuration for all Riviera Digital repositories.

## What's in this repo

| Folder | Purpose |
|--------|---------|
| `.github/copilot-instructions.md` | Organization-wide coding standards for GitHub Copilot |
| `agents/` | Shared AI agents (worker, planner, reviewer) |
| `prompts/` | Reusable prompt templates (code review, commit messages, etc.) |
| `profile/` | GitHub organization public profile |

## Quick Start

### 1. AI Agents

These agents are available across all Riviera Digital repos:

- **worker** — Executes approved plans step by step with build verification
- **planner** — Interactive planning partner for organizing tasks into sprints
- **reviewer** — Reviews completed work, verifies code quality, closes plans

**Workflow:** planner → worker → reviewer

### 2. Prompt Templates

Use these prompts in VS Code with GitHub Copilot:

| Prompt | What it does |
|--------|-------------|
| `code-review` | Reviews selected code against our .NET standards |
| `commit-message` | Generates a Conventional Commit message from staged changes |
| `new-feature` | Scaffolds a new feature with proper architecture layers |
| `pr-description` | Generates a PR description from branch diff |

### 3. Coding Standards

The `copilot-instructions.md` file defines organization-wide rules:

- **Coding standards** — PascalCase, async/await, OperationResult\<T\>, no MediatR
- **Git workflow** — master (production) + development, Conventional Commits
- **Language policy** — English for code, Serbian for UI text
- **Security** — OWASP awareness, input validation, secrets management
- **AI usage** — what AI can do freely vs. what requires approval

## Repo-specific overrides

Individual repos have their own `.github/copilot-instructions.md` with repo-specific rules. The org-level instructions provide the baseline; repo-level instructions add project-specific details.

| Repo | Focus |
|------|-------|
| Kontrol | Modular Clean Architecture, Manual CQRS, module patterns |
| Mozaik | MVVM, Blazor components, Material Design |
| Porto | Email service patterns |
| Poster | Lightweight marketing sites, Tailwind CSS |

## For New Team Members

1. Make sure you have [VS Code](https://code.visualstudio.com/) with [GitHub Copilot](https://github.com/features/copilot)
2. The agents and prompts from this repo are automatically available in all org repos
3. Read the `copilot-instructions.md` to understand our coding standards
4. Read `CONTRIBUTING.md` for contribution guidelines
5. Start with the **planner** agent when tackling a new task

## Branching & Commits

- **Branches**: `master` (production), `development` (dev), `feature/*`, `fix/*`
- **Commits**: Conventional Commits format — `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`
- **Flow**: feature branch → development → master
