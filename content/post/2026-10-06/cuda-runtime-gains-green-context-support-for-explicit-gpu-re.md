---
title: "CUDA Runtime Gains Green Context Support for Explicit GPU Resource Partitioning"
slug: "cuda-runtime-gains-green-context-support-for-explicit-gpu-resource-partitioning"
description: "Multiple independent components – latency‑sensitive kernels, background throughput work, data‑preprocessing, or workflow stages – now often share a single GPU process. Controlling how GPU resources..."
date: 2026-10-06T22:08:14+05:30
tags: [CUDA, GPU, GreenContexts, ParallelComputing]
categories: ["AI", "GPU Programming", "Parallel Computing", "Computer Architecture"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image1-3-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# CUDA Runtime Gains Green Context Support for Explicit GPU Resource Partitioning

Multiple independent components – latency‑sensitive kernels, background throughput work, data‑preprocessing, or workflow stages – now often share a single GPU process. Controlling how GPU resources are shared between them remains difficult; components can interfere unpredictably and existing tools offer limited ability to partition resources.

## 🔍 Overview
Green contexts let applications explicitly select a subset of GPU execution resources and target work to those resources directly. This addresses the shortcomings of traditional CUDA contexts, which are heavyweight, incur hardware context‑switch overhead, and were designed for a era when a single dominant workload typically occupied the GPU.

## 🛠️ How it works
* **SM partitioning** – Assign a specific subset of Streaming Multiprocessors (SMs) to a green context; work submitted through that context runs only on those SMs, enabling concurrent workloads without competing for the same compute units.
* **Work‑queue provisioning** – Explicitly allocate workqueues to a green context, avoiding unintended serialization when independent stream‑ordered workloads would otherwise map to the same underlying workqueues.
* **Lightweight creation** – Green contexts are cheap to create and destroy and do not implicitly synchronize unrelated GPU work.
* **Explicit programming model** – Applications target work to a chosen green context rather than relying on implicit/current device state.

## ⚙️ Key details
| Feature | Description |
|---|---|
| Availability (Driver API) | Green contexts have been available since NVIDIA CUDA 12.4. |
| Availability (Runtime API) | Starting with CUDA 13.1, they are accessible through the Runtime API. |
| Runtime type | Represented by `cudaExecutionContext_t`, a Runtime abstraction for CUDA contexts. |
| Creation API | `cudaGreenCtxCreate()` returns a handle that can be passed to `cudaExecutionCtxStreamCreate()`. |
| Stream creation | Streams are created from the green context; work submitted to those streams uses the context’s resources. |
| Full‑device fallback | Applications can still use the traditional Runtime model or obtain the device‑wide context with `cudaDeviceGetExecutionCtx()`. |
| Minimal code impact | Code changes are minimal; the mental model becomes clearer by explicitly choosing a green context. |

## 🚀 Availability
* **Driver API** – green contexts have been supported since CUDA 12.4.
* **Runtime API** – support added in CUDA 13.1, enabling applications to define resource partitions without leaving the Runtime layer.

## 💡 Why it matters
GPU workloads often need a small, latency‑sensitive kernel to coexist with a larger, throughput‑oriented worker (e.g., communication/GEMM overlap in distributed training, or latency‑sensitive operators in AI sensor platforms like NVIDIA Holoscan). While CUDA stream priority is a standard tool for prioritizing such critical work, green contexts provide a more robust mechanism: by partitioning SMs and provisioning dedicated workqueues, applications can reduce interference, express expected concurrency, and keep latency‑sensitive kernels from being delayed by background work.

---


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2024/04/gpu-occupancy-workloads-featured-960x540.png)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2020/12/CUDA_3x2.jpg)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image4-1.webp)

#CUDA #GPU #GreenContexts #ParallelComputing

---

*Source: [Control How Your GPU Shares Work with Green Contexts | NVIDIA Technical Blog](https://developer.nvidia.com/blog/control-how-your-gpu-shares-work-with-green-contexts/)*
