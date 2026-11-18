---
title: "NVIDIA Introduces Daviator and Mixed Precision for DFT GPU Acceleration"
slug: "nvidia-introduces-daviator-and-mixed-precision-for-dft-gpu-acceleration"
description: "NVIDIA has introduced two new capabilities to address performance bottlenecks in generating ground-truth data for machine learning interatomic potentials (MLIPs): a library called Daviator for..."
date: 2026-11-18T22:09:17+05:30
tags: [DFT, VASP, GPUComputing, HPC, MLIP, NVIDIA]
categories: ["AI", "High-Performance Computing", "Scientific Computing", "GPU Acceleration", "Materials Science"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image4-10-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Introduces Daviator and Mixed Precision for DFT GPU Acceleration

NVIDIA has introduced two new capabilities to address performance bottlenecks in generating ground-truth data for machine learning interatomic potentials (MLIPs): a library called Daviator for batched GPU kernels and a new mixed-precision execution layer. These updates target the high volume of density functional theory (DFT) calculations required to train next-generation models, offering up to 22x faster time-to-solution and up to 75% lower cost compared to CPU execution.

## 🔍 The Problem with Current GPU DFT
Training MLIPs requires tens to hundreds of millions of DFT calculations. Plane-wave DFT, primarily implemented via VASP, is the standard for this task. While VASP’s OpenACC implementation speeds up large-system calculations, it struggles with the small unit cells and dense k-point grids common in MLIP data generation.

In periodic systems with small unit cells, hundreds to thousands of k-points are required. Currently, VASP processes these k-points sequentially on the GPU. For small systems, this results in significant kernel launch overhead that dominates compute time. A single-atom iron system with 752 k-points, for instance, ran 8x slower on GPU hardware than on CPU. Additionally, modern NVIDIA GPUs are increasingly optimized for lower-precision data types (FP32), while traditional DFT runs in FP64, creating a gap in available throughput.

## 🧩 How Daviator and Mixed Precision Work
**Daviator** is a library of GPU kernels that replaces sequential per-k-point processing with batched operations. Its core is a batched Davidson eigensolver that swaps sequential loops for batched FFTs, GEMMs, and custom kernels. This approach reduces GPU kernel launches, allowing Streaming Multiprocessor (SM) occupancy to reach near saturation. Data remains resident in GPU memory, while VASP retains ownership of the self-consistent field (SCF) loop, mixing, symmetry, and I/O.

The **mixed-precision execution layer** enables further performance gains by leveraging GPUs with a high FP32:FP64 throughput ratio. This is particularly effective on inference-class and workstation GPUs, such as the RTX PRO 6000, which features a 64:1 FP32:FP64 ratio.

## ⚙️ Key Details and Benchmarks
- **Integration:** Daviator is accessible through the NVIDIA ALCHEMI VASP microservice by setting `LDAVIATOR=True` in the `INCAR` file. Existing VASP inputs work without modification.
- **Performance:** On a projected reference dataset workload, the combination of these features shows up to 22x faster time-to-solution and up to 75% lower cost compared to CPU execution.
- **Speed-ups:** Daviator overcomes OpenACC limitations, achieving over 2x speed-ups relative to the CPU baseline for a single iron atom.
- **Configuration:** Users must set specific environment variables to ensure efficient kernel caching:
  - `export CUDA_CACHE_PATH=/tmp/cudacache`
  - `export CUDA_CACHE_DISABLE=0`

## 🚀 Availability and Limitations
Daviator is currently available for single-node execution. Multi-node support, coverage for systems with non-collinear spins (`vasp_ncl`), and explicit gamma-only runs (`vasp_gam`) are expected in a later stage. Some GPU kernels may trigger compilation on first use depending on the batch size.

## 💡 Why It Matters
As AI workloads drive GPU hardware development toward lower-precision data types, the stagnation of FP64-only code performance threatens the scalability of DFT data generation. By addressing small-system GPU inefficiency and leveraging mixed precision, these capabilities allow researchers to generate the massive datasets required for MLIP training more efficiently and at a lower cost.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/mlip-tensor-core-featured-660x370-jpg.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image4-10-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image11.webp)

#DFT #VASP #GPUComputing #HPC #MLIP #NVIDIA

---

*Source: [Tackling GPU Bottlenecks in Plane-Wave DFT with K-Point Batching and Mixed Precision | NVIDIA Technical Blog](https://developer.nvidia.com/blog/tackling-gpu-bottlenecks-in-plane-wave-dft-with-k-point-batching-and-mixed-precision/)*
