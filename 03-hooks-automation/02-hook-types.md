# 03 › Hooks & Automation › Hook Types

## Available Hook Types

| Type | When Triggered |
|---|---|
| `PreToolUse` | **Before** Claude calls a tool |
| `PostToolUse` | **After** Claude calls a tool |
| `Notification` | When Claude shows a notification |
| `Stop` | When Claude completes a task |

---

## PreToolUse

For stopping dangerous commands or checking before execution:

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "echo 'Bash command running' >> ~/.claude/audit.log"
          }
        ]
      }
    ]
  }
}
```

If the hook exits with `exit 2`, Claude cancels that tool call.

---

## PostToolUse

Run lint after a file is saved:

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit",
        "hooks": [
          {
            "type": "command",
            "command": "npm run lint --silent 2>&1 | head -20"
          }
        ]
      }
    ]
  }
}
```

---

## Stop

Runs when Claude finishes work:

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "osascript -e 'display notification \"Claude finished\" with title \"Claude Code\"'"
          }
        ]
      }
    ]
  }
}
```

---

## → Next Step

You've learned the hook types, now apply them with ready-to-use recipes:

**[03 › Recipes](./03-recipes.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Where to write the hook definition | [settings.json](./01-settings-json.md) |
| Want ready-to-use recipes | [Recipes](./03-recipes.md) |
| Hook runs but behaves unexpectedly | Check exit code and command output |
