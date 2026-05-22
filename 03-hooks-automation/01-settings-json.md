# 03 › Hooks & Automation › settings.json

## Location and Format {#location-and-format}

There are two locations:

| File | Scope |
|---|---|
| `~/.claude/settings.json` | All projects (global) |
| `.claude/settings.json` | This project only (project-level) |

> [!CAUTION]
> Make sure `.claude/settings.json` is inside the `.claude/` directory.
> If left as `settings.json` in the project root, Claude won't read it.

---

## Basic Structure

```json
{
  "permissions": {
    "allow": [],
    "deny": []
  },
  "hooks": {
    "PreToolUse": [],
    "PostToolUse": [],
    "Notification": [],
    "Stop": []
  }
}
```

---

## Permission Definitions

```json
{
  "permissions": {
    "allow": [
      "Bash(npm run *)",
      "Bash(git status)",
      "Bash(git diff *)",
      "Edit(src/**)",
      "Read(**)"
    ],
    "deny": [
      "Bash(rm -rf *)",
      "Bash(git push --force)"
    ]
  }
}
```

Glob is supported: `*` single segment, `**` multiple segments.

---

## → Next Step

Now that you understand settings.json, learn about hook types:

**[03 › Hook Types](./02-hook-types.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Asking where settings.json goes | This page's "Location" section |
| What are the hook types | [Hook Types](./02-hook-types.md) |
| Permitted command still being asked | Check glob pattern |
