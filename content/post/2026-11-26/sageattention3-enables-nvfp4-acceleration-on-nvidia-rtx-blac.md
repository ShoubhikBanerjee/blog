---
title: "SageAttention3 enables NVFP4 acceleration on NVIDIA RTX Blackwell SM120"
slug: "sageattention3-enables-nvfp4-acceleration-on-nvidia-rtx-blackwell-sm120"
description: "NVIDIA has introduced SageAttention3, a native NVFP4 attention mechanism specifically designed for the NVIDIA RTX Blackwell streaming multiprocessor (SM) 120 architecture. This development addresses..."
date: 2026-11-26T22:08:01+05:30
tags: [NVIDIA, SageAttention3, NVFP4, Blackwell, GPU]
categories: ["AI", "GPU Computing", "Machine Learning", "Performance Optimization", "Computer Vision"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2025/10/floating-cubes-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# SageAttention3 enables NVFP4 acceleration on NVIDIA RTX Blackwell SM120

NVIDIA has introduced SageAttention3, a native NVFP4 attention mechanism specifically designed for the NVIDIA RTX Blackwell streaming multiprocessor (SM) 120 architecture. This development addresses the specific constraints of consumer and professional RTX GPUs, where existing hardware-specific pipelines from data center GPUs cannot be directly applied due to different Tensor Core architectures.

## 🧩 How it works
SageAttention3 performs both Query-Key ($QK$) and Attention-Weight Value ($PV$) matrix multiplications using NVFP4, a format introduced with the NVIDIA Blackwell architecture that offers hardware-accelerated 4-bit matrix multiplication. The mechanism utilizes register recycling and improved scheduling to accelerate attention performance beyond BF16.

- **Register Recycling**: By reclaiming score registers after softmax outputs are packed into NVFP4, the next tile’s matrix multiplication can overlap with remaining softmax work on the current tile.
- **Two-Level Scaling**: Since NVFP4 quantization generates an NVFP4 data tensor and an FP8 scaling tensor, and softmax outputs are bound to a narrow [0, 1] range that can underutilize NVFP4 dynamic range, the mechanism normalizes values to fully utilize the dynamic range before quantizing the result.
- **Tiled Execution**: In the tiled kernel, a Compute Thread Array (CTA) uses four producer warps and eight consumer warps. For each $N_{128}$ tile, consumers execute $QK$, softmax/probability quantization, and $PV$ in sequence.

## ⚙️ Key details
The hardware and software constraints driving this implementation include:

| Component/Aspect | Detail |
| :--- | :--- |
| **Target Hardware** | NVIDIA RTX PRO 6000 Blackwell Series (SM120) |
| **Limitation** | SM120 uses a different Tensor Core architecture than data center GPUs, preventing direct application of FlashAttention3/4 pipelines |
| **MMA Constraint** | OMMA operation is constrained to $m_{16}, n_{8}, k_{64}$; covering $k=128$ requires issuing two MMA instructions |
| **Data Loading** | TMA Loads are bound to $128 \times 128$ shapes to utilize GPU bandwidth |
| **Inference Context** | On NVIDIA RTX Blackwell, BF16 attention is primarily MMA-bound, whereas data center variants are softmax-bound |

## 🚀 Availability
Reactor, a developer platform providing infrastructure for real-time video and world models, has integrated this kernel into their production serving stack. The integration is currently serving real customer traffic and reporting speedups in performance.

#NVIDIA #SageAttention3 #NVFP4 #Blackwell #GPU

---

*Source: [How to Optimize NVFP4 Attention on NVIDIA RTX Blackwell Through Register Recycling | NVIDIA Technical Blog](https://developer.nvidia.com/blog/how-to-optimize-nvfp4-attention-on-nvidia-rtx-blackwell-through-register-recycling/)*
