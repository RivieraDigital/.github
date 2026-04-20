---
agent: ask
description: "Code review for Riviera Digital .NET standards"
---

Review the selected code for issues based on Riviera Digital coding standards:

## Check for

1. **Async correctness**: Any `.Result`, `.Wait()`, or `Task.Run()` misuse?
2. **Null safety**: Missing null checks at system boundaries (API inputs, external data)?
3. **Security**: SQL injection risk, XSS, exposed secrets, missing `[Authorize]`?
4. **Error handling**: Using `OperationResult<T>` correctly? Exceptions for control flow?
5. **Architecture**: Business logic in the correct layer? Controllers thin?
6. **DI registration**: New services registered with correct lifetime?
7. **Naming**: PascalCase for public members, camelCase for locals, I-prefix for interfaces?
8. **Validation**: Input validated at system boundaries?

## Output format

For each issue found, provide:
- **Severity**: Critical / Warning / Info
- **Location**: file and line
- **Problem**: what's wrong
- **Fix**: how to fix it

If no issues found, say "Clean — no issues found."
