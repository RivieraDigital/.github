---
agent: ask
description: "Generate a Conventional Commit message from staged changes"
---

Generate a commit message following the Conventional Commits convention based on the staged changes.

## Format

```
type(scope): short description

[optional body — what and why, not how]
```

## Types
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation only
- `chore`: Build, tooling, dependencies
- `refactor`: Code restructuring (no behavior change)
- `test`: Adding or fixing tests
- `style`: Formatting, whitespace (no logic change)
- `perf`: Performance improvement

## Rules
- **Subject line**: max 72 characters, imperative mood ("add" not "added")
- **Scope**: module or area affected (e.g., `catalog`, `auth`, `ui`)
- **Body**: only if the change needs explanation beyond the subject
- **No period** at the end of the subject line
- Use lowercase for type and scope

## Examples
- `feat(catalog): add product search endpoint`
- `fix(orders): correct tax calculation for HR region`
- `refactor(identity): extract token validation to service`
- `chore: update NuGet packages to latest`

Analyze the staged changes and output ONLY the commit message, nothing else.
