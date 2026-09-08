---
title: "Tracking Pull Request Performance of Top SWE Coding Agents"
description: "A new repository tracks the opened and merged pull requests (PRs) from top software engineering (SWE) coding agents developed by OpenAI, GitHub, and other organizations."
date: 2026-09-09T00:16:34+05:30
tags: [SWEagents, GitHub, OpenAI, CodingAI]
categories: ["AI Agents", "Software Engineering", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/3076502?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Tracking Pull Request Performance of Top SWE Coding Agents

A new repository tracks the opened and merged pull requests (PRs) from top software engineering (SWE) coding agents developed by OpenAI, GitHub, and other organizations.

## 🔍 Overview
The repository monitors three types of pull requests:
* **All PRs**: Every pull request created by an agent, including DRAFT PRs.
* **Ready PRs**: Non-draft pull requests that are ready for review and merging.
* **Merged PRs**: Pull requests that were successfully merged into the codebase.

## ⚙️ Key details
Different agents employ varying workflows for PR creation:
* **Codex**: Iterates privately and creates ready PRs directly, which results in high merge rates and very few drafts.
* **Copilot and Codegen**: Create draft PRs first to encourage public iteration before marking them as ready for review.

To ensure a fair comparison across these different workflows, the provided statistics focus exclusively on Ready PRs.

| Agent | Ready PRs | Merged PRs | Merge Rate |
| :--- | :--- | :--- | :--- |
| Copilot | 1,601,066 | 1,537,196 | 96.01% |
| Codex | 6,677,490 | 5,972,386 | 89.44% |
| Cursor | 731,870 | 748,740 | 102.31% |
| Devin | 239,253 | 147,091 | 61.48% |
| Codegen | 5,628 | 3,462 | 61.51% |
| Jules | 233,646 | 201,335 | 86.17% |

#SWEagents #GitHub #OpenAI #CodingAI

---

*Source: [aavetis/PRarena](https://github.com/aavetis/PRarena)*
