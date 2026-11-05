---
title: "NVIDIA Advances Agentic Inference with Rubin Architecture and NVFP4 Numerical Precision"
slug: "nvidia-advances-agentic-inference-with-rubin-architecture-and-nvfp4-numerical-precision"
description: "NVIDIA is advancing its AI factory capabilities through the new Rubin architecture and NVFP4 precision. The company treats AI performance as a co-designed challenge involving GPU architecture,..."
date: 2026-11-05T22:04:09+05:30
tags: [NVIDIA, Rubin, AIInference, HBM4, DeepLearning]
categories: ["AI", "GPU Architecture", "Artificial Intelligence", "Hardware Engineering"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image5-1-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Advances Agentic Inference with Rubin Architecture and NVFP4 Numerical Precision

NVIDIA is advancing its AI factory capabilities through the new Rubin architecture and NVFP4 precision. The company treats AI performance as a co-designed challenge involving GPU architecture, scale-up interconnects, serving software, CPUs, and storage to achieve significant throughput gains for agentic inference.

## ⚙️ Rubin Architecture and Performance

NVIDIA Rubin increases memory bandwidth significantly while maintaining capacity to optimize the most contested memory tier in AI factories.

- Rubin memory bandwidth has risen to 19.2 TB/s, while capacity holds at 288 GB of HBM4.
- The NVIDIA Vera Rubin NVL72 delivers up to 30x the throughput per megawatt of the GB300 NVL72 at 160 tokens per second per user.
- Each Rubin GPU provides 3.0 TB/s of NVLink 6 bandwidth, enabling approximately 20.7 TB of aggregate HBM4 across a rack.
- Rubin adds inline memory tensor accelerator (TMA) descriptor updates, allowing one shared descriptor to serve experts with a common layout and reducing metadata overhead.

## 🧩 NVFP4 Numerical Precision

NVFP4 is a new numerical format that uses a 4-bit E2M1 element with two levels of scaling: an FP8 (E4M3) scale factor for every 16-value micro-block and a per-tensor FP32 scale. It has become the default precision for agentic benchmarks including AA-AgentPerf, SemiAnalysis AgentX, and MLPerf Endpoints.

| Metric | Benefit of NVFP4 |
| :--- | :--- |
| Model Footprint | 3.5x reduction relative to FP16; 1.8x reduction relative to FP8 |
| KV Cache Footprint | Up to 50% reduction compared to FP8 |
| Resident Context | Approximately 2x more context stays on device |
| Throughput | Up to 4x the throughput of an FP8 baseline |

## 🔍 Mixture-of-Experts Scaling

To manage Mixture-of-Experts (MoE) models where all expert weights must reside in HBM, NVIDIA utilizes Wide expert parallelism (Wide-EP) through NVIDIA TensorRT-LLM.

- **Wide-EP:** Spreads experts across eight or more GPUs. For DeepSeek-R1 at EP64, each GPU holds four experts per layer (232 blocks) instead of the full model.
- **Expert Parallel Load Balancer (EPLB):** Redistributes hot and cold experts between forward passes to prevent GPU memory overcommitment.
- **NVLink Interconnect:** On GB200 NVL72, 130 TB/s of aggregate NVLink bandwidth absorbs all-to-all dispatch and combine traffic. 
- **Performance:** Large EP (EP32) delivers up to 1.8x more output tokens per second per GPU than small EP (EP8) at 100 tokens per second per user.

## 💡 Distributed Serving with Dynamo

NVIDIA Dynamo acts as the distributed serving layer to manage the key-value (KV) cache, which stores intermediate attention calculations from previously processed tokens. The Dynamo router tracks where KV blocks reside and considers both worker load and cached-prefix overlap when placing requests. This architecture leads to higher cache-hit rates during prefill and less bandwidth consumption during decode.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/dynamo-memory.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image5-1-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image8-3.webp)

#NVIDIA #Rubin #AIInference #HBM4 #DeepLearning

---

*Source: [Five Ways NVIDIA Co-Design Maximizes the Value of Every Byte in the AI Factory | NVIDIA Technical Blog](https://developer.nvidia.com/blog/five-ways-nvidia-co-design-maximizes-the-value-of-every-byte-in-the-ai-factory/)*
