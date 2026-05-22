# 02 › CLAUDE.md › Advanced

Import, memory system, permission management, and context layering.

---

## Splitting with @import

When CLAUDE.md gets too large, break it into parts:

```markdown
# CLAUDE.md

@./docs/architecture.md
@./docs/conventions.md
@./docs/testing.md
```

Each `@` line includes the content of the relevant file as if written directly.

---

## PROJECT_CONTEXT and SESSION_CONTEXT Layering

When CLAUDE.md starts to bloat, separate permanent and temporary context:

| File | Contains | How often it changes |
|---|---|---|
| `CLAUDE.md` | Behavioral rules, constraints, commands | Rarely |
| `PROJECT_CONTEXT.md` | Architecture decisions, tech choices, important context | A few times a month |
| `SESSION_CONTEXT.md` | Ongoing work, open decisions, temporary notes | Every session |

**Import in CLAUDE.md:**

```markdown
@./PROJECT_CONTEXT.md
@./SESSION_CONTEXT.md
```

**SESSION_CONTEXT.md example:**

```markdown
# Session Context

## Ongoing Work
- Payment module left half-done — src/payment/webhook.ts

## Open Decisions
- Retry strategy: exponential backoff or fixed interval?

## Next Step
- Write webhook tests
```

At the start of each new conversation, Claude reads this file and picks up exactly where you left off. Update SESSION_CONTEXT.md when the session is complete.

---

## Memory System

Claude Code's persistent memory is stored per project under `~/.claude/projects/`.

**Manual saving:**
```
"Remember this: In this project, migrations live under schema/."
```

**When to use:**
- Information you repeat in every conversation
- Personal preferences you don't want in CLAUDE.md

---

## Permission Management

`~/.claude/settings.json` or `.claude/settings.json`:

```json
{
  "permissions": {
    "allow": [
      "Bash(npm run *)",
      "Bash(git *)",
      "Edit(src/**)"
    ],
    "deny": [
      "Bash(rm -rf *)"
    ]
  }
}
```

→ For details: [settings.json](../03-hooks-automation/01-settings-json.md)

---

## → Next Step

Now that CLAUDE.md is set up, automate repetitive tasks:

**[03 › Hooks & Automation](../03-hooks-automation/README.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| @import not working | [Basic Structure — File Location](./01-basic-structure.md#file-location) |
| Permitted command still being asked | [settings.json](../03-hooks-automation/01-settings-json.md) |
| Memory saved but forgotten | [Context Management](../05-prompt-strategies/02-context-management.md) |
