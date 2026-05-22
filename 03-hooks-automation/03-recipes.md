# 03 › Hooks & Automation › Recipes

Ready-to-use hook examples — copy and paste.

---

## Recipe 1: Auto Lint on Every Edit

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit",
        "hooks": [
          {
            "type": "command",
            "command": "npm run lint --silent 2>&1 | tail -5"
          }
        ]
      }
    ]
  }
}
```

---

## Recipe 2: Block Dangerous Commands

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "if echo \"$CLAUDE_TOOL_INPUT\" | grep -qE 'rm -rf|drop table|truncate'; then echo 'Dangerous command blocked!' >&2; exit 2; fi"
          }
        ]
      }
    ]
  }
}
```

---

## Recipe 3: Completion Notification (macOS)

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "osascript -e 'display notification \"Task completed\" with title \"Claude Code\" sound name \"Glass\"'"
          }
        ]
      }
    ]
  }
}
```

---

## Recipe 4: Run Tests Before Git Commit

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash(git commit*)",
        "hooks": [
          {
            "type": "command",
            "command": "npm test -- --run 2>&1 | tail -10"
          }
        ]
      }
    ]
  }
}
```

---

## → Next Step

If you want to turn repetitive prompts into commands:

**[03 › Custom Commands](./04-custom-commands.md)**

Or move on to agent usage:

**[04 › Agents](../04-agents/README.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Recipe not working | [settings.json Location](./01-settings-json.md#location-and-format) |
| Didn't know which hook type to use | [Hook Types](./02-hook-types.md) |
| What does exit 2 do | [PreToolUse explanation](./02-hook-types.md) |
