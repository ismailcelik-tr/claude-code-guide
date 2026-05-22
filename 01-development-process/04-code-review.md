# 01 › Development Process › Code Review

Efficiency in PR and code review with Claude Code.

---

## Diff Review

```
/review
```

or:

```
"Review the git diff main...HEAD output.
 List any security vulnerabilities, performance issues, and style violations."
```

---

## Generating PR Descriptions

```
"Summarize the changes in this branch.
 Write it in GitHub PR description format: Summary, Test Plan, Breaking Changes."
```

---

## Generating Inline Comments

```
/review --comment
```

This command reads the changes in the PR and posts them as inline comments to GitHub.

---

## Reviewing Someone Else's Code

```
"Review this PR: [file content or diff]
 Only list real errors or significant issues.
 Don't make style comments."
```

---

## → Next Step

Once review is complete, move to deployment:

**[01 › Deployment](./05-deployment.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Review was too superficial | [Advanced Prompt Techniques](../05-prompt-strategies/04-advanced.md) |
| Reviewed the wrong files | [Context Management](../05-prompt-strategies/02-context-management.md) |
| Test gaps were identified | [Test & Debug](./03-test-and-debug.md) |
| Want to move to deployment | [Deployment](./05-deployment.md) |
