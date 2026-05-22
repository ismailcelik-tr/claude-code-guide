# Scenario 01 › SaaS from Scratch

**Situation:** You're starting a new SaaS project. Empty directory, no CLAUDE.md, no idea where to begin.

**Difficulty:** 🟢 Beginner  
**Time:** ~30 minutes for initial setup

---

## Step 1 — Create the Project Directory and Start Claude

```bash
mkdir my-saas && cd my-saas
git init
claude
```

---

## Step 2 — Write CLAUDE.md Manually

There's no codebase yet, so `/init` won't work. Write the first CLAUDE.md by hand:

```
"I'm building a SaaS project. Stack: Next.js 14, TypeScript,
 PostgreSQL, Prisma. We'll use NextAuth for auth.
 Create a suitable CLAUDE.md for this project."
```

Claude produces a draft. Review it, add project-specific rules, and save.

→ For a template: [Full-Stack CLAUDE.md](../02-claude-md/examples/fullstack.md)

---

## Step 3 — Plan the Architecture

```
"We're building a SaaS project with this stack:
 Next.js 14 (App Router), TypeScript, PostgreSQL, Prisma, NextAuth.

 Before we start:
 1. Suggest a directory structure
 2. List the first files to create
 3. Point out potential issues

 Show me your plan so I can approve it."
```

Claude enters plan mode and waits for your approval before proceeding.

---

## Step 4 — Generate the Skeleton

After approving the plan, proceed in stages. Don't ask for everything at once:

```
"First, create only the base directory structure and empty files.
 Don't fill in any content yet."
```

Then:

```
"Now write the Prisma schema. Include a User and Subscription model."
```

---

## Step 5 — Set Up Hooks

Put automation in place before you start coding:

```
"Create .claude/settings.json for this project.
 Run npm run lint and npm run typecheck after every Edit."
```

→ Details: [Hooks & Automation](../03-hooks-automation/README.md)

---

## Step 6 — Develop the First Feature

Infrastructure is ready. For each feature, follow this loop:

```
Plan → Develop → Test → Review → commit
```

```
"Implement user registration and login.
 Use NextAuth + Prisma.
 Stop after each step and wait for my approval."
```

---

## Common Pitfalls in This Scenario

| Mistake | Why It Happens | Fix |
|---|---|---|
| Diving into code without CLAUDE.md | Wanting to save time | Claude works without context — you'll have to re-explain the project in every conversation |
| Asking for the entire app in one prompt | Ambition | Claude either stays too shallow or makes too many assumptions |
| Starting development without setting up hooks | Being in a hurry | Lint errors accumulate and become hard to clean up later |

---

## → Next Step

Once this scenario is complete, learn how to modernize an existing codebase:

**[Scenario 02 › Legacy Modernization](./02-legacy-modernization.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| How does /plan work | [Plan Mode](../05-prompt-strategies/01-plan-mode.md) |
| I didn't know how to write CLAUDE.md | [CLAUDE.md Basic Structure](../02-claude-md/01-basic-structure.md) |
| Hook setup failed | [settings.json](../03-hooks-automation/01-settings-json.md) |
