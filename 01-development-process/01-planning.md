# 01 › Development Process › Planning

How to set up a plan with Claude Code before starting a project.

---

## Plan Mode

Before starting a large or ambiguous task, enter plan mode:

```
/plan
```

or tell Claude Code directly:

> "Show me your plan before starting this task, I'd like to approve it."

Claude inspects the file structure, suggests an approach, and waits for your approval — it doesn't start implementing.

**When to use:**
- Changes that affect multiple files
- Features that require architectural decisions
- Situations where requirements aren't fully clear yet

---

## Create CLAUDE.md at Project Start

The first thing on every new project:

```bash
claude
# then:
/init
```

`/init` reads the existing codebase and generates a CLAUDE.md draft. Run this in the project's root directory.

→ For details: [CLAUDE.md Basic Structure](../02-claude-md/01-basic-structure.md)

---

## Breaking a Large Task into Small Pieces

Don't give Claude the whole task at once. Instead:

```
"We're going to implement a user registration system.
 First list the tasks, then we'll go through them one by one."
```

Move to the next step only after approving each one.

---

## Reference Links

- [Plan Mode Details](../05-prompt-strategies/01-plan-mode.md)
- [Setting Project Context with CLAUDE.md](../02-claude-md/02-project-specific.md)

---

## → Next Step

Once your plan is approved, it's time to code:

**[01 › Development](./02-development.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Don't know how plan mode works | [Plan Mode](../05-prompt-strategies/01-plan-mode.md) |
| /init failed or CLAUDE.md came out empty | [CLAUDE.md Basic Structure](../02-claude-md/01-basic-structure.md) |
| Task too large, don't know where to start | This page's "Break It Down" section |
