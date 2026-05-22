# Template: Monorepo CLAUDE.md

For repos with multiple packages or applications.

---

## Root CLAUDE.md

```markdown
# [Monorepo Name]

## Structure
This repo contains the following packages:
- packages/ui — shared React component library
- packages/utils — shared utility functions
- apps/web — user application (Next.js)
- apps/admin — admin panel (Next.js)
- apps/api — REST API (Node.js)

## Package Manager
Using pnpm workspace.

## Commands
- `pnpm dev` — starts all applications
- `pnpm dev --filter=web` — starts only web
- `pnpm test` — all tests
- `pnpm build` — all builds

## Dependency Rules
- apps/ packages can depend on packages/
- packages/ packages CANNOT depend on each other
- To add external package from root: `pnpm add <package> --filter=<app>`

## General Rules
- TypeScript strict mode on
- Each package has its own test configuration
- If type changes affect packages/utils, check all apps
```

---

## Subdirectory CLAUDE.md (apps/api)

```markdown
# API Application

@../../CLAUDE.md

## Specific to This Package
- Port: 3001
- Database: PostgreSQL, connection from DATABASE_URL env
- Migration: run with `pnpm db:migrate`

## Important Directories
- src/routes/ — endpoint definitions
- src/services/ — business logic
- prisma/ — Prisma schema and migrations
```

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| @import not working | [Advanced — Import](../03-advanced.md) |
| Claude couldn't understand which package I'm in | Add subdirectory CLAUDE.md |
| Full-stack but not monorepo | [Full-Stack Template](./fullstack.md) |
