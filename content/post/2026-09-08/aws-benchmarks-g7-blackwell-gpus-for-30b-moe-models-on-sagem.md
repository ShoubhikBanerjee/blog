---
title: "AWS benchmarks G7 Blackwell GPUs for 30B MoE models on SageMaker"
description: "Amazon Web Services (AWS) has published new benchmarks comparing NVIDIA Blackwell-powered G7 GPU instances against G5 and G6 families for deploying 30B-parameter Mixture-of-Experts (MoE) models on..."
date: 2026-09-09T00:16:34+05:30
tags: [AWS, SageMaker, NVIDIA, Blackwell, MoE, AIInference]
categories: []
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/02/ML-21730-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS benchmarks G7 Blackwell GPUs for 30B MoE models on SageMaker

Amazon Web Services (AWS) has published new benchmarks comparing NVIDIA Blackwell-powered G7 GPU instances against G5 and G6 families for deploying 30B-parameter Mixture-of-Experts (MoE) models on SageMaker. The tests focus on cost and performance improvements for large-scale AI inference workloads.

## 🔍 Overview
AWS evaluated two 30B MoE models—**Qwen3-Coder-30B** (for enterprise coding tasks) and **NVIDIA Nemotron-3-Nano-30B** (for reasoning/agentic workloads)—across GPU instance families using SageMaker's Generative AI Inference Recommendations. The study highlights G7 instances' efficiency gains despite using fewer accelerators and less memory.

## 🧩 How it works
- **Direct benchmarking**: Used DJL Large Model Inference (LMI) containers to compare:
  - `ml.g5.12xlarge` (A10G, 4 GPUs, 96GB memory)
  - `ml.g6.12xlarge` (L4, 4 GPUs, 96GB memory)
  - `ml.g7.12xlarge` (RTX PRO 4500 Blackwell, 2 GPUs, 64GB memory)
- **Automated optimization**: Leveraged SageMaker recommendations with vLLM to evaluate G6, G6e (L40S), and G7 configurations for throughput, latency, and cost-per-token.

## ⚙️ Key details
- **G7 advantages**: 
  - Native FP4 Tensor Core support (reduces model size to ~4 bits/weight with minimal quality loss)
  - Higher memory bandwidth improves MoE decoding efficiency
  - Achieves comparable performance to G5/G6 with half the GPUs and less memory
- **Instance comparisons**:
    | Instance Family | GPUs | Aggregate GPU Memory | Key Feature                  |
    |------------------|------|-----------------------|------------------------------|
    | G5               | 4    | 96GB                  | A10G (no FP4 acceleration)   |
    | G6               | 4    | 96GB                  | L4 (no FP4 acceleration)     |
    | G7               | 2    | 64GB                  | Blackwell (native FP4)       |

## 🚀 Availability
G7 instances are **generally available only in US East (Ohio) and US West (Oregon) regions**. 

## 💡 Why it matters
The benchmarks demonstrate that G7 instances deliver measurable improvements in throughput and latency for MoE architectures while optimizing costs. Native FP4 support provides a structural advantage for memory-bandwidth-bound MoE deployments, enabling efficient enterprise use of 30B-parameter models with reduced infrastructure footprint.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/02/ML-21730-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/02/ML-21730-2.png)

#AWS #SageMaker #NVIDIA #Blackwell #MoE #AIInference

---

*Source: [Benchmarking small LLM inference on SageMaker AI: G7 vs G5 and G6 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/benchmarking-small-llm-inference-on-sagemaker-ai-g7-vs-g5-and-g6/)*
