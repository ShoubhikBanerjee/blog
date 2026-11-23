---
title: "Specular Uses AI Agents to Find Deep Bugs in Concurrent and Distributed Systems"
slug: "specular-uses-ai-agents-to-find-deep-bugs-in-concurrent-and-distributed-systems"
description: "Specular (formerly Specula) is a tool that uses coding agents to find deep bugs in concurrent and distributed system code. It employs AI coding agents to write TLA+ specifications of target systems,..."
date: 2026-11-23T22:18:20+05:30
tags: []
categories: ["AI"]
image: "https://avatars.githubusercontent.com/u/218440141?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Specular Uses AI Agents to Find Deep Bugs in Concurrent and Distributed Systems

Specular (formerly Specula) is a tool that uses coding agents to find deep bugs in concurrent and distributed system code. It employs AI coding agents to write TLA+ specifications of target systems, including invariants that capture correctness properties and formal models describing system implementations. The tool then model-checks these specifications and reproduces violations at the code level. Specular has been used to find bugs in many open-source projects, and a list of found bugs is maintained. Case-study reports, models, and reproduction evidence are available in an archive, with a `case-studies` submodule that pins this archive and its system and run indexes.

## 🧩 How it Works

Specular automates the process of finding subtle bugs in complex systems:

- Coding agents read code and infer invariants
- Agents write TLA+ specifications that model the system
- Model-checking is performed on the specifications
- Violations are reproduced directly at the code level

## ⚙️ Key Details

Specular requires specific development environments:

| Environment | Requirement |
|-------------|-------------|
| Python | 3.10+ with pip |
| Java | 21+ with Maven |

System requirements are substantial:

- At least 32 GB of RAM (more is preferable)
- 100 GB of free disk space
- GitHub CLI (`gh`) installed

Supported coding agents include:

- Claude Code
- Codex
- Copilot CLI
- OpenCode
- Pi

## 🚀 Availability

Installation and setup:

```
uv tool install -e .   # installs the `specular` command
 specular setup          # installs the agent skills and MCP tools
```

Configuration requires adding MCP tools to agent config:

- `trace_debugger`
- `spec_analyzer`
- `inv_checking_tool`

The `spec_analyzer` MCP tool requires building the CFA tool with Maven first. Automatic MCP configuration is skipped for older Copilot CLI versions, so upgrading to the latest version is recommended.

## 💡 Why It Matters

Specular's approach is significant because it can find deep bugs that traditional testing often misses. By using formal methods (TLA+ specifications and model checking), it can verify correctness properties that are difficult to test empirically. The bugs found span many open-source projects, demonstrating the practical value of this AI-assisted formal verification approach. The workflow starts with exploring outputs in `runs/<run-id>`, beginning with `runs/latest/pipeline-summary.md` after each run.

Optional configuration through `mysys-guidance.md` helps focus on target modules and scenarios with consistent modeling scope across runs.

---

*Source: [specular-org/Specular](https://github.com/specular-org/Specular)*
