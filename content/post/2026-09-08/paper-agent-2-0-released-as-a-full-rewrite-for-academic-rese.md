---
title: "Paper-Agent 2.0 Released as a Full Rewrite for Academic Research"
description: "Paper-Agent is an intelligent paper retrieval and research tool designed for researchers and students. Version 2.0 is a complete rewrite of the 1.x version, upgrading the engineering implementation..."
date: 2026-09-09T00:16:34+05:30
tags: [PaperAgent, AIagents, AcademicResearch, LangGraph, NLP]
categories: ["AI Agents", "Academic Tools", "Software Development"]
image: "https://avatars.githubusercontent.com/u/94357205?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Paper-Agent 2.0 Released as a Full Rewrite for Academic Research

Paper-Agent is an intelligent paper retrieval and research tool designed for researchers and students. Version 2.0 is a complete rewrite of the 1.x version, upgrading the engineering implementation while maintaining a multi-agent core workflow of retrieval, reading, analysis, and writing.

## 🔍 Overview
Based on a multi-agent collaboration architecture (LangGraph), Paper-Agent uses natural language processing (NLP) and automated search to help users find academic papers, analyze literature, and conduct research. It is applicable to scenarios such as paper writing, academic research, and research project management.

## 🧩 How it works
The tool follows a structured pipeline to transform a research topic into a written document:

*   **Retrieval**: Automatically retrieves papers from arXiv, OpenAlex, and Semantic Scholar. It filters and removes duplicates based on themes, constraints, years, sources, and quantity.
*   **Reading**: Evaluates relevance via abstracts. Relevant papers are downloaded, converted from PDF to Markdown, chunked, extracted, and stored in a local vector database.
*   **Analysis**: The `AnalyseAgent` performs per-paper analysis by sub-topic followed by a global synthesis to identify research status, consensus, controversies, gaps, temporal evolution, and outlooks.
*   **Writing**: The `WritingOutlineAgent` generates an outline with evidence mapping, and the `WritingAgent` writes section-by-section, supplementing retrieval if evidence is insufficient and performing limited revisions after review.

## ⚙️ Key details
Paper-Agent 2.0 introduces several technical upgrades:

| Component | Implementation/Feature |
| :--- | :--- |
| Frontend | Vue 3 + TypeScript + Vite |
| Package Management | `uv` for Python dependency installation |
| Data Sources | arXiv, OpenAlex, Semantic Scholar |
| Persistence | SQLite + File System (prevents loss of history on refresh) |
| Progress Tracking | SSE (Server-Sent Events) for real-time workbench updates |
| Backend | Default listener at `127.0.0.1:8000` with auto-reload in dev mode |

Additional technical capabilities include:
*   Visual configuration of model Providers, Agent tiers, and embedding parameters in the browser.
*   Tracking of actual token usage across different model tiers used in various stages.
*   One-click connectivity testing for configured providers.

## 🚀 Availability
Users with a Python 3.12 virtual environment can set up the tool using `uv sync` and `npm run front:install`. API documentation is available at `http://127.0.0.1:8000/docs`.

#PaperAgent #AIagents #AcademicResearch #LangGraph #NLP

---

*Source: [Tswoen/Paper-Agent](https://github.com/Tswoen/Paper-Agent)*
