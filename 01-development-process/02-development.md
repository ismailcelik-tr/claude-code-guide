# 01 › Development Process › Development

How to use Claude Code while actively writing code.

---

## Reading and Editing Files

When permitted, Claude reads and edits files directly. It shows you which file it will change and why, then waits for approval.

**Good prompt example:**
```
"Add rate limiting to the validateUser function in src/auth/login.ts.
 Do it without breaking the existing tests."
```

**Avoid:**
```
"Improve the auth system."  ← too vague
```

---

## Refactoring

```
"Read this file and extract the repeated code.
 List everything you're going to change first, then apply."
```

For large refactors, use plan mode → [Planning](./01-planning.md)

---

## Adding New Features

1. Have Claude read the relevant existing code first
2. Tell Claude what to add and where
3. Review the generated code, then approve

```
"These files currently exist: [file list].
 Add a new payment module without touching them."
```

---

## Tool Permissions

Claude Code asks for permission for some commands. Be careful when granting permission for frequently used commands:

- `Bash` — terminal commands
- `Edit` / `Write` — file changes
- `WebFetch` — internet access

→ For permission management: [settings.json](../03-hooks-automation/01-settings-json.md)

---

## → Next Step

Once you've written the code, move to testing:

**[01 › Test & Debug](./03-test-and-debug.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Claude changed too many files | [Common Mistakes](../05-prompt-strategies/03-common-mistakes.md) |
| Claude edited the wrong file | [CLAUDE.md Project-Specific](../02-claude-md/02-project-specific.md) |
| Code was written without being tested | [Test & Debug](./03-test-and-debug.md) |
