# 01 › Development Process › Test & Debug

Using Claude Code for writing tests and debugging.

---

## Generating Tests

```
"Write unit tests for src/utils/parser.ts.
 Cover edge cases: empty input, null, maximum length."
```

If a test file already exists, have Claude read it first:

```
"Learn the existing test style from the test/utils/ folder,
 then write parser.test.ts in the same style."
```

---

## Debugging

Paste the error message as-is:

```
"I'm getting this error:
 TypeError: Cannot read properties of undefined (reading 'map')
 at src/components/UserList.tsx:42

 Read the relevant file and find the cause."
```

Claude reads the file, finds the line, explains the root cause, and fixes it.

---

## Log Analysis

You can paste long log output directly:

```
"Analyze this CI log and list the reason for failure:"
[log content]
```

---

## Tests Pass But Production Breaks

This usually comes from mock/real environment differences.

1. Find what's being mocked in the test environment
2. Explain the real environment difference to Claude
3. Write an integration test

```
"This test uses a mock database.
 Write an integration test that works with a real Postgres connection."
```

---

## → Next Step

If tests pass, you're ready for code review:

**[01 › Code Review](./04-code-review.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Test was generated but doesn't run | [Development — Reading Existing Code](./02-development.md) |
| Error message is unclear | [Common Mistakes](../05-prompt-strategies/03-common-mistakes.md) |
| Tests pass but production breaks | This page's "Mock/Real" section |
| Want to move to code review | [Code Review](./04-code-review.md) |
