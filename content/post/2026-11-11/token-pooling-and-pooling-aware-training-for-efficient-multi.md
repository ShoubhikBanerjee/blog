---
title: "Token Pooling and Pooling-Aware Training for Efficient Multi-Vector Embedding Models"
slug: "token-pooling-and-pooling-aware-training-for-efficient-multi-vector-embedding-models"
description: "Token pooling and pooling-aware training have been introduced to reduce the storage requirements of multi-vector embedding models by merging similar token vectors. This approach allows these models..."
date: 2026-11-11T22:05:42+05:30
tags: [MachineLearning, InformationRetrieval, NLP]
categories: ["AI", "Machine Learning", "Data Science", "Information Retrieval"]
image: "https://huggingface.co/blog/assets/train-sentence-transformers/st-hf-thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Token Pooling and Pooling-Aware Training for Efficient Multi-Vector Embedding Models

Token pooling and pooling-aware training have been introduced to reduce the storage requirements of multi-vector embedding models by merging similar token vectors. This approach allows these models to maintain high retrieval performance while significantly lowering the vector count in a document corpus.

## 🔍 Overview

Unlike single-vector embedding models that compress a document into one vector, multi-vector models like ColBERT maintain a collection of contextual token vectors. This allows different parts of a query to match different parts of a document using MaxSim scoring, where each query vector selects its best matching document vector and scores are summed. However, this method creates high storage demands, as a corpus with millions of documents can contain hundreds of millions of vectors.

## 🧩 How it works

Token pooling groups similar token embeddings to create smaller representations. This development builds on research such as Stefan Josef's Learn to Pool and LightOn's pooling regularization study.

*   **HierarchicalTokenPooling**: This method uses Ward hierarchical clustering to group similar embeddings. Starting with one group per token, it repeatedly merges the two groups that cause the smallest increase in the sum of squared distances from each vector to its group's mean.
*   **Group Representation**: Each group is represented by its mean, and the resulting vectors are normalized for use in MaxSim scoring.
*   **Adaptive Pooling**: This uses a shared distance threshold to merge similar embeddings more aggressively. It preserves more vectors for documents with distinct content and fewer for others based on a target average vector count.
*   **Pooling-Aware Training**: This process teaches the encoder to preserve essential information during the merging process, leading to better retrieval from the same storage budget.

## ⚙️ Key details

The following table outlines the features and components of this token pooling implementation:

| Feature | Function | 
| :--- | :--- |
| pool_factor | Determines the reduction in document vectors; a factor of 4 retains ~25% of vectors. |
| distance_threshold | Allows vector counts to grow when more distinct embeddings need preservation. |
| Calibration | Returns a threshold for adaptive pooling based on document embeddings and a target average. |
| First token protection | By default, the first token is protected from merging during the pooling process. |
| Query consistency | Pooling applies only to document embeddings, leaving query embeddings unchanged. |

## 💡 Why it matters

Token pooling addresses the high storage costs associated with multi-vector models. For instance, storing 200 vectors per document for a million documents at 4 bits per residual coordinate requires 12.8 GB. Pooling those documents to 50 vectors reduces the requirement to 3.2 GB.

Performance retention is high, especially when using specialized training:
*   With `pool_factor=4`, a normally trained model retains 94.6% of its unpooled NanoBEIR nDCG@10.
*   Pooling-aware training increases this retention to 97.8% at the same storage budget.
*   Pooling remains useful even when applied to ordinary multi-vector models not specifically trained for it.

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/token-pooling/mve_token_pooling_results.png)

#MachineLearning #InformationRetrieval #NLP

---

*Source: [Token Pooling-Aware Training for Multi-Vector Embedding Models](https://huggingface.co/blog/token-pooling)*
