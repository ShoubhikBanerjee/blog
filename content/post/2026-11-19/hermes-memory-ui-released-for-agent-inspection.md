---
title: "Hermes Memory UI Released for Agent Inspection"
slug: "hermes-memory-ui-released-for-agent-inspection"
description: "The Read-only Hermes Agent plugin has been introduced for inspecting memory in the Hermes Dashboard and Hermes Desktop, providing a unified Python backend API alongside separate delivery artifacts."
date: 2026-11-19T22:12:49+05:30
tags: [HermesAgent, AIPlugins, MemoryManagement, DeveloperTools]
categories: ["AI", "AI Agents", "Developer Tools", "Software Updates"]
image: "https://avatars.githubusercontent.com/u/20925002?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Hermes Memory UI Released for Agent Inspection

The Read-only Hermes Agent plugin has been introduced for inspecting memory in the Hermes Dashboard and Hermes Desktop, providing a unified Python backend API alongside separate delivery artifacts.

## 🔍 Overview
- Read-only Hermes Agent plugin for inspecting memory in Hermes Dashboard and Hermes Desktop.
- The Dashboard and Desktop interfaces are separate delivery artifacts sharing only the profile-aware Python backend API.
- The plugin is intentionally read-only and does not add, edit, replace, or remove memories.
- Writes must go through Hermes' memory and fact_store tools or provider classes to preserve validation, locking, mirroring, FTS, HRR vectors, and memory-bank maintenance.

## 🧩 Supported Memory Sources
| Memory Source | Description / Capabilities |
| --- | --- |
| Built-in memory (`MEMORY.md`, `USER.md`) | Agent notes, environment facts, project conventions, user profile, and preferences. Works always. |
| Session search | Explicit read-only search over previous Hermes sessions via session_search tool, with optional source/type filters (CLI, Telegram, cron, Discord, web, API). |
| Holographic memory | Local SQLite fact store at `$HERMES_HOME/memory_store.db` tracking facts, categories, trust scores, retrieval counters, and timestamps. |
| Mem0 memory | Read-only Mem0 Platform memories via provider config, including scopes, scores, timestamps, and metadata. |
| Honcho memory | Read-only Honcho workspace, host, peer, and provider configuration state with user/AI peer cards, representations, conclusions, and context search. |
| Mnemosyne memory | Read-only local SQLite store inspection for episodes, facts, instructions, gists, and graph rows, with explicit recall and injected-context preview. |
| Hindsight memory | Read-only/query-only Hindsight provider configuration state with explicit recall and reflect actions, and contents view for memory units and retained source documents. |
| ByteRover memory | Read-only ByteRover CLI (brv) project status and registered locations, supporting explicit BM25 search and optional query/synthesis action. |

## ⚙️ Key Technical Details
- Built-in memory view works always, while external memory provider sections show only when configured.
- Dashboard is a web plugin with its own manifest, tracked browser bundle, and stylesheet (`dashboard/`).
- Desktop plugin (`desktop/plugin.js`) is a standalone, uncompiled ESM disk plugin importing only the Hermes Desktop SDK, React, and the JSX runtime without requiring an npm build.
- The Desktop plugin registers the `/memory` full-page route, a Memory sidebar item, and an Open Memory command-palette action.
- Desktop requests use the plugin-scoped, profile-aware `ctx.rest` client reaching the same `/api/plugins/hermes-memory-ui/` backend used by Dashboard.
- The regular plugin must be installed and present in `plugins.enabled` so Hermes mounts `dashboard/plugin_api.py`.

## 🚀 Installation and Availability
- Default profile lives at `~/.hermes`, while a named profile lives at `~/.hermes/profiles/<name>` (use `hermes -p <name>` and set `HERMES_HOME="$HOME/.hermes/profiles/<name>"`).
- Install directly from GitHub: `hermes plugins install xraysight/hermes-memory-ui --enable`.
- To enable the Hermes Desktop interface, copy the disk plugin to `$HERMES_HOME/desktop-plugins/hermes-memory-ui/plugin.js`.
- Hermes Desktop inventories the UI separately under Settings → Plugins.
- Update existing installation using `hermes plugins update hermes-memory-ui`.

#HermesAgent #AIPlugins #MemoryManagement #DeveloperTools

---

*Source: [xraysight/hermes-memory-ui](https://github.com/xraysight/hermes-memory-ui)*
