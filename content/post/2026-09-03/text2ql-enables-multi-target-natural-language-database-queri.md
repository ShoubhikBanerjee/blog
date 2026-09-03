---
title: "text2ql Enables Multi-Target Natural Language Database Queries with Deterministic Mode"
description: "A new open‑source Python framework called **text2ql** was submitted on 2 Sep 2026. It targets natural‑language interfaces to databases and claims to overcome three common structural limitations."
date: 2026-09-03T18:04:33+05:30
tags: [text2ql, NL2SQL, opensource, databases, AI]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# text2ql Enables Multi-Target Natural Language Database Queries with Deterministic Mode

A new open‑source Python framework called **text2ql** was submitted on 2 Sep 2026. It targets natural‑language interfaces to databases and claims to overcome three common structural limitations.

## 🔍 Overview
- Addresses exclusive focus on relational SQL, mandatory reliance on large‑language‑model (LLM) inference at query time, and lack of runtime signals for semantically incorrect queries.
- Introduces a language‑agnostic Intermediate Representation named **QueryIR** and a pluggable renderer architecture.

## 🧩 How it works
- A single seven‑stage detection pipeline can generate queries for both **SQL** and **GraphQL** targets.
- Supports two operating modes:
  1. **LLM‑backed mode** – leverages an LLM to interpret natural language.
  2. **Zero‑LLM deterministic mode** – bypasses LLM inference entirely.
- Every generated query is accompanied by a runtime confidence score ranging from **0.15 to 0.97**, computed via an additive signal model.

## ⚙️ Key details
- **Performance (LLM‑backed mode)** on 50‑query random samples from the Spider and BIRD benchmarks:
  - Exact‑match accuracy: **62 %–70 %**
  - Execution accuracy: **84 %–91 %**
- **Performance (Deterministic mode)** on 100 test cases:
  - Execution accuracy: **100 %** with zero parse errors
  - Median latency: **3.2 ms**
  - No API cost (zero‑LLM)
- Ablation study shows **schema‑aware prompting** adds **+18.4 percentage points** to exact‑match performance compared with a schema‑free baseline.

| Mode                | Exact Match | Execution Accuracy | Median Latency | API Cost |
|---------------------|-------------|--------------------|----------------|----------|
| LLM‑backed          | 62 %–70 %   | 84 %–91 %          | –              | –        |
| Deterministic (zero‑LLM) | –           | 100 %               | 3.2 ms         | None     |

## 🚀 Availability
- **text2ql** is released as open‑source under the **Apache 2.0** license.
- Implemented in Python and designed to be language‑agnostic via the QueryIR.

## 💡 Why it matters
- By providing a deterministic, zero‑LLM option, text2ql eliminates inference latency and API costs while guaranteeing execution correctness.
- The runtime confidence scores give developers immediate feedback on query reliability.
- Supporting both SQL and GraphQL expands applicability across relational and graph databases.


#text2ql #NL2SQL #open-source #databases #AI

---

*Source: [text2ql: Multi-Target Natural Language Querying via a Language-Agnostic Intermediate Representation](https://arxiv.org/abs/2609.02115v1)*
