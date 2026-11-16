---
title: "NVIDIA Vera Rubin Architecture Debuts in MLPerf Training v6.1"
slug: "nvidia-vera-rubin-architecture-debuts-in-mlperf-training-v6-1"
description: "NVIDIA's Vera Rubin architecture has made its debut in MLPerf Training v6.1, showcasing impressive performance and scalability. The new architecture, along with its CUDA software stack, has..."
date: 2026-11-16T22:14:27+05:30
tags: [NVIDIA, VeraRubin, MLPerf, AITraining, CUDA, DeepLearning]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Computer Hardware", "Software Development"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/techblog_featured2_1520x855-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Vera Rubin Architecture Debuts in MLPerf Training v6.1

NVIDIA's Vera Rubin architecture has made its debut in MLPerf Training v6.1, showcasing impressive performance and scalability. The new architecture, along with its CUDA software stack, has demonstrated significant advancements in AI training capabilities.

## 🔍 Overview
- MLPerf Training v6.1 marks the debut of the NVIDIA Vera Rubin architecture.
- Vera Rubin NVL72 platform delivered the fastest time to train on six of the seven benchmarks.
- NVIDIA platforms hold the fastest time to train on every benchmark in v6.1.
- Vera Rubin successfully completed the entire suite in its inaugural run.

## ⚙️ Key Details
- Vera Rubin NVL72 achieved up to 2x more performance than a highly optimized NVIDIA GB300 NVL72 baseline.
- For the DeepSeek-V3 671B benchmark, NVIDIA demonstrated massive scale on a 10,240-GPU GB300 NVL72 cluster.
- Vera Rubin maintained above 97% overall efficiency when scaling from 256 to 1,024 GPUs.
- NVIDIA platforms were the only ones to submit results across all seven benchmarks.

## 🚀 Availability
- The Vera Rubin architecture is now available and has been tested in MLPerf Training v6.1.

## 💡 Why it Matters
- The performance gains span the entire modeling pipeline, supporting everything from large-scale pretraining to reinforcement learning post-training.
- The new architecture is designed to handle the most demanding workloads, including the 671-billion-parameter token-dropless Mixture-of-Experts (MoE) model.
- The Vera Rubin platform also proved its flexibility by submitting on two different inference backends: NVIDIA NeMo RL with TensorRT-LLM and with vLLM.
- The NVIDIA Vera CPU is integral to the architecture, sustaining more than 22,500 concurrent RL environments across 256 CPUs in a single Vera CPU rack.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/techblog_featured2_1520x855-1024x576-jpg.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image4-8.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image2-11.webp)

#NVIDIA #VeraRubin #MLPerf #AITraining #CUDA #DeepLearning

---

*Source: [NVIDIA Vera Rubin NVL72 Achieves up to 2x Blackwell Ultra Performance in MLPerf Training v6.1 | NVIDIA Technical Blog](https://developer.nvidia.com/blog/nvidia-vera-rubin-nvl72-achieves-up-to-2x-blackwell-ultra-performance-in-mlperf-training-v6-1/)*
