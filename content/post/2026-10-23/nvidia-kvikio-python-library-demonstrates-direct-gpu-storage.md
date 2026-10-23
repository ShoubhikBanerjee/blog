---
title: "NVIDIA KvikIO Python Library Demonstrates Direct GPU Storage Access via GPUDirect Storage"
slug: "nvidia-kvikio-python-library-demonstrates-direct-gpu-storage-access-via-gpudirect-storage"
description: "NVIDIA’s Magnum IO GPUDirect Storage (GDS) now works with the KvikIO Python library to let AI applications move data directly from storage into GPU memory, bypassing the CPU."
date: 2026-10-23T18:02:55+05:30
tags: [NVIDIA, GPUDirectStorage, KvikIO, AI, Python]
categories: ["AI", "Machine Learning", "Hardware Acceleration", "Data Engineering", "Python Development"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/03/ai-data-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA KvikIO Python Library Demonstrates Direct GPU Storage Access via GPUDirect Storage

NVIDIA’s Magnum IO GPUDirect Storage (GDS) now works with the KvikIO Python library to let AI applications move data directly from storage into GPU memory, bypassing the CPU.

## 🔍 Overview
- GPU applications are processing ever‑growing datasets with increasingly powerful accelerators.
- The 2025 Stanford AI Index reports that compute for notable AI models has been doubling roughly every five months, while the size of datasets used to train LLMs has been doubling roughly every eight months.
- As computation and data scale together, moving data efficiently from storage becomes a necessity for keeping accelerators supplied.
- NVIDIA Magnum IO GPUDirect Storage (GDS) addresses this challenge by enabling a direct data path between supported storage and GPU memory.
- The direct path avoids unnecessary staging through CPU memory and reduces overall CPU utilization in the system.
- GDS is supported by a growing ecosystem that includes many major storage vendors.
- At the application layer, Python plays a central role in modern AI development; as of August 2025, nearly half of all new AI projects on GitHub were built primarily in Python.

## 🧩 How It Works
| Component | Role |
|---|---|
| **GPUDirect Storage (GDS)** | Enables a direct data path between supported storage and GPU memory. |
| **cuFile** | C library and API through which applications and frameworks access GDS. |
| **KvikIO** | Python and C++ library that sits above cuFile, providing high‑level, idiomatic interfaces and additional controls over how I/O requests are performed. |

- The application supplies a file‑system path and a GPU buffer.
- KvikIO decides whether to route the request through cuFile (direct path) or use its POSIX compatibility path, which stages data through host memory.
- When cuFile is selected, KvikIO registers the file and issues the I/O using the target GPU buffer.
- cuFile then determines the actual transfer path based on system support, the file system, and its configuration; it may use the accelerated GDS path or fall back to a CPU‑staged compatibility path.
- Reaching the cuFile API confirms that KvikIO selected cuFile, but does not by itself confirm that the accelerated GDS path was activated.

## ⚙️ Tutorial Highlights
- Demonstrates how to use the NVIDIA KvikIO Python API to configure storage I/O, read data into GPU memory, and confirm that the accelerated path within GDS was activated.
- Shows how to inspect KvikIO and cuFile settings that influence the path each operation takes.
- Tested on an x86_64 system with an NVIDIA H100 GPU, CUDA 13.3, and cuFile 1.18.
- The system used a local NVMe device formatted with ext4; a PIX connection between the GPU and NVMe device means the path traverses at most one PCIe bridge.
- IOMMU and ACS were disabled to preserve PCIe peer‑to‑peer transfers, and the `nvidia-fs` kernel module was loaded to provide the accelerated path.

## 💡 Why It Matters
- Doubling compute and dataset sizes increase pressure on the storage‑to‑GPU data pipeline.
- Direct storage‑to‑GPU transfers reduce CPU overhead, freeing CPU resources for other parts of the AI workload.
- Providing a high‑level Python interface (KvikIO) aligns with the fact that nearly half of new AI projects are Python‑centric, lowering the barrier for developers to adopt accelerated I/O.
- A growing storage‑vendor ecosystem around GDS broadens hardware compatibility for future AI systems.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/execution-flow-nvidia-kvikio.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/terminal-check-session-kvikio-gds-diagnostic.gif)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/03/ai-data-1024x576.png)

#NVIDIA #GPUDirectStorage #KvikIO #AI #Python

---

*Source: [How to Read Data into GPU Memory in Python with NVIDIA GPUDirect Storage | NVIDIA Technical Blog](https://developer.nvidia.com/blog/how-to-read-data-into-gpu-memory-in-python-with-nvidia-gpudirect-storage/)*
