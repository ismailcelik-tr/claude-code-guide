# 05 › Prompt Strategies › Advanced

## The /think Command

Force Claude to think more deeply on a complex decision:

```
/think

"List the possible side effects of this migration strategy."
```

or inline in your message:

```
"Think through this: which edge cases could this change break?"
```

---

## Specify Output Format

Ask Claude to produce output in a specific format:

```
"Return the analysis results in this format:
 - Problem: [what]
 - Why: [root cause]
 - Solution: [suggested steps]
 - Risk: [side effects if any]"
```

---

## Set a Role

Give context at the start of your prompt:

```
"As a senior backend developer, review this API design.
 Evaluate it from a performance and security perspective."
```

---

## Step-by-Step Approval

Approve each step individually:

```
"After completing each step, stop and wait for my approval.
 Don't move to the next step until I confirm."
```

---

## Compressing with /compact

Clears context in long conversations:

```
/compact
```

Before running it, note important decisions in CLAUDE.md so nothing is lost.

---

## → Next Step

Once you've completed all sections, go back to the start and pick up anything you missed:

**[Main Navigation](../README.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| /think didn't think deeply enough | Ask a more specific question |
| Step-by-step approval isn't working | Try plan mode → [Plan Mode](./01-plan-mode.md) |
| I'm losing context | [Context Management](./02-context-management.md) |
| I want to return to the home page | [Navigation Tree](../README.md) |
