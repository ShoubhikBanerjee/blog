---
title: "Jane Street Implements Mamba‑2 in NVIDIA cuTile Python DSL"
slug: "jane-street-implements-mamba2-in-nvidia-cutile-python-dsl"
description: "Machine learning engineers at Jane Street have implemented the state‑of‑the‑art Mamba‑2 sequence model using NVIDIA’s cuTile Python‑based DSL and partnered with NVIDIA to optimize the kernels."
date: 2026-10-20T12:01:18+05:30
tags: [cuTile, Mamba2, TensorCores]
categories: ["AI", "Machine Learning", "GPU Computing", "Deep Learning Models"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2025/11/Solving-Math-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Jane Street Implements Mamba‑2 in NVIDIA cuTile Python DSL

Machine learning engineers at Jane Street have implemented the state‑of‑the‑art Mamba‑2 sequence model using NVIDIA’s cuTile Python‑based DSL and partnered with NVIDIA to optimize the kernels.

## 🔍 Overview
- **cuTile** is a Python‑based domain‑specific language and parallel programming model for NVIDIA GPUs that automatically leverages advanced hardware capabilities to deliver peak performance for tile‑level GPU programming.
- By abstracting thread‑ and warp‑level scheduling behind high‑level, tile‑centric primitives, cuTile enables you to write GPU kernels in Python while compiler optimizations automatically target advanced hardware features like Tensor Cores.
- **Mamba‑2** is a sequence model that aims for the best of both worlds: the fixed‑size hidden state of an RNN and the efficient, chunk‑wise computation of attention‑style models.
- Jane Street, a global trading firm that uses deep learning for quantitative research, implemented Mamba‑2 in cuTile and worked with NVIDIA to optimize the kernels.

## 🧩 How cuTile Works
- Import the package as `cuda.tile` and expose it as `ct` throughout the kernel implementations.
- High‑level tile primitives hide the low‑level details of thread and warp scheduling.
- The compiler maps these primitives to Tensor‑Core‑friendly matrix operations without the user writing explicit CUDA kernels.

## 🧩 Mamba‑2 Architecture in cuTile
- The core recurrence is:
  $$h_t = \exp(A \cdot dt_t) h_{t-1} + dt_t B_t x_t$$
- `h_t` is a fixed‑size hidden **matrix** of size \(S, H\); it carries state across tokens.
- Inputs per token \(t\):
  - `x_t` (vector of size H) – similar to values in attention.
  - `dt_t` (scalar per head, always negative) – controls update magnitude.
  - `B_t` (vector of size S) – similar to keys.
  - `c_t` (vector of size S) – similar to queries and used to produce outputs.
- The output equation can be written as:
  $$y_t = c_t^{\mathsf{T}} h_{t-1} + D x_t$$
- When processing a chunk of \(T\) tokens, the recurrence can be expressed with Tensor‑Core‑friendly matrix products:
  $$h_{t+T} = h_t + B X^{\mathsf{T}}$$
  where \(B\) stacks the \(b_{t+i}\) vectors and \(X\) stacks the \(x_{t+i}\) vectors.
- Adding the skip connection yields the full chunk computation:
  $$Y = C h_t + ((C B^{\mathsf{T}}) \cdot M) X + D X$$
  where `M` is a causal mask, analogous to the mask used in causal softmax attention.
- Removing the decay term reduces Mamba‑2 to linear attention with renamed components.

## ⚙️ Key Implementation Details
- The implementation groups `x_t`, `b_t`, `c_t`, and `y_t` into matrices, enabling the use of Tensor Cores for the bulk of the work.
- Traditional softmax attention scales compute and memory linearly with sequence length during inference, while RNNs have a fixed memory footprint but suffer from slow, non‑parallelizable training.
- Mamba‑2’s matrix‑based hidden state and chunked computation aim to combine a fixed memory cost with Tensor‑Core acceleration.

## 💡 Why It Matters
- By expressing the recurrence as matrix multiplications, the workload becomes memory‑bound rather than compute‑bound, allowing the fast Tensor Core pathways to be used.
- The approach avoids materializing an enormous hidden‑state tensor, which would otherwise limit performance.
- This joint effort shows how a high‑level Python DSL can bridge sophisticated sequence models and low‑level GPU hardware features without hand‑written CUDA kernels.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/mamba-2-chunk-computation.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/performance-cutile-mamba-2-forward-pass.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/causal-masking-safe-exponential.webp)

#cuTile #Mamba2 #TensorCores

---

*Source: [Accelerating Mamba-2 with High-Performance Forward Pass Kernels in NVIDIA CUDA Tile | NVIDIA Technical Blog](https://developer.nvidia.com/blog/accelerating-mamba-2-with-high-performance-forward-pass-kernels-in-nvidia-cuda-tile/)*
