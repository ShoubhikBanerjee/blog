---
title: "funes adds durable local memory to coding agents"
description: "Earlier this year, *Software Forgets: Agent Traces Are the Memory* made the case that coding agents already produce the record we keep losing. funes turns those traces into usable memory."
date: 2026-09-03T18:04:33+05:30
tags: [AIagents, memory, coding, local, funes]
categories: [AI]
image: "https://huggingface.co/blog/assets/funes/thumbnail.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# funes adds durable local memory to coding agents

Earlier this year, *Software Forgets: Agent Traces Are the Memory* made the case that coding agents already produce the record we keep losing. funes turns those traces into usable memory.

## 🔍 Overview
- funes is a durable memory layer for your agents (Claude Code, Codex, pi, and Hermes).
- It is built from the sessions already on your machine and works locally with a single command.
- The memory can also be shipped to a private Hugging Face dataset you own.

## 🧩 How it works
- A deterministic pipeline parses every supported trace into a uniform *turn‑and‑block* shape, chunks it, embeds it with a pinned local model, and writes it to a local Lance dataset.
- A query combines vector search and BM25, fuses their rankings, reranks the candidates with a cross‑encoder, reweights them by recency, and attaches neighboring chunks.
- Indexing is incremental: new runs add new turns instead of re‑embedding the entire history, and older content can be backfilled in bounded steps.

## ⚙️ Key details
- **Single binary** – no external ML runtime is required; embedding and reranking happen on your machine.
- **Recall inside conversation** – the agent can retrieve the original text (not a summary) with exact provenance (agent, timestamp, session, turn) without manually pasting old context.
- **Cross‑agent memory** – Claude Code, Codex, pi, and Hermes all write to the same shape; recall spans their combined histories and each hit indicates which agent produced it.
- **Exact provenance** – each result includes a `get` command that opens the full turn and surrounding context.
- **Local by default** – no account or Hub repository is needed; a hosted model does not process your sessions for indexing.

## 🚀 Availability
- Install funes with one command; it builds the first index, gives the agent recall and `get` tools, and sets up automation to index each completed turn.
- The bind can publish your current memory to a private Hugging Face dataset if you choose.

## 💡 Why it matters
- Traces are only potential memory; funes provides the indexing, retrieval, ranking, and exact provenance needed for agents to *use* those traces while they work.
- Raw evidence stays intact; nothing is distilled into a fact at write time, and every result can always lead back to the original turn.
- By keeping the memory local and deterministic, the coding agent retains full reasoning control while benefiting from fast, accurate recall.

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/funes/recall.gif)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/funes/ask.gif)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/funes/cross-agents.gif)

#AIagents #memory #coding #local #funes

---

*Source: [Give Your Coding Agents a Memory You Own](https://huggingface.co/blog/funes)*
