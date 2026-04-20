# Contributing to Riviera Digital Projects

## Getting Started

1. Clone the repository
2. Make sure you have .NET 10.0 SDK installed
3. Open in VS Code with GitHub Copilot enabled
4. Run `dotnet build` to verify everything compiles

## Branching

- Create feature branches from `development`: `feature/short-description`
- Create bugfix branches from `development`: `fix/short-description`
- Never push directly to `master` or `development`

## Making Changes

1. Create a feature/fix branch from `development`
2. Make your changes following the coding standards (see `.github/copilot-instructions.md`)
3. Run `dotnet build` — must compile clean
4. Run `dotnet test` — all tests must pass
5. Commit with Conventional Commits format

## Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
feat(scope): add new feature
fix(scope): fix the bug
docs: update documentation
chore: update dependencies
refactor(scope): restructure code
```

## Pull Requests

- Target branch: `development`
- Include a clear description (use the `pr-description` prompt)
- Reference any related issues
- Ensure build passes before requesting review

## Code Standards

- **async/await** — no `.Result`, `.Wait()`, `Task.Run()`
- **OperationResult\<T\>** — for all service returns
- **PascalCase** public members, **camelCase** locals
- **Validate input** at system boundaries
- **Never commit secrets** — use environment variables

## Questions?

If you're unsure about an approach, use the **planner** agent to discuss before implementing.
