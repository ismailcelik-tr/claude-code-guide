# 05 › Prompt Strategies › Context Management

## What is Context?

Claude's "memory" is all the messages it holds within a single conversation. As conversations grow longer, context starts to fill up.

---

## What Happens When Context Fills Up?

- Older messages get summarized or dropped
- Claude may "forget" earlier decisions
- Performance can degrade

---

## Use Context Efficiently

**Don't add unnecessary things to the conversation:**
- Don't paste long file contents manually — tell Claude to read the file
- Don't repeat the same instructions in every message — move them to CLAUDE.md

**Move frequently used context to CLAUDE.md:**
```markdown
## Architecture Decisions
- All API calls go through src/api/client.ts
```

---

## Clear the Conversation

When context is too full, start a new conversation and summarize the important context:

```
"In our previous conversation we did: [summary].
 Now I want to do: [new task]."
```

---

## The /compact Command

```
/compact
```

Compresses the conversation history, clears context while preserving knowledge.

---

## → Next Step

Now that you know how to manage context, review the common mistakes:

**[05 › Common Mistakes](./03-common-mistakes.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Claude forgot a previous decision | Move it to CLAUDE.md or summarize in a new conversation |
| The conversation got very slow | Run /compact |
| What is the memory system | [CLAUDE.md Advanced](../02-claude-md/03-advanced.md) |
