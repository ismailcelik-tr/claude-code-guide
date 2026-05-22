# Claude Code — Quick Reference Card

All commands, shortcuts, and hook recipes in one page.

---

## Slash Commands

| Command | What It Does |
|---|---|
| `/init` | Scans the current project and generates a `CLAUDE.md` draft |
| `/plan` | Enters plan mode — Claude waits for approval before implementing |
| `/review` | Inspects the current diff for code quality |
| `/review --comment` | Posts review findings as inline comments on a GitHub PR |
| `/think` | Guides Claude toward deeper, step-by-step reasoning |
| `/compact` | Compresses conversation history, clears context while preserving knowledge |
| `/help` | Shows the list of available commands |
| `/clear` | Clears the conversation and starts a new session |

---

## Keyboard Shortcuts

| Shortcut | What It Does |
|---|---|
| `Esc` | Cancels the running operation |
| `Ctrl + C` | Stops the current task |
| `↑ / ↓` | Navigate through previous messages |

---

## Prompt Templates

### File Editing
```
"For [function/section] in [file path], [what to do].
 Do it without breaking the existing [test/structure]."
```

### Debugging
```
"I'm getting this error:
 [error message]
 Read [file path] and find the root cause."
```

### Generating Tests
```
"Write unit tests for [file path].
 Learn the existing test style from the [test directory] folder."
```

### Requesting a Plan
```
"Show me your plan before you start implementing, so I can approve it.
 [task description]"
```

### Agent Task
```
"Use an Explore subagent to [what to search for].
 Context: [project info]
 Return: [format]"
```

### Parallel Task
```
"Run these two tasks in parallel:
 1. [independent task A]
 2. [independent task B]"
```

### Specifying Output Format
```
"Return the result in this format:
 - Problem: [what]
 - Why: [root cause]
 - Solution: [steps]
 - Risk: [side effects]"
```

---

## CLAUDE.md Minimal Template

```markdown
# Project Name

## Overview
[1-2 sentences]

## Tech Stack
- [Language / Framework]
- [Database]

## Commands
- [dev command]
- [test command]

## Rules
- [rule 1]
- [rule 2]
```

---

## settings.json Minimal Template

```json
{
  "permissions": {
    "allow": [
      "Bash(npm run *)",
      "Bash(git status)",
      "Bash(git diff *)",
      "Read(**)"
    ],
    "deny": [
      "Bash(rm -rf *)",
      "Bash(git push --force)"
    ]
  },
  "hooks": {
    "PreToolUse": [],
    "PostToolUse": [],
    "Stop": []
  }
}
```

**File location:** `~/.claude/settings.json` (global) or `.claude/settings.json` (project)

---

## Ready-to-Use Hook Recipes

### Auto Lint (on every edit)
```json
"PostToolUse": [{
  "matcher": "Edit",
  "hooks": [{ "type": "command", "command": "npm run lint --silent 2>&1 | tail -5" }]
}]
```

### Block Dangerous Commands
```json
"PreToolUse": [{
  "matcher": "Bash",
  "hooks": [{ "type": "command", "command": "if echo \"$CLAUDE_TOOL_INPUT\" | grep -qE 'rm -rf|drop table|truncate'; then echo 'Blocked!' >&2; exit 2; fi" }]
}]
```

### Completion Notification (macOS)
```json
"Stop": [{
  "hooks": [{ "type": "command", "command": "osascript -e 'display notification \"Task completed\" with title \"Claude Code\" sound name \"Glass\"'" }]
}]
```

### Run Tests Before Commit
```json
"PreToolUse": [{
  "matcher": "Bash(git commit*)",
  "hooks": [{ "type": "command", "command": "npm test -- --run 2>&1 | tail -10" }]
}]
```

---

## Custom Command Template

**`.claude/commands/command-name.md`:**

```markdown
[Describe what to do]

Steps:
1. [step]
2. [step]

$ARGUMENTS  ← to accept a parameter
```

Usage: `/command-name [optional parameter]`

→ Details: [Custom Commands](./03-hooks-automation/04-custom-commands.md)

---

## Subagent Types

| Type | When |
|---|---|
| `Explore` | Read-only research — doesn't modify files |
| `Plan` | Architectural/approach approval before implementation |
| `claude` | Research + implementation together |
| `general-purpose` | Broad, multi-step tasks |

---

## Common Mistakes and How to Avoid Them

| Mistake | Fix |
|---|---|
| Vague task | Give file path + function name + expected behavior |
| Task too large | Break it down with `/plan`, approve one step at a time |
| Claude is forgetting the project | Move the instructions to CLAUDE.md |
| Context is full | Run `/compact` or start a new conversation |
| Agent returned wrong result | Write the prompt independently — it doesn't know the previous conversation |
| Hook not triggering | Check the location of `.claude/settings.json` |

---

## Useful Links

| Section | File |
|---|---|
| How to write CLAUDE.md | [02 › CLAUDE.md](./02-claude-md/README.md) |
| Hook types and examples | [03 › Hooks & Automation](./03-hooks-automation/README.md) |
| Agent usage | [04 › Agents](./04-agents/README.md) |
| Prompt strategies | [05 › Prompt Strategies](./05-prompt-strategies/README.md) |
| Full navigation | [Home](./README.md) |
