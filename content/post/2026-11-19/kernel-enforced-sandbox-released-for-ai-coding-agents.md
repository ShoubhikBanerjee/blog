---
title: "Kernel-Enforced Sandbox Released for AI Coding Agents"
slug: "kernel-enforced-sandbox-released-for-ai-coding-agents"
description: "An update has been released regarding cplt, a kernel-enforced sandbox designed for AI coding agents to prevent credential theft, unauthorized pushes to main, PR merges, and secret exfiltration."
date: 2026-11-19T22:12:49+05:30
tags: [AI, Security, DeveloperTools, AIAgents, Linux]
categories: ["AI", "Artificial Intelligence", "Software Development", "Security"]
image: "https://avatars.githubusercontent.com/u/11848947?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Kernel-Enforced Sandbox Released for AI Coding Agents

An update has been released regarding cplt, a kernel-enforced sandbox designed for AI coding agents to prevent credential theft, unauthorized pushes to main, PR merges, and secret exfiltration.

## 🔍 Overview

AI agents execute arbitrary code, and a compromised agent can read `~/.ssh`, push to main, merge PRs, or exfiltrate code unless the operating system prevents it. The cplt tool acts as a kernel-level sandbox and wrapper for various AI coding interfaces and shells.

## 🧩 How it works

The tool wraps multiple coding agents and shells to ensure that while the agent can write code, it cannot perform restricted destructive actions or access sensitive files. Every restriction applies to the agent and to every process it spawns.

- Runs Copilot CLI, Claude Code, OpenCode, Gemini CLI, Antigravity, Pi, goose, DeepSeek Harness, or a plain shell
- Deny by default for credentials, secrets, and sensitive files
- Command-level git and gh interception
- Outbound network filtering with an audit log
- Per-repo policy in `.cplt.toml`, committed to version control for tamper-proof auditing
- Zero-config start for developers with escape hatches

## ⚙️ Key details

Operating system support and isolation mechanisms vary by platform:

| Platform | Mechanism | Details |
| --- | --- | --- |
| macOS | Apple Seatbelt/SBPL via `sandbox-exec` | Supported |
| Linux | Landlock LSM + seccomp-BPF + optional Bubblewrap | Kernel 5.13+, full network filtering on 6.7+ |
| Windows | No native support | Run inside WSL2 (ordinary Linux install where Microsoft kernel ships Landlock) |

Additional configuration and usage commands include:
- `brew install navikt/tap/cplt` (macOS)
- `cplt --shell-install` to make 'copilot' run sandboxed persistently
- `cplt doctor` to check the environment
- `cplt -- -p "fix the tests"` to run Copilot in the sandbox
- `cplt config set git_guard.protect_default_branch_only false` to block every push instead of just main
- `cplt config set git_guard.mode warn` to observe instead of blocking

## 🚀 Availability

- Distributed as a single binary that runs on a locked-down laptop
- Installation available via Homebrew for macOS (`brew install navikt/tap/cplt`) and via apt for Debian or Ubuntu

#AI #Security #DeveloperTools #AIAgents #Linux

---

*Source: [navikt/cplt](https://github.com/navikt/cplt)*
