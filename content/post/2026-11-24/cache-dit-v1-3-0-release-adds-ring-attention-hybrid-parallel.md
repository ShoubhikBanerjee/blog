---
title: "Cache-DiT v1.3.0 Release Adds Ring Attention, Hybrid Parallelism"
slug: "cache-dit-v1-3-0-release-adds-ring-attention-hybrid-parallelism"
description: "Cache-DiT v1.3.0 has been released. The new version introduces several key updates."
date: 2026-11-24T18:09:57+05:30
tags: [CacheDiT, DiffusionModels, Parallelism]
categories: ["AI", "Machine Learning", "Deep Learning", "Distributed Systems"]
image: "https://avatars.githubusercontent.com/u/204302598?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Cache-DiT v1.3.0 Release Adds Ring Attention, Hybrid Parallelism

Cache-DiT v1.3.0 has been released. The new version introduces several key updates.

## 🔍 Overview
Cache-DiT is a diffusion model framework that now supports Ring Attention, batched P2P communication, and hybrid parallelism.

## 🧩 How it works
The major changes involve:
- **Ring Attention** with batched P2P communication
- **USP** (Hybrid Ring and Ulysses) for efficient scaling
- **Hybrid 2D and 3D Parallelism** combining USP and Tensor Parallel (TP)
- Reduction of VAE‑P communication overhead

## ⚙️ Key details
| Feature | Description |
|---|---|
| Ring Attention | Attention mechanism using a ring topology with batched P2P |
| USP | Hybrid Ring and Ulysses parallelism |
| Hybrid 2D/3D Parallelism | Combines USP and Tensor Parallel for efficient scaling |
| VAE-P Comm overhead | Reduced communication overhead for VAE-P |

## 🚀 Availability
The release is publicly available on GitHub: https://github.com/vipshop/cache-dit
Documentation can be found at https://cache-dit.readthedocs.io/en/latest/user_guide/CONTEXT_PARALLEL and https://cache-dit.readthedocs.io/en/latest/user_guide/HYBRID_PARALLEL/.

## 💡 Why it matters
These updates enable more efficient distributed training and inference for diffusion models, making larger-scale models more accessible.

#CacheDiT #DiffusionModels #Parallelism

---

*Source: [xlite-dev/Awesome-LLM-Inference](https://github.com/xlite-dev/Awesome-LLM-Inference)*
