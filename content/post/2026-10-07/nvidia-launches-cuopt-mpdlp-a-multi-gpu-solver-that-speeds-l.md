---
title: "NVIDIA launches cuOpt mPDLP, a multi‑GPU solver that speeds large LPs up to 10×"
slug: "nvidia-launches-cuopt-mpdlp-a-multigpu-solver-that-speeds-large-lps-up-to-10"
description: "Supply‑chain networks and modern energy grids are becoming more complex, stretching existing planning tools.  To keep pace, teams must evaluate larger models and cope with higher uncertainty within..."
date: 2026-10-07T22:09:50+05:30
tags: [LinearProgramming, GPUComputing, SupplyChain, EnergySystems]
categories: ["AI", "Optimization", "High‑Performance Computing", "Supply Chain Management", "Energy Systems"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/geometric-structure-1-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA launches cuOpt mPDLP, a multi‑GPU solver that speeds large LPs up to 10×

Supply‑chain networks and modern energy grids are becoming more complex, stretching existing planning tools.  To keep pace, teams must evaluate larger models and cope with higher uncertainty within practical planning windows, but today’s biggest problems often take hours to converge or exceed the memory of a single GPU, creating a bottleneck for business‑critical workflows.

## 🔍 Overview
- Supply‑chain problems are expanding across more SKUs, lanes, and constraints than ever before.  
- Energy grids are balancing more distributed sources in real time.  
- GPU‑accelerated decision optimization already delivers >10× speedup over CPU solvers for large‑scale linear programming (LP) problems.
- The new cuOpt Multi‑GPU Primal‑Dual hybrid gradient for Linear Programming (mPDLP) solver pushes the limits further by solving the benchmark zib03 on multiple GPUs with a solve rate nearly 10× faster than a year before.
- Partner applications include Kinaxis (globally constrained supply and production planning) and PSR (large‑scale energy‑system capacity‑expansion models).

## 🧩 How it works
- **Primal‑Dual hybrid gradient (PDLP)**: a first‑order, gradient‑descent‑like method that is highly parallelizable and GPU‑friendly.
- **Hot loop**: Sparse Matrix‑Vector Multiplication (SpMV) followed by several map operations.  All map operations are trivial to distribute across GPUs.
- **Distributed challenge**: SpMV is memory‑bound; increasing bandwidth directly speeds the operation.
- **Bandwidth solutions**: either wait for the next GPU generation or add more GPUs, multiplying total bandwidth.
- **Multi‑GPU distribution**:
  1. Reorder the matrix to improve load balancing.
  2. Partition the matrix into sub‑blocks along rows and columns.
  3. Perform an SpMV on each sub‑block, then sum partial results to reconstruct the full output.
- This approach builds on earlier D‑PDLP work and demonstrates the potential of multi‑GPU acceleration.

## ⚙️ Key Details
- **Performance**: >10× speedup over CPU solvers on a single GPU; mPDLP is ~10× faster than the prior single‑GPU cuOpt version.
- **Scale**: Handles the zib03 benchmark (over 104 million non‑zeros) that many solvers cannot fit in a single GPU’s memory.
- **Hardware stack**:
  - **NVLink** – fast point‑to‑point GPU‑GPU data exchange.
  - **NVSwitch** – orchestrates communication among many GPUs.
- **Software stack**:
  - **NCCL** – C/C++ library for GPU‑direct point‑to‑point and collective operations (AllReduce, AllGather, Broadcast) that leverage NVLink/NVSwitch.
- **Result**: With NVLink, NVSwitch, and NCCL, multiple GPUs behave as one high‑bandwidth shared machine, keeping data on the GPU and allowing the algorithm to scale without CPU involvement.

| Component | Role |
|-----------|------|
| NVLink    | Fast, optimized GPU‑to‑GPU data exchange |
| NVSwitch  | Efficiently orchestrates communication among several GPUs |
| NCCL      | Provides GPU‑direct point‑to‑point and collective operations |

## 🚀 Availability
The mPDLP solver is now part of the NVIDIA cuOpt portfolio and can be deployed on systems equipped with NVLink/NVSwitch‑enabled GPUs.

---
*Figures illustrating solve‑time improvements and benchmark performance are available in the image list.*

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/progression-solve-times-zib03.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/wall-clock-speedup-comparison-cuopt-mpdlp-versus-single-gpu-cuopt.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/performance-comparison-cuopt-mpdlp-d-pdlp-benchmark-datasets.webp)

#LinearProgramming #GPUComputing #SupplyChain #EnergySystems

---

*Source: [Scaling Decision Optimization to 100 Million Variables and Beyond with mPDLP in NVIDIA cuOpt | NVIDIA Technical Blog](https://developer.nvidia.com/blog/scaling-decision-optimization-to-100-million-variables-and-beyond-with-mpdlp-in-nvidia-cuopt/)*
