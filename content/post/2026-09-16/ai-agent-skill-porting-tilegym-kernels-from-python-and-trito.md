---
title: "AI Agent Skill Porting TileGym Kernels from Python and Triton-TileIR to cuTile Rust"
slug: "ai-agent-skill-porting-tilegym-kernels-from-python-and-triton-tileir-to-cutile-rust"
description: "A new AI agent skill has been developed to translate GPU kernels written in cuTile Python and Triton-TileIR into cuTile Rust (cutile-rs), a tile-based system designed for safe and idiomatic GPU..."
date: 2026-09-16T22:05:42+05:30
tags: [Rust, GPU, CUDA, AIagents, TileGym]
categories: ["AI", "Software Development", "AI Agents", "GPU Programming"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2025/07/neon-green-cube-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# AI Agent Skill Porting TileGym Kernels from Python and Triton-TileIR to cuTile Rust

A new AI agent skill has been developed to translate GPU kernels written in cuTile Python and Triton-TileIR into cuTile Rust (cutile-rs), a tile-based system designed for safe and idiomatic GPU kernel authoring in Rust.

## 🔍 Overview

Using this AI agent skill, all 24 public TileGym operators were ported to cuTile Rust. These operators comprise roughly 40 GPU kernels, including:

* Element-wise operations
* Flash-attention decode
* Multi-head Latent Attention (MLA)
* Mixture-of-experts (MoE) models

On average, the ported kernels reached 99.5% of the performance of the original cuTile Python implementations.

## 🧩 How it works

cuTile Python, Triton-TileIR, and cuTile Rust are all front ends for the same intermediate representation (IR): the CUDA Tile IR (cuda_tile dialect). All three use the tileiras compiler to perform tile-level optimizations and emit GPU binaries.

To ensure a faithful port, the translated kernel must reproduce the reference kernel's IR structure, including the same reductions, tile shapes, and memory-op families. This is verified by "diffing" the reference kernel Tile IR against the translated kernel Tile IR before tests are executed.

The translation process utilizes a bounded multi-agent pipeline that covers:
* Analysis
* The device kernel
* Host and FFI code
* Benchmarking

## ⚙️ Key details

While cuTile Python JIT compilation specializes kernels implicitly at call time, cuTile Rust requires every specialization to be declared in the kernel's signature.

Other technical specifications include:
* **Compilation:** Rust source is compiled ahead of time, with tile shapes and element types checked by rustc.
* **Specialization:** The crate embeds the kernel AST; the runtime specializes it with concrete const-generic values and compiles a cached cubin at first launch.
* **FFI Dispatch:** Dispatches over a fixed symbol/dtype table spanning f32, f16, bf16, i32, i64, f8e5m3, and f8e4m3fn.
* **Memory Safety:** The system splits mutable outputs into disjoint pieces and preserves the host-side ownership contract across kernel launches.

## 🚀 Availability

cuTile Rust is integrated into TileGym as a backend. The operator API can be routed to Rust kernels using `tilegym.set_backend("cutile-rs")`. The AI translation skill is available in the TileGym repo for use with custom kernels.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/cuda-tile-translation-python-rust-flow.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/cutile-rust-versus-python-kernels-tilegym-operators.webp)

#Rust #GPU #CUDA #AIagents #TileGym

---

*Source: [Translating CUDA Tile Operations from Python to Rust Using Agentic AI | NVIDIA Technical Blog](https://developer.nvidia.com/blog/translating-cuda-tile-operations-from-python-to-rust-using-agentic-ai/)*
