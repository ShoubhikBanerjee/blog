---
title: "Amazon SageMaker AI Introduces Concurrency Sweeps for Generative AI Endpoints"
slug: "amazon-sagemaker-ai-introduces-concurrency-sweeps-for-generative-ai-endpoints"
description: "Amazon SageMaker AI has updated its Inference Recommendations to include concurrency sweeps, a systematic benchmarking approach used to right-size generative AI endpoints by optimizing..."
date: 2026-09-22T22:03:42+05:30
tags: [AmazonSageMaker, vLLM, GenerativeAI, LLMInference, NVIDIA]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "AI Performance"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/17/ML-21905-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker AI Introduces Concurrency Sweeps for Generative AI Endpoints

Amazon SageMaker AI has updated its Inference Recommendations to include concurrency sweeps, a systematic benchmarking approach used to right-size generative AI endpoints by optimizing price-performance while maintaining acceptable latency.

## 🔍 Overview

A concurrency sweep sends controlled, increasing levels of simultaneous requests to a SageMaker AI endpoint to analyze performance. This feature is built into Amazon SageMaker AI Inference Recommendations, eliminating the need to build or maintain custom load-testing infrastructure.

## 🧩 How it works

The concurrency sweep measures two primary metrics at each level of traffic:
- **Throughput**: The number of tokens per second produced by the endpoint.
- **Latency**: The time taken for each request.

The workflow consists of four steps:
1. Deploy the model to a SageMaker AI endpoint using the native vLLM container.
2. Configure the workload profile (input and output token counts, streaming mode).
3. Run the concurrency sweep using the `CreateAIBenchmarkJob` API.
4. Analyze the results to identify optimal concurrency and right-size the fleet.

## ⚙️ Key details

In a deployment scenario using the NVIDIA Nemotron-3 Nano 30B Mixture-of-Experts (MoE) model on an `ml.g7e.2xlarge` instance (backed by an NVIDIA Blackwell GPU), the following configurations are applied:

| Configuration | Detail |
| :--- | :--- |
| Container | vLLM Deep Learning Container for SageMaker AI |
| `SM_VLLM_ENFORCE_EAGER` | Required for Nemotron-3 Nano's Mamba-Transformer hybrid architecture |
| GPU Memory Utilization | Set to 0.85 to provide headroom for KV cache growth |
| Prefix Caching | Enabled to reuse cached key-value pairs for repeated system prompts |

Workload profiles are defined using `CreateAIWorkloadConfig` with the following parameters:

| Parameter | Value | Description |
| :--- | :--- | :--- |
| `prompt_input_tokens_mean` | 1,024 | Average input prompt length |
| `output_tokens_mean` | 256 | Average generated response length |

Streaming is enabled to capture time to first token (TTFT) metrics for interactive user experiences. The benchmark engine (AIPerf) runs each concurrency level sequentially within a single job, sending the total number of requests defined under `request_count` at each level.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/17/ML-21905-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/17/ML-21905-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/17/ML-21905-3.jpg)

#AmazonSageMaker #vLLM #GenerativeAI #LLMInference #NVIDIA

---

*Source: [Right-size generative AI endpoints with concurrency sweeps on Amazon SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/right-size-generative-ai-endpoints-with-concurrency-sweeps-on-amazon-sagemaker-ai/)*
