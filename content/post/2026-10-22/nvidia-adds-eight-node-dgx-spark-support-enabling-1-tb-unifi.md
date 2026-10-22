---
title: "NVIDIA Adds Eight‑Node DGX Spark Support, Enabling 1 TB Unified Memory for Frontier Models"
slug: "nvidia-adds-eightnode-dgx-spark-support-enabling-1-tb-unified-memory-for-frontier-models"
description: "AI developers aren’t just running a single model anymore—they’re orchestrating multiple models in parallel, chaining inference calls, and experimenting with frontier‑class architectures that demand..."
date: 2026-10-22T22:11:45+05:30
tags: [NVIDIA, DGXSpark, AIClusters, LargeModels]
categories: ["AI", "Hardware", "Machine Learning", "High‑Performance Computing", "AI Infrastructure"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/workstation-3d-render-dgx-spark-key-visual-single-gtc26-4655400-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Adds Eight‑Node DGX Spark Support, Enabling 1 TB Unified Memory for Frontier Models

AI developers aren’t just running a single model anymore—they’re orchestrating multiple models in parallel, chaining inference calls, and experimenting with frontier‑class architectures that demand hundreds of gigabytes of memory.

## 🔍 Overview
NVIDIA announced at GTC Berlin official support for eight‑node DGX Spark clusters. The new configuration scales unified memory to 1 TB, opening the door to frontier‑class models, multi‑agent workloads, and near‑linear pre‑training, all on‑premises.

## 🧩 How it works
- **Memory scaling**: a single DGX Spark node provides 128 GB unified memory; four nodes give 512 GB; eight nodes reach 1 TB.
- **Model support**: the 1 TB pool can host models that previously wouldn’t start on a four‑node system, exemplified by the full GLM 5.3 (753B) model from Z.ai.
- **Interactive serving**: the eight‑node cluster can run the GLM 5.3 Flash checkpoint and deliver roughly 80 tokens per second (TPS) in generation, suitable for interactive local development.
- **Cluster management**: NVIDIA Sync provides easy clustering; its Cluster Assistant handles setup and device management. Support for eight‑node clusters in NVIDIA Sync is slated for the end of the year.

## ⚙️ Key details
- **Collective communication**: Tensor‑parallel inference spends a meaningful fraction of time in collective operations such as all‑reduce.
- **RoCEnante backend**: a Spark‑optimized collective backend that reduces latency for small‑message, low‑concurrency, modest‑rank‑count patterns typical of tensor‑parallel decode on local AI hardware.
  - Implements an all‑to‑all exchange followed by local reduction using a single GPU kernel.
  - Fewer communication steps than ring all‑reduce; each rank shares its full input with every peer.
  - Benefits: lower latency for small messages and modest rank counts.
  - Trade‑off: increased data movement; less efficient as messages or rank count grow.
- **When to use NCCL**: for high concurrency, larger clusters, or ring topologies, NVIDIA Collective Communications Library (NCCL) performs better.
- **Performance gains** (non‑quantized model):
  - ~5 % higher prefill throughput and ~21 % higher decode throughput at four nodes (NVFP4).
  - ~18 % higher decode throughput at eight nodes.
- **Integration**: the RoCEnante backend is merged into FlashInfer and falls back transparently to NCCL if its startup test fails. It applies only to switch‑connected topologies.

| Backend | Best for | Trade‑off |
|--------|----------|----------|
| RoCEnante | Small messages, low concurrency, modest rank count (e.g., 4–8 nodes) | More data movement; latency advantage diminishes as rank count grows |
| NCCL | High concurrency, larger clusters, ring topologies | Slightly higher latency for small‑message patterns |

## 🚀 Availability
- Official eight‑node DGX Spark cluster support announced at GTC Berlin.
- NVIDIA Sync will include eight‑node clustering capabilities by the end of the year.
- RoCEnante backend is already integrated into FlashInfer for switch‑connected clusters.

## 💡 Why it matters
- The unified 1 TB memory pool lets developers run frontier‑class mixture‑of‑experts models locally, reducing reliance on remote cloud resources.
- Interactive token‑generation speeds (≈80 TPS) make on‑premise experimentation with large models feasible.
- Optimized collective communication (RoCEnante) improves decoding throughput, directly benefiting generation latency for multi‑GPU deployments.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/workstation-3d-render-dgx-spark-key-visual-single-gtc26-4655400-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image3-18-660x370-png.webp)

#NVIDIA #DGXSpark #AIClusters #LargeModels

---

*Source: [Running Frontier-Class AI Models Across 8 NVIDIA DGX Spark Nodes | NVIDIA Technical Blog](https://developer.nvidia.com/blog/running-frontier-class-ai-models-across-8-nvidia-dgx-spark-nodes/)*
