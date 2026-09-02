---
title: "Optimizing Speculative Decoding Draft Length for LLM Inference"
description: "Speculative decoding is a technique for accelerating the autoregressive decoding phase of LLM inference by predicting multiple tokens per iteration. New guidelines detail how to optimize draft length..."
date: 2026-09-02T22:08:32+05:30
tags: [speculativedecoding, LLMinference, mixtureofexperts, GPUoptimization, attentionmechanism, GEMMoptimization]
categories: [AI]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/llm-optimize-deploy-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# Optimizing Speculative Decoding Draft Length for LLM Inference

Speculative decoding is a technique for accelerating the autoregressive decoding phase of LLM inference by predicting multiple tokens per iteration. New guidelines detail how to optimize draft length based on workload characteristics and hardware constraints, particularly for mixture-of-experts models and attention-heavy workloads.

## 🔍 Overview

Speculative decoding works by using a small draft model to predict several likely next tokens, which are then verified in parallel with a single pass through the larger target model. This approach reduces the total number of decoding iterations while increasing the arithmetic intensity of the target model, without requiring higher concurrency.

The target model accepts the proposed tokens in sequence until it encounters the first mismatch. The next prediction cycle then resumes from that position. Because only tokens accepted by the target model are retained, speculative decoding produces the same output sequence as standard decoding, unless the acceptance criteria are deliberately relaxed.

## 🧩 Key Metrics

- **Draft length (\(D\))**: The number of proposed tokens per target iteration
- **Acceptance length (\(AL\))**: The number of tokens produced (accepted) per target iteration
- \(AL\) ranges from \(1\) to \((1 + D)\) because the target can always produce one new ground-truth token in addition to the accepted draft tokens

## ⚙️ Compute and Memory Dynamics

During verification, compute scales with \((1 + D)\), but memory access remains unchanged. The goal is to increase \(D\) until \(T_{\mathrm{verif}}\) remains constant, typically up to the point where verification transitions from memory bound to compute bound.

With speculation, the GEMM-\(M\) for each target linear layer GEMM grows from \(M\) to \(M \times (1 + D)\), where \(M\) is the GEMM-\(M\) with no speculation.

| Draft length | Batch size reduction for compute-bound |
|-------------|----------------------------------------|
| \(D=7\) | One-eighth of batch size needed vs. \(D=0\) |

As mixture-of-experts (MoE) models become sparser and long-context workloads increase KV capacity pressure, the effective concurrency per expert decreases, making larger draft lengths attractive across the Pareto frontier.

## 📐 Three Guidelines for Draft Length Selection

**Guideline 1**: Increase speculative decoding draft length to push GEMMs into the compute-bound region without increasing KV cache capacity pressure.

**Guideline 2**: When attention dominates decode time, choose \(D = \frac{128}{G} – 1\).

For reasoning and agentic workloads, attention tends to dominate the execution time in the throughput-oriented region. On current GPU devices, attention kernels achieve good hardware utilization at GEMM-\(M=128\). The \(G = 32\) variant reaches throughput saturation at a lower value of \(D\). Beyond the throughput saturation point, attention is no longer DRAM bandwidth bound, and its runtime scales with \(D\).

**Guideline 3**: If you choose \(D > \frac{128}{G} – 1\), prefer values where \(G \times (1 + D)\) is a multiple of 128 to avoid tile underutilization.

Attention runtime also depends on tile size. Runtime increases in steps as \(G \times (1 + D)\) crosses a multiple of 128, the software tile size for the benchmarked attention kernel. If \(G \times (1 + D)\) falls between two tile boundaries, the last tile is only partially utilized but still costs about as much as a full tile.

## 📊 Performance Characteristics

- With \(D=7\), one-eighth of the batch size is needed to become compute bound compared to \(D=0\)
- Normalized attention throughput varies with \(D\) for different \(G\) values across 32K and 128K KV sequence lengths
- Attention kernel tile size is 128

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/speculative-decoding-flow.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/gemm-throughput-spec-decode.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/normalized-attention-tflops.webp)

#speculativedecoding #LLMinference #mixtureofexperts #GPUoptimization #attentionmechanism #GEMMoptimization

---

*Source: [Co-Designing AI Models Using Speculative Decoding for Faster LLM Inference | NVIDIA Technical Blog](https://developer.nvidia.com/blog/co-designing-ai-models-using-speculative-decoding-for-faster-llm-inference/)*
