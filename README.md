<div align="center">

<img src="./assets/claude-icon.svg" width="80" alt="Claude Code Guide"/>

# Claude Code Guide

[![English](https://img.shields.io/badge/🇬🇧_English-This_Page-0d1117?style=for-the-badge)](./README.md)
[![Türkçe](https://img.shields.io/badge/🇹🇷_Türkçe-README.tr.md-DA7756?style=for-the-badge)](./README.tr.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](./LICENSE)
[![Language](https://img.shields.io/badge/Language-English-blue?style=for-the-badge)](./README.md)
[![Built for Claude Code](https://img.shields.io/badge/Claude%20Code-DA7756?style=for-the-badge&logo=data:image/svg%2bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxMDAgMTAwIj48ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg1MCw1MCkiIGZpbGw9IiNmZmYiPjxyZWN0IHg9Ii00IiB5PSItMzAiIHdpZHRoPSI4IiBoZWlnaHQ9IjI4IiByeD0iNCIvPjxyZWN0IHg9Ii00IiB5PSItMzAiIHdpZHRoPSI4IiBoZWlnaHQ9IjI4IiByeD0iNCIgdHJhbnNmb3JtPSJyb3RhdGUoNDUpIi8+PHJlY3QgeD0iLTQiIHk9Ii0zMCIgd2lkdGg9IjgiIGhlaWdodD0iMjgiIHJ4PSI0IiB0cmFuc2Zvcm09InJvdGF0ZSg5MCkiLz48cmVjdCB4PSItNCIgeT0iLTMwIiB3aWR0aD0iOCIgaGVpZ2h0PSIyOCIgcng9IjQiIHRyYW5zZm9ybT0icm90YXRlKDEzNSkiLz48cmVjdCB4PSItNCIgeT0iLTMwIiB3aWR0aD0iOCIgaGVpZ2h0PSIyOCIgcng9IjQiIHRyYW5zZm9ybT0icm90YXRlKDE4MCkiLz48cmVjdCB4PSItNCIgeT0iLTMwIiB3aWR0aD0iOCIgaGVpZ2h0PSIyOCIgcng9IjQiIHRyYW5zZm9ybT0icm90YXRlKDIyNSkiLz48cmVjdCB4PSItNCIgeT0iLTMwIiB3aWR0aD0iOCIgaGVpZ2h0PSIyOCIgcng9IjQiIHRyYW5zZm9ybT0icm90YXRlKDI3MCkiLz48cmVjdCB4PSItNCIgeT0iLTMwIiB3aWR0aD0iOCIgaGVpZ2h0PSIyOCIgcng9IjQiIHRyYW5zZm9ybT0icm90YXRlKDMxNSkiLz48L2c+PC9zdmc+&logoColor=white)](https://claude.ai/code)
[![Scenarios](https://img.shields.io/badge/Scenarios-8-8b5cf6?style=for-the-badge)](./06-scenarios/README.md)
[![Contributing](https://img.shields.io/badge/Contributing-Open-orange?style=for-the-badge)](./CONTRIBUTING.md)

**A guide for software developers to use Claude Code effectively at every stage of the development process**

</div>

---

Select your current position in the diagram below and navigate to the relevant section. If you take a wrong step, the **↩ Something Went Wrong** table at the bottom of each page will guide you back.

---

## Navigation

```mermaid
flowchart TD
    START([🚀 Start]) --> KARAR{Where are you?}

    KARAR -->|Starting from scratch| B00["🟢 00 · Getting Started\nSetup & first steps"]
    KARAR -->|Building an app| SDLC["🔵 01 · Development Process"]
    KARAR -->|No CLAUDE.md yet| CMD["🟡 02 · CLAUDE.md"]
    KARAR -->|Need automation| HOOK["🟡 03 · Hooks & Automation"]
    KARAR -->|Using agents| AJAN["🟠 04 · Agents"]
    KARAR -->|Prompts are inefficient| PROMPT["🔴 05 · Prompt Strategies"]
    KARAR -->|Want real examples| SCN["📖 06 · Scenarios"]

    SDLC --> P1["🟢 Planning"]
    P1 --> P2["🟢 Development"]
    P2 --> P3["🟡 Test & Debug"]
    P3 --> P4["🟡 Code Review"]
    P4 --> P5["🔴 Deployment"]

    P3 -- "❌ errors found" --> P2
    P4 -- "❌ tests missing" --> P3
    P5 -- "❌ production broke" --> P3

    click B00 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/00-getting-started/README.md"
    click SDLC href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-development-process/README.md"
    click P1 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-development-process/01-planning.md"
    click P2 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-development-process/02-development.md"
    click P3 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-development-process/03-test-and-debug.md"
    click P4 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-development-process/04-code-review.md"
    click P5 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-development-process/05-deployment.md"
    click CMD href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/02-claude-md/README.md"
    click HOOK href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/03-hooks-automation/README.md"
    click AJAN href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/04-agents/README.md"
    click PROMPT href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/05-prompt-strategies/README.md"
    click SCN href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/06-scenarios/README.md"

    style START fill:#1a1a2e,color:#fff,stroke:#7c3aed
    style KARAR fill:#1e3a5f,color:#fff,stroke:#3b82f6
    style B00 fill:#14532d,color:#fff,stroke:#22c55e
    style SDLC fill:#1e3a5f,color:#fff,stroke:#3b82f6
    style P1 fill:#14532d,color:#fff,stroke:#22c55e
    style P2 fill:#14532d,color:#fff,stroke:#22c55e
    style P3 fill:#713f12,color:#fff,stroke:#eab308
    style P4 fill:#713f12,color:#fff,stroke:#eab308
    style P5 fill:#7f1d1d,color:#fff,stroke:#ef4444
    style CMD fill:#713f12,color:#fff,stroke:#eab308
    style HOOK fill:#713f12,color:#fff,stroke:#eab308
    style AJAN fill:#7c2d12,color:#fff,stroke:#f97316
    style PROMPT fill:#7f1d1d,color:#fff,stroke:#ef4444
    style SCN fill:#1e3a5f,color:#fff,stroke:#818cf8
```

> Color scale: 🟢 Easy/Beginner — 🟡 Intermediate — 🟠 Advanced — 🔴 Requires attention  
> Red arrows (`❌`) indicate fallback paths on failure.

---

## Sections

| # | Section | What you'll learn |
|---|---|---|
| ⚡ | [Cheat Sheet](./cheatsheet.md) | All commands, shortcuts, templates and hook recipes on one page |
| 00 | [Getting Started](./00-getting-started/README.md) | What is Claude Code, setup, how to follow this guide |
| 01 | [Development Process](./01-development-process/README.md) | Planning → Development → Test → Review → Deployment |
| 02 | [CLAUDE.md](./02-claude-md/README.md) | Setting up project context, templates, import and memory |
| 03 | [Hooks & Automation](./03-hooks-automation/README.md) | settings.json, hook types, ready-to-use recipes |
| 04 | [Agents](./04-agents/README.md) | Agent tool, subagent types, parallel execution |
| 05 | [Prompt Strategies](./05-prompt-strategies/README.md) | Plan mode, context management, common mistakes, advanced |
| 06 | [Real Scenarios](./06-scenarios/README.md) | SaaS from scratch, legacy modernization, production crisis, and more |

---

## Quick Recovery Map

| Situation | Go back to |
|---|---|
| Claude doesn't seem to understand the project | [CLAUDE.md Basic Structure](./02-claude-md/01-basic-structure.md) |
| Hook never triggers | [settings.json Location](./03-hooks-automation/01-settings-json.md#location-and-format) |
| Agent returns unexpected result | [Agent Tool — Basic Usage](./04-agents/01-agent-tool.md) |
| Claude writes too much / too little code | [Common Mistakes](./05-prompt-strategies/03-common-mistakes.md) |
| CI/CD broke at deploy step | [Deployment Checklist](./01-development-process/05-deployment.md#checklist) |
| Context filled up, conversation lost | [Context Management](./05-prompt-strategies/02-context-management.md) |
| Tests pass but production breaks | [Test & Debug](./01-development-process/03-test-and-debug.md) |

---

## Contributing

This repo is open to community contributions.

- Report errors or missing content → [Open an issue](https://github.com/ismailcelik-tr/claude-code-guide/issues/new)
- Content contributions → [CONTRIBUTING.md](./CONTRIBUTING.md)
- Security reports → [SECURITY.md](./SECURITY.md)
- License → [MIT](./LICENSE)
