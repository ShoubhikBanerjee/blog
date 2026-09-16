---
title: "Launch of Trajectory for Normalizing AI Agent Transcripts"
slug: "launch-of-trajectory-for-normalizing-ai-agent-transcripts"
description: "A new development called `trajectory` has been released to normalize agent transcripts from various runtimes into a single validated, model-ready record format."
date: 2026-09-17T00:45:10+05:30
tags: [AIagents, TypeScript, Python, MachineLearning]
categories: ["AI", "AI Agents", "Software Development", "Data Normalization"]
image: "https://avatars.githubusercontent.com/u/177780362?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Launch of Trajectory for Normalizing AI Agent Transcripts

A new development called `trajectory` has been released to normalize agent transcripts from various runtimes into a single validated, model-ready record format.

## 🔍 Overview
`trajectory` provides a TypeScript API that converts different transcript formats into deterministic, structured records. These records are designed for use in training, evaluation, analysis, and inference.

## 🧩 How it works
The caller provides a transcript string and its source. The process involves the following:

* **Normalization**: `normalizeTranscript()` handles the conversion and does not touch the filesystem.
* **Data Structure**: A trajectory consists of an ordered array starting with a `meta` record that identifies the source and available session metadata. Every conversational record includes an ISO timestamp.
* **Output**: The result includes `records` containing the normalized trajectory and `diagnostics`, which is empty if no recoverable cleanup was required.
* **Tooling**: Tool result records may include an `ok: boolean` if the source provides an authoritative structured outcome.
* **Session Discovery**: `listTrajectories()` enumerates sessions in a source's standard local store, newest first, using cursor pagination.

## ⚙️ Key details
`trajectory` supports a wide range of input sources:

| Source | Format/Detail |
| :--- | :--- |
| `atif` | ATIF-v1.0 through ATIF-v1.7 whole-trajectory JSON |
| `claude-code` | Native Claude Code JSONL |
| `codex` | Native Codex rollout JSONL |
| `copilot-cli` | Native GitHub Copilot CLI event JSONL |
| `cursor` | Cursor role/message content-block JSONL capture |
| `droid` | Native Droid session JSONL |
| `gemini-cli` | Native Gemini CLI whole-session JSON |
| `hermes` | Session-store message-row array or a `{ "session": {...}, "messages": [...] }` envelope |
| `letta-code` | Letta Code client `transcript.jsonl` |
| `omp` | Native OMP (Oh My Pi) coding-agent session JSONL (pi-agent session format) |
| `openclaw` | Native OpenClaw session JSONL (pi-agent session format) |
| `opencode` | Native OpenCode `{ "info": ..., "messages": [...] }` session JSON |
| `openhands` | JSON event array or an events-API `{ "items": [...] }` envelope |
| `pi` | Native pi-coding-agent session JSONL |
| `deepagents` | Deep Agents CLI LangGraph SQLite store plus `threadId` |

Note: ATIF, Copilot CLI, Cursor, Gemini CLI, and OpenCode are export-only input contracts and return `listing_unavailable`.

## 🚀 Availability
The tool is available via the following packages:

* **TypeScript**: Published as `@letta-ai/trajectory`
* **Python**: Published as `agent-trajectory` (imported as `trajectory`)

For Deep Agents, `normalizeCheckpoint` reads sessions from its local LangGraph SQLite store by thread ID.

#AIagents #TypeScript #Python #MachineLearning

---

*Source: [letta-ai/trajectory](https://github.com/letta-ai/trajectory)*
