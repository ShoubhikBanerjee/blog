---
title: "NVIDIA Vera Rubin Achieves 10× Agentic Throughput Per Kilowatt in MLPerf Endpoints v1.0"
slug: "nvidia-vera-rubin-achieves-10-agentic-throughput-per-kilowatt-in-mlperf-endpoints-v1-0"
description: "NVIDIA released provisional results for its Vera Rubin NVL72 platform in the MLPerf Endpoints v1.0 benchmark, showing more than 10× the agentic throughput per kilowatt compared to the verified GB300..."
date: 2026-11-16T22:14:27+05:30
tags: [MLPerf, NVIDIA, Inference, AgenticWorkloads, Throughput]
categories: ["AI", "Machine Learning", "AI Agents", "Benchmarking", "Performance"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/mlperf-endpoints-vera-rubin-featured-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Vera Rubin Achieves 10× Agentic Throughput Per Kilowatt in MLPerf Endpoints v1.0

NVIDIA released provisional results for its Vera Rubin NVL72 platform in the MLPerf Endpoints v1.0 benchmark, showing more than 10× the agentic throughput per kilowatt compared to the verified GB300 NVL72 while maintaining a minimum end‑to‑end interactivity of 50 tokens per second per user.

## 🔍 Overview
- Agentic workloads are demanding more from inference systems.
- AI agents carry growing conversation histories across turns and generate a mix of reasoning, tool calls, and responses.
- Inference systems must support users at scale while remaining responsive.
- The MLPerf Endpoints v1.0 dataset captures coding trajectories that accumulate history over many turns and enterprise workflows that reuse shared instructions, tool definitions, and business rules.

## 🧩 How It Works
- The benchmark evaluates serving capacity and responsiveness using coding and enterprise workflows through API endpoints.
- During performance runs, generated tool calls and workflow intent are checked against reference values.
- Separate SWE‑bench Verified evaluations assess end‑to‑end task‑solving capability.
- These checks evaluate whether faster serving preserves model quality.

## ⚙️ Key Details
- **Vera Rubin NVL72 (32 accelerators)**
  - Run 9: concurrency = 1,024 queries
  - TTFT P90 = 4,673.9 ms
  - System TPS = 41,414.2 tokens/sec
  - E2E average interactivity = 50.4 tokens/sec per user
  - Operating power = 100.89 kW
- **GB300 NVL72 (48 accelerators)**
  - Run 6: concurrency = 48 queries
  - TTFT P90 = 2,305.1 ms
  - System TPS = 2,210.4 tokens/sec
  - E2E average interactivity = 56.2 tokens/sec per user
  - Operating power = 60 kW

## 📊 Performance Results for Model Variants
- **Kimi K3**
  - Vera Rubin: run 9, 1,024 queries, 41,414.2 TPS, 50.4 interactivity, 100.89 kW
  - GB300: run 6, 48 queries, 2,210.4 TPS, 56.2 interactivity, 60 kW
- **DeepSeek‑V4.1‑Flash**
  - Vera Rubin: run 6, 1,408 queries, 272,711.7 TPS, 294.49 interactivity, 75.67 kW
  - GB300: run 1, 16 queries, 3,054.0 TPS, 288.65 interactivity, 7.50 kW
- **Qwen3.6‑35B‑A3B**
  - Vera Rubin: run 8, 320 queries, 47,785.5 TPS, 411.9 interactivity, 12.61 kW
  - GB300: run 2, 36 queries, 5,960.4 TPS, 531.6 interactivity, 7.50 kW

## 📈 Tradeoff Curve
- Figure 2 shows the tradeoff between throughput per provisioned kilowatt and E2E interactivity across at least seven concurrency levels per curve.
- The curves illustrate how much throughput each system delivers at a given responsiveness requirement.

## 🔬 Verification Status
- GB300 results are verified by the MLCommons Association.
- Vera Rubin results are provisional.
- Pending MLCommons Association verification, results may change.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/mlperf-endpoints-vera-rubin-featured-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/mlperf-endpoints-figure-2-updated-e1794616402812.webp)

#MLPerf #NVIDIA #Inference #AgenticWorkloads #Throughput

---

*Source: [NVIDIA Vera Rubin NVL72 Leads Agentic Inference Performance on MLPerf Endpoints v1.0 | NVIDIA Technical Blog](https://developer.nvidia.com/blog/nvidia-vera-rubin-nvl72-leads-agentic-inference-performance-on-mlperf-endpoints-v1-0/)*
