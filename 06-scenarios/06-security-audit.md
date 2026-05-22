# Scenario 06 › Security Audit

**Situation:** You want to scan your codebase for security issues — before a deploy, as a periodic audit, or after an incident.

**Difficulty:** 🔴 Advanced  
**Rule:** Security findings must be fixed before they are made public.

---

## Step 1 — Dependency Scanning

```
"Read package.json and package-lock.json.
 List dependencies with known security vulnerabilities.
 For each one: severity level, affected version, safe version."
```

---

## Step 2 — Code Analysis

Have Claude inspect critical files:

```
"Inspect these files from a security perspective:
 [file list]

 Look for:
 - SQL injection / NoSQL injection
 - XSS risks
 - Authentication bypass
 - Sensitive data exposure
 - Insecure direct object references (IDOR)

 For each finding: file, line, risk level, suggested fix."
```

---

## Step 3 — Authentication & Authorization Check

```
"Read the auth middleware.
 Check:
 - Is token validation complete?
 - Is authorization checked on every endpoint?
 - Is session duration configured correctly?"
```

---

## Step 4 — Fix Security Findings

Once findings are clear, fix them in priority order:

```
"Start with the high-risk findings.
 For each fix:
 1. Make the minimal code change
 2. Explain what the fix does
 3. Write a regression test"
```

---

## Step 5 — Secret Scanning

```
"Scan the codebase for hardcoded secrets, API keys, or passwords.
 Don't look at .env files — only scan source code."
```

> [!CAUTION]
> Never paste real secret values into Claude. Only share variable names and file locations.

---

## Common Pitfalls in This Scenario

| Mistake | Consequence |
|---|---|
| Only scanning dependencies and skipping the code | Vulnerabilities in the application layer stay invisible |
| Fixing everything at once without prioritizing | Time wasted on low-risk items while critical ones wait |
| Pasting secrets into Claude | Security risk |
| Not writing tests after fixing | The vulnerability can be reintroduced in a later PR |

---

## → Next Step

**[Scenario 07 › API Integration](./07-api-integration.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| I didn't know how to fix a security finding | [Development](../01-development-process/02-development.md) |
| How to write tests | [Test & Debug](../01-development-process/03-test-and-debug.md) |
| I want to report a security issue | [SECURITY.md](../SECURITY.md) |
