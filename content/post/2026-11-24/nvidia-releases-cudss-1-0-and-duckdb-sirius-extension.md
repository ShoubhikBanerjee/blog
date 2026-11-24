---
title: "NVIDIA Releases cuDSS 1.0 and DuckDB Sirius Extension"
slug: "nvidia-releases-cudss-1-0-and-duckdb-sirius-extension"
description: "NVIDIA has released version 1.0 of its cuDSS library for sparse linear systems and collaborated with DuckLabs to release Sirius, a GPU-accelerated extension for DuckDB, enabling high-performance..."
date: 2026-11-24T12:08:32+05:30
tags: [NVIDIA, cuDSS, DuckDB, GPU, HighPerformanceComputing]
categories: ["AI", "High-Performance Computing", "Data Analytics", "Software Development", "Hardware"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2024/06/DatacenterKV-2-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases cuDSS 1.0 and DuckDB Sirius Extension

NVIDIA has released version 1.0 of its cuDSS library for sparse linear systems and collaborated with DuckLabs to release Sirius, a GPU-accelerated extension for DuckDB, enabling high-performance analytical queries on NVIDIA hardware.

## 🧩 How cuDSS Works
The cuDSS library is designed to solve large sparse linear systems for engineering and scientific simulations. It targets numerically challenging sparse systems, particularly symmetric indefinite ones, by offering symmetry-preserving matching and scaling as well as Bunch-Kaufman pivoting. 

- **Matching and Scaling**: Uses the HSL MC64 algorithm from the HSL collection of Fortran codes. This feature preserves symmetry and is enabled by default in cuDSS 1.0, improving accuracy and reducing memory and performance penalties associated with previous nonsymmetric matching.
- **Bunch-Kaufman Pivoting**: Allows 2×2 pivots to maintain factorization stability while preserving symmetry. The algorithm applies a local test to each column to choose between 1×1 pivots, interchanged 1×1 pivots, or 2×2 blocks.
- **Default Configuration**: cuDSS 1.0 defaults to using matching and scaling with `CUDSS_MATCHING_ALG_MAX_DIAG_PRODUCT` and Bunch-Kaufman pivoting with `CUDSS_PIVOT_BUNCH_KAUFMAN`. Users can restore previous behavior using `CUDSS_CONFIG_FORCE_NONSYMMETRIC_MATCHING`.

## 📊 cuDSS Performance
Benchmark matrices for cuDSS were selected from semiconductor design, manufacturing, and computer-aided engineering workflows, including circuit simulation, TCAD, thermal, structural, electromagnetic, and fluid dynamics. Performance was benchmarked against Intel MKL version 2026.1.0 using an NVIDIA B200 GPU and an Intel Xeon Platinum 8570 CPU. 

| Phase | Geometric-Mean Speedup |
| :--- | :--- |
| Analysis | 2.5x |
| Numerical Factorization | 5.9x |
| Triangular Solve | 151x |

cuDSS performance has improved over previous releases, with optimizations for superpanels in factorization, multithreaded analysis, and tuned solve-phase kernels. Developers can access these gains by upgrading without changing application code.

## 🐝 Sirius for DuckDB
Sirius is an open-source, GPU-native SQL engine developed through a collaboration between the University of Wisconsin–Madison and NVIDIA, released as a DuckDB core extension in partnership with DuckLabs. 

- **Integration**: Developers can install and load Sirius using two SQL commands (`INSTALL sirius;` and `LOAD sirius;`). It requires DuckDB 2.0 and an NVIDIA GPU with a compatible driver. 
- **Architecture**: DuckDB handles SQL parsing and optimization, while Sirius executes the resulting query plans on the GPU using a CUDA backend.
- **Performance**: In TPC-H benchmarks with data stored in Amazon S3, Sirius delivered significant speedups over CPU-based DuckDB. 
    - At Scale Factor 1,000 (1 TB), total query runtime fell from 347.3 seconds to 63.2 seconds.
    - At Scale Factor 3,000 (3 TB), runtime dropped from 752.4 seconds to 160.6 seconds, a 4.69x speedup.
    - With tuned settings, a two-GPU AWS instance configuration achieved 3.25x to 5.50x speedups over the best CPU-based configurations, reducing query-time compute cost by up to approximately 79%.

## 🚀 Availability
The general availability of cuDSS marks it as a production-ready library for commercial applications. Sirius is available as a DuckDB core extension, with a download size of approximately 700 MB.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/analysis-phase-speedup-cudss-1.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/factorization-phase-speedup-cudss-1.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/solve-phase-speedup-cudss-1.webp)

#NVIDIA #cuDSS #DuckDB #GPU #HighPerformanceComputing

---

*Source: [Accelerating Direct Sparse Solvers for Computational Engineering with NVIDIA cuDSS 1.0 | NVIDIA Technical Blog](https://developer.nvidia.com/blog/accelerating-direct-sparse-solvers-for-computational-engineering-with-nvidia-cudss-1-0/)*
*Source: [Get Started with GPU-Accelerated DuckDB Analytics Using the Sirius Core Extension | NVIDIA Technical Blog](https://developer.nvidia.com/blog/get-started-with-gpu-accelerated-duckdb-analytics-using-the-sirius-core-extension/)*
