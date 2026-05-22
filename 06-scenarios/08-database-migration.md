# Scenario 08 › Database Migration

**Situation:** You need to change your database schema — a new column, table restructuring, or a large data migration. The system must keep running throughout.

**Difficulty:** 🔴 Advanced  
**Rule:** Every migration must be reversible.

---

## Step 1 — Analyze the Change

```
"I need to do this migration: [description]
 Current schema: [schema or model file]

 List:
 - Affected tables and columns
 - Is there a risk of data loss?
 - What is needed for zero downtime?
 - What is the rollback plan?"
```

---

## Step 2 — Expand-Contract Strategy

The zero-downtime approach for large schema changes:

```
"How do I perform this migration using the expand-contract pattern?
 Current column: [old column]
 Target: [new structure]

 Create a step-by-step plan — each step must be independently deployable."
```

**What is expand-contract:**
1. **Expand** — add the new structure alongside the old, write to both
2. **Migrate** — move existing data to the new structure
3. **Contract** — remove the old structure

---

## Step 3 — Write the Migration File

```
"Write this migration using [Prisma / Flyway / Alembic / ActiveRecord]:
 [change description]

 Write up and down migrations together.
 Add batch processing for large tables."
```

---

## Step 4 — Data Validation

Verify data integrity after the migration:

```
"Write queries that validate data integrity after this migration.
 Check for missing data, null constraint violations, or constraint failures."
```

---

## Step 5 — Rollback Plan

```
"Write a rollback plan for if this migration fails.
 What to do at each step?
 How to revert without data loss?"
```

> [!CAUTION]
> Always test on a staging environment before running a production migration, and take a database backup.

---

## Common Pitfalls in This Scenario

| Mistake | Consequence |
|---|---|
| Running migration without taking a backup | Data loss may be irreversible |
| Not writing a down migration | Rollback becomes impossible |
| Acquiring a lock on a large table | Service outage in production |
| Not testing on staging first | Encountering problems for the first time in production |

---

## → Next Step

Once you've completed all scenarios, check the quick reference card:

**[Quick Reference Card](../cheatsheet.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Production is down after migration | [Production Crisis](./03-production-crisis.md) |
| Works in test, doesn't work in prod | [Deployment](../01-development-process/05-deployment.md) |
| I don't know how to test the migration | [Test & Debug](../01-development-process/03-test-and-debug.md) |
