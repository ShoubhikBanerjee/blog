---
title: "Amazon SageMaker JumpStart Adds One‑Click Model Deployment and Pre‑Configured Endpoints (2026 Update)"
slug: "amazon-sagemaker-jumpstart-adds-oneclick-model-deployment-and-preconfigured-endpoints-2026-update"
description: "Amazon SageMaker JumpStart, the service that gives users access to a broad catalog of pretrained models, announced two 2026 improvements that make finding and deploying models easier."
date: 2026-10-14T22:09:38+05:30
tags: [AWS, SageMaker, JumpStart, AIModels]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence", "MLOps"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/12/ML-22153-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker JumpStart Adds One‑Click Model Deployment and Pre‑Configured Endpoints (2026 Update)

Amazon SageMaker JumpStart, the service that gives users access to a broad catalog of pretrained models, announced two 2026 improvements that make finding and deploying models easier.

## 🔍 Overview
- The Model Hub section of the Amazon SageMaker AI console lets you browse the JumpStart catalog, view sample notebooks, and open them directly in SageMaker Studio.
- Two new capabilities were added in 2026:
  1. **Deep‑link integration** – a single click takes you from a Hugging Face model discovery page to SageMaker AI deployment.
  2. **Pre‑configured endpoint deployment options** – named configurations tuned for low cost, low latency, or general‑purpose workloads, including Neuron‑optimized settings for generative AI models.

## 🛠️ New Features
- **One‑click model deployment** from Hugging Face to SageMaker via the deep link.
- **Named endpoint configurations** that automatically select instance types and settings based on the chosen priority:
  | Priority | Description |
  |----------|-------------|
  | Low Cost | Optimized for minimal expense |
  | Low Latency | Optimized for fastest response |
  | General‑Purpose | Balanced cost and performance |
- Support for a wide range of generative AI models, with Neuron‑optimized options where applicable.

## 📦 How to Use
A reusable Python script demonstrates the workflow in three steps:
1. **Discover and deploy** a model from JumpStart.
2. **Run sample prompts** to measure latency, output length, and single‑request generation rate.
3. **Clean up** the endpoint.

```python
REGION = "us-east-1"
MODEL_ID = "huggingface-vlm-qwen3-5-27b"
MODEL_VERSION = "1.13.0"

from sagemaker.core.jumpstart.notebook_utils import list_jumpstart_models
from sagemaker.core.jumpstart.accessors import JumpStartModelsAccessor
from sagemaker.core.jumpstart.configs import JumpStartConfig
from sagemaker.core.training.configs import Compute
from sagemaker.serve import ModelBuilder
from sagemaker.core.payloads import retrieve_all_examples
```
- The SageMaker Python SDK runs a lightweight, repeatable performance test.
- The pattern works for many compatible JumpStart models, although model‑specific payload formats, required instance types, EULA requirements, and response schemas may need adjustments.

## ⚙️ Technical Details
- Deployment time varies by model, instance type, quota, and AWS Region.
- Pre‑configured endpoint options provide ready‑made configurations for different workload priorities, simplifying the selection of compute resources.
- The deep‑link integration eliminates manual steps between Hugging Face model discovery and SageMaker deployment.

## 🚀 Availability
- These improvements were introduced in 2026 and are accessible through the SageMaker console in supported AWS Regions (e.g., `us-east-1`).

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/12/ML-22153-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/12/ML-22153-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/12/ML-22153-3.jpg)

#AWS #SageMaker #JumpStart #AIModels

---

*Source: [Deploy and evaluate models with Amazon SageMaker JumpStart | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/deploy-and-evaluate-models-with-amazon-sagemaker-jumpstart/)*
