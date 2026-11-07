---
title: "Reshard Collective Enables Efficient Weight Refit for Large‑Scale RL Training"
slug: "reshard-collective-enables-efficient-weight-refit-for-largescale-rl-training"
description: "During reinforcement learning (RL) post‑training, training trajectories are generated on the fly by running inference with the current policy model. In large‑scale setups inference and training run..."
date: 2026-11-07T18:01:21+05:30
tags: [RL, WeightRefit, Reshard, NCCL]
categories: ["AI", "Machine Learning", "Distributed Computing", "Deep Learning", "Reinforcement Learning"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/green-cube.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Reshard Collective Enables Efficient Weight Refit for Large‑Scale RL Training

During reinforcement learning (RL) post‑training, training trajectories are generated on the fly by running inference with the current policy model. In large‑scale setups inference and training run on separate GPU resources in a disaggregated configuration, and the system periodically refreshes inference‑GPU weights with the latest parameters from the training GPUs; this transfer is called **refit**.

## 🔍 Overview
- RL post‑training generates trajectories on the fly via inference with the current policy model.
- Inference and training run in parallel on separate GPU resources in a disaggregated setup.
- Periodic weight refresh on inference GPUs is termed **refit**.

## ⚙️ Why refit is challenging
- Inference and training use different parallelism mappings (data, context, tensor, expert, pipeline), so weight shards are laid out differently.
- Refit must move all model weights, making the communication payload comparable to the total model size.
- Frontier models already require ~10 TB of data per refit (e.g., Kimi K3 ≈5.6 TB, Qwen 3.8 2.4T A95B ≈4.8 TB), and the payload grows with model scale.
- Existing implementations use a gather‑and‑broadcast pattern:
  * Training GPUs all‑gather local shards into a complete tensor.
  * The complete tensor is broadcast to inference GPUs, each keeping only its needed shard.
- This sends the full tensor to every inference GPU, creating redundant communication in both phases.

## 🧩 The Reshard collective solution
- The Reshard collective is a new type of collective communication designed to accelerate RL weight refit.
- Implemented as **NCCL M2N Reshard**, an open‑source reference in the NVIDIA/nccl‑extensions GitHub repository.
- Builds on PyTorch’s Distributed Tensor (DTensor) abstraction, which describes a tensor’s global shape, device mesh, and placements (shard or replicate).
- Refit is reformulated as a DTensor‑to‑DTensor **resharding** operation: converting the training layout to the inference layout directly, without constructing a full intermediate tensor.
- This transfers only the theoretical minimum amount of data, respecting arbitrary shard boundaries and replication patterns.

## 📊 Model size examples
| Model | Parameters (trillion) | Approx. BF16 weight size (TB) |
|-------|-----------------------|------------------------------|
| Kimi K3 | 2.8 | 5.6 |
| Qwen 3.8 2.4T A95B | 2.4 | 4.8 |

## 🚀 Availability
- NCCL M2N Reshard source code is publicly available via the NVIDIA/nccl‑extensions GitHub repo.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/direct-shard-to-shard-transfer-dtensor.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/reshard-operation-example.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/tp4-to-tp2dp2-example.gif)

#RL #WeightRefit #Reshard #NCCL

---

*Source: [Accelerating Reinforcement Learning Weight Refit with the Reshard Collective | NVIDIA Technical Blog](https://developer.nvidia.com/blog/accelerating-reinforcement-learning-weight-refit-with-the-reshard-collective/)*
