---
title: "Shep Launches as Open-Source Orchestrator for Autonomous AI Development"
slug: "shep-launches-as-open-source-orchestrator-for-autonomous-ai-development"
description: "Shep is the open-source orchestrator for the autonomous development cycle. It runs parallel AI agents — Claude Code, Kimi Code, Codex CLI, Copilot CLI, Cursor CLI, Gemini CLI, Cline, or any agent CLI..."
date: 2026-11-25T22:10:10+05:30
tags: []
categories: ["AI"]
image: "https://avatars.githubusercontent.com/u/252908629?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Shep Launches as Open-Source Orchestrator for Autonomous AI Development

Shep is the open-source orchestrator for the autonomous development cycle. It runs parallel AI agents — Claude Code, Kimi Code, Codex CLI, Copilot CLI, Cursor CLI, Gemini CLI, Cline, or any agent CLI — each in its own isolated git worktree, and drives every feature from a one-line description through optional spec gates, implementation, commit, push, CI watching with auto-fix, and a draft pull request.

Agent-agnostic, local-first, MIT-licensed.

## 🚀 Availability

Shep can be tried instantly with:

- `npx @shepai/cli` — opens the dashboard at localhost:4050
- `npm i -g @shepai/cli` — or install globally

## ⚙️ Key details

Three commands from zero to an open pull request:

- `npm i -g @shepai/cli`
- `cd ~/projects/my-app`
- `shep feat new "add a /health endpoint that returns uptime and version" --push --pr`

Shep creates a worktree, runs your agent, commits, pushes, and opens a PR. It requires Node.js 22+, pnpm 10+, Git, the GitHub CLI (`gh`), and an authenticated agent CLI — `claude`, `kimi`, `codex`, `copilot`, `cursor-agent`, `gemini` or `cline`. Cursor's binary is `cursor-agent`, not `cursor`.

## 💡 Why it matters

Prefer zero install? app.shep.bot runs Shep in your browser, free.

The default flow is prompt → implement → commit → push → PR. Your working directory is never touched: every feature lives in its own worktree on its own branch. If CI fails, the agent reads the logs and pushes a fix (3 retries by default, configurable).

For complex features, add `--no-fast` to enable the full spec-driven pipeline — requirements, research, and a plan as versioned YAML artifacts, with approval gates before any code is written.

Shep also supports app generation:

- `shep app new "A booking tool for climbing gyms"` — start an app — any stack

A new app starts one of two ways:

- **Plan it first** (default, `blank`) | Any. Chosen by the app's first feature during research | Requirements → research → plan, each approved before code
- **Quick prototype** (`--starter vite-shadcn`) | Vite + React + TypeScript + Tailwind + shadcn | Built straight from chat with a live preview, no spec phase

Every later feature attaches to its app — create it in the app's folder, or with **Add feature** on the app page. Already have code? Run `shep feat new` in that repository, or open the folder from **Apps**. In the web UI: **Apps → New app**.

Swap agents per feature, per repo, anytime. Three agents, three worktrees, zero branch conflicts — monitored from one place.

---

*Source: [shep-ai/shep](https://github.com/shep-ai/shep)*
