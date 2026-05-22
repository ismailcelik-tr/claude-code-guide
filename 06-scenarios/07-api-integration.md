# Scenario 07 › API Integration

**Situation:** You're connecting a third-party API to your application — payments, notifications, maps, social media, or any other service.

**Difficulty:** 🟢 Beginner

---

## Step 1 — Understand the API

Give Claude the documentation or OpenAPI spec:

```
"Read this API documentation:
 [URL or content]

 Summarize:
 - Auth method (API key, OAuth, Bearer)
 - The endpoints I'll be using
 - Rate limit rules
 - Error codes and their meanings"
```

---

## Step 2 — Design the Integration Layer

```
"Design a service layer for this API.
 Existing project structure: [directory structure]

 Make sure to:
 - Read the API key from an environment variable
 - Create a separate function for each endpoint
 - Centralize error handling
 - Add retry logic"
```

---

## Step 3 — Develop with Mocks

Use mocks before connecting to the real API:

```
"Mock these endpoints for this API:
 [endpoint list]

 So I can test the integration in the test environment
 without making real API requests."
```

---

## Step 4 — Error Handling

```
"This API can return these error codes:
 [error codes]

 How should my application behave for each one?
 What should it show the user, how should it log?"
```

---

## Step 5 — Test in the Real Environment

When switching from mock to the real API:

```
"Create a checklist before taking the integration to production.
 Include API key management, rate limit tracking,
 and fallback scenarios."
```

---

## Common Pitfalls in This Scenario

| Mistake | Consequence |
|---|---|
| Writing the API key directly in the code | Secret exposure risk |
| Developing without mocks | Every test hits the real API and exhausts the rate limit |
| Skipping error handling | The app crashes when the API goes down |
| Ignoring rate limits | Service suddenly cuts out in production |

---

## → Next Step

**[Scenario 08 › Database Migration](./08-database-migration.md)**

---

## ↩ Something Went Wrong

| Situation | Go back to |
|---|---|
| API integration can't be tested | [Test & Debug](../01-development-process/03-test-and-debug.md) |
| Environment variable management | [Deployment — Environment Variables](../01-development-process/05-deployment.md) |
| Adding API info to CLAUDE.md | [CLAUDE.md Project-Specific](../02-claude-md/02-project-specific.md) |
