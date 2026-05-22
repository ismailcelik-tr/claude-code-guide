# 03 › Hooks & Automation › Custom Commands

If you've typed the same prompt more than three times, turn it into a slash command.

---

## What is a Custom Command?

Markdown files you place in the `.claude/commands/` directory. Claude Code recognizes them as slash commands using `/command-name`.

```
project/
└── .claude/
    └── commands/
        ├── review.md
        ├── deploy-check.md
        └── sprint-summary.md
```

---

## Write Your First Command

**`.claude/commands/review.md`:**

```markdown
Review the changes in the current branch.

Check for:
1. Security vulnerabilities
2. Missing tests
3. Compliance with CLAUDE.md rules

For each finding: file path, line number, suggestion.
```

Now `/review` before every PR is all you need.

---

## Useful Command Examples

### Deploy Checklist

**`.claude/commands/deploy-check.md`:**

```markdown
Create a pre-deploy checklist.

Verify:
- [ ] All tests passing
- [ ] .env.example is up to date
- [ ] Migrations are ready
- [ ] CHANGELOG.md updated

List any missing items.
```

### Sprint Summary

**`.claude/commands/sprint-summary.md`:**

```markdown
Read recent commits and summarize what was done this sprint.

Format:
## Completed
## In Progress
## Known Issues
```

### Quick Debug

**`.claude/commands/debug.md`:**

```markdown
Analyze this error: $ARGUMENTS

1. Identify the root cause
2. Read the relevant files
3. Suggest a fix with minimal changes
```

Pass a parameter to the command with `$ARGUMENTS`:

```
/debug "TypeError: Cannot read properties of undefined"
```

---

## When Should You Write a Command?

| Situation | Do |
|---|---|
| Typed the same prompt 3+ times | Turn it into a command |
| Everyone on the team runs the same process | Turn it into a command |
| One-time task | Write a direct prompt |
| Too context-specific | Write a direct prompt |

---

## → Next Step

Automation is set up, now move to agent usage:

**[04 › Agents](../04-agents/README.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Command not recognized | Make sure `.claude/commands/` is in the project root |
| $ARGUMENTS not working | Use the literal text `$ARGUMENTS` in the command file |
| Unsure whether to use hook or command | Hooks trigger automatically, commands are called manually |
| Where does settings.json go | [settings.json](./01-settings-json.md#location-and-format) |
