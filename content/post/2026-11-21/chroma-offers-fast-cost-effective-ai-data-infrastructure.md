---
title: "Chroma Offers Fast, Cost‑Effective AI Data Infrastructure"
slug: "chroma-offers-fast-costeffective-ai-data-infrastructure"
description: "Chroma has released a new update that highlights its fast, cost‑effective open‑source data infrastructure for AI."
date: 2026-11-21T06:15:51+05:30
tags: [Chroma, AIDataInfrastructure, OpenSource, VectorSearch]
categories: ["AI", "Machine Learning", "Data Infrastructure", "Open Source"]
image: "https://avatars.githubusercontent.com/u/105881770?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Chroma Offers Fast, Cost‑Effective AI Data Infrastructure

Chroma has released a new update that highlights its fast, cost‑effective open‑source data infrastructure for AI.

## 🔍 Overview
- Chroma - the open‑source data infrastructure for AI
- Our hosted service, Chroma Cloud, powers serverless vector, hybrid, and full‑text search.

## 🧩 How it Works
- Core API: create_collection, get_collection, get_or_create_collection, delete_collection
- Add docs with collection.add(...): handles tokenization, embedding, indexing automatically; can supply custom embeddings.
- Update and delete docs available.
- Row‑based API coming soon.
- Query with collection.query(query_texts=[...], n_results=2); can get by id.
- Metadata filtering via metadatas.

## ⚙️ Key Details
- Extremely fast, cost‑effective, scalable and painless.
- Create a DB in under 30 seconds with $5 of free credits.
- Persistence can be added easily.
- Apache 2.0 license.

## 🚀 Availability
- Releases new tagged versions of PyPI and NPM packages on Mondays.
- Hotfixes released any time during the week.
- Try it with $5 free credits in under 30 seconds.

## 💡 Why it Matters
- Rapidly developing project.
- Welcomes PR contributors and ideas for improvement.
- Chroma Cloud powers serverless vector, hybrid, and full‑text search.

```python
import chromadb
client = chromadb.Client()
collection = client.create_collection("all-my-documents")
collection.add(
    documents=["This is document1", "This is document2"],
    metadatas=[{"source": "notion"}, {"source": "google-docs"}],
    ids=["doc1", "doc2"]
)
results = collection.query(query_texts=["This is a query document"], n_results=2)
```

#Chroma #AIDataInfrastructure #OpenSource #VectorSearch

---

*Source: [chroma-core/chroma](https://github.com/chroma-core/chroma)*
