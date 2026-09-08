---
title: "Garry Tan Releases gstack to Transform Claude Code into Virtual Engineering Team"
slug: "garry-tan-releases-gstack-to-transform-claude-code-into-virtual-engineering-team"
description: "Garry Tan, President & CEO of Y Combinator, has released gstack, a tool designed to turn Claude Code into a virtual engineering team consisting of 23 specialists and eight power tools."
date: 2026-09-09T00:31:26+05:30
tags: [gstack, ClaudeCode, AIagents, SoftwareEngineering, DeveloperTools]
categories: ["AI Agents", "Software Development", "Developer Productivity"]
image: "https://avatars.githubusercontent.com/u/19957?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Garry Tan Releases gstack to Transform Claude Code into Virtual Engineering Team

Garry Tan, President & CEO of Y Combinator, has released gstack, a tool designed to turn Claude Code into a virtual engineering team consisting of 23 specialists and eight power tools.

## 🔍 Overview

Using gstack, Garry Tan reports the following productivity increases measured across 40 public and private garrytan/* repositories (including Bookface, excluding one demo repo):

* **Recent output:** 3 production services and 40+ shipped features in the last 60 days, completed part-time.
* **Run rate:** 2026 run rate is ~810× the 2013 pace (11,417 vs 14 logical lines/day).
* **Annual comparison:** Year-to-date through April 18, 2026 has produced 240× the entire 2013 year.

## 🧩 How it works

gstack utilizes slash commands and Markdown to simulate various professional roles:

| Role | Function |
| :--- | :--- |
| CEO | Rethinks the product |
| Eng Manager | Locks architecture |
| Designer | Catches AI slop |
| Reviewer | Finds production bugs |
| QA Lead | Opens a real browser |
| Security Officer | Runs OWASP + STRIDE audits |
| Release Engineer | Ships the PR |

## ⚙️ Key details

**Technical Requirements:**
* Claude Code
* Git
* Bun v1.0+
* Node.js (Windows only)

**Browser Integration:**
* **Recommended (macOS 15+):** The Aside browser, which provides browser skills, `/make-pdf`, and `/diagram` using real logged-in sessions.
* **Alternative:** Running `./setup` builds gstack's own bundled browser.

**Key Commands:**
* `/office-hours`: Describe what you're building
* `/plan-ceo-review`: Review feature ideas
* `/review`: Review branches with changes
* `/qa`: Test staging URLs

**Full Skills List:**
/office-hours, /plan-ceo-review, /plan-eng-review, /plan-design-review, /design-consultation, /design-shotgun, /design-html, /review, /ship, /land-and-deploy, /canary, /benchmark, /browse, /connect-chrome, /qa, /qa-only, /design-review, /scrape, /setup-browser-cookies, /setup-deploy, /setup-gbrain, /retro, /investigate, /document-release, /document-generate, /codex, /cso, /autoplan, /plan-devex-review, /devex-review, /careful, /freeze, /guard, /unfreeze, /gstack-upgrade, /learn.

## 🚀 Availability

gstack is released under the MIT license and is free. It can be installed via the following command:

`git clone --single-branch --depth 1 https://github.com/garrytan/gstack.git ~/.claude/skills/gstack && cd ~/.claude/skills/gstack && ./setup`

Every Claude Code session includes a silent, network-failure-safe auto-update check throttled to once per hour.

#gstack #ClaudeCode #AIagents #SoftwareEngineering #DeveloperTools

---

*Source: [garrytan/gstack](https://github.com/garrytan/gstack)*
