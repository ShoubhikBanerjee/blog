---
title: "Exa Optimizes Web Embedding Pipeline on AWS Neuron Hardware"
slug: "exa-optimizes-web-embedding-pipeline-on-aws-neuron-hardware"
description: "Exa is updating its web‑index embedding infrastructure to run more cheaply and flexibly on AWS Inferentia2 and Trainium2 hardware."
date: 2026-11-19T22:12:49+05:30
tags: [Exa, AWSNeuron, EmbeddingOptimization, VectorDB]
categories: ["AI", "Machine Learning", "Infrastructure", "Cloud Computing", "Search Engines"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/13/ML-22138-featured-image-1.png"
author: "Shoubhik Banerjee"
draft: false
---

# Exa Optimizes Web Embedding Pipeline on AWS Neuron Hardware

Exa is updating its web‑index embedding infrastructure to run more cheaply and flexibly on AWS Inferentia2 and Trainium2 hardware.

## 🔍 Overview
- Exa builds one of the few true web indexes by aggregating knowledge from public, private and synthetic sources.
- Multi‑tower semantic machine‑learning models embed web data and query data into the same vector space, allowing natural‑language and keyword queries.
- An in‑house vector database is the keystone technology for serving this embedded knowledge.
- Every structured web document that ranks as high enough quality must be embedded before it can be served.

## ⚙️ Optimization Details
- Moving to a superior document model required re‑embedding 30 billion high‑priority documents, temporarily doubling the embedding load and prompting a hardware re‑evaluation.
- Selected AWS Neuron hardware (Inferentia2 xlarge instance with one chip and two NeuronCores); the workload runs on a single NeuronCore, and Kubernetes pods pack onto larger instances to avoid idle cores.
- Initial Inferentia2 implementation used straightforward data‑parallel FP16 representation of the model.
- A progressive series of optimizations delivered roughly a **1.5×** throughput improvement:
  - **Weight layout optimization** aligned weight layout with model scheduling, eliminating unnecessary transposes.
  - **Autocast** allowed the compiler to down‑cast matrix multiplications to lower precision while preserving dynamic range; the down‑cast outputs met a 0.999 cosine‑similarity correctness gate.
  - The **Neuron Kernel Interface (NKI) library** supplied optimized kernels for common layers; using these pre‑built kernels gave immediate gains.
  - A **drop‑in attention kernel** added the next performance bump.
  - Profiling with Neuron Explorer revealed large HBM spill/reload; a custom **weight‑stationary fused SwiGLU MLP kernel** eliminated those stalls.
  - Most kernel logic was written in the higher‑level NKI language for readability and easier debugging; lower‑level NKI ISA was used only for specific tensor operations.
  - The **attention kernel** was rewritten to match the exact shapes of Exa’s model, cutting FLOPs spent on padding and further improving performance.

## 🚀 Deployment Model
- Inference runs on an asynchronous pipeline that must be high‑volume and fast to serve recent data quickly and shrink the time between discovery and serving.
- Pods are scheduled to keep all NeuronCores busy, providing container homogeneity across the embedding fleet.

## 💡 Why it matters
- Faster, cheaper embedding enables more up‑to‑date web documents to be available in Exa’s index.
- All optimizations preserve model accuracy (≥ 0.999 cosine similarity) while reducing hardware cost and improving utilization.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/13/ML-22138-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/13/ML-22138-2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/13/ML-22138-3-1.png)

#Exa #AWSNeuron #EmbeddingOptimization #VectorDB

---

*Source: [Exa boosts embedding throughput by 50% to index billions of documents on AWS AI chips | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/exa-boosts-embedding-throughput-by-50-to-index-billions-of-documents-on-aws-ai-chips/)*
