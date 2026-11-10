---
title: "Amazon Bedrock Managed Knowledge Base adds single-shot RAG and retrieval‑only modes"
slug: "amazon-bedrock-managed-knowledge-base-adds-single-shot-rag-and-retrievalonly-modes"
description: "Amazon Bedrock Managed Knowledge Base now supports two new request modes—single‑shot Retrieval Augmented Generation (RAG) and retrieval‑only—available through the **AgenticRetrieveStream** API."
date: 2026-11-10T18:03:23+05:30
tags: [AmazonBedrock, RAG, AIretrieval, FoundationModels]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Cloud Computing", "Natural Language Processing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-22223-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Managed Knowledge Base adds single-shot RAG and retrieval‑only modes

Amazon Bedrock Managed Knowledge Base now supports two new request modes—single‑shot Retrieval Augmented Generation (RAG) and retrieval‑only—available through the **AgenticRetrieveStream** API.

## 🔍 Overview
- **Single‑shot RAG**: the service performs one search of your knowledge bases and then uses a foundation model (FM) to generate an answer from the retrieved passages.
- **Retrieval‑only**: the service returns the matching passages without invoking a foundation model, letting the application or user work directly with the source text.
- These modes complement the existing *agentic retrieval* workflow, where the service plans and runs multiple searches before answering.

## 🧩 How it works
- The foundation model can break a question into sub‑queries, retrieve relevant evidence, and evaluate whether the results are sufficient.
- If gaps are found, the model can refine the search and retrieve additional evidence, up to the configured iteration limit.
- The planner may retrieve a full document when a passage lacks context, helping to fill gaps that a single retrieval might miss.
- When response generation is enabled, the service combines retrieved information into an answer with citations.
- Trace events expose the planning and retrieval steps so developers can inspect how an answer was produced.

## ⚙️ Modes comparison
| Mode | Retrievals | Foundation model calls | Planning rounds | Output |
|------|------------|------------------------|-----------------|--------|
| Single‑shot RAG | One retrieval | One call to generate answer (no planning rounds) | None | Answer with citations |
| Retrieval‑only | One retrieval | None (no answer generation) | None | Passages only |
| Agentic retrieval | Multiple searches (iterative) | One call per iteration + final answer generation | One query rewrite + retrieval per planning round | Answer with citations |

## 📊 Technical details
- **maxAgentIteration** range is now **0–5**, closing the gap for limited‑iteration use cases.
- A value of *n* allows up to *n − 1* agentic planning rounds; the last iteration is reserved for answer generation.
- Each planning round consists of one query rewrite followed by a retrieval.
- The initial retrieval that runs before the first planning step is counted as a retrieval, not an iteration.
- All three modes support multiple knowledge bases, including when `maxAgentIteration` is set to 0 or 1.
- Single‑shot RAG uses a single FM call, which can reduce latency and model usage compared with full agentic retrieval.
- Retrieval‑only requests make **no** foundation model calls.
- Using `maxAgentIteration=0` is the recommended setting when only passages are needed.

## 🚀 Availability
- The new request modes are accessible through the existing Bedrock Managed Knowledge Base API via **AgenticRetrieveStream**.
- Developers can select the desired mode by setting the appropriate `maxAgentIteration` value and toggling response generation.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-22223-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-22223-2-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-22223-3-1.jpg)

#AmazonBedrock #RAG #AIretrieval #FoundationModels

---

*Source: [Single-shot and agentic retrieval with Amazon Bedrock Managed Knowledge Base | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/single-shot-and-agentic-retrieval-with-amazon-bedrock-managed-knowledge-base/)*
