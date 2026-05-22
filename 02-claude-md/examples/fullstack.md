# Template: Full-Stack CLAUDE.md

For projects with both frontend and backend.

---

```markdown
# [Project Name]

## Overview
[What it does, who uses it — 2-3 sentences]

## Tech Stack
### Frontend
- Framework: [React / Next.js / Vue]
- Language: TypeScript
- Styling: [Tailwind / styled-components]
- State: [Zustand / Redux / Context]

### Backend
- Runtime: [Node.js / Python / Go]
- Framework: [Express / FastAPI / Gin]
- Database: [PostgreSQL / MongoDB]
- Auth: [JWT / OAuth2]

## Directory Structure
src/
├── app/          # Next.js app router or page components
├── components/   # shared UI components
├── api/          # API client layer
├── hooks/        # custom React hooks
└── types/        # shared TypeScript types

server/
├── routes/       # API route definitions
├── controllers/  # business logic
├── models/       # database models
└── middleware/   # Express middleware

## Commands
- `npm run dev` — starts frontend + backend together
- `npm run dev:server` — backend only
- `npm test` — all tests
- `npm run db:migrate` — run migration

## Architectural Decisions
- All API communication through src/api/ only
- No direct database access — everything through controllers
- Shared types kept in sync between src/types/ and server/types/

## Rules
- No `any` types
- API endpoints are versioned: /api/v1/
- Integration test required for every new endpoint
- No console.log in commits

## Testing Strategy
- Unit: Vitest (src/)
- Integration: Jest + Supertest (server/)
- E2E: Playwright (tests/e2e/)
```

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Not enough for monorepo | [Monorepo Template](./monorepo.md) |
| Need a simpler template | [Minimal Template](./minimal.md) |
