---
title: "GPU Fractioning Operator Enables Fine‑Grained GPU Sharing in Kubernetes"
slug: "gpu-fractioning-operator-enables-finegrained-gpu-sharing-in-kubernetes"
description: "Many AI workloads need only a fraction of a GPU, and allocating a whole device to each workload can leave capacity idle. An open‑source Kubernetes operator called **gpu‑fractioning** now lets..."
date: 2026-10-28T22:03:50+05:30
tags: [GPUSharing, Kubernetes, CUDA, AIWorkloads]
categories: ["AI", "Machine Learning", "Cloud Computing", "Container Orchestration", "Hardware Acceleration"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/CUDAMemoryKV-660x370.webp"
author: "Shoubhik Banerjee"
draft: false
---

# GPU Fractioning Operator Enables Fine‑Grained GPU Sharing in Kubernetes

Many AI workloads need only a fraction of a GPU, and allocating a whole device to each workload can leave capacity idle. An open‑source Kubernetes operator called **gpu‑fractioning** now lets platform teams share GPUs at the memory and compute level, using new CUDA 13.4 enforcement features and NVIDIA’s existing sharing mechanisms.

## 🔍 Overview
- AI workloads often require only part of a GPU’s memory and compute resources.
- Sharing GPUs lets platform teams serve more workloads with the same hardware.
- NVIDIA GPUs already support several sharing approaches: MIG, time‑slicing, and Multi‑Process Service (MPS).

## 🛠️ How it works
- **CUDA 13.4 memory enforcement**: a workload requests a memory size; CUDA reserves it and rejects allocations that exceed the limit, giving the workload a guaranteed minimum and a maximum it can grow into when memory is free.
- **Compute modes**: each workload can run in the default time‑sharing mode or choose the sm‑sharing mode (MPS) that runs processes concurrently in separate address spaces.
- The enforcement logic runs on the node; it is independent of the scheduler that placed the workload.

## ⚙️ Key components
- **gpu‑fractioning operator** (hosted under the KAI Scheduler GitHub organization) – sets up MPS on every GPU node, applies per‑workload memory limits and compute mode, and measures usage per fraction.
- **NVIDIA GPU Operator** – provides the driver and container‑runtime setup; gpu‑fractioning runs alongside it.
- **Pod annotations** – developers specify resource limits and compute mode in the pod YAML; the scheduler writes the chosen GPU slice and mode into per‑container annotations.
- **GPU Fractioning Operator** – reads those annotations and configures the assigned GPUs to enforce the requested memory and compute settings.
- **KAI Scheduler** – first scheduler integrated with gpu‑fractioning; from version v0.18.0 it offers a sharing mode called **NvFractions** that selects a slice of a GPU for each workload and writes the required annotations.

## 🚀 Availability
- The gpu‑fractioning operator is open source and lives on GitHub under the KAI Scheduler organization.
- It works with any Kubernetes scheduler capable of writing the required annotations; KAI Scheduler is the reference implementation.
- Starting with KAI Scheduler v0.18.0, the NvFractions mode is available out‑of‑the‑box.

## 💡 Why it matters
- Enables multiple AI workloads to run on a single GPU without idle capacity.
- Provides transparent memory enforcement and optional compute sharing modes.
- Allows administrators to choose the sharing strategy that best fits their cluster.

### GPU sharing techniques in NVIDIA GPUs
| Technique | Key property |
|-----------|--------------|
| Multi‑Instance GPU (MIG) | Splits a GPU into hardware‑isolated instances that are transparent to the application |
| Time‑slicing | Lets several processes take turns without memory enforcement |
| Multi‑Process Service (MPS) – sm‑sharing | Runs processes concurrently in separate address spaces |


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/CUDAMemoryKV-1024x576.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/kai-scheduler-representation-660x370.jpg)

#GPUSharing #Kubernetes #CUDA #AIWorkloads

---

*Source: [Memory-Enforced GPU Sharing in Kubernetes with NVIDIA CUDA 13.4 | NVIDIA Technical Blog](https://developer.nvidia.com/blog/memory-enforced-gpu-sharing-in-kubernetes-with-nvidia-cuda-13-4/)*
