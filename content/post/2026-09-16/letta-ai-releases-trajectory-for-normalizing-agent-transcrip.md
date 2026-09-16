---
title: "Letta AI Releases Trajectory for Normalizing Agent Transcripts into Unified Records"
slug: "letta-ai-releases-trajectory-for-normalizing-agent-transcripts-into-unified-records"
description: "Letta AI has introduced `trajectory`, a tool designed to convert agent transcripts from various incompatible runtimes into a single, validated, model-ready record format. This development provides a..."
date: 2026-09-16T22:05:42+05:30
tags: [AIagents, TypeScript, Python, MachineLearning, SoftwareDevelopment]
categories: ["AI", "AI Agents", "Machine Learning", "Software Development"]
image: "https://avatars.githubusercontent.com/u/177780362?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Letta AI Releases Trajectory for Normalizing Agent Transcripts into Unified Records

Letta AI has introduced `trajectory`, a tool designed to convert agent transcripts from various incompatible runtimes into a single, validated, model-ready record format. This development provides a unified TypeScript API and Python wrapper to transform reasoning, tool calls, and messages into deterministic structures for training, evaluation, and inference.

## 🔍 Overview

Agent tools currently represent core concepts—such as messages, reasoning, and tool results—in incompatible native formats. `trajectory` provides a standardized interface to turn these formats into structured records designed to be consumed by agents for memory formation, dreaming, and search.

*   **TypeScript Package:** Published as `@letta-ai/trajectory`.
*   **Python Wrapper:** Published as `agent-trajectory` (imports as `trajectory`).
*   **Validation:** The complete contract is available as runtime validation and via `schema/trajectory-v1.schema.json`.

## 🧩 How it works

The system operates by taking a transcript string and its source from the caller. While the core normalization function, `normalizeTranscript()`, does not touch the filesystem, a separate discovery layer called `listTrajectories()` can enumerate sessions in a source's standard local store using newest-first cursor pagination.

Normalization produces an object containing two main fields:
*   `records`: The normalized trajectory data.
*   `diagnostics`: A field that is empty if the transcript required no recoverable cleanup.

Each source adapter is maintained in its own folder under `src/adapters/`, containing a README that documents exact input contracts, decoding behaviors, and any data the adapter drops.

## ⚙️ Key details

A normalized trajectory is structured as an ordered array containing several specific record types. Every conversational record includes an ISO timestamp.

| Record Type | Description |
| :--- | :--- |
| `meta` | A leading record identifying the source and available session metadata. |
| `user` / `assistant` | Standard prose records for conversation participants. |
| `reasoning` | Optional records included when the source exposes reasoning data. |
| `assistant tool-call` | Records with stable IDs and stringified JSON-object arguments. |
| `tool` | Records linked to earlier calls by `tool_call_id`. |
| `observation` | Generic records for environment feedback not attributed to a specific tool call, such as merged terminal output. |
| `system` | Optional records included only when `filters.systemMessages` is set to `"include"`. |

Tool result records may include an `ok: boolean` field if the source exposes an authoritative structured outcome. This field is omitted when a reliable status is not available, as the system never interprets result text as success or failure.

| Source | Authoritative Outcome Field |
| :--- | :--- |
| Pi/OpenClaw | `isError` |
| Claude Code | `is_error` |
| Letta Code | `resultOk` |
| OpenHands / Cursor | `is_error` |
| OpenCode / Gemini | terminal state |
| Copilot CLI | `success` |

## 🚀 Availability

The tool supports various input sources with different access methods. For Deep Agents, `normalizeCheckpoint` reads sessions directly from a local LangGraph SQLite store by thread ID. Other sources, including ATIF, Copilot CLI, Cursor, Gemini CLI, and OpenCode, use export-only input contracts where the caller must locate and read the exports themselves.

#AIagents #TypeScript #Python #MachineLearning #SoftwareDevelopment

---

*Source: [letta-ai/trajectory](https://github.com/letta-ai/trajectory)*
