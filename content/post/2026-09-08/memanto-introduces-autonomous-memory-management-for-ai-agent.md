---
title: "Memanto introduces autonomous memory management for AI agent fleets"
description: "Memanto, a companion Memory Agent, runs alongside a fleet of AI agents to manage their memories automatically."
date: 2026-09-09T00:16:34+05:30
tags: [AIAgents, MemoryManagement, OpenKnowledgeFormat]
categories: ["Artificial Intelligence", "AI Agents", "Machine Learning", "Software Tools"]
image: "https://avatars.githubusercontent.com/u/220075209?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Memanto introduces autonomous memory management for AI agent fleets

Memanto, a companion Memory Agent, runs alongside a fleet of AI agents to manage their memories automatically.

## 🔍 Overview
- A second agent that runs beside your fleet and performs six autonomous actions.
- No library calls, no wrapper, no code changes required.
- Supports macOS, Linux, and Windows.

## 🧩 How it works
- **Stream watching** – Memanto watches the interaction streams of the agents it serves and pulls durable knowledge out of ephemeral traffic (decisions, preferences, facts, failures).
- **Canonical estate** – Extracted memories are merged into one canonical estate where duplicates collapse, fragments join, and repeated observations strengthen confidence.
- **Contradiction handling** – When new knowledge contradicts old, Memanto supersedes the old entry while preserving the prior belief and its timestamp.
- **Managed forgetting** – Decay, expiry, and deliberate deletion are policies Memanto executes, preventing the estate from becoming noisy.
- **Pre‑action briefing** – Before an agent acts, Memanto hands it the minimal relevant slice of the estate.
- **Cross‑framework sharing** – Through the Open Knowledge Format the estate crosses frameworks and vendors, letting agents such as Claude Code, Cursor, and custom stacks share one memory instead of five silos.
- **Daily loop** – Each day new memories are curated, duplicates merged across agents, and contradictions flagged for review.

## ⚙️ Key details
- **Features**
  - Runs as a separate agent alongside your fleet.
  - Watches interaction streams and extracts durable knowledge.
  - Merges memories into a single estate, collapsing duplicates and joining fragments.
  - Supersedes contradictory knowledge while preserving history.
  - Executes decay, expiry, and deletion policies automatically.
  - Provides a minimal relevant memory slice to agents before they act.
  - Shares the estate across different frameworks via the Open Knowledge Format.
  - Daily curation loop with duplicate merging and contradiction flagging.
  - Local UI dashboard (`memanto ui`) to browse, search, and audit the estate.
  - Exportable estate as plain Markdown (`memanto memory export --okf`).
  - Migration support for Mem0, Letta, Supermemory, or any OKF bundle.
  - No code changes, no wrapper, no rewrite of the agent loop.
  - Available on macOS, Linux, and Windows.

- **Command reference**
| Command | Purpose |
|---|---|
| `memanto connect <agent>` | Connects Memanto to an agent (e.g., claude-code, cursor, codex, windsurf, cline, goose, copilot) |
| `memanto recall "deployment policy" --as-of 2026-08-05` | Retrieves a memory snapshot as of a specific date |
| `memanto recall "deployment policy" --changed-since v2.1` | Retrieves changes since a given version |
| `memanto ui` | Opens a local dashboard to browse, search, and audit the whole estate |
| `memanto memory export --okf` | Exports the estate in Open Knowledge Format (plain Markdown, readable, diffable, committable, greppable) |
| `memanto migrate` | Imports from or exports to Mem0, Letta, Supermemory, or any OKF bundle |

## 🚀 Availability
- Install with `pip install memanto`.
- Runs on macOS, Linux, and Windows.

## 💡 Why it matters
- Agents share one managed memory estate, eliminating siloed silos.
- Managed forgetting keeps recall sharp even after a year of operation.
- Daily automated curation means the fleet knows more than it did yesterday without manual sorting.
- The Open Knowledge Format makes the estate portable, version‑controlled, and human‑readable.


#AIAgents #MemoryManagement #OpenKnowledgeFormat

---

*Source: [moorcheh-ai/memanto](https://github.com/moorcheh-ai/memanto)*
