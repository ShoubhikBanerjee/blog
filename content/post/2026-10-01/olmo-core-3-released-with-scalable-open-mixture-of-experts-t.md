---
title: "Olmo‑core 3 released with scalable open Mixture‑of‑Experts training"
slug: "olmocore-3-released-with-scalable-open-mixtureofexperts-training"
description: "Olmo‑core 3 is now available – a major upgrade to the open‑source framework for building large language models that uses a redesigned Mixture‑of‑Experts (MoE) training system."
date: 2026-10-01T22:03:23+05:30
tags: [OlmoCore3, MixtureOfExperts, DistributedTraining]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Deep Learning", "AI Infrastructure"]
image: "https://cdn-uploads.huggingface.co/production/uploads/638e39b249de7ae552d977b5/uKnK93gjkKbmJmSx94WO2.png"
author: "Shoubhik Banerjee"
draft: false
---

# Olmo‑core 3 released with scalable open Mixture‑of‑Experts training

Olmo‑core 3 is now available – a major upgrade to the open‑source framework for building large language models that uses a redesigned Mixture‑of‑Experts (MoE) training system.

## 🔍 Overview
Olmo‑core 3 is built to scale MoE training into the trillion‑parameter range while keeping computational efficiency. It powers the next generation of Olmo models and continues the effort to open the tools and training infrastructure behind each new model.

## 🧩 How it works
The new stack combines several parallelism techniques to distribute massive MoE models across GPU clusters:
- **Expert parallelism** – spreads experts across GPUs so each device stores only a part of the full expert pool.
- **Pipeline parallelism** – splits model layers across groups of GPUs, reducing per‑GPU memory requirements.
- **Distributed optimizer** – shares optimizer state across GPUs instead of keeping a full copy on every GPU.
- **Rowwise expert parallelism** – places routed data directly into expert input buffers, minimizing extra data movement.
- **GPU‑resident routing** – keeps routing metadata on the GPUs, allowing the CPU to queue work without waiting for copies.
- **Grouped GEMM** – batches many small expert computations so GPUs execute them more efficiently.
- **MXFP8 support** – a lower‑precision number format that reduces memory usage and raises throughput.

## ⚙️ Key technical details
- Previous Olmo‑core MoE used Fully Sharded Data Parallelism (FSDP); Olmo‑core 3 switches to Distributed Data Parallelism (DDP) and keeps experts resident on GPUs, avoiding repeated weight gathering.
- The redesign improves throughput compared with the earlier FSDP implementation.
- MXFP8 yields about **21 % higher training throughput** than the BF16 baseline while lowering peak active memory from **103 GiB to 95 GiB**.

## 🚀 Performance benchmarks
| Configuration | Active parameters per token | Total parameters | Throughput impact |
|---|---|---|---|
| Expert pool 8 → 128 (4 experts per token) | ~3.2 B | 4.6 B → 47 B | < 5 % drop |
| 47 B‑parameter MoE on 8 NVIDIA B300 GPUs | ~3.2 B (approx.) | 47 B | 2.7× faster (52 k vs 19.4 k tokens / s per GPU) |
| MXFP8 on 4 NVIDIA B300 GPUs | – | – | +21 % throughput, memory 103 GiB → 95 GiB |

The same infrastructure has also been benchmarked at **over one trillion total parameters**, and a 1.2‑trillion‑parameter model (58.36 B active parameters per token) has been run across 512 GPUs.

## 📦 Availability
Olmo‑core 3 is released today as the open‑source framework for developing large language models with scalable MoE training.


![figure](https://www.datocms-assets.com/64837/1790799330-olmo-core-3-blog-draft-google-docs-image-2.png?fit=max&h=810&w=1550)

![figure](https://www.datocms-assets.com/64837/1790799917-olmo-core-3-blog-draft-google-docs-image-3.png?fit=max&h=810&w=1550)

![figure](https://cdn-uploads.huggingface.co/production/uploads/638e39b249de7ae552d977b5/c_Rnu4DRj6Djxk1IT0gKu.png)

#OlmoCore3 #MixtureOfExperts #DistributedTraining

---

*Source: [Introducing Olmo-core 3: Open, scalable training infrastructure for large MoEs](https://huggingface.co/blog/allenai/olmocore3)*
