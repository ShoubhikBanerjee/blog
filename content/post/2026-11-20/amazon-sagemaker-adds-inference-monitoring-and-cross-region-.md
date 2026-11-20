---
title: "Amazon SageMaker adds inference monitoring and cross-Region routing"
slug: "amazon-sagemaker-adds-inference-monitoring-and-cross-region-routing"
description: "Amazon SageMaker AI has introduced new capabilities for managing generative AI inference endpoints, including a feature for optimized inference recommendations and a new resource for cross-Region..."
date: 2026-11-20T06:16:59+05:30
tags: [AmazonSageMaker, InferenceRouting, LLMOps, AWS, GenerativeAI]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "Generative AI"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22416-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker adds inference monitoring and cross-Region routing

Amazon SageMaker AI has introduced new capabilities for managing generative AI inference endpoints, including a feature for optimized inference recommendations and a new resource for cross-Region inference routing.

## 🔍 Overview

Inference endpoints are typically well-tuned at launch, but traffic patterns evolve, prompts grow longer, and serving engines ship new releases. Consequently, well-tuned endpoints quietly drift, leading to latency increases or idle GPU capacity. SageMaker AI now monitors endpoints to surface performance and cost improvement opportunities and introduces a router that provides a single invocation path across multiple AWS Regions and accounts.

## 🧩 How it works

The monitoring feature uses an agentic experience in Amazon SageMaker Studio to analyze operational signals, including latency, GPU utilization, and serving configuration. It does not read user requests or responses. The system follows a four-step loop: observe, notify, recommend, and decide. Observing involves monitoring latency and capacity on default-eligible endpoints. When issues are detected, notifications are sent via AWS Health. The recommendation step opens the agentic experience in SageMaker Studio to benchmark alternatives on separate compute. Users then decide whether to apply results, ensuring production endpoints are not changed without explicit action.

The cross-Region inference routing feature uses a new resource called the inference router. Applications register destinations that serve a model and invoke the router instead of a specific endpoint. The router prefers destinations in its own Region and shifts traffic to other registered destinations only when the local one cannot serve reliably. It publishes health states (healthy, overloaded, degraded) to Amazon CloudWatch based on server errors, throttles, and timeouts, without requiring user-tuned thresholds.

## ⚙️ Key details

Monitoring features and routing targets are summarized below:

| Feature | Key Details |
| :--- | :--- |
| **Monitoring** | Enabled by default for vLLM containers on GPU instances; analyzes latency and capacity without reading request/response data; no additional GPU cost. |
| **Findings** | Surfaces latency drift (p50 latency rise), unused capacity (idle GPUs), and configuration gaps (missing patches or optimizations). |
| **Notifications** | Sent via AWS Health (one per endpoint) and email, explaining observations and next steps. |
| **Benchmarks** | Run on separate compute; users can compare response time, throughput, and cost per million tokens. |
| **Inference Router** | Prefers local Region; fails over to registered destinations in other Regions/accounts; passes InferenceId and CustomAttributes. |
| **Health Scoring** | Server errors lower scores; request-caused errors do not; model latency is not an input. |

## 🚀 Availability

The monitoring feature is on by default for SageMaker AI inference endpoints using vLLM serving containers and GPU instances, with the option to opt out. The inference router can be created in a specific AWS Region to prefer that location, and it works across one or more AWS Regions and AWS accounts. Existing direct InvokeEndpoint calls continue to function alongside the router.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22416-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22416-2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22416-3-1.png)

#AmazonSageMaker #InferenceRouting #LLMOps #AWS #GenerativeAI

---

*Source: [Amazon SageMaker AI now detects latency drift, idle GPUs, and missed optimizations on your inference endpoints | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/amazon-sagemaker-ai-now-detects-latency-drift-idle-gpus-and-missed-optimizations-on-your-inference-endpoints/)*
*Source: [Keep inference running through regional capacity shortfalls with cross-Region inference routing in Amazon SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/keep-inference-running-through-regional-capacity-shortfalls-with-cross-region-inference-routing-in-amazon-sagemaker-ai/)*
