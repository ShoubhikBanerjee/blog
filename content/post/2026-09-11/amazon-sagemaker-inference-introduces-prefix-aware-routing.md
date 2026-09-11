---
title: "Amazon SageMaker Inference Introduces Prefix-Aware Routing"
slug: "amazon-sagemaker-inference-introduces-prefix-aware-routing"
description: "Amazon SageMaker Inference has introduced prefix-aware routing, a new routing strategy designed to optimize how requests are handled by instances."
date: 2026-09-11T22:04:55+05:30
tags: [AmazonSageMaker, LLM, Inference, MachineLearning]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/10/ML-21885-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker Inference Introduces Prefix-Aware Routing

Amazon SageMaker Inference has introduced prefix-aware routing, a new routing strategy designed to optimize how requests are handled by instances.

## 🧩 How it works

Prefix-aware routing analyzes the beginning of each request payload to determine which instance should handle it. Its primary functions include:

* **Consistency**: Requests with the same beginning are consistently sent to the same instance.
* **Distribution**: Different beginnings are spread across different instances.
* **Cache Optimization**: If multiple requests share a prefix, they are routed to the same machine to keep that machine's cache warm.
* **Automated Management**: The endpoint handles routing based on request content; users do not need to manage affinity or tag requests.
* **Load Balancing**: If a target instance is at capacity due to a popular prefix, the endpoint routes the request to a less busy instance.
* **Stability**: Most requests continue going to the same instance when instances are added or removed.

## ⚙️ Key details

Amazon SageMaker Inference now offers three routing strategies for real-time endpoints:

| Strategy | Description |
| :--- | :--- |
| RANDOM | The default routing strategy. |
| LEAST_OUTSTANDING_REQUESTS | Routes based on outstanding requests. |
| PREFIX_AWARE | New strategy that routes based on the request beginning. |

Users can set the strategy per production variant in the endpoint configuration and switch between strategies without redeploying the model.

## 💡 Why it matters

In benchmarks using Llama 3.1 70B Instruct on 7 ml.p5.48xlarge instances with vLLM (prefix caching enabled), prefix-aware routing showed the following results compared to the random routing baseline:

**General Impact**
* P50 TTFT reduced by up to 77 percent.
* Throughput increased by up to 16 percent.
* KV cache hit rates increased from roughly 25 percent to over 80 percent.

**Specific Test Scenarios**
* **8,000-token shared prefixes (sustained over 1 hour)**:
    * P50 TTFT: Reduced by 71–77 percent.
    * P90 TTFT: Reduced by 33–37 percent.
    * Throughput: Increased 15–16 percent.
    * KV cache hit rate: Increased from approximately 25 to 82 percent.
* **Variable-length ShareGPT-style conversations (30 minutes)**:
    * P50 TTFT: Reduced by 13–16 percent.
    * P90 TTFT: Reduced by 24–37 percent.
    * Throughput: Increased 1.7–2.0 percent.
    * KV cache hit rate: Increased from approximately 30 to 80 percent.

**Performance Overhead**
* The routing logic adds 1.3–1.9 milliseconds per request, while model TTFT in tests ranged from 63–280 milliseconds.
* Traffic distribution remained balanced, with each of the 7 instances receiving 13.3–15.4 percent of requests.

#AmazonSageMaker #LLM #Inference #MachineLearning

---

*Source: [Reduce LLM latency with prefix-aware routing on Amazon SageMaker Inference | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/reduce-llm-latency-with-prefix-aware-routing-on-amazon-sagemaker-inference/)*
