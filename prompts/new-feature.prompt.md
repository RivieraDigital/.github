---
agent: agent
description: "Scaffold a new feature with proper architecture layers"
tools:
  - search/codebase
  - terminal
---

Scaffold a new feature following Riviera Digital architecture conventions.

## What to create

Based on the feature description, create the necessary files across the architecture layers:

### Domain Layer
- Entity classes with properties and value objects
- Enums if needed

### Contracts Layer
- `*Request.cs` — input DTO with validation attributes
- `*Response.cs` — output DTO
- Service interface (`I*Service.cs`)

### Application Layer
- Command + CommandHandler (for write operations)
- Query + QueryHandler (for read operations)
- Service implementation
- Input validation logic

### Infrastructure Layer (if needed)
- Repository implementation
- EF Core entity configuration
- External service integration

### API Layer
- Controller action with proper HTTP method and route
- Controller inherits from base controller class

## Checklist
- [ ] DTOs in Contracts — never expose Domain entities
- [ ] `OperationResult<T>` for all service returns
- [ ] Async/await throughout — no `.Result` or `.Wait()`
- [ ] DI registration for new services
- [ ] Input validation in Application layer
- [ ] `[Authorize]` on controller actions (unless explicitly public)
- [ ] Proper naming: PascalCase public, camelCase local, I-prefix interfaces

## Instructions
1. Ask which module/area this feature belongs to
2. Scan existing code in that module for patterns to follow
3. Create files matching the existing conventions
4. Register services in DI
5. Run `dotnet build` to verify
