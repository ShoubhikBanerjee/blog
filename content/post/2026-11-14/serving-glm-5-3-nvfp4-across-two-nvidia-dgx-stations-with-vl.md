---
title: "Serving GLM-5.3 NVFP4 Across Two NVIDIA DGX Stations with vLLM"
slug: "serving-glm-5-3-nvfp4-across-two-nvidia-dgx-stations-with-vllm"
description: "A tutorial demonstrates how to locally serve the NVIDIA GLM-5.3 NVFP4 model across two NVIDIA DGX Stations using vLLM and tensor parallelism. The setup connects both Stations over ConnectX-8 RDMA to..."
date: 2026-11-14T18:03:06+05:30
tags: [vLLM, NVIDIA, DGXStation, TensorParallelism, MixtureOfExperts, LLMInference]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "GPU Computing", "Model Deployment"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image3-3-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# Serving GLM-5.3 NVFP4 Across Two NVIDIA DGX Stations with vLLM

A tutorial demonstrates how to locally serve the NVIDIA GLM-5.3 NVFP4 model across two NVIDIA DGX Stations using vLLM and tensor parallelism. The setup connects both Stations over ConnectX-8 RDMA to serve requests through a single OpenAI-compatible API endpoint.

## 🔍 Overview

* **Model Scale:** NVIDIA GLM-5.3 NVFP4 is a quantized version of Z.ai's mixture-of-experts (MoE) model, containing 753 billion parameters with 40 billion parameters activated per token.
* **Memory Challenge:** The model checkpoint requires approximately 464 GB of storage, exceeding the 252 GB of HBM3e memory available on a single GB300 GPU.
* **GPU-Only Execution:** Sparse activation reduces token computation, but all weights must remain accessible because tokens route to different experts. Using two DGX Stations keeps all model weights in GPU memory with CPU weight offloading disabled.

## 🧩 How It Works

* **Tensor Parallelism (TP=2):** Splits the model's weights and computation evenly across the two GB300 GPUs.
* **Node Roles:** Station A (rank 0) hosts the OpenAI-compatible API server. Station B (rank 1) acts strictly as a worker node without an API server.
* **Request Execution:** Both Stations compute every incoming request simultaneously. Station A returns the final answer through the API endpoint.
* **Interconnect Validation:** The Stations communicate via ConnectX-8 RDMA over two direct rails (`cx8r0` and `cx8r1`). Pre-deployment checks confirm device mapping (such as `mlx5_1`) and IPv4 addressing to prevent NCCL timeouts.

## ⚙️ Key System Requirements

| Component / Requirement | Description |
| --- | --- |
| Hardware | Two GB300 DGX Stations running Linux, validated via the Connect Two DGX Stations playbook and GPU-memory RDMA test |
| Storage | At least 464 GB of free disk space per Station for the model checkpoint, container image, and temporary files |
| Container Image | `vllm/vllm-openai:v0.30.0-aarch64@sha256:4864d46625cbc3307623e29ac742030655e27249feba7b97ec925ce4cc4dfb56` |
| Model Source | Repository `nvidia/GLM-5.3-NVFP4` (revision `e3b8f9f2fad29727dfa95e766c5cac18ea1414bf`) stored at `$HOME/models/GLM-5.3-NVFP4` |
| User Access | SSH and sudo access on both Stations using the same Linux username; `docker` group membership |
| License & Datasets | Acceptance of NVIDIA Open Model Agreement, original GLM-5.3 license, SPEED-Bench (under NVIDIA Evaluation Dataset License Agreement), and access to Hugging Face gated dataset `cais/hle` |

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/04/gtc25-tech-blog-dgx-gb300-1920x1080-1-660x370.png)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/02/genai-visual-mixture-of-experts-3105423-e1772062206929-658x370.webp)

#vLLM #NVIDIA #DGXStation #TensorParallelism #MixtureOfExperts #LLMInference

---

*Source: [When One GPU Isn’t Enough: Serving GLM-5.3 Across Two NVIDIA DGX Stations with vLLM | NVIDIA Technical Blog](https://developer.nvidia.com/blog/when-one-gpu-isnt-enough-serving-glm-5-3-across-two-nvidia-dgx-stations-with-vllm/)*
