---
title: "NVIDIA Releases CUDA Toolkit 13.4 with Windows on Arm and Rubin GPU Support"
slug: "nvidia-releases-cuda-toolkit-13-4-with-windows-on-arm-and-rubin-gpu-support"
description: "NVIDIA has released CUDA Toolkit 13.4, introducing support for Windows on Arm and early developer preview support for the next-generation Rubin GPU architecture. This update focuses on enhancing GPU..."
date: 2026-09-10T22:04:27+05:30
tags: [CUDA, NVIDIA, WindowsOnArm, Rubin, GPU]
categories: ["AI", "Parallel Computing", "Software Development", "GPU Architecture"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/06/cuda-python-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases CUDA Toolkit 13.4 with Windows on Arm and Rubin GPU Support

NVIDIA has released CUDA Toolkit 13.4, introducing support for Windows on Arm and early developer preview support for the next-generation Rubin GPU architecture. This update focuses on enhancing GPU management, improving data transport across NVLink fabric, and expanding memory management capabilities for high-performance computing.

## 🔍 Overview
CUDA applications, which have long been supported on Arm platforms through Linux, can now be developed for the Windows on Arm platform. The release also adds functional support for the NVIDIA Rubin architecture (compute capability 107) as a preview, allowing developers to begin porting applications before general availability. Rubin is identified as the next-generation architecture powering agentic AI.

## ⚙️ Key details
* **Multi-process Server (MPS) V3:** Features a modernized control layer with a scriptable CLI, named server instances, and namespaces to organize concurrent workloads.
* **CUDA Compute Fabric Transport (CFT):** A transport-centric method for moving data across NVLink fabric at scale using logical endpoints instead of virtual address mapping.
* **Locality Domains:** Exposes programmatic access to specific portions of a GPU containing streaming multiprocessors (SMs) and device memory.
* **Memory Management:** The driver now defaults to Coherent Driver-based Memory Management (CDMM) on coherent platforms such as NVIDIA Grace Hopper, Grace Blackwell, and Vera Rubin.
* **Installer Changes:** CUDA SDK installers no longer bundle the NVIDIA driver; the `nvidia-open` driver or `cuda-toolkit` packages must be installed separately.

## 🧩 How it works
| Component | Functionality |
| :--- | :--- |
| MPS V3 | Provides TOML configuration support, SM partition controls, and cgroup-integrated GPU memory limits for precise partitioning. |
| CFT | Supports asynchronous put, get, and reduction operations directly from the GPU; reports completion and error status for fabric transfers. |
| SM_107 | New architecture target enabling compilation for Rubin GPUs. |
| CUDA Python 1.1.0 | Expands the stable API with texture and surface programming and improved CUDA graph integration. |
| Locality Domains | Allows applications to allocate device memory and create green contexts with SM resources in the same domain. |

## 🚀 Availability
Functional support for the NVIDIA Rubin architecture is currently in preview. CUDA Compute Fabric Transport is available exclusively through the CUDA Driver API and is intended for developers of communication libraries. Host compiler compatibility for this release has been extended to include GCC 16 and Clang 22.

## 💡 Why it matters
MPS V3 ensures that GPU resources can be maximized in containerized environments while maintaining strict resource isolation for every process. Additionally, the new CFT approach reduces virtual-address pressure in large multi-GPU systems, supporting both unicast and multicast communication patterns for advanced applications.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/06/cuda-python-1024x576.png)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/Agentic-AI-Qwen-660x370.png)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2021/06/CUDA-toolkit-featured.png)

#CUDA #NVIDIA #WindowsOnArm #Rubin #GPU

---

*Source: [CUDA Toolkit 13.4 Adds Windows on Arm Support and Greater Control over Shared GPUs | NVIDIA Technical Blog](https://developer.nvidia.com/blog/cuda-toolkit-13-4-adds-windows-on-arm-support-and-greater-control-over-shared-gpus/)*
