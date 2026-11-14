---
title: "cuBLAS Enhances FP64 Performance Using Integer Tensor Cores"
slug: "cublas-enhances-fp64-performance-using-integer-tensor-cores"
description: "NVIDIA cuBLAS now provides automatic acceleration for DGEMM (real 64-bit floating-point) and ZGEMM (complex 64-bit floating-point) operations without requiring application code changes. This..."
date: 2026-11-14T12:02:58+05:30
tags: [NVIDIA, cuBLAS, GPU, HPC, TensorCores]
categories: ["AI", "High Performance Computing", "Software Engineering", "Artificial Intelligence"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image5-7-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# cuBLAS Enhances FP64 Performance Using Integer Tensor Cores

NVIDIA cuBLAS now provides automatic acceleration for DGEMM (real 64-bit floating-point) and ZGEMM (complex 64-bit floating-point) operations without requiring application code changes. This capability leverages the Automatic Dynamic Precision (ADP) framework to map FP64 arithmetic onto integer Tensor Cores while maintaining native FP64 accuracy.

## 🧩 How it works
cuBLAS breaks double-precision numbers into integer pieces, performs multiplication on the GPU’s Tensor Cores, and reassembles the results. Both the Ozaki and 2M schemes align input matrix exponents and convert them to a shared-exponent, variable-length integer representation for accurate accumulation.

| Algorithm | Function | Efficiency Detail |
| :--- | :--- | :--- |
| Ozaki-I | DGEMM | Grows with the square of the slice count |
| Ozaki-II | DGEMM | Uses Chinese Remainder Theorem; linear scaling in number of moduli |
| 2M | ZGEMM | Cuts complex matrix multiplication from four real multiplications to two |

## ⚙️ Key details
*   **Heuristics:** cuBLAS automatically selects between Ozaki-I and Ozaki-II for optimal performance.
*   **Memory Management:** cuBLAS utilizes memory-parsimonious tiling, discarding residue pairs immediately after their corresponding GEMM operation.
*   **Fallback:** The system reverts to native FP64 MMA instructions if the required mantissa bits exceed library defaults or user-defined limits.
*   **New Format:** Rubin GPUs utilize the TI16 format (12-bit integer) to accelerate Ozaki computations via the tcgen05.mma instruction.

## 🚀 Performance Metrics
*   **DGEMM (Ozaki-II):** Achieves 5.5x and 3.9x speedups on NVIDIA VR NVL72 and GB200 respectively. Throughput reaches up to 175, 147, and 37 TFLOPS on VR NVL72, GB200, and RTX PRO 6000.
*   **ZGEMM (2M):** Achieves a 5x speedup over native Complex FP64 on the NVIDIA GB200.
*   **End-to-End (CCSD):** Achieves 2x and 1.4x speedups on VR NVL72 and GB200 using DGEMM with Ozaki-II.
*   **End-to-End (BerkeleyGW):** Achieves 6.6x and 3.9x speedups using ZGEMM with the 2M algorithm.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image5-7-1024x575-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image4-7.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image6-7.webp)

#NVIDIA #cuBLAS #GPU #HPC #TensorCores

---

*Source: [Faster Scientific Simulations with New FP64 Algorithms in NVIDIA cuBLAS | NVIDIA Technical Blog](https://developer.nvidia.com/blog/faster-scientific-simulations-with-new-fp64-algorithms-in-nvidia-cublas/)*
