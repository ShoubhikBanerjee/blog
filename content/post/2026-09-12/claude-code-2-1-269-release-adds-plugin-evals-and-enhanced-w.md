---
title: "Claude Code 2.1.269 Release Adds Plugin Evals and Enhanced Workflow Controls"
slug: "claude-code-2-1-269-release-adds-plugin-evals-and-enhanced-workflow-controls"
description: "Claude Code has released version 2.1.269, a broad update introducing plugin evaluation tools, output-style switching, and expanded telemetry and workflow controls across CLI, VS Code, web, and Slack..."
date: 2026-09-12T18:03:09+05:30
tags: [ClaudeCode, AI, DeveloperTools, CLI]
categories: ["AI", "AI Development", "Software Engineering", "Developer Experience"]
author: "Shoubhik Banerjee"
draft: false
---

# Claude Code 2.1.269 Release Adds Plugin Evals and Enhanced Workflow Controls

Claude Code has released version 2.1.269, a broad update introducing plugin evaluation tools, output-style switching, and expanded telemetry and workflow controls across CLI, VS Code, web, and Slack experiences.

## ⚙️ Key Details

### New Features
- **Claude Plugin Eval**: A tool to run a plugin's eval suite against Claude Code to receive scored, reproducible results in JSON and HTML report formats.
- **Output-Style Switching**: The `/output-style [name]` command allows users to list and switch output styles, including within cloud, headless sessions, and via Remote Control.
- **Workflow and Telemetry Enhancements**:
    - Added `CLAUDE_CODE_WORKFLOW_MAX_CONCURRENT_AGENTS` (range 1–256) to increase the concurrent agent limit for inference-bound fan-outs in the Workflow tool.
    - Added `OTEL_METRICS_INCLUDE_REPOSITORY` to tag OpenTelemetry metrics and events with `vcs.*` repository attributes.
    - Added `CLAUDE_CODE_GATEWAY_MODEL_DISCOVERY_TIMEOUT_MS` to extend the LLM gateway discovery timeout (default 3s).
- **UI and Tooling Updates**:
    - A new spinner tip suggests using `/focus` for a view featuring only the prompt, a one-line work summary, and the response.
    - Bash tool results now include a diff of files changed when `bashEditDiffEnabled` is set.

### Fixed Issues

| Area | Fix Description |
| :--- | :--- |
| **Prompt Cache** | Fixed partial invalidation after responses were cut off at output-token limits and fixed context re-sending issues after interruptions. |
| **Terminal** | Resolved issues with F1/F2/F4 in kitty-protocol, Delete in st, Alt+arrows in rxvt-unicode, and Shift+punctuation in WezTerm. |
| **Plugins** | Fixed synced MCP servers not connecting on remote session resume and ensured LSP servers (e.g., rust-analyzer) receive an exit signal even if shutdown fails. |
| **Sessions** | Fixed headless sessions losing replies during model switches or retries, and resolved reports of "waiting for your input" while background agents were active. |
| **General** | Fixed CMYK JPEG decoding failures and restored prompt suggestions for languages without spaces (e.g., Japanese, Chinese, Thai). |

#ClaudeCode #AI #DeveloperTools #CLI

---

*Source: [Anthropic Release Notes](https://releasebot.io/updates/anthropic)*
