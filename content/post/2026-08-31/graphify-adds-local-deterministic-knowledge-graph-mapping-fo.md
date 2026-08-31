---
title: "Graphify adds local, deterministic knowledge-graph mapping for codebases"
description: "A new tool called Graphify lets developers turn an entire codebase and its associated documentation into a locally‑generated, queryable knowledge graph."
date: 2026-08-31T18:32:11+05:30
tags: [graphify, knowledgegraph, localAI, devtools, AIcoding]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/297659074?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Graphify adds local, deterministic knowledge-graph mapping for codebases

A new tool called Graphify lets developers turn an entire codebase and its associated documentation into a locally‑generated, queryable knowledge graph.

## 🔍 Overview
- Turn any codebase, with its docs, SQL schemas, configs, and PDFs, into a queryable knowledge graph.
- Provides a `/graphify` skill for Claude Code, Cursor, Codex, and Gemini CLI.
- Generates the graph on demand instead of grepping through files.

## 🧩 How it works
- Code is parsed with **tree‑sitter AST** – deterministic, no LLM, nothing leaves the machine.
- Docs, PDFs, images, and video are processed with the assistant’s model or a configured API key for a semantic pass.
- Every edge in the graph is explained and tagged:
  - `EXTRACTED` – explicit in the source.
  - `INFERRED` – resolved by Graphify.
- The result is a real graph, not a vector index; there are no embeddings or vector stores.

## ⚙️ Features
- **Fully local**: code maps for free, with no data leaving the machine.
- **Deterministic parsing** via AST ensures reproducible results.
- **Edge transparency**: each connection is labeled as extracted or inferred.
- **Queryability**: ask a question, trace the path between two things, or request an explanation of a concept.
- **Output files** after running `/graphify`:
  - `graph.html` – interactive view; click nodes, filter, search.
  - `GRAPH_REPORT.md` – highlights key concepts, surprising connections, suggested questions.
  - `graph.json` – full graph for any downstream queries.

## 🚀 Availability
- Early access is open before the public v1 launch at **app.graphify.com**.
- An always‑on background version is being built at **graphify.com**; early access also at **app.graphify.com**.
- Install the CLI:
  ```
  uv tool install graphifyy   # or: pipx install graphifyy
  ```
- Register the skill with your AI assistant:
  ```
  graphify install
  ```
- Run the skill inside the assistant:
  ```
  /graphify
  ```
- The FastAPI codebase has been successfully mapped by Graphify, showing nodes as concepts, colors as detected communities, and full clickability in `graph.html`.

## 📦 Compatibility
| Assistant | Integration |
|-----------|-------------|
| Claude Code | /graphify skill |
| Cursor | /graphify skill |
| Codex | /graphify skill |
| Gemini CLI | /graphify skill |


#graphify #knowledgegraph #localAI #devtools #AIcoding

---

*Source: [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify)*
