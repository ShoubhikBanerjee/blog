---
title: "AI Agent Skill Translates CUDA Tile Kernels to cuTile Rust"
slug: "ai-agent-skill-translates-cuda-tile-kernels-to-cutile-rust"
description: "A new AI agent skill has been developed to translate GPU kernels from cuTile Python and Triton-TileIR into cuTile Rust, a tile-based system designed for safe and idiomatic GPU kernel authoring in the..."
date: 2026-09-17T00:45:10+05:30
tags: [Rust, CUDA, GPU, AIagents, TileGym]
categories: ["AI", "Software Development", "AI Agents", "GPU Programming"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2025/07/neon-green-cube-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# AI Agent Skill Translates CUDA Tile Kernels to cuTile Rust

A new AI agent skill has been developed to translate GPU kernels from cuTile Python and Triton-TileIR into cuTile Rust, a tile-based system designed for safe and idiomatic GPU kernel authoring in the Rust programming language.

## 🔍 Overview

cuTile Rust extends the Rust ownership model to tile-based GPU kernels by splitting mutable outputs into disjoint pieces and preserving the host-side ownership contract across kernel launches. It serves as one of three front ends—alongside cuTile Python and Triton-TileIR—that feed into the same CUDA Tile IR (the cuda_tile dialect) and the tileiras compiler, which emits the GPU binary.

## 🧩 How it works

The translation process uses a bounded multi-agent pipeline that covers the following stages:

*   Analysis
*   Device kernel creation
*   Host and FFI code generation
*   Benchmarking

Each stage concludes with a machine-checkable verdict. Because all three front ends share the same IR, translation is verified by "diffing" the Tile IR of the reference kernel and the translated kernel to ensure they reproduce the same reductions, tile shapes, and memory-op families before tests are executed.

## ⚙️ Key details

There are significant differences between the JIT compilation of cuTile Python and the ahead-of-time compilation of Rust source:

*   **Specialization:** cuTile Python specializes kernels implicitly at call time. In contrast, cuTile Rust requires every specialization to be declared in the kernel's signature; nothing is specialized unless declared.
*   **Structural Changes:** A single Python kernel may become multiple Rust entries. For example, layer_norm splits into 2-Dnchw and 1-Dw1 entries because the branch changes tile rank.
*   **Compilation:** Rust source is compiled ahead of time, with tile shapes and element types checked by rustc. The crate embeds the kernel AST, and the runtime specializes it with concrete const-generic values to compile a cached cubin at first launch.
*   **ABI Support:** Supporting a dtype is an explicit ABI extension. Supported types include sf32, f16, bf16, i32, i64, f8e5m2, and f8e4m3fn.

## 🚀 Availability

The translation skill is shipped in the TileGym repo. In TileGym, cuTile Rust functions as a backend that can be activated using `tilegym.set_backend("cutile-rs")` to route the operator API to Rust kernels.

## 💡 Why it matters

Using this AI agent skill, all 24 public TileGym operators—comprising roughly 40 GPU kernels—were ported to cuTile Rust. These kernels range from element-wise operations to mixture-of-experts (MoE) models, Multi-head Latent Attention (MLA), and flash-attention decode. On average, the ported kernels reached 99.5% of cuTile Python performance.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/cuda-tile-translation-python-rust-flow.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/cutile-rust-versus-python-kernels-tilegym-operators.webp)

#Rust #CUDA #GPU #AIagents #TileGym

---

*Source: [Translating CUDA Tile Operations from Python to Rust Using Agentic AI | NVIDIA Technical Blog](https://developer.nvidia.com/blog/translating-cuda-tile-operations-from-python-to-rust-using-agentic-ai/)*
