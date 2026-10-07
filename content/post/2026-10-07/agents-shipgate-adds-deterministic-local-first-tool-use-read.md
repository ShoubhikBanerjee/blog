---
title: "Agents Shipgate adds deterministic local‑first tool‑use readiness review"
slug: "agents-shipgate-adds-deterministic-localfirst-tooluse-readiness-review"
description: "Agents Shipgate is an open‑source CLI and GitHub Action that provides a deterministic merge gate for AI‑generated agent capability changes. It performs a local‑first, static Tool‑Use Readiness review..."
date: 2026-10-07T22:09:50+05:30
tags: [AIagents, ToolUseReadiness, OpenSource]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Software Development", "Security"]
image: "https://avatars.githubusercontent.com/u/230805254?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Agents Shipgate adds deterministic local‑first tool‑use readiness review

## 🔍 Overview
Agents Shipgate is an open‑source CLI and GitHub Action that provides a deterministic merge gate for AI‑generated agent capability changes. It performs a local‑first, static Tool‑Use Readiness review of a pull request before the agent receives production‑like permissions.

## 🧩 How it works
- The tool runs **locally** and **statically** – it does **not** execute the agent, make tool calls, invoke LLMs, or access the network.
- It scans a wide range of tool‑surface definitions (MCP, OpenAPI, SDKs, workflow artifacts, etc.) and produces a deterministic **Tool‑Use Readiness Report**.
- Using the `diff` command, it compares the PR branch with its merge base on the repository’s default branch (e.g., `origin/main`). One entry is printed per changed grant or replaced rule.
- If the PR targets a non‑default branch, the `--base` flag can be used (e.g., `--base origin/feature`).
- No manifest, policy, saved baseline, skill, or account is required, and nothing is written back to the repository.

## ⚙️ Key details
- **Open‑source** CLI + GitHub Action.
- Scans the following tool surfaces:
  
  | Tool Surface | Included in Scan |
  |--------------|-----------------|
  | MCP | ✅ |
  | OpenAPI | ✅ |
  | OpenAI Agents SDK | ✅ |
  | Anthropic Messages API | ✅ |
  | Google ADK | ✅ |
  | LangChain/LangGraph | ✅ |
  | CrewAI | ✅ |
  | OpenAI API | ✅ |
  | Codex repo config | ✅ |
  | Codex plugin | ✅ |
  | n8n | ✅ |
  | Conductor OSS workflow artifacts | ✅ |
- Shows source‑observed changes per agent, including before/after signatures and source locations, unless a specific `--scope` is provided.
- Supports comparison of OpenAI Agents SDK and Google ADK tool bindings **without** a manifest or baseline.
- Prints one entry per changed grant; static configuration reflects what files *permit*, not what the agent actually did.
- Provides a review question asking whether the declared capability changes are intended.

## 🚀 Availability
- The deterministic merge gate functionality is **new in version 1.2.0**.
- Install from PyPI into a clean virtual environment (e.g., `pipx install agents-shipgate`).
- Users of older releases need to upgrade with `pipx upgrade agents-shipgate`.
- Example usage in version 1.2.0 shows three changes from four rows, with three widening what the agent may do.

## 💡 Why it matters
Agents Shipgate lets developers see exactly **what capability changes** a coding‑agent PR introduces **before it merges**. Because the review is performed locally and without network access, teams can safely assess permission changes without executing the agent or contacting external services. This deterministic, static analysis helps enforce intentional tool‑use policies and reduces the risk of unintended privilege expansions.

#AIagents #ToolUseReadiness #OpenSource

---

*Source: [ThreeMoonsLab/agents-shipgate](https://github.com/ThreeMoonsLab/agents-shipgate)*
