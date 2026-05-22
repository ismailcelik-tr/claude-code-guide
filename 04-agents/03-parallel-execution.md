# 04 › Agents › Parallel Execution

## When to Run in Parallel? {#when-to-run-in-parallel}

Run two tasks in parallel when **neither depends on the other's result**.

**Parallel is appropriate:**
- "Run frontend and backend tests at the same time"
- "Inspect these two independent modules with separate agents"

**Sequential is required:**
- "First research, then begin implementation"
- "Do B based on the result of A"

---

## Running Agents in Parallel

Give Claude a single message with instructions for multiple agents:

```
"Run these two tasks in parallel:
 1. Use Explore to list all endpoints in src/api/
 2. Use Explore to list all components in src/components/"
```

---

## Background Execution

When you don't need the result immediately:

```
"Run this research in the background and notify me when it's done.
 [task description]"
```

---

## The Cost of Parallelism

Each agent is an independent Claude instance — token cost multiplies. Only use parallel execution for tasks that are truly independent.

---

## → Next Step

Now that you understand agents, move on to prompt strategies:

**[05 › Prompt Strategies](../05-prompt-strategies/README.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Agents interfered with each other | The tasks weren't truly independent — run them sequentially |
| I'm waiting for an agent result but it never finishes | It may be a background agent — continue the conversation; a notification will arrive |
| I don't know what the Agent tool is | [Agent Tool Basics](./01-agent-tool.md) |
