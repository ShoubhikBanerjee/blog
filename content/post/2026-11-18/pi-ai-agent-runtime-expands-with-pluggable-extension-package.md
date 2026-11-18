---
title: "Pi AI-agent Runtime Expands with Pluggable Extension Packages"
slug: "pi-ai-agent-runtime-expands-with-pluggable-extension-packages"
description: "Pi AI-agent runtime now supports pluggable extension packages that expose LLM-callable tools via MCP, covering workspace integrations, automation, memory, scheduling, and more. These packages enable..."
date: 2026-11-18T22:09:17+05:30
tags: [AIagents, TypeScript, MCP, LLM, Automation, Plugins]
categories: ["AI", "AI Agents", "Software Development", "Machine Learning", "Productivity"]
image: "https://avatars.githubusercontent.com/u/271512104?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Pi AI-agent Runtime Expands with Pluggable Extension Packages

Pi AI-agent runtime now supports pluggable extension packages that expose LLM-callable tools via MCP, covering workspace integrations, automation, memory, scheduling, and more. These packages enable developers to build composable AI agents using shared TypeScript libraries.

## 🧩 Available Extensions

The following extension packages are available under the `@amaster.ai` npm scope:

| Package | Purpose |
|---------|---------|
| `@amaster.ai/pi-browser-use` | Browser automation via chrome-devtools-mcp |
| `@amaster.ai/pi-attachments` | Attachment normalization, upload handling, document parsing |
| `@amaster.ai/pi-telemetry` | Runtime traces, TTFT, token/cost accounting |
| `@amaster.ai/pi-task-scheduler` | Cron-based scheduled task management |
| `@amaster.ai/pi-goal` | Goal derivation and agent condition monitoring |
| `@amaster.ai/pi-web-access` | Web search, URL extraction, image search |
| `@amaster.ai/pi-computer-use` | Cross-platform desktop automation |
| `@amaster.ai/pi-channels` | Feishu, WeCom, and webhook messaging |
| `@amaster.ai/pi-memory` | Persistent curated memory injection |
| `@amaster.ai/pi-security` | Resource-aware security policy engine |
| `@amaster.ai/pi-teamwork` | Team collaboration and issue management |
| `@amaster.ai/pi-image-gen` | Image generation via multiple providers |
| `@amaster.ai/pi-video-gen` | Video model clips and batch rendering |
| `@amaster.ai/pi-lark` | Lark/Feishu workspace integration |
| `@amaster.ai/pi-wecom` | WeCom workspace integration |
| `@amaster.ai/pi-dingtalk` | DingTalk workspace integration |

## ⚙️ Core Packages

| Package | Purpose |
|---------|---------|
| `@amaster.ai/pi-shared` | Shared runtime types and contracts |
| `@amaster.ai/pi-storage` | JSON-file and MySQL/Prisma persistence adapters |

## 🚀 Key Capabilities

- Each extension exposes LLM-callable tools via MCP
- Host applications provide HTTP routing, authentication, and product-specific UI
- Packages are ESM-only and composable
- On Pi 0.99+, video, teamwork, and memory tools expose bounded structured results
- Scripts can consume IDs, memory entries, media paths, and QC metadata
- Extension packages declare their entry point in the `pi.extensions` field of `package.json`

#AIagents #TypeScript #MCP #LLM #Automation #Plugins

---

*Source: [TGYD-helige/pi](https://github.com/TGYD-helige/pi)*
