---
title: "AutoMem Update: Persistent Memory and Benchmark Performance for AI Agents"
slug: "automem-update-persistent-memory-and-benchmark-performance-for-ai-agents"
description: "AutoMem has received an update introducing persistent memory for AI chat applications, combining a graph and vector index to maintain context across sessions."
date: 2026-11-19T06:12:23+05:30
tags: [AutoMem, AIagents, VectorDatabase, KnowledgeGraph, MemoryManagement]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Software Development"]
image: "https://avatars.githubusercontent.com/u/193913467?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AutoMem Update: Persistent Memory and Benchmark Performance for AI Agents

AutoMem has received an update introducing persistent memory for AI chat applications, combining a graph and vector index to maintain context across sessions.

## 🧩 How it works
- Combines two storage layers behind a single API to give AI a memory that survives the chat.
- FalkorDB stores memories as nodes with 11 typed relationships between them, serving as the canonical record.
- Qdrant stores an embedding for every memory.
- Uses embeddings from Voyage, OpenAI, or a local provider, with optional enrichment to add more structure over time.
- Vector matches find similarities while recording typed relationships between memories.
- Looks up memories directly through its graph and vector index to keep normal retrieval fast and avoid extra generative-LLM charges.

## ⚙️ Key details
- Exposes both Model Context Protocol (MCP) and a REST API.
- Local MCP bridge works with Claude Desktop, Cursor, Claude Code, Codex, Copilot, and more.
- Remote MCP connects the service to ChatGPT Developer Mode, Claude.ai, and ElevenLabs over HTTPS.
- Can be run locally with Docker, on your own infrastructure, or as a small Railway service group.

## 📊 Benchmark results
- On the independent Agent Memory Benchmark's BEAM long-context tests using local FastEmbed embeddings and a Gemini answerer and judge, AutoMem scored 57.4% at 10 million source tokens.
- Provided the answerer an average of only ~2.6–4.8k retrieved tokens.
- BEAM scores are a rubric mean (0, 0.5 or 1 per item), not pass/fail.
- AMB results are submitted and the provider PR is still under review, so they are not yet official on its leaderboard.
- The neutral third-party harness comes first in the benchmark table, followed by internal rows representing AutoMem's own engineering baselines.

## 💡 Why it matters
- Keeps memory useful as an agent's history grows by maintaining high efficiency in token retrieval.
- Ensures memory is not locked to one chat app.

#AutoMem #AIagents #VectorDatabase #KnowledgeGraph #MemoryManagement

---

*Source: [verygoodplugins/automem](https://github.com/verygoodplugins/automem)*
