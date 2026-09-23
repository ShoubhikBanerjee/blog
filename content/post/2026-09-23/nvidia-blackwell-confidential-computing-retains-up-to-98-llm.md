---
title: "NVIDIA Blackwell Confidential Computing retains up to 98% LLM inference throughput"
slug: "nvidia-blackwell-confidential-computing-retains-up-to-98-llm-inference-throughput"
description: "NVIDIA demonstrated that running a 32K‑input/1K‑output LLM inference workload inside confidential virtual machines (CVMs) on a Blackwell‑based DGX B200 system keeps almost all of the baseline..."
date: 2026-09-23T22:05:40+05:30
tags: [NVIDIA, ConfidentialComputing, LLMInference]
categories: ["AI", "Machine Learning", "Hardware", "Security"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2024/12/cybersecurity-graphic-1-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Blackwell Confidential Computing retains up to 98% LLM inference throughput

NVIDIA demonstrated that running a 32K‑input/1K‑output LLM inference workload inside confidential virtual machines (CVMs) on a Blackwell‑based DGX B200 system keeps almost all of the baseline performance.

## 🔍 Overview
NVIDIA Confidential Computing (CC) provides memory‑encrypted CVMs, confidential GPUs, and encrypted NVLink, enabling LLM inference to run securely while preserving throughput.

## 🧩 How it works
- **Secure data path** – The Blackwell CC architecture enforces hardware‑based protection for data and workloads in use.
- **Host‑to‑device transfer** – In the B200 CC, transfers go through a software‑encrypted bounce buffer because the GPU cannot directly access protected CVM memory.
- **TensorRT LLM adaptations**
  - Uses CC‑aware memory selection, opting for pageable memory on protected paths instead of always using pinned memory.
  - Moves repeated‑token and sampling‑data readback to an asynchronous worker, so protected copies do not block the main scheduler during decode.
  - Measures tactics with the GPU `%globaltimer` inside CC while keeping CUDA events outside CC.
- **NVLink limitation** – NVLS (NVLink SHARP) multicast is not available in B200 CC configurations.

## ⚙️ Key details
- **Model**: `nvidia/DeepSeek-R1-0528-NVFP4`
- **Inference framework**: TensorRT LLM (Docker container) with PyTorch backend
- **Sequence lengths**: 32K input, 1K output
- **Parallelism**: TP=8, EP=1, PP=1; KV cache in FP8
- **Concurrency tested**: 1, 2, 4, 8, 16 requests
- **Hardware**: 1 NVIDIA DGX B200 system (8 NVIDIA B200 GPUs), GPU power limit 1,000 W
- **Platform**: Intel TDX
- **Host OS / kernel**: Ubuntu 25.10 / 6.17.0-20-generic
- **Guest OS / kernel**: Ubuntu 24.04.4 LTS / 6.8.0-124-generic, 256 vCPUs, 2 NUMA nodes
- **Driver / software stack**: NVIDIA driver 595.71.05, VBIOS FW 1.4.x, CUDA 13.2, TensorRT LLM 1.3.0rc22, NCCL v2.30, OpenSSL 3.6.0, Docker + NVIDIA Container Toolkit

## 📈 Performance results
- Across concurrency levels 1–16, CC retained **96.1 %–98.2 %** of the output‑token throughput compared with a non‑confidential baseline.
- Mean TPOT (time‑per‑output‑token) stayed within **1.2 %–4.3 %** of the baseline.
- These results show that the security overhead of CC is limited to a few percent while providing full data protection.

## 💡 Why it matters
The Blackwell confidential computing architecture creates a hardware‑enforced security path that protects data in use without sacrificing most of the inference performance required for large‑scale LLM deployments.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/cc-on-off-output-token-throughput.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/mean-tpot-cc-on-off.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2023/07/confidential-computing-featured.png)

#NVIDIA #ConfidentialComputing #LLMInference

---

*Source: [Enabling Private High-Performance Production AI Inference with NVIDIA Confidential Computing | NVIDIA Technical Blog](https://developer.nvidia.com/blog/enabling-private-high-performance-production-ai-inference-with-nvidia-confidential-computing/)*
