---
title: "AI coding toolkit updates remove legacy DSH support and refine agent rules"
slug: "ai-coding-toolkit-updates-remove-legacy-dsh-support-and-refine-agent-rules"
description: "The professional-grade AI coding toolkit has released an update that removes support for the legacy DeepSeek Harness (DSH) code and refines how agent instructions are managed across multiple..."
date: 2026-11-18T22:09:17+05:30
tags: [AIcoding, Claude, DevTools, MLAgents, ReinforcementLearning]
categories: ["AI", "AI Development", "Machine Learning", "Developer Tools", "Software Engineering"]
image: "https://avatars.githubusercontent.com/u/24587195?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AI coding toolkit updates remove legacy DSH support and refine agent rules

The professional-grade AI coding toolkit has released an update that removes support for the legacy DeepSeek Harness (DSH) code and refines how agent instructions are managed across multiple platforms. This update introduces machine-enforced safety features, expands skill libraries, and adjusts how global and local installations interact with project-specific rules.

## 🔍 Overview

The toolkit now includes 116 skills and 44 agents, offering multi-platform support for tools such as Claude, Cursor, Windsurf, Copilot, Gemini, Cline, Roo Code, Aider, Augment, Antigravity, Codex CLI, and opencode. It features machine-enforced safety, lifecycle hooks, persona presets, opt-in plugin packs, and benchmark tooling. The update explicitly removes the last DeepSeek Harness (DSH) code (v5.4.0). Consequently, `ai-toolkit dsh` is now an unknown command, `--editors dsh` is an unknown editor, and the toolkit no longer migrates old DSH project skills or registry entries.

## 🧩 How it works

* **Security Auditing**: The `security-auditor` reviews source code, configurations, and dependencies, then verifies fixes with local checks.
* **Agent Instructions**: Project instructions reside in a committed `AGENTS.md` file, which `CLAUDE.md` imports. The `ai-toolkit adopt-agents-md` command moves existing `CLAUDE.md` content to `AGENTS.md`. This process ensures that nothing truncates the file, with Codex `project_doc_max_bytes` raised and 24,000-byte Antigravity warnings accounted for.
* **Rule Management**: A toolkit-generated `AGENTS.md` file (marked `# AI Toolkit Instructions`) is no longer imported, preventing Claude from loading rules from `~/.claude/rules/` twice. The `adopt-agents-md` command refuses to merge into this specific file. Agents other than Claude Code do not read that file.
* **Hooks and Triggers**: Hooks run from the `hooks.json` directory and gate only `run_command`. Workspace rules carry `trigger` frontmatter and are designed to fit Antigravity's size limits.
* **MCP Server Integration**: Injected servers, such as `rag-mcp`, are written to each `claude-switch` profile, similar to `mcp install`. The `remove-mcp` and `uninstall` commands clean these entries. Registered rules that require an MCP server only reach a file when its readers have that server; `rag-mcp-legal-rules` remains an opt-in feature.
* **Local vs. Global Installation**: `install --local` installs everything a client can load from `$HOME` before project files, using the recorded global profile. The `--no-global` flag opts out of this, and `update` preserves the profile.

## ⚙️ Key details

* **Model Support**: Skills and defaults reference Claude Haiku 5.5 and Sonnet 5.5, while the Codex reference includes GPT-6.1 Sol.
* **Language Scoping**: Language knowledge skills (e.g., `rust-rules`, `kotlin-patterns`) are scoped to languages used by registered projects. After running `ai-toolkit install --local` in at least one project, the global install turns off other languages' skills through `skillOverrides` in `~/.claude/settings.json` to prevent their descriptions from loading into every session.
* **Workflow Migration**: All 13 legacy workflows remain available alongside their skills. The Doctor tool checks the global `global_workflows` directory and provides migration instructions for specific clients.
* **Status Reporting**: Redirecting account status to a legacy-encoded pipe preserves readable progress bars and paths. A refused usage read displays `Unavailable: rate_limited, retry in 40m` from the provider's `Retry-After` header (`retry_after_seconds` in JSON), occurring once per account.
* **Requirements**: The toolkit requires Node.js >= 18 and Python >= 3.11. It will not run on `/usr/bin/python3` if it is Python 3.9.

## 💡 Why it matters

Claude Code automatically picks up the 116 skills, 44 agents, quality hooks, and the safety constitution. Global Claude MCP installs reach every `claude-switch` profile. This structure ensures that developers can maintain rigorous security standards and efficient agent behavior across a wide range of coding environments without manually managing redundant rule files or unsupported legacy commands.

## 🎮 Unity ML-Agents Documentation

The Unity Machine Learning Agents Toolkit (ML-Agents) is an open-source project that enables games and simulations to serve as environments for training intelligent agents using deep reinforcement learning and imitation learning. The ML-Agents package documentation serves as the primary resource, including installation instructions, version compatibility, features, tutorials, API references, and citation guidelines. For installation and setup issues or training discussions, users are directed to the Unity ML-Agents discussion forum. Other problems or feature requests should be submitted as GitHub issues. Further community resources and information regarding privacy and in-editor analytics are available on the ML-Agents package documentation home page.

#AIcoding #Claude #DevTools #MLAgents #ReinforcementLearning

---

*Source: [softspark/ai-toolkit](https://github.com/softspark/ai-toolkit)*
*Source: [Unity-Technologies/ml-agents](https://github.com/Unity-Technologies/ml-agents)*
