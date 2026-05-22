# 02 › CLAUDE.md › Project-Specific

Adding project-specific context beyond the basic structure.

---

## How Much Detail is Enough?

**Too little:** Claude misunderstands the project, you need to correct it frequently.  
**Too much:** CLAUDE.md bloats, becomes hard to keep up to date.

Golden rule: Add **anything Claude has been forced to ask more than once** to CLAUDE.md.

---

## Project-Specific Additions

### Restrictions and Constraints

```markdown
## Constraints
- Don't use lodash, prefer native JS methods
- No any types
- Don't touch src/legacy/ — migration in progress
```

### Architectural Decisions

```markdown
## Architecture
- We use Zustand for state management (no Redux)
- API calls only go through src/api/
- Shared types are defined in src/types/index.ts
```

### Testing Strategy

```markdown
## Tests
- Unit tests: Vitest
- E2E tests: Playwright, in tests/e2e/
- At least 80% coverage expected per PR
```

### Team Conventions

```markdown
## Commit Format
feat: new feature
fix: bug fix
refactor: code improvement
```

---

## Subdirectory CLAUDE.md

In large projects, each module can have its own CLAUDE.md:

```
project/
├── CLAUDE.md              # general rules
├── frontend/
│   └── CLAUDE.md          # frontend-specific
└── backend/
    └── CLAUDE.md          # backend-specific
```

---

## → Next Step

If you want to split CLAUDE.md or learn about memory/permission management:

**[02 › Advanced](./03-advanced.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| CLAUDE.md got too large | [Advanced — Import](./03-advanced.md) |
| Didn't know which directory to use in monorepo | [Monorepo Template](./examples/monorepo.md) |
| Claude still didn't follow constraints | [Common Mistakes](../05-prompt-strategies/03-common-mistakes.md) |
