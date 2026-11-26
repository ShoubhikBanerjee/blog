---
title: "llama.cpp and AMD Launch Benchmark Dashboard for Local AI Inference"
slug: "llama-cpp-and-amd-launch-benchmark-dashboard-for-local-ai-inference"
description: "The llama.cpp project and AMD have released a new benchmark dashboard for measuring local inference performance on AMD Ryzen and Radeon hardware. Available on Hugging Face, the dashboard enables..."
date: 2026-11-26T18:08:23+05:30
tags: [llamacpp, AMD, benchmarking, localinference]
categories: ["AI", "Machine Learning", "Hardware", "Artificial Intelligence"]
image: "https://cdn-uploads.huggingface.co/production/uploads/67289c93ff90038d9a6e5675/tbIvyMSISXCm64WYP3atl.png"
author: "Shoubhik Banerjee"
draft: false
---

# llama.cpp and AMD Launch Benchmark Dashboard for Local AI Inference

The llama.cpp project and AMD have released a new benchmark dashboard for measuring local inference performance on AMD Ryzen and Radeon hardware. Available on Hugging Face, the dashboard enables developers to track prompt processing and text generation performance across different llama.cpp builds, models, and quantizations.

## 📊 Overview
The dashboard is designed to make performance comparisons straightforward for AMD developers. Users can select specific hardware, models, and llama.cpp builds to compare quantizations and follow performance changes over time.

Key features include:
- Tracking PP512 (512 input tokens, no generation) and TG128 (128 generated tokens)
- Build history tab to monitor performance across all recorded builds
- Context scaling tab to observe how token-generation throughput changes as context grows
- Access to underlying benchmark results through public workflows

## ⚙️ Key Details
| Component | Description |
|---|---|    |------------|
| Hardware Options | Radeon 8060S (gfx1151), Radeon AI Pro R9700S (gfx1201) |
| Test Metrics | PP512 and TG128, both starting at context depth zero |
| Benchmark Frequency | Weekly public workflows |
| Model Set | Inkling 2 Mini, Qwen, Gemma, gpt-oss, and LFM models |
| GGUF Formats | Q4_K_M, Q8_0, BF16, F16 |

The benchmark workflows run with Flash Attention enabled and disabled, using 10 repetitions per configuration. Performance is measured as mean throughput (avg_ts) for both PP512 and TG128 tests.

## 🚀 Availability
The dashboard is hosted on Hugging Face and reads directly from the public ggml-org/install.sh-benches-data Storage Bucket. Users can click the data source link beside each chart title to access the underlying JSONL files for specific build, hardware, and model combinations.

Standard results follow the path format <build>/<hardware>/<model>/<quant>.jsonl, while workload sweeps use <quant>-tg.jsonl filenames.

## 💡 Why It Matters
This tool provides transparent, accessible performance data for local AI inference on AMD hardware, helping developers optimize their deployments and understand the impact of different quantization strategies and hardware configurations.

#llama.cpp #AMD #benchmarking #local-inference

---

*Source: [Introducing the llama.cpp benchmark dashboard for AMD Ryzen and Radeon](https://huggingface.co/blog/ggml-org/llamacpp-amd-bench)*
