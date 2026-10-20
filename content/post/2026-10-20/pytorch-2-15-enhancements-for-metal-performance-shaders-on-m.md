---
title: "PyTorch 2.15 Enhancements for Metal Performance Shaders on Mac"
slug: "pytorch-2-15-enhancements-for-metal-performance-shaders-on-mac"
description: "PyTorch 2.15 introduces significant performance and memory optimizations for Apple silicon Macs via Metal Performance Shaders (MPS), specifically targeting Large Language Model (LLM) decoding,..."
date: 2026-10-20T22:03:21+05:30
tags: [PyTorch, AppleSilicon, Metal, LLM, MachineLearning]
categories: ["AI", "Machine Learning", "Software Development", "Hardware Acceleration"]
image: "https://huggingface.co/blog/assets/mps-pytorch-2-15/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# PyTorch 2.15 Enhancements for Metal Performance Shaders on Mac

PyTorch 2.15 introduces significant performance and memory optimizations for Apple silicon Macs via Metal Performance Shaders (MPS), specifically targeting Large Language Model (LLM) decoding, Mixture-of-Experts (MoE) models, and video processing.

## 💡 Why it matters

Performance gains are most evident in MoE models, which decode 5–6.5× faster than in version 2.14. For example, on an M3 Ultra using `torch.compile`:

| Model | 2.14 Speed | PyTorch 2.15 Speed |
| :--- | :--- | :--- |
| Qwen3.6-35B-A3B | 9.4 tokens/s | 61.3 tokens/s |
| LFM2.5-8B-A1B | 23.6 tokens/s | 123.6 tokens/s |

## 🧩 How it works

- **FP8 Support**: PyTorch 2.15 adds `torch.float8_e4m3fn` tensors on MPS. These use one byte per value, requiring half the storage of BF16 or FP16. Tensors can be multiplied directly on the GPU using `F.scaled_mm`, which supports rowwise and tensorwise scaling.
- **MoE Optimizations**: New Metal kernels read group offsets directly on the GPU using Metal Performance Primitives or a separate Metal path, replacing the 2.14 method of copying offsets to the CPU. A dedicated decoding path and specialized kernels for small groups further reduce GPU-CPU syncs and improve top-k routing.
- **Linear Layer Improvements**: `F.linear` now connects to GEMV kernels for common [1, 1, hidden_size] decoding inputs with fused bias additions. This resulted in a 1.23× geometric-mean speedup across 96 BF16 layer shapes from real models.
- **General GPU Acceleration**: Softmax over the vocabulary is approximately 8× faster, and there is increased GPU support for complex LU and triangular solves, QR decomposition, and small-matrix inverses.

## ⚙️ Key details

- **Video and Audio**: Faster paths are available for reductions, interpolation backward, dropout, padding, convolutions, and audio/video training. 
- **Memory Efficiency**: Wan2.2's tiled VAE video decode memory peak has been reduced from 270 GiB to approximately 8 GiB.
- **Bug Fixes**: A padding change fixes an issue where the Qwen-Image-2.1 VAE encoder corrupted images on MPS. Encode-decode round trips now match CPU at 29.95 dB PSNR, up from 10.06 dB.
- **Python Control**: Users now have access to public MPS streams and more reliable event timing.

## 🚀 Availability

- **System Requirements**: Apple silicon Mac running macOS 15 or later.
- **Software Requirements**: PyTorch 2.15 requires Python 3.11 or later.
- **Diagnostics**: The MPS availability check now specifies the reason if the OS is too old or no Metal GPU is available.

## 🔍 Looking Ahead

PyTorch 2.16 is expected to bring faster LLM decoding, more MPSGraph-to-Metal migrations, and attention fully implemented on Metal.

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/mps-pytorch-2-15/moe-decode-throughput.png)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/mps-pytorch-2-15/softmax-sampling.png)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/mps-pytorch-2-15/wan-vae-memory.png)

#PyTorch #AppleSilicon #Metal #LLM #MachineLearning

---

*Source: [MPS in PyTorch 2.15](https://huggingface.co/blog/mps-pytorch-2-15)*
