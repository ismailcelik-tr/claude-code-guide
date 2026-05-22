# Scenario 05 › Performance Optimization

**Situation:** The application is starting to slow down. Users are complaining but it's not clear where the problem is.

**Difficulty:** 🟡 Intermediate  
**Rule:** Don't optimize without measuring first.

---

## Step 1 — Measure First, Then Interpret

```
"We're experiencing performance issues in this application.
 First tell me what metrics I need to measure and
 how to measure them. Don't change any code yet."
```

---

## Step 2 — Identify the Bottleneck

Give Claude the profiling output or slow query log:

```
"Analyze this profiling output:
 [output]

 List the 3 areas that take the most time.
 For each one, give a root cause hypothesis."
```

Or if there's a slow API endpoint:

```
"Why might this endpoint be slow?
 [endpoint code]
 Look at database queries, N+1 problems, unnecessary computation."
```

---

## Step 3 — One Change, One Measurement

Isolate each optimization:

```
"Suggest the most minimal fix for this N+1 problem.
 Don't touch anything else — only solve this one issue.
 Tell me how to measure before and after as well."
```

---

## Step 4 — Database Optimization

```
"Analyze this query:
 [SQL or ORM code]

 Compare the options: adding an index, rewriting the query,
 or using eager loading."
```

---

## Step 5 — Frontend Performance

```
"This component runs [operation] on every render.
 Is using useMemo / useCallback appropriate here?
 Explain the trade-offs."
```

---

## Common Pitfalls in This Scenario

| Mistake | Consequence |
|---|---|
| Optimizing without measuring | You optimize the wrong thing |
| Changing multiple things at once | You can't tell which change made a difference |
| Micro-optimization obsession | You miss the real bottleneck |
| Adding a cache to hide the problem | The root cause remains and grows over time |

---

## → Next Step

**[Scenario 06 › Security Audit](./06-security-audit.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| I don't know how to do profiling | [Test & Debug](../01-development-process/03-test-and-debug.md) |
| Tests broke after optimization | [Test & Debug](../01-development-process/03-test-and-debug.md) |
| Claude suggested too large a change | [Common Mistakes](../05-prompt-strategies/03-common-mistakes.md) |
