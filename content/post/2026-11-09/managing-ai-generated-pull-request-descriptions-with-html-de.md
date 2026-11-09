---
title: "Managing AI-Generated Pull Request Descriptions with HTML Details and Summary Tags"
slug: "managing-ai-generated-pull-request-descriptions-with-html-details-and-summary-tags"
description: "Developers are increasingly utilizing coding agents like Claude Code and Codex to open pull requests (PRs) and manage project changes. While these agents generate accurate and comprehensive..."
date: 2026-11-09T18:02:52+05:30
tags: [GitHub, AIagents, ClaudeCode, Markdown, PullRequests]
categories: ["AI", "AI Agents", "Software Development", "Web Development"]
image: "https://static.simonwillison.net/static/2026/details-summary-card.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Managing AI-Generated Pull Request Descriptions with HTML Details and Summary Tags

Developers are increasingly utilizing coding agents like Claude Code and Codex to open pull requests (PRs) and manage project changes. While these agents generate accurate and comprehensive descriptions—detailing the problem, the solution, and verification steps—the volume of text can be overwhelming, leading to the use of specific Markdown techniques to organize information for human reviewers.

## 🧩 How it works
GitHub Markdown supports the HTML `<details><summary>` elements, which render as a collapsed heading that can be expanded to view larger blocks of text. This feature allows developers to bundle agent-written content behind a concise, human-curated summary:
*   The `<summary>` tag serves as the clickable line of text that acts as a summary.
*   The `<details>` element wraps the rest of the content to keep it hidden until expanded.
*   A carefully selected opening paragraph provides a high-level explanation to get readers up to speed.
*   The full agent-written description is placed within the tags to prevent the reader's eyes from glazing over.
*   Screenshots are sometimes included to quickly illustrate new features.

## ⚙️ Key details
To maintain clarity, the order of the tags can be remembered using the five-syllable mnemonic "details-summary." Developers use the summary line to identify the source and intensity of the AI work.

| Attribute | Usage in PR Summary |
| :--- | :--- |
| Model Name | Identifies the specific agent used, such as Claude Opus 5.5. |
| Effort Level | Indicates the intensity of the work, such as "Medium". |
| Human Judgement | Used to select the short opener or extract a summary from the agent's text. |

## 💡 Why it matters
Using the `<details><summary>` structure ensures that the PR remains a functional unit of work for bundling commits and documenting decisions without sacrificing readability. It provides a promise to the reader that the visible text represents human judgment on what is worth their time, while keeping the exhaustive agent-generated verification steps and data accessible for those who need it.

![figure](https://static.simonwillison.net/static/2026/details-summary-pr.gif)

#GitHub #AIagents #ClaudeCode #Markdown #PullRequests

---

*Source: [Hide your slop PR descriptions behind <details><summary>](https://simonwillison.net/2026/Nov/9/details-summary/)*
