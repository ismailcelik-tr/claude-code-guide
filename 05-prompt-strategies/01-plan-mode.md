# 05 › Prompt Strategies › Plan Mode

## What is Plan Mode?

Claude shows you what it's going to do before it starts implementing, and waits for your approval.

---

## How to Activate It

```
/plan
```

or in natural language:

```
"Show me your plan before you start implementing, so I can approve it."
```

---

## What Does Claude Do in Plan Mode?

1. Reads and researches the codebase
2. Presents approach options (if needed)
3. Writes a step-by-step plan
4. **Waits for your approval**
5. Begins implementation only after approval

---

## What Should You Do When You See the Plan?

- **To approve:** "Go ahead" or "Start"
- **To revise:** "Change step 3 — do Y instead of X"
- **To cancel:** "Stop, let's try a different approach"

---

## When to Use It

| Task | Plan Mode? |
|---|---|
| Change affecting multiple files | Yes |
| Feature requiring an architectural decision | Yes |
| Single-line fix | No |
| Clear and simple task | Optional |

---

## → Next Step

Now that you understand plan mode, learn about context management:

**[05 › Context Management](./02-context-management.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Plan mode is active but Claude started implementing | Did you say "continue" without approving? |
| Plan was too detailed / too shallow | [Advanced — Prompt Techniques](./04-advanced.md) |
| I want to go back to the planning phase | [Development Process — Planning](../01-development-process/01-planning.md) |
