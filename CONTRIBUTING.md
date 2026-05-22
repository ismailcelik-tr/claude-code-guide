# Contributing Guide

Thanks for wanting to contribute to this repo.

---

## How to Contribute

### Reporting Errors or Missing Information

If you find incorrect or outdated information on a page:

1. [Open an issue](https://github.com/ismailcelik-tr/claude-code-guide/issues/new)
2. Specify which file and section it's in
3. Include what the correct information should be

### Content Contribution (PR)

1. Fork the repo
2. Create a new branch: `git checkout -b content/topic-name`
3. Make your change
4. Open a PR — indicate which section it affects in the title

---

## Content Standards

- **Language:** English (for `.md` files), Turkish (for `.tr.md` files)
- **Target audience:** Software developers (beginner to advanced)
- **Code examples:** Must be real, working examples
- **Every page must have:** `## → Next Step` and `## ↩ Something Went Wrong` sections
- **Links:** Use relative paths (`../directory/file.md`) — diagram `click href` directives require full URLs

## Adding a New Section

1. Number the directory sequentially (`07-new-topic/`)
2. Add a new `click` and `style` line to the navigation diagram in `README.md`
3. Add a row to the sections table
4. Add the relevant reference to `cheatsheet.md`

---

## Questions

If you're unsure about something, open an issue first, then submit a PR.
