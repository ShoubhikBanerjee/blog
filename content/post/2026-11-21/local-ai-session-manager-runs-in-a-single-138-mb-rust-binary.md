---
title: "Local AI Session Manager Runs in a Single 138 MB Rust Binary"
slug: "local-ai-session-manager-runs-in-a-single-138-mb-rust-binary"
description: "A new self‑reflective AI session manager can run entirely locally from one Rust binary of about 138 MB, embedding SQLite and a vector index, and requiring no containers, database servers, Python, or..."
date: 2026-11-21T22:09:40+05:30
tags: [AI, Rust, LocalLLM, SelfReflect, DeveloperTools]
categories: ["AI", "Artificial Intelligence", "Software Engineering", "Machine Learning", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/1927846?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Local AI Session Manager Runs in a Single 138 MB Rust Binary

A new self‑reflective AI session manager can run entirely locally from one Rust binary of about 138 MB, embedding SQLite and a vector index, and requiring no containers, database servers, Python, or API keys.

## 🔍 Overview
- Single executable (~138 MB) written in Rust
- Embedded SQLite stores chunks, embeddings, and enrichment state
- In‑memory HNSW vector index for fast local search
- FastEmbed provides 384‑dimensional local embeddings
- No external dependencies such as Docker, database servers, or API keys

## 🧩 How it Works
- Sessions start with a concise recap paragraph that states intent, completed work, settled items, open items, and the next step.
- Every clause in a session can carry a receipt linking to a commit, task, verdict, or correction; clauses without evidence are omitted.
- **Dreams**: the system checks past conclusions against git history and marks stale anchors with the commit that changed them.
- **Compaction**: after a compact, the system stores pointers to the original turns and can retrieve them via `csr_transcript`.
- A companion pane shows what the AI was told, what it missed, and any user corrections.
- The plumbing layer uses SQLite and a local vector index to search past sessions; the AI can invoke this directly through MCP tools.

## ⚙️ Key Details
- CI on 2026‑11‑18: `cargo test --locked --no-fail-fast` → 6,939 passed, 0 failed, 34 ignored
- `cargo fmt`, `clippy -D warnings`, and `actionlint` report no issues
- Installer tests pass 58 of 58
- Repo can be scanned manually with `csr-engine codemap scan --repo <path>`
- Local vector search and embedding generation require zero external services

## 🚀 Availability
- The binary runs locally in a single process; no Docker, no remote services, and no API keys are needed.
- Users can map a repository to enable code‑aware answers across all worktrees.
- The system integrates with Claude via the Self‑Reflect plugin to maintain session continuity.


#AI #Rust #LocalLLM #SelfReflect #DeveloperTools

---

*Source: [ramakay/claude-self-reflect](https://github.com/ramakay/claude-self-reflect)*
