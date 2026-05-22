# Scenario 04 › Adding a New Feature

**Situation:** You're adding a new feature to a working project — without breaking existing code, without dropping test coverage.

**Difficulty:** 🟡 Intermediate

---

## Step 1 — Understand the Existing Code

Before writing the feature, have Claude read the relevant area:

```
"Read these files: [relevant files]
 I'm going to add a new [feature name].
 Learn the existing patterns — don't write anything yet."
```

---

## Step 2 — Identify the Impact Area

```
"I want to add [feature description].
 Which existing files will be affected?
 Which new files will be needed?
 List them — don't start implementing."
```

---

## Step 3 — Approve with Plan Mode

```
"/plan

 Add [feature] in a way that fits the existing [relevant module] structure.
 Constraints:
 - Don't break the existing API contract
 - Don't add new dependencies
 - Don't let test coverage drop below 80%"
```

Review the plan, revise if needed, then approve.

---

## Step 4 — Tests First, Then Code

Test-driven development becomes easier with Claude:

```
"First write failing tests for [feature].
 Then write the implementation that makes those tests pass."
```

---

## Step 5 — Regression Check

After writing the feature:

```
"Can your changes break any existing tests?
 Scan all test files and list risky areas."
```

---

## Step 6 — Code Review

```
"/review

 Added: [feature summary]
 Changed files: [list]
 Pay special attention to: [critical area]"
```

---

## Common Pitfalls in This Scenario

| Mistake | Consequence |
|---|---|
| Writing without reading the existing code | Claude produces code that doesn't match the project's patterns |
| "Add and test everything" instead of "add just this" | Higher regression risk |
| Merging without writing tests | Broken feature carries forward to the next sprint |

---

## → Next Step

**[Scenario 05 › Performance Optimization](./05-performance-optimization.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| How do I use plan mode | [Plan Mode](../05-prompt-strategies/01-plan-mode.md) |
| I don't know how to write tests | [Test & Debug](../01-development-process/03-test-and-debug.md) |
| How do I do a code review | [Code Review](../01-development-process/04-code-review.md) |
| We broke existing code | [Common Mistakes](../05-prompt-strategies/03-common-mistakes.md) |
