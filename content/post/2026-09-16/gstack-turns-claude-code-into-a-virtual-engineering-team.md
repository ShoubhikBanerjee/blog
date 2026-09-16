---
title: "gstack turns Claude Code into a virtual engineering team"
slug: "gstack-turns-claude-code-into-a-virtual-engineering-team"
description: "gstack is a set of Claude Code skills that assemble a virtual engineering team."
date: 2026-09-17T00:45:10+05:30
tags: [gstack, ClaudeCode, AItools, Automation]
categories: ["AI", "Artificial Intelligence", "Software Development", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/19957?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# gstack turns Claude Code into a virtual engineering team

gstack is a set of Claude Code skills that assemble a virtual engineering team.

## 🔍 Overview
- "gstack is my answer."
- Turns Claude Code into a virtual engineering team consisting of:
  - a CEO who rethinks the product
  - an engineering manager who locks architecture
  - a designer who catches AI slop
  - a reviewer who finds production bugs
  - a QA lead who opens a real browser
  - a security officer who runs OWASP + STRIDE audits
  - a release engineer who ships the PR
- Implements twenty‑three specialists and eight power tools, all invoked via slash commands, presented in Markdown, released under an MIT license.

## 🛠️ How it works
- **Required environment**: Claude Code, Git, Bun v1.0+, Node.js (Windows only).
- **macOS recommendation**: Aside browser (macOS 15+) to drive browser‑related skills (/make‑pdf, /diagram) with real logged‑in sessions.
- If the recommended browser is not used, `./setup` builds gstack's own bundled browser for the same skills.
- The `/cso` skill additionally requires a Bun release built with all four `--no-compile-autoload-*` flags and a native toolchain:
  - static‑capable C compiler on Linux
  - Xcode command‑line tools on macOS
  - Visual Studio 2022 Build Tools with Desktop development with C++ on Windows.

## ⚙️ Key details
- In the last 60 days: 3 production services, 40+ shipped features, part‑time work while running YC full‑time.
- 2026 run rate is ~810× the 2013 pace (11,417 vs 14 logical lines/day).
- Year‑to‑date through April 18 2026 has already produced 240× the entire 2013 year.
- Metrics measured across 40 public + private `garrytan/*` repositories (including Bookface) after excluding one demo repo.

## 🚀 Availability
- Install command:
  ```
  git clone --single-branch --depth 1 https://github.com/garrytan/gstack.git ~/.claude/skills/gstack && \
  cd ~/.claude/skills/gstack && ./setup
  ```
- For slower registries, set `GSTACK_CSO_IMAGE_PULL_TIMEOUT_SECONDS` (e.g., 120; accepted range 5–300 seconds).
- The complete preload is capped at one hour.

## 📦 Available skills
- /office-hours
- /plan-ceo-review
- /plan-eng-review
- /plan-design-review
- /design-consultation
- /design-shotgun
- /design-html
- /review
- /ship
- /land-and-deploy
- /canary
- /benchmark
- /browse
- /connect-chrome
- /qa
- /qa-only
- /design-review
- /scrape
- /setup-browser-cookies
- /setup-deploy
- /setup-gbrain
- /retro
- /investigate
- /document-release
- /document-generate
- /codex
- /cso
- /autoplan
- /plan-devex-review
- /devex

## 💡 Why it matters
- Provides a complete virtual engineering workflow within Claude Code, covering product strategy, architecture, design, code review, quality assurance, security auditing, and release engineering without external tools.
- All components are free, open‑source, and accessible via simple slash commands.


#gstack #ClaudeCode #AItools #Automation

---

*Source: [garrytan/gstack](https://github.com/garrytan/gstack)*
