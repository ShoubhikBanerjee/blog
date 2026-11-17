---
title: "Haiku RAG Launches Open-Source Agentic Retrieval System with Docling and Ollama"
slug: "haiku-rag-launches-open-source-agentic-retrieval-system-with-docling-and-ollama"
description: "A new open-source project called Haiku RAG has been released, offering an agentic retrieval-augmented generation system that answers questions about user documents with citations to page numbers and..."
date: 2026-11-17T22:09:21+05:30
tags: [AI, RAG, OpenSource, LLM, Docling, LanceDB]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Open Source Software", "Natural Language Processing"]
image: "https://avatars.githubusercontent.com/u/183103?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Haiku RAG Launches Open-Source Agentic Retrieval System with Docling and Ollama

A new open-source project called Haiku RAG has been released, offering an agentic retrieval-augmented generation system that answers questions about user documents with citations to page numbers and section headings. The system runs on an embedded LanceDB database with open models through Ollama by default, requiring no server or API key. It supports multiple providers via Pydantic AI, and the same database can live on S3, GCS, Azure, or LanceDB Cloud. Built on LanceDB, Pydantic AI, and Docling, it ingests PDFs, office documents, HTML, Markdown, and images. The stored DoclingDocument preserves headings, tables, pictures, and page provenance. Search utilizes hybrid vector and full-text retrieval, optional reranking with cross-encoders and various providers, section-aware context expansion, and image search with multimodal embedders. It can answer with RAG capability, searching, running sandboxed Python for counting and aggregation, and citing page numbers and headings. Vision models receive figures directly. Optional capabilities compact earlier evidence and require answers to declare grounding. Citations can be checked by drawing chunks on page images from CLI, chat TUI, or Python. Integration options include Python API, native Pydantic AI capabilities, plugin hooks, MCP server for Claude Code, Codex, and Claude Desktop, plus a reference web app. The haiku-ingester service supports filesystem, HTTP, S3, and WebDAV sources with a SQLite or Postgres job queue, control plane, dashboard, tags, rollback, vacuum, and health checks. Python 3.12 or newer is required. Installation offers two packages: `pip install haiku.rag` for full features including Docling, VoyageAI, Cohere embedders, all rerankers, and TUI; and `pip install haiku.rag-slim` for core with extras. Default configuration uses Ollama for embeddings and answers. Commands include `haiku-rag init`, `haiku-rag add-src`, `haiku-rag search`, `haiku-rag ask`, `haiku-rag chat`, and `haiku-rag mcp --stdio`. The ingester service runs separately with `haiku-ingester serve` and supports continuous ingestion from configured sources.

#AI #RAG #OpenSource #LLM #Docling #LanceDB

---

*Source: [ggozad/haiku.rag](https://github.com/ggozad/haiku.rag)*
