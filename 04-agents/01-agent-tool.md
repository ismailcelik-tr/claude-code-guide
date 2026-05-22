# 04 › Agents › Agent Tool

## What is the Agent Tool?

Claude Code can delegate complex tasks to another Claude instance. That subagent runs with its own tool set, context, and permissions.

---

## When to Use It

**Use it:**
- Research tasks that scan the entire codebase
- Deep analysis without bloating the main conversation
- Independent subtasks that can run in parallel

**Don't use it:**
- Single-line fixes
- Sequential tasks where each step depends on the previous
- Work that requires direct interaction with the user

---

## Basic Usage

Tell Claude explicitly:

```
"Use an Explore subagent to list all API endpoints in the src/ directory.
 Return results as: file path + HTTP method."
```

---

## How to Write a Good Agent Prompt

The agent **cannot see** the previous conversation. Write a self-contained prompt:

```
"You are doing research for this task:
 [Context: what to examine]
 [Goal: what to find]
 [Format: how to return results]"
```

---

## → Next Step

Once you understand the Agent tool, learn how to pick the right subagent type:

**[04 › Subagent Types](./02-subagent-types.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Agent returned wrong results | Write the prompt independently — it doesn't know the previous conversation |
| I didn't know which subagent type to use | [Subagent Types](./02-subagent-types.md) |
| I want to run agents in parallel | [Parallel Execution](./03-parallel-execution.md) |
