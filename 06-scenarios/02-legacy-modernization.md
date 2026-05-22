# Scenario 02 › Legacy Modernization

**Situation:** There's a codebase that hasn't been touched in years. No tests, no documentation, no TypeScript. You're going to modernize it step by step.

**Difficulty:** 🟡 Intermediate  
**Risk:** High — there's a chance of breaking the existing system

---

## The Golden Rule

> Never change all the code at once. Keep the system running after every step.

---

## Step 1 — Understand the Codebase

Give Claude a reading task first — no changes yet:

```
"Inspect the src/ directory. Find and list:
 1. The most critical files (frequently referenced)
 2. Obvious security risks
 3. The largest areas of technical debt
 Don't change anything — just report."
```

Using an Explore subagent is safer:

```
"Use an Explore subagent to analyze the src/ directory.
 Produce a file dependency map."
```

---

## Step 2 — Write CLAUDE.md Based on the Current State

```
"Read this directory structure and package.json.
 Create a CLAUDE.md that describes this legacy project.
 Specifically note:
 - Files not to be touched (src/legacy/)
 - Existing naming conventions
 - Known broken areas"
```

---

## Step 3 — Establish a Test Safety Net

Before making changes, pin down existing behavior with tests:

```
"Read src/core/payment.js.
 Write characterization tests that document the current behavior of this file.
 The goal is to document the current output, not to make the tests pass."
```

---

## Step 4 — Modernize in Small Pieces

Open a separate session for each file or module:

```
"Modernize only the src/utils/date.js file:
 1. Convert to ES modules
 2. Add JSDoc
 3. Keep existing tests passing
 Don't touch any other files."
```

---

## Step 5 — TypeScript Migration (optional)

Start with the lowest-risk file:

```
"Migrate src/utils/date.js to TypeScript.
 Don't use any types.
 Update imports in other files but don't touch anything else."
```

---

## Step 6 — Verify After Every Step

```
"Run the tests after your changes.
 If any test fails, fix it before moving on."
```

---

## Common Pitfalls in This Scenario

| Mistake | Consequence |
|---|---|
| Refactoring without writing tests first | You can't tell what you broke |
| Changing multiple files at once | You can't isolate the source of the error |
| Migrating to TypeScript with `any` | You haven't gained type safety |
| Entering restricted zones like `src/legacy/` | If other systems depend on it, it will break |

---

## → Next Step

Once modernization is complete, learn how to manage production crises:

**[Scenario 03 › Production Crisis](./03-production-crisis.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| How do I use an Explore subagent | [Subagent Types](../04-agents/02-subagent-types.md) |
| How do I generate tests | [Test & Debug](../01-development-process/03-test-and-debug.md) |
| Claude modified a file it shouldn't have | [CLAUDE.md Constraints](../02-claude-md/02-project-specific.md) |
