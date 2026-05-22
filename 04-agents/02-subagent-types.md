# 04 › Agents › Subagent Types

## Available Subagent Types

| Type | Best For |
|---|---|
| `Explore` | Codebase research, finding files, searching for symbols |
| `Plan` | Designing implementation plans, architectural suggestions |
| `claude` | General-purpose, access to all tools |
| `general-purpose` | Broad research and multi-step tasks |
| `claude-code-guide` | Questions about the Claude Code CLI and API |

---

## Explore — When?

When you only need to research and will **not modify** any files:

```
"Use an Explore subagent to:
 - List all React component files
 - Find which hooks each one uses"
```

Explore has no access to Edit or Write, so it can't accidentally make changes.

---

## Plan — When?

To get architectural or approach approval before implementation:

```
"Use a Plan subagent to produce an implementation plan for this feature:
 [feature description]
 Take the existing file structure into account."
```

---

## claude (General) — When?

When research and implementation happen together, or when you need special tool access.

---

## → Next Step

Now that you know the subagent types, try running them in parallel:

**[04 › Parallel Execution](./03-parallel-execution.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Explore agent modified a file | Impossible — Explore has no Edit/Write access |
| Plan agent was too detailed / too vague | Add constraints and context to the prompt |
| I didn't know which type to pick | Rule: read-only → Explore, planning → Plan, both → claude |
