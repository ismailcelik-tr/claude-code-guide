# 05 › Prompt Strategies › Common Mistakes

## Mistake 1: Vague Task

**Wrong:**
```
"Improve the auth system."
```

**Right:**
```
"Add an expiry check to the token validation function
 in src/auth/middleware.ts. Return 401 for expired tokens."
```

---

## Mistake 2: Task Too Large

**Wrong:**
```
"Migrate the entire app to TypeScript."
```

**Right:**
```
"Let's use plan mode first to decide which files to start with.
 Then we'll proceed one file at a time."
```

---

## Mistake 3: Re-explaining Context Every Message

Instead of re-describing the project in every message, use CLAUDE.md.

→ [CLAUDE.md Project-Specific](../02-claude-md/02-project-specific.md)

---

## Mistake 4: Giving Claude Too Many Permissions

Don't allow every `Bash` command. Keep the allow list minimal.

→ [settings.json Permission Management](../03-hooks-automation/01-settings-json.md)

---

## Mistake 5: Not Verifying the Result

Don't skip validation just because Claude said it "did it." Manually verify every important change, or run tests automatically via a hook.

---

## Mistake 6: Long Prompt Chains

Instead of 10-message back-and-forth, clarify everything in one message:

```
"I know: [context]
 I want to do: [goal]
 Constraint: [constraints]
 Expected output: [format]"
```

---

## → Next Step

Once you know how to avoid common mistakes, move to advanced techniques:

**[05 › Advanced](./04-advanced.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| I still can't get the result I want | [Advanced Techniques](./04-advanced.md) |
| I didn't know what to put in CLAUDE.md | [CLAUDE.md Project-Specific](../02-claude-md/02-project-specific.md) |
| I have a context management problem | [Context Management](./02-context-management.md) |
