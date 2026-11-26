---
title: "Mastra AI releases skills framework for building AI applications with TypeScript"
slug: "mastra-ai-releases-skills-framework-for-building-ai-applications-with-typescript"
description: "Mastra is a framework for building AI-powered applications and agents with a modern TypeScript stack. It supports skill discovery via the `.well-known` standard and provides installation methods..."
date: 2026-11-26T22:08:01+05:30
tags: [TypeScript, AI, framework, skills, agents, development]
categories: ["AI", "AI Development", "Software Development", "AI Agents", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/149120496?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Mastra AI releases skills framework for building AI applications with TypeScript

Mastra is a framework for building AI-powered applications and agents with a modern TypeScript stack. It supports skill discovery via the `.well-known` standard and provides installation methods through `npx skills add https://mastra.ai/`.

## 🔍 Overview

Mastra introduces a skills framework for developing AI applications using TypeScript. The system enables automatic skill discovery through the `.well-known` skills standard, allowing developers to discover capabilities without manual configuration.

## 🧩 How it works

The framework implements progressive disclosure with reference files covering multiple development aspects:

| Reference File | Purpose |
|--------------|---------|
| `create-mastra.md` | Setup & Installation |
| `embedded-docs.md` | Find APIs in `node_modules/@mastra/*/dist/docs/` |
| `remote-docs.md` | Fetch from `https://mastra.ai/llms.txt` |
| `common-errors.md` | Common errors and solutions |
| `migration-guide.md` | Version upgrade workflows |
| `mastra-api.md` | Inspect and call resources on local, platform, or remote servers |
| `platform.md` | Build and deploy apps to Mastra Platform |
| `gateway.md` | One key for many providers, failover, spend tracking |
| `trace-query.md` | Select completed traces with recursive predicates |
| `feedback.md` | Report verified bugs and concrete documentation defects |

The main skill file teaches core concepts and routes to appropriate reference files based on user questions. A standalone Factory skill enables coding agents using `mastra api factory`, covering first-use CLI/login checks and URL-based connection capabilities.

## ⚙️ Key details

### Installation Methods

- `npx skills add mastra-ai/skills`
- `gh skill install mastra-ai/skills`
- `git clone https://github.com/mastra-ai/skills.git` (then configure agent to load from cloned directory)

### Well-Known Discovery

- RFC 8615 Well-Known URI: `https://mastra.ai/.well-known/skills/`
- Index: `https://mastra.ai/.well-known/skills/index.json`
- Mastra skill: `https://mastra.ai/.well-known/skills/mastra/SKILL.md`
- Factory skill: `https://mastra.ai/.well-known/skills/mastra-factory/SKILL.md`

### Factory Skill Features

The Factory skill is a comprehensive skill for AI development that covers:

- First-use CLI/login checks
- URL-based connection from any directory
- Project and queue summaries
- Work-item session/thread and memory inspection
- Health interpretation
- User-authorized operations

### Installation Options

- `npx skills add mastra-ai/skills --skill mastra-factory` (install just the Factory skill with interactive agent/scope selection)
- Global install with `--agent <agent> -g` for supported agents explicitly
- Multi-agent installs can partially succeed; verify with `npx skills list` (add `-g` for global scope)

## 🚀 Availability

The skills repository is available via:

- GitHub: `git clone https://github.com/mastra-ai/skills.git`
- RFC 8615 Well-Known URI for automatic discovery
- Direct URL installation: `npx skills add https://mastra.ai/`

The repository is served via Apache-2.0 license and welcomes contributions through forking, improvement to `SKILL.md` files, testing with development workflows, and submitting pull requests.

#TypeScript #AI #framework #skills #agents #development

---

*Source: [mastra-ai/skills](https://github.com/mastra-ai/skills)*
