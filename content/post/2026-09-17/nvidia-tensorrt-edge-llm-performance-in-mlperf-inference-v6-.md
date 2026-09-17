---
title: "NVIDIA TensorRT Edge-LLM Performance in MLPerf Inference v6.1 Edge Agentic Benchmark"
slug: "nvidia-tensorrt-edge-llm-performance-in-mlperf-inference-v6-1-edge-agentic-benchmark"
description: "NVIDIA TensorRT Edge-LLM has completed the MLPerf Inference v6.1 Edge Agentic benchmark running the Qwen3.6-27B model on a single NVIDIA Jetson AGX Thor Developer Kit."
date: 2026-09-17T12:07:20+05:30
tags: [MLPerf, TensorRT, JetsonAGXThor, EdgeAI, LLM]
categories: ["AI", "Machine Learning", "Edge Computing", "Artificial Intelligence"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image5-6-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA TensorRT Edge-LLM Performance in MLPerf Inference v6.1 Edge Agentic Benchmark

NVIDIA TensorRT Edge-LLM has completed the MLPerf Inference v6.1 Edge Agentic benchmark running the Qwen3.6-27B model on a single NVIDIA Jetson AGX Thor Developer Kit.

## ⚙️ Key details

The system was configured with the following specifications:
* **Hardware**: One NVIDIA Jetson AGX Thor Developer Kit
* **Memory**: 128 GB of unified memory
* **Power Mode**: MAXN
* **Execution Mode**: SingleStream
* **Model**: Qwen3.6-27B

## 📊 Performance results

The TensorRT Edge-LLM submission completed the performance workload in 24 minutes and 36 seconds, which is 6.4x faster than the llama.cpp reference submission of 2 hours and 37 minutes.

| Metric | Value |
| :--- | :--- |
| Output throughput | 52.33 tokens per second |
| Median time to first token | 247.12 ms |
| Median time per output token | 14.68 ms |
| BFCL overall accuracy | 87.94% |

## 🧩 How it works

The result was achieved using several optimization techniques:

* **Quantization**: The submission used NVFP4 (a 4-bit floating-point format supported by the NVIDIA Blackwell GPU) for weights and activations, including the language-model head, and FP8 for the KV cache. This smaller representation increases available unified memory for application workloads, speculative decoding state, and long context.
* **KV Cache Reuse**: TensorRT Edge-LLM identifies reusable prompt prefixes and restores cached attention KV pages. Because Qwen3.6 uses a hybrid model architecture, the runtime also restores partial KV-page state and the recurrent state. In this workload, approximately 96% of prompt tokens were served with hot cache, requiring the prefill of only ~0.5M of the 13.6M total prompt tokens.
* **Tree-based Multi-Token Prediction (MTP)**: A draft model predicts several future tokens which the target model verifies together in one forward pass. The server configuration utilized:
    * 8 draft steps
    * Top-2 candidates at each drafting depth
    * A 16-node verification tree

## 🔍 Overview

The MLPerf Edge Agentic benchmark measures OpenAI-compatible model endpoints across two phases:

* **Performance**: The workload consists of 20 conversations and 1,007 generated turns. Input length grows to approximately 23.5K tokens.
* **Accuracy**: This phase uses Berkeley Function Calling Leaderboard (BFCL) v4 prompts with reasoning off and single-turn only to balance evaluation time and accuracy on edge devices.

#MLPerf #TensorRT #JetsonAGXThor #EdgeAI #LLM

---

*Source: [TensorRT Edge-LLM Completes the MLPerf Edge Agentic Benchmark 6.4x Faster on Jetson AGX Thor | NVIDIA Technical Blog](https://developer.nvidia.com/blog/tensorrt-edge-llm-completes-the-mlperf-edge-agentic-benchmark-6-4x-faster-on-jetson-agx-thor/)*
