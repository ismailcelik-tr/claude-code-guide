# 01 › Development Process › Deployment

Using Claude Code in CI/CD integration and deployment.

---

## CI/CD Failure Analysis

Give Claude a failed pipeline log:

```
"I'm pasting the GitHub Actions log.
 Which step failed and why? How do I fix it?"
[log content]
```

---

## Environment Variable and Config Management

```
"Read this .env.example file.
 List the missing variables for the production environment."
```

> [!CAUTION]
> Don't paste real secret values (API keys, passwords) to Claude. Only share variable names.

---

## Docker / Container

```
"Review this Dockerfile.
 Suggest improvements to reduce image size and close security vulnerabilities."
```

---

## Checklist {#checklist}

Review with Claude before deploying:

```
"Create a pre-deploy checklist.
 Project: [project type], target environment: [prod/staging], platform: [AWS/Vercel/…]"
```

Claude lists items like migrations, env vars, dependencies, health checks.

---

## → Next Step

If you want to automate the process:

**[03 › Hooks & Automation](../03-hooks-automation/README.md)**

Or to use Claude Code more efficiently:

**[05 › Prompt Strategies](../05-prompt-strategies/README.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| Can't understand the CI/CD log | This page's "CI/CD Failure Analysis" section |
| Production breaks after deploy | [Test & Debug](./03-test-and-debug.md) |
| Missing environment variables | This page's "Environment Variable" section |
| Need to go back to the beginning | [Development Process Home](./README.md) |
