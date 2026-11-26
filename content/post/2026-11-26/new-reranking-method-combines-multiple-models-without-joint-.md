---
title: "New Reranking Method Combines Multiple Models Without Joint Training"
slug: "new-reranking-method-combines-multiple-models-without-joint-training"
description: "Researchers have introduced a method for combining heterogeneous rerankers without requiring joint training, offering improvements in both accuracy and speed for multistage RAG pipelines. The..."
date: 2026-11-26T18:08:23+05:30
tags: [AI, reranking, transformers, RAG, retrieval, languagemodels]
categories: ["AI", "Computer Science", "Artificial Intelligence", "Machine Learning", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# New Reranking Method Combines Multiple Models Without Joint Training

Researchers have introduced a method for combining heterogeneous rerankers without requiring joint training, offering improvements in both accuracy and speed for multistage RAG pipelines. The approach uses two lightweight semantic coarse scorers, Cache-Pointwise and Cache-Shapley, which learn from passage relevance labels and enable efficient inference with cacheable representations. These scorers are designed to work in cascades with other models like CrossEncoder or Provence, improving answer accuracy by up to 9.43 percentage points while speeding up online pruning by up to 1.88x. The technique was evaluated on NoLiMa 32K with Gemma and shown to improve accuracy when composed with ColBERTv2 via reciprocal rank fusion. However, the effectiveness of such cascades depends on the reader model, reranker pairing, and stage configuration. The work opens new directions for studying stage order, candidate budgets, and rank fusion in reranking compositions.

#AI #reranking #transformers #RAG #retrieval #language-models

---

*Source: [When Rerankers Work Together: Better and Faster Reranking without Joint Training](https://arxiv.org/abs/2611.33844v1)*
