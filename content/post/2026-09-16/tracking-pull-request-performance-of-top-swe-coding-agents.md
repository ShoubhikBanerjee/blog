---
title: "Tracking Pull Request Performance of Top SWE Coding Agents"
slug: "tracking-pull-request-performance-of-top-swe-coding-agents"
description: "A new repository tracks the opened and merged pull requests (PRs) from top software engineering (SWE) coding agents developed by OpenAI, GitHub, and other entities."
date: 2026-09-17T00:45:10+05:30
tags: [SWEagents, codingagents, GitHub, OpenAI]
categories: ["AI", "AI Agents", "Software Engineering", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/3076502?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Tracking Pull Request Performance of Top SWE Coding Agents

A new repository tracks the opened and merged pull requests (PRs) from top software engineering (SWE) coding agents developed by OpenAI, GitHub, and other entities.

## 🔍 Overview

The repository categorizes pull requests into three types:
* **All PRs**: Every pull request created by an agent, including DRAFT PRs.
* **Ready PRs**: Non-draft pull requests that are ready for review and merging.
* **Merged PRs**: Pull requests that were successfully merged into the codebase.

## ⚙️ Key details

Different agents utilize different workflows for PR creation:
* **Codex**: Iterates privately and creates ready PRs directly, resulting in high merge rates and few drafts.
* **Copilot and Codegen**: Create draft PRs first to encourage public iteration before marking them as ready for review.

To ensure a fair comparison across these different workflows, statistics focus on Ready PRs only.

## 📊 Agent Statistics

| Agent | Ready PRs | Merged PRs | Merge Rate |
| :--- | :--- | :--- | :--- |
| Copilot | 1,606,114 | 1,542,535 | 96.04% |
| Codex | 6,896,711 | 6,179,306 | 89.6% |
| Cursor | 820,725 | 834,966 | 101.74% |
| Devin | 244,909 | 150,954 | 61.64% |
| Codegen | 5,628 | 3,462 | 61.51% |
| Jules | 235,475 | 202,177 | 85.86% |

#SWEagents #codingagents #GitHub #OpenAI

---

*Source: [aavetis/PRarena](https://github.com/aavetis/PRarena)*
