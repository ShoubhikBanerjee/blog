---
title: "OpenQodex adds pre-push code review for Claude Code, Codex, and Cursor"
slug: "openqodex-adds-pre-push-code-review-for-claude-code-codex-and-cursor"
description: "Open source code review tool OpenQodex now runs inside coding agents to check every change before you push. It operates without requiring a separate account or API key, acting as a separate reviewer..."
date: 2026-11-25T06:12:19+05:30
tags: [OpenQodex, CodeReview, AIagents, ClaudeCode, OpenSource]
categories: ["AI", "AI Agents", "Developer Tools", "Open Source"]
image: "https://avatars.githubusercontent.com/u/336816094?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# OpenQodex adds pre-push code review for Claude Code, Codex, and Cursor

Open source code review tool OpenQodex now runs inside coding agents to check every change before you push. It operates without requiring a separate account or API key, acting as a separate reviewer that validates code changes made by agents in Claude Code, Codex, Cursor, and Cline.

## 🔍 Overview
- OpenQodex is an open source code review tool for coding agents.
- It runs a separate reviewer that checks every change an agent writes before the user pushes.
- No account or key of its own is required.
- It is available for use in Claude Code, Codex, Cursor, and Cline.

## 🧩 How it works
- **Code Graph**: A code graph provides the agent with a map of the codebase.
- **Scanner Integration**: It runs scanners that fit the changed files, keeping findings on the changed lines. A scanner is a program that checks code without a model, such as gitleaks or semgrep.
- **Dependency Check**: Every supported lockfile in the repository is checked against osv.dev at every review and scan of a change. Advisories outside the changed lines are shown but never counted.
- **Fresh Reviewers**: Separate Claude Code or Codex processes on the user's login run the review, with no memory of the current session.
- **Verification**: A script checks every line a reviewer quotes as evidence against the code. Verifiers confirm or refute every candidate and every scanner finding.

## ⚙️ Key details
- **Initiation**: Users say to their agent, "review my change with openqodex".
- **Setup**: The `init` command finds agents on the machine, lists the files it will write, and asks for confirmation once.
- **Terminal Execution**: In your own terminal, run `~/.openqodex/bin/openqodex review`.
- **Sandbox Limitation**: In its default sandbox, Codex gives commands no network, so the terminal command must be run outside the sandbox.
- **Scope**: The review covers commits not yet pushed plus everything uncommitted.
- **Output**: The tool prints a receipt with the verdict, one line per finding, and the path to `report.html`. It also writes `report.md`, `report.json`, and `report.sarif`.

## 🚀 Availability
- Works in Claude Code, Codex, Cursor, Cline, and Goose.
- The host identifier can be `claude-code`, `codex`, `cursor`, `cline`, or `goose`.
- An `npx` install does not put OpenQodex on the system PATH.
- The reviewer was tested with Claude Code 2.1.330 using claude-opus-5-5.

#OpenQodex #CodeReview #AIagents #ClaudeCode #OpenSource

---

*Source: [openqodex/openqodex](https://github.com/openqodex/openqodex)*
