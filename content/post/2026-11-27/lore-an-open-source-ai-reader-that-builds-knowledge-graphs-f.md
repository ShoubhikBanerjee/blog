---
title: "LORE: An open-source AI reader that builds knowledge graphs from e-books with citation support"
slug: "lore-an-open-source-ai-reader-that-builds-knowledge-graphs-from-e-books-with-citation-support"
description: "LORE is an open-source AI reader that transforms e-books into interactive knowledge graphs, answering questions with every sentence cited and respecting the user's reading progress without revealing..."
date: 2026-11-27T22:09:22+05:30
tags: [AIreader, knowledgegraph, OpenSource, ebooks, MCP, citations]
categories: ["AI", "Artificial Intelligence", "Reading Technology", "Knowledge Management", "Open Source Software"]
image: "https://avatars.githubusercontent.com/u/114429089?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LORE: An open-source AI reader that builds knowledge graphs from e-books with citation support

LORE is an open-source AI reader that transforms e-books into interactive knowledge graphs, answering questions with every sentence cited and respecting the user's reading progress without revealing later spoilers.

## 📚 What LORE Does

LORE turns each book into a knowledge graph of its characters, places, groups and events, then answers questions from the text itself. Every sentence in an answer cites the passage it comes from, and a second pass checks each citation against that passage and removes anything the book doesn't say.

## 🔍 How It Tracks Progress

Users can set their reading progress per book, and all outputs—answers, the graph, character profiles, and timelines—stop at the specified chapter. This is enforced at retrieval, ensuring the model never sees what comes later in the book.

## 🧩 Key Features

- Answers questions about characters, places, and events
- Provides character profiles, story timelines, and relationship maps
- Supports long, sectioned analyses with full citations
- Click any character for detailed profiles with passage-backed information
- Handles tracking character changes across multiple books
- Manages complex world and magic system explanations

## ⚙️ Technical Implementation

LORE uses Gemini (free tier works), Claude, or OpenAI for reading and writing; embeddings run locally on Ollama. An MCP server enables integration with Claude Desktop, Claude Code, and other MCP clients to search libraries and ask questions.

Users can choose their AI model on the admin page, with options including self-hosted models like llama.cpp's llama-server, vLLM, LM Studio, or Ollama. Each person added to the system gets their own private library.

## 🚀 Availability and Setup

Self-hosting requires Python 3.12+, uv, Node.js 18+, and Ollama. The local embedding model is installed via `ollama pull nomic-embed-text`. A Gemini API key (or Claude/OpenAI key) is required, which can be stored in an environment variable or in `~/.config/lore/gemini.env`.

The fastest option is the hosted beta at lore.jrvn.site, where new accounts start with A Study in Scarlet already processed for immediate use. Setup involves opening the app, adding books via EPUB or PDF, and waiting for processing to complete.

## 💡 Integration Options

LORE runs an MCP server, allowing Claude to search the library and ask questions with reading position constraints. The hosted beta integrates at claude.ai via Settings → Connectors → Add custom connector using https://lore.jrvn.site/mcp. Self-hosted instances run through `uv run lore mcp` (stdio) or `uv run lore mcp --http`.

#AIreader #knowledgegraph #OpenSource #ebooks #MCP #citations

---

*Source: [Jatin-Roopchandani/LORE](https://github.com/Jatin-Roopchandani/LORE)*
