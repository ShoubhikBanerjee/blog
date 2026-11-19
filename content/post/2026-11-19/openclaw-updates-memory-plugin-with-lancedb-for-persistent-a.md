---
title: "OpenClaw Updates Memory Plugin with LanceDB for Persistent AI Context"
slug: "openclaw-updates-memory-plugin-with-lancedb-for-persistent-ai-context"
description: "OpenClaw has released an update to its memory plugin, now enhanced with LanceDB for persistent, cross-session memory capabilities."
date: 2026-11-19T12:23:35+05:30
tags: [O, p, e, n, C, l, a, w, A, I, A, g, e, n, t, s, M, e, m, o, r, y, M, a, n, a, g, e, m, e, n, t, L, a, n, c, e, D, B]
categories: ["AI", "A", "I", "A", "g", "e", "n", "t", "s", ",", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "V", "e", "c", "t", "o", "r", "D", "a", "t", "a", "b", "a", "s", "e", "s", ",", "S", "o", "f", "t", "w", "a", "r", "e", "D", "e", "v", "e", "l", "o", "p", "m", "e", "n", "t"]
image: "https://avatars.githubusercontent.com/u/266910790?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# OpenClaw Updates Memory Plugin with LanceDB for Persistent AI Context

OpenClaw has released an update to its memory plugin, now enhanced with LanceDB for persistent, cross-session memory capabilities.

## 🔍 Overview

The plugin provides a brain that remembers across sessions, agents, and time. It stores preferences, decisions, and project context.

## 🧩 How it works

*   **Classification:** LLM-powered 6-category classification (profiles, preferences, entities, events, cases, patterns).
*   **Retention:** Weibull decay model ensures important memories stay while noise fades.
*   **Retrieval:** Hybrid Retrieval (Vector + BM25) fused with Cross-Encoder Reranking.
*   **Automation:** Relevant memories automatically surface before each reply.

## ⚙️ Key details

*   **Version:** v1.1.0-beta.10.
*   **Architecture:** Fully adapted for OpenClaw 2026.3+ new plugin architecture.
*   **Hooks:** Uses `before_prompt_build` hooks (replacing deprecated `before_agent_start`).
*   **Isolation:** Per-agent, per-user, and per-project memory boundaries.
*   **CPU Requirement:** CPU must support AVX instructions.
*   **Compatibility:** LanceDB native vector search may require AVX2 on some Linux x64 builds and can crash AVX-only CPUs with SIGILL.

## 🚀 Availability

*   **Installation:** Run `npm i memory-lancedb-pro@beta`.
*   **Setup:** Use the community-maintained setup script.
*   **Configuration:** Add the plugin's install directory as an absolute path in `plugins.load.paths` in `openclaw.json`.
*   **Post-Upgrade:** Run `openclaw doctor --fix` after upgrading.
*   **API:** Supports OpenAI, Jina, Gemini, Ollama, or any OpenAI-compatible API.
*   **Fallback:** Set `retrieval.disableNativeCosine: true` or `MEMORY_LANCEDB_DISABLE_NATIVE_COSINE=1` to use a scoped row scan plus JavaScript cosine ranking.

#O #p #e #n #C #l #a #w #, # #A #I # #A #g #e #n #t #s #, # #M #e #m #o #r #y # #M #a #n #a #g #e #m #e #n #t #, # #L #a #n #c #e #D #B

---

*Source: [CortexReach/memory-lancedb-pro](https://github.com/CortexReach/memory-lancedb-pro)*
