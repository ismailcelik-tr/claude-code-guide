# Scenario 03 › Production Crisis

**Situation:** Something is exploding in the live system. Users are affected and every minute counts.

**Difficulty:** 🔴 Advanced  
**Priority:** Get the system back up first, then find the root cause

---

## How to Use Claude During a Crisis

Don't panic and write long explanations. Be short, clear, focused.

---

## Step 1 — Isolate the Error Quickly

Paste the error log or stack trace directly:

```
"There's this error in production:
 [error message / stack trace]

 First, just identify the root cause. Don't suggest a fix yet."
```

Once Claude explains the root cause, continue:

```
"OK. Now suggest the lowest-risk fix.
 Minimal change — don't break anything else."
```

---

## Step 2 — Log Analysis

Paste the CI/CD or application log:

```
"Analyze this production log.
 Find when the error started and what changed before it."
[log contents]
```

---

## Step 3 — Quick Fix (Hotfix)

```
"Read this file: [file path]
 Fix [the problem] with the minimum change possible.
 Don't add anything new — just repair what's broken."
```

> [!CAUTION]
> Don't attempt a major refactor during a crisis. Get the system working first.

---

## Step 4 — Validate the Change

Before deploying the fix:

```
"Summarize the change you made:
 - What changed
 - Could there be any side effects
 - How do I verify it"
```

---

## Step 5 — Post-Crisis Analysis

Once the system is stable:

```
"Analyze why this production crisis happened.
 What can be done to prevent it from happening again?
 Suggest improvements to tests, monitoring, or the code."
```

---

## What to Avoid During a Crisis

| Don't | Why |
|---|---|
| Say "rewrite everything" | Big changes during a crisis create new crises |
| Deploy multiple fixes at the same time | You can't tell which one worked |
| Push a fix without testing it | It may trigger a second crisis |
| Paste secrets/API keys into Claude | Security risk — only share variable names |

---

## → Next Step

Now that you know how to manage crises, learn how to add features with zero regressions:

**[Scenario 04 › Adding a New Feature](./04-new-feature.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| How do I analyze logs | [Test & Debug — Log Analysis](../01-development-process/03-test-and-debug.md) |
| Problem during the deployment process | [Deployment](../01-development-process/05-deployment.md) |
| Claude suggested too large a change | [Common Mistakes](../05-prompt-strategies/03-common-mistakes.md) |
