---
title: "Amazon SageMaker HyperPod Inference Gateway for GPU-Aware Routing"
slug: "amazon-sagemaker-hyperpod-inference-gateway-for-gpu-aware-routing"
description: "Amazon has announced the Amazon SageMaker HyperPod Inference Gateway, a Kubernetes-native, GPU-aware routing system designed to optimize how inference requests are placed on GPU clusters."
date: 2026-09-18T22:02:10+05:30
tags: [AmazonSageMaker, Kubernetes, LLM, GPU, CloudComputing]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/16/ML-21822-featured-image-2.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker HyperPod Inference Gateway for GPU-Aware Routing

Amazon has announced the Amazon SageMaker HyperPod Inference Gateway, a Kubernetes-native, GPU-aware routing system designed to optimize how inference requests are placed on GPU clusters.

## 💡 Why it matters
Running large language models (LLMs) at scale on GPU clusters is expensive, and default Kubernetes load balancers can exacerbate this. Standard round-robin and least-connections algorithms lack visibility into GPU internals, such as:
* Saturated KV caches
* Long-context generations in progress
* Loaded LoRA adapters in memory

These limitations cause requests to pile up behind busy pods while idle capacity remains unused, leading to unpredictable GPU utilization, wasted spend, and first-token latency spikes of 4+ seconds during traffic bursts.

## 🧩 How it works
The Inference Gateway uses a two-tier design built on Kubernetes-native primitives:

| Tier | Deployment | Function |
| :--- | :--- | :--- |
| Tier 1 | amazon-sagemaker-hyperpod-inference addon | Installs on each HyperPod/EKS cluster to handle local intelligent routing using real-time GPU signals. |
| Tier 2 | Built on top of Tier 1 | Provides fleet-wide coordination across multiple clusters and regions, including global rate limiting, cost-aware traffic shaping, and cross-cluster failover. |

## ⚙️ Key details
* **Deployment**: Deploys as a single EKS managed addon on existing HyperPod infrastructure using a declarative `InferenceGatewayConfig` custom resource.
* **Compatibility**: Exposes a standard OpenAI-compatible endpoint.
* **Request Routing**: The Body-Based Router natively routes requests to the correct model pool based on the model field in the request body via defined schedulers.
* **LoRA Optimization**: The EPP’s LoRA Affinity Scorer identifies pods with the requested adapter resident in GPU memory to eliminate adapter swap latency. If no pod has it loaded, the request is routed to the pod with the most available capacity to load it quickly.
* **Tuning**: Each scorer includes a configurable weight to tune routing for specific workloads, such as throughput-optimized batch or latency-sensitive chat.

#AmazonSageMaker #Kubernetes #LLM #GPU #CloudComputing

---

*Source: [Introducing Amazon SageMaker HyperPod Inference Gateway | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-amazon-sagemaker-hyperpod-inference-gateway/)*
