---
title: "NVIDIA CUDA 13.5 Features Vera Rubin Support and Enhanced Multi-Process Service"
slug: "nvidia-cuda-13-5-features-vera-rubin-support-and-enhanced-multi-process-service"
description: "NVIDIA CUDA 13.5 has reached general availability, bringing the NVIDIA Vera Rubin architecture to enterprise production. This update provides new platform support, including Windows on Arm for DGX..."
date: 2026-11-05T06:03:43+05:30
tags: [CUDA, NVIDIA, VeraRubin, MPS, GPU]
categories: ["AI", "Software Development", "Parallel Computing", "Enterprise Infrastructure"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image1-16-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA CUDA 13.5 Features Vera Rubin Support and Enhanced Multi-Process Service

NVIDIA CUDA 13.5 has reached general availability, bringing the NVIDIA Vera Rubin architecture to enterprise production. This update provides new platform support, including Windows on Arm for DGX Station, and introduces advanced customization for GPU work scheduling through locality domains and Multi-Process Service (MPS) v3.

## 🔍 Overview
- NVIDIA CUDA 13.5 achieves general availability (GA) across major new platforms.
- NVIDIA Vera Rubin support has moved to GA, making it ready for enterprise production.
- Windows on Arm support, which has been GA since CUDA 13.4, now extends to the NVIDIA DGX Station for Windows.
- Enhanced GPU scheduling is introduced via locality domains and updated MPS controls.

## ⚙️ Key details
- **SM Resource Control:** Applications can choose between uniform streaming multiprocessor (SM) partitions or utilize the `cudaDevSmResourceGroupLocalityDomainSupplementalSms` flag to include all available SMs in selected domains.
- **Driver Compatibility:** Starting with the Rubin architecture, CUDA supports Windows Driver Display Model (WDDM) and Microsoft Compute Driver Model (MCDM), while Tesla Compute Cluster (TCC) is no longer supported.
- **CUDA Graph Enhancements:** Support is added for batched 1D memory copies, enabling `cudaMemcpyBatchAsync` calls to be captured and replayed within reusable graph workflows.
- **CUDA Tile Kernels:** Kernels can now perform direct multi-GPU communication and call SIMT library device functions from cuTile Python or CUDA Tile C++ on data already in registers or shared memory.

## 🧩 How it works
| Feature | Functionality |
| :--- | :--- |
| Weighted timeslicing | Scales the base compute timeslice per MPS server to give longer compute turns to specific workloads. |
| SM partition load balancing | Enables workloads to borrow capacity via `--max-chunks` and lend SMs when idle using `--shareable=true`. |
| Cgroup-based routing | Maps cgroup v2 subtrees to MPS namespaces to route clients automatically through the daemon's main socket. |
| Polling memory accounting | Provides a fallback for usage and limit verification; forced via `nvidia-cuda-mps-control memacct set force_polling=true`. |
| Multi-GPU access | Uses unicast pointers for NVLink-connected GPUs and multicast pointers for NVSwitch fabrics with NVLink SHARP support. |

In addition to these features, applications can use discovery mode within the `cudaDevSmResourceSplit()` API to obtain partition SM counts. MPS v3 also ensures that borrowed resources are reclaimed before reassignment, while applications continue to see a stable base partition size.

## 🚀 Availability
- **Enterprise Production:** NVIDIA Vera Rubin support is now in general availability.
- **Platform Extensions:** Windows on Arm support is now available for NVIDIA DGX Station for Windows.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2025/12/CUDA-MPS-e1765825617242-657x370.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image1-16-1024x576-png.webp)

#CUDA #NVIDIA #VeraRubin #MPS #GPU

---

*Source: [NVIDIA CUDA 13.5 Brings NVIDIA Vera Rubin GA Support | NVIDIA Technical Blog](https://developer.nvidia.com/blog/nvidia-cuda-13-5-brings-nvidia-vera-rubin-ga-support/)*
