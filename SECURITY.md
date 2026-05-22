# Security Policy

---

## About This Repo

This repo contains only **documentation** — it does not include executable code. The classic security vulnerability disclosure scenario does not apply here.

However, please follow the process below for **incorrect or dangerous security advice** in the content.

---

## Reporting Incorrect Security Content

If you see advice in the guide that could create a security risk (for example: a dangerous permission suggestion, a secret management mistake, an unsafe hook example):

1. **Don't open a public issue** — report by email/DM first
2. Contact: send a DM to [@ismailcelik-tr](https://github.com/ismailcelik-tr) on GitHub
3. Add `[SECURITY]` to the subject line

---

## Safe Usage Reminders

When applying this guide, keep the following in mind:

- **Never paste secrets or API keys into Claude** — only share variable names
- **Don't leave the `deny` list empty** — at minimum, block `rm -rf` and `git push --force`
- **Test hook commands before using in production** — try them in staging first to prevent unexpected side effects
- **Before committing settings.json to git** — verify it contains no sensitive information

---

## Acknowledgment

Contributors who submit security reports will be credited in CONTRIBUTING.md (if they wish).
