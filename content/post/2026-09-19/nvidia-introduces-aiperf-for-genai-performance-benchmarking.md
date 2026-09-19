---
title: "NVIDIA Introduces AIPerf for GenAI Performance Benchmarking"
slug: "nvidia-introduces-aiperf-for-genai-performance-benchmarking"
description: "NVIDIA has released AIPerf, a ground-up rewrite and the designated successor to GenAI-Perf for measuring AI performance."
date: 2026-09-19T18:02:19+05:30
tags: [NVIDIA, AIPerf, GenAI, Benchmarking, LLM]
categories: ["AI", "Machine Learning", "AI Infrastructure", "Software Development"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image3-10-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Introduces AIPerf for GenAI Performance Benchmarking

NVIDIA has released AIPerf, a ground-up rewrite and the designated successor to GenAI-Perf for measuring AI performance.

## 🔍 Overview

AIPerf is a multiprocessed system that operates differently than its predecessor by not running on top of Perf Analyzer. The system utilizes worker processes to generate load and separate record-processor services to handle results, with coordination managed over ZMQ.

## ⚙️ Key details

AIPerf includes the following capabilities:

* **Endpoint Support:** Supports over 15 endpoint types, including chat, responses, NIM rankings, and image generation.
* **Dataset Integration:** Supports public datasets like ShareGPT and trace replay formats from WEKA (AgentX), Baseten, and Mooncake.
* **Arrival Patterns:** Supports gamma, Poisson, and constant arrival patterns with tunable burstiness and gradual ramping for request rate and concurrency.
* **Synthetic Distributions:** Includes vLLM/SGLang range-ratio for variable ISL/OSL.

## 📊 Performance Metrics

Once a run completes, AIPerf writes full results to JSON and CSV and prints a metrics table to the console. Each metric is reported in percentile breakdowns (p25, p50, p75, p90, p95, p99).

| Metric | Description |
| :--- | :--- |
| TTFT (Time to First Token) | How long from request sent to first token received |
| ITL (Inter-Token Latency) | Time between successive tokens during generation |
| Request Latency | End-to-end time for the full response |
| Output Token Throughput | Tokens generated per second across all concurrent requests |

## 🚀 Availability

AIPerf can be installed using `uv`:

```bash
uv tool install aiperf
uv venv venv
source venv/bin/activate
uv pip install aiperf
```

Note: On aarch64, the crick dependency requires a C toolchain (Development Tools on RHEL or build-essential on Debian/Ubuntu) as it ships as source-only.

#NVIDIA #AIPerf #GenAI #Benchmarking #LLM

---

*Source: [Benchmarking LLM Inference at Scale with AIPerf | NVIDIA Technical Blog](https://developer.nvidia.com/blog/benchmarking-llm-inference-at-scale-with-aiperf/)*
