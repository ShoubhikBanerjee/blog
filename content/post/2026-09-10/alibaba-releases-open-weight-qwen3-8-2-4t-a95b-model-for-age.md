---
title: "Alibaba Releases Open-Weight Qwen3.8-2.4T-A95B Model for Agentic Workloads"
slug: "alibaba-releases-open-weight-qwen3-8-2-4t-a95b-model-for-agentic-workloads"
description: "On August 12, 2026, Alibaba’s Qwen team released Qwen3.8-2.4T-A95B, marking the first time a Qwen-Max-class model has been made available as open weights. This model is the largest and most capable..."
date: 2026-09-10T12:09:25+05:30
tags: [Qwen, OpenWeights, LLM, AmazonSageMaker, AIagents]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21725-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Alibaba Releases Open-Weight Qwen3.8-2.4T-A95B Model for Agentic Workloads

On August 12, 2026, Alibaba’s Qwen team released Qwen3.8-2.4T-A95B, marking the first time a Qwen-Max-class model has been made available as open weights. This model is the largest and most capable in the Qwen family, designed for the most demanding reasoning and agentic workloads.

## 🧩 How it works

Qwen3.8-2.4T-A95B utilizes a hybrid linear-plus-full-attention architecture to enable efficient long-context inference:

*   **Gated DeltaNet layers:** 69 of 92 layers use linear attention with a bounded recurrent state, replacing the growing KV-cache with fixed-size memory.
*   **Gated Attention layers:** 23 of 92 layers use full quadratic attention for high-fidelity token interactions.
*   **Fine-grained MoE:** Capacity is distributed across 512 small experts to improve specialization and routing efficiency.

This 3:1 ratio of linear to full attention keeps compute and memory bounded as context scales toward 1M tokens.

## ⚙️ Key details

| Feature | Specification |
| :--- | :--- |
| Total Parameters | 2.4 Trillion |
| Activated Parameters | 95 Billion per token |
| Native Context | Up to 262K tokens (extensible to 1M) |
| Formats | Standard Transformers (Hugging Face) |
| Quantizations | MXFP4 and NVFP4 (W4A4) |

## 💡 Why it matters

Designed for agentic execution, the model targets capabilities including:

*   Multi-step coding
*   Long-horizon planning
*   Autonomous tool use
*   Complex research workflows

Developers can use the `reasoning_effort` parameter (low, medium, high) to trade compute for reasoning depth per request. According to vendor benchmarking, the model shows strength in terminal-based coding (86.6), instruction following (IFBench 82.8), and research workflows (PaperBench 93.0).

## 🚀 Availability

While the open weights allow data to stay within an organization's infrastructure and eliminate per-token API fees, hosting requires purpose-built GPU infrastructure. Deployment is supported on Amazon SageMaker HyperPod using vLLM on ml.p6-b300 instances (8× NVIDIA B300 Blackwell Ultra GPUs).

HyperPod utilizes Amazon Elastic Kubernetes Service (Amazon EKS) as the control plane and provides an Inference Operator with an `InferenceEndpointConfig` CRD to specify model and GPU resource requests. The ml.p6-b300.48xlarge instance type requires reserved capacity via Flexible Training Plans.

#Qwen #OpenWeights #LLM #AmazonSageMaker #AIagents

---

*Source: [Deploying Qwen3.8-2.4T-A95B on Amazon SageMaker HyperPod with vLLM | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/deploying-qwen3-8-2-4t-a95b-on-amazon-sagemaker-hyperpod-with-vllm/)*
