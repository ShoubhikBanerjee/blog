---
title: "Contiguity, Not Importance: Budgeted Repair of Stale KV Caches After Document Edits"
slug: "contiguity-not-importance-budgeted-repair-of-stale-kv-caches-after-document-edits"
description: "KV‑cache reuse can cut inference cost in retrieval‑augmented generation (RAG) and agentic systems, but edits to retrieved knowledge, working memory, or user state can make cached contexts stale."
date: 2026-09-17T18:02:05+05:30
tags: [KVCache, RAG, ModelRepair, AIInference]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# Contiguity, Not Importance: Budgeted Repair of Stale KV Caches After Document Edits

KV‑cache reuse can cut inference cost in retrieval‑augmented generation (RAG) and agentic systems, but edits to retrieved knowledge, working memory, or user state can make cached contexts stale.

## 🔍 Overview
- Under causal self‑attention, a local edit can affect downstream KV states.
- A full re‑prefill restores consistency but is costly.
- Refreshing only the edited span can leave downstream dependencies stale.

## ⚙️ Budgeted Repair Approach
- The problem is framed as **in‑place repair** = budgeted recomputation.
- Training‑free position‑selection policies are evaluated on a factual RAG benchmark with matched direct and derived edits.

## 📊 Findings
- Across three model families, all policies fix direct‑edit cases; derived cases separate the policies.
- With the primary budget, a contiguous edit‑local window recovers **≥ 0.94** of the post‑edit answer margin and outperforms attention‑based, KV‑deviation, and structural selectors.
- Mechanistic analysis: position sets that work under clean‑state transplantation can fail under actual recomputation because scattered positions inherit surrounding staleness.
- The edit‑local advantage depends on adjacency and largely disappears when the answer‑bearing text moves downstream.
- Answer‑relevant edits almost always corrupt model behavior; failure severity is difficult to predict.
- Repair using the edit‑local window is **13–21×** faster than a full re‑prefill.

## 💡 Implications
- When the dependent text remains adjacent to the edit, unconditional edit‑local repair provides a fast, cost‑effective solution to stale KV caches.

#KVCache #RAG #ModelRepair #AIInference

---

*Source: [Contiguity, Not Importance: Budgeted Repair of Stale KV Caches After Document Edits](https://arxiv.org/abs/2609.17983v1)*
*Source: [Long-Context Demonstration Selection Using State Space Models](https://arxiv.org/abs/2609.17888v1)*
