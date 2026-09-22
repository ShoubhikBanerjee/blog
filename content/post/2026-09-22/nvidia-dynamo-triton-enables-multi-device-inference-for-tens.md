---
title: "NVIDIA Dynamo-Triton Enables Multi-Device Inference for TensorRT"
slug: "nvidia-dynamo-triton-enables-multi-device-inference-for-tensorrt"
description: "NVIDIA has updated its software stack to allow a single TensorRT network to execute across multiple GPUs. This development integrates NVIDIA TensorRT multi-device inference with NVIDIA Dynamo-Triton..."
date: 2026-09-22T06:03:33+05:30
tags: [NVIDIA, TensorRT, TritonInferenceServer, GenerativeAI, GPU]
categories: ["AI", "Machine Learning", "AI Infrastructure", "GPU Computing"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/grid-robot-arm-cleaning-plate-1-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Dynamo-Triton Enables Multi-Device Inference for TensorRT

NVIDIA has updated its software stack to allow a single TensorRT network to execute across multiple GPUs. This development integrates NVIDIA TensorRT multi-device inference with NVIDIA Dynamo-Triton to bridge the gap between multi-GPU acceleration and consumable inference services.

## 🔍 Overview

NVIDIA TensorRT multi-device inference enables a network to run across multiple GPUs using NCCL-backed distributed collectives while maintaining TensorRT inference optimizations. NVIDIA Dynamo-Triton (formerly NVIDIA Triton Inference Server) release 26.07 now enables this capability through its TensorRT backend.

## 🧩 How it works

* **Model Management**: A single Triton `KIND_MODEL` instance can own multiple GPUs, creating CUDA streams, NCCL communicators, and per-rank TensorRT execution contexts.
* **Client Interaction**: The application calls one named model via a gRPC endpoint. The client does not coordinate GPU ranks itself; instead, the Dynamo-Triton TensorRT backend loads the versioned plan, creates the multi-rank execution state, and exposes the endpoint.
* **Compilation**: The distributed graph is compiled into each TensorRT plan before deployment. Dynamo-Triton activates this plan rather than converting a single-device engine into a distributed one.
* **Parallelism**: Using Ulysses context parallelism, workloads can be distributed across as many as eight NVIDIA GPUs. Within the 36 transformer layers, Ulysses changes the partitioning axis around attention so every rank processes the full video sequence for a nonoverlapping subset of heads.

## ⚙️ Key details

In a demonstration using NVIDIA Cosmos 3 Nano video generation, the system processed 44,160 video tokens. The transformer stage was identified as the highest-impact area for acceleration, accounting for 93.4% of single-GPU generation time.

| Component/Metric | Detail |
| :--- | :--- |
| Engine Export | Exported from PyTorch and compiled with Torch-TensorRT |
| Distributed Collectives | reduce-scatter, all-to-all, and all-gather |
| Per-Plan Collectives | Two initial reduce-scatters, three all-to-alls per transformer layer, and one final all-gather |
| Performance (1 GPU) | 156.595 seconds end-to-end latency |
| Performance (8 GPUs) | 34.183 seconds end-to-end latency |
| Transformer RPC Speedup | 6.09 times (at 8 GPUs) |

## 🚀 Availability

* **TensorRT**: Fully supported starting with version 11.0.
* **Dynamo-Triton**: Multi-device inference capability is enabled in release 26.07.

## 💡 Why it matters

As generative AI compute and memory demands increasingly exceed the capacity of a single GPU, this integration allows organizations to:

* Trade additional GPU resources for shorter request latency.
* Keep application interfaces and surrounding workflows stable.
* Remove rank and communicator lifecycle code from the client.
* Reduce user wait times and accelerate review-and-refine cycles in latency-sensitive generative media workflows.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/nvidia-triton-tensorrt-application-workflow-multi-gpu-execution.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/ullysses-context-parallelism-one-transformer-layer.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/end-to-end-triton-transformer-rpc-latency-across-gpu-configurations.webp)

#NVIDIA #TensorRT #TritonInferenceServer #GenerativeAI #GPU

---

*Source: [Simplifying Model Serving Across Multiple GPUs with NVIDIA TensorRT Multi-Device Integration in NVIDIA Dynamo-Triton | NVIDIA Technical Blog](https://developer.nvidia.com/blog/simplifying-model-serving-across-multiple-gpus-with-nvidia-tensorrt-multi-device-integration-in-nvidia-dynamo-triton/)*
