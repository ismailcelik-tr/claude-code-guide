# 02 › CLAUDE.md › Basic Structure

## What is CLAUDE.md?

A Markdown file you place in the root directory of your project. Claude Code reads this file at the start of every conversation.

---

## File Location {#file-location}

```
project-root/
├── CLAUDE.md        ← here
├── src/
└── package.json
```

> [!CAUTION]
> If you place CLAUDE.md inside `src/` or another subdirectory, Claude will **not read it automatically**.
> Always place it in the **root directory** of your project.

You can also add it to subdirectories — but those files are only read when working inside that directory.

---

## Basic Structure

```markdown
# Project Name

## Overview
Describe what the project does in 2-3 sentences.

## Tech Stack
- Frontend: React 18, TypeScript
- Backend: Node.js, Express
- Database: PostgreSQL

## Directory Structure
- src/components/ — UI components
- src/api/ — API layer
- src/utils/ — utility functions

## Common Commands
- npm run dev — development server
- npm test — run tests
- npm run build — production build

## Rules
- Write unit tests for every function
- No console.log left behind
- Use conventional commit messages
```

---

## Auto-Generate with /init

In an existing project:

```bash
claude
/init
```

Claude scans the codebase and generates a CLAUDE.md draft. Then review and edit it.

---

## → Next Step

Now that you've set up the basic structure, add project-specific context:

**[02 › Project-Specific](./02-project-specific.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| /init didn't work | [00 Getting Started — Installation](../00-getting-started/README.md) |
| Set up basic structure, want more | [Project-Specific](./02-project-specific.md) |
| Claude still doesn't understand the project | [Project-Specific — Deepening Context](./02-project-specific.md) |
