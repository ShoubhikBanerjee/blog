---
title: "Update on Deja-Vu: Local Memory and Cross-Agent Handoff for 48 Coding Agents"
slug: "update-on-deja-vu-local-memory-and-cross-agent-handoff-for-48-coding-agents"
description: "Deja-vu (deja) has received new updates providing local memory, session search, and cross-agent handoff across 48 coding agents including Claude Code, Codex, Cursor, OpenCode, Gemini CLI, OpenClaw,..."
date: 2026-11-18T12:19:35+05:30
tags: [AIagents, ClaudeCode, Go, DeveloperTools, Memory]
categories: ["AI", "Software Development", "Artificial Intelligence", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/99616188?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Update on Deja-Vu: Local Memory and Cross-Agent Handoff for 48 Coding Agents

Deja-vu (deja) has received new updates providing local memory, session search, and cross-agent handoff across 48 coding agents including Claude Code, Codex, Cursor, OpenCode, Gemini CLI, OpenClaw, and Hermes.

## 🔍 Overview
- Supports 48 coding agents that already save every session to disk.
- Built as a single Go binary featuring 7 hooks and MCP.
- Indexes all session data locally with zero LLM calls, achieving a 0.7 ms in-process lookup and a ~4% index footprint.
- Achieves a recall of 97.2% R@5 on LongMemEval-S.

## 🧩 Features and Commands
- Interactive terminal search: Running `deja` with no arguments opens a search across every agent's history, prioritizing sessions behind uncommitted changes and recent work in the current project.
- Navigation: Use up and down arrows to pick a session, enter to open at the match, forward slash to search inside a session, square brackets to jump between turns, and Control-s to toggle date or relevance sort (`deja search --sort date`).
- Filtering: Filter by agent (e.g., `codex:`), time (today, yesterday, week, month), or project (`in:<project>`).
- Session management: Press `r` to reopen a session in its native agent, or `o` to continue it in another agent with its goal, decisions, and open work.
- Recover deleted chats: Tab switches between the current project, all projects, and Deleted sessions.
- Command-line tools:
  - `deja "jwt refresh token"`: Lexical plus structural search across all 48 agent stores.
  - `deja handoff --to codex`: Continue the active session's goal and state in another agent.
  - `deja restore internal/auth/jwt.go`: Recover code an agent overwrote before git commit.
  - `deja blame internal/auth/jwt.go:42`: Trace which agent session wrote or replaced a line.
  - `deja audit`: Check retention risk, purged chats, and index health across all 48 stores.

## ⚙️ Performance Benchmarks
- Recall: 97.2% LongMemEval-S (compared to MemPalace at 96.6% and agentmemory at 95.2%).
- Token usage: Uses half the tokens of agentmemory on a task the machine had already solved.
- Speed: Indexing and lookup take 13.6 seconds and 0.7 ms lookup across 19,195 sessions (next of 7 tools took 72 seconds).

## 🚀 Availability
- Node.js / npm: `npx @vshulcz/deja-vu install --auto` (1-step cross-platform install and wire installed agents).
- Shell script: `curl -fsSL https://raw.githubusercontent.com/vshulcz/deja-vu/main/install.sh | sh && deja install --auto`.
- Homebrew: `brew install deja-vu && deja install --auto`.

#AIagents #ClaudeCode #Go #DeveloperTools #Memory

---

*Source: [vshulcz/deja-vu](https://github.com/vshulcz/deja-vu)*
