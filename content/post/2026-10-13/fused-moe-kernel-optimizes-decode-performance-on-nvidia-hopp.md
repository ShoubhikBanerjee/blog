---
title: "Fused MoE Kernel Optimizes Decode Performance on NVIDIA Hopper GPUs"
slug: "fused-moe-kernel-optimizes-decode-performance-on-nvidia-hopper-gpus"
description: "Mixture‑of‑Experts (MoE) models boost LLM capacity while keeping per‑token compute low, but the decode phase suffers from high latency because the underlying GPU kernels are inefficient."
date: 2026-10-13T22:07:53+05:30
tags: [MixtureOfExperts, HopperGPU, KernelOptimization, LLMInference]
categories: ["AI", "Machine Learning", "Hardware Acceleration", "Large Language Models", "GPU Architecture"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/08/ML-22058-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Fused MoE Kernel Optimizes Decode Performance on NVIDIA Hopper GPUs

Mixture‑of‑Experts (MoE) models boost LLM capacity while keeping per‑token compute low, but the decode phase suffers from high latency because the underlying GPU kernels are inefficient.

## 🔍 Overview
- MoE is a sparsely‑activated architecture that scales large language model capacity while keeping per‑token compute low.
- MoE operations make up a large share of total compute time, so inefficiencies directly raise request latency and cost.
- Optimizing MoE operations through kernel engineering offers the largest opportunity for performance gains.

## 🧩 How MoE and Fused Kernels Work
- **Fused MoE** merges token routing, data shuffling, and specialized network calculations into a single batched GPU operation, replacing separate sequential loop operations.
- This fusion provides latency advantages but adds complexity to kernel implementation and debugging.

## ⚙️ Hopper WGMMA Constraints
- NVIDIA Hopper uses the Warp Group Matrix Multiply‑Accumulate (WGMMA) instruction, executed across a cooperative warp‑group of 128 threads.
- In the `wgmma.mma_async` definition, the hardware fixes the matrix row dimension **M** to 64, defining the thread‑mapping topology.
- Operand **A** must occupy this fixed **M = 64** dimension (using registers or shared memory); Operand **B** occupies the variable **N** dimension via a shared‑memory descriptor.
- The operand slots are structurally non‑interchangeable, and peak tile utilization requires **M ≥ 64**.
- The hardware enforces a minimum layout shape for the leading dimension of the first operand, locking the block height to exactly 64 rows.

### Table: Operand Mapping on Hopper WGMMA
| Operand | Fixed/Variable Dimension | Mapping Requirement |
|---------|---------------------------|----------------------|
| A | Fixed **M = 64** rows | Must fill a 64‑row layout bucket |
| B | Variable **N** dimension | Can be large (e.g., 8192) |

## 📈 Decoding Bottleneck and the Flip Technique
- Decode processes a single token per user sequence, yielding a thin batch dimension **M** (often **M < 64**, sometimes **M = 1**).
- Matrix **A** becomes a thin vector (e.g., 1 × 4096), while matrix **B** (expert weights) remains a large dense block (e.g., 4096 × 8192).
- Because **M** is tiny, **A** cannot fill the hardware’s 64‑row layout, leaving many Tensor Core lanes idle and causing poor utilization.
- MoE layers fracture the workload across many experts, making them especially sensitive to these constraints.
- For a `topk=8` routine, the effective **N** dimension inside the fused kernel expands to tens or hundreds of thousands of parameters.
- **Flipping the multiplication** (transposing the matrices before PTX assembly) moves the large expert dimension **N = 8192** into the first operand position, satisfying the mandatory 64‑row requirement and unlocking hardware prefetching.
- This re‑alignment matches the exact topography of Hopper silicon, allowing the expansive **N** dimension to flood the required rows and dramatically improve hardware utilization.

## 💡 Why It Matters
- By addressing the structural asymmetry of Hopper’s WGMMA instruction, the fused MoE kernel reduces decode latency.
- Better utilization of Tensor Core capacity lowers the compute cost of serving MoE‑based LLMs.
- The technique enables MoE models to retain their capacity‑scaling benefits without incurring prohibitive inference overhead.

#MixtureOfExperts #HopperGPU #KernelOptimization #LLMInference

---

*Source: [Mixture-of-Experts kernel engineering on Amazon SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/mixture-of-experts-kernel-engineering-on-amazon-sagemaker-ai/)*
