---
agent: ask
description: "Generate a PR description from branch diff"
---

Generate a Pull Request description based on the changes in this branch.

## Output format

```markdown
## What

[1-2 sentence summary of what this PR does]

## Why

[Brief explanation of the motivation or problem being solved]

## Changes

- [Bullet list of key changes, grouped by area]

## Testing

- [ ] Builds clean (`dotnet build`)
- [ ] [Any manual testing steps]

## Notes

[Optional: anything the reviewer should know — breaking changes, dependencies, follow-up work]
```

## Rules
- Keep it concise — reviewers don't read essays
- Focus on WHAT changed and WHY, not HOW (the code shows how)
- Group changes by module or area if multiple areas were touched
- Flag breaking changes prominently
- Mention any new dependencies or configuration changes
