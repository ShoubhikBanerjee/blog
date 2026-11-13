---
title: "Amazon Announces Public Availability of SGLang-Neuron for AWS Trainium"
slug: "amazon-announces-public-availability-of-sglang-neuron-for-aws-trainium"
description: "Amazon has announced that SGLang-Neuron is publicly available through an AWS Deep Learning Container, released by RadixArk in collaboration with Annapurna Labs. SGLang-Neuron is an out-of-tree plugin..."
date: 2026-11-13T22:02:12+05:30
tags: [Amazon, AWSTrainium, SGLang, PyTorch, AIInference]
categories: ["AI", "Machine Learning", "Cloud Computing", "AI Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/12/ML-22453-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Announces Public Availability of SGLang-Neuron for AWS Trainium

Amazon has announced that SGLang-Neuron is publicly available through an AWS Deep Learning Container, released by RadixArk in collaboration with Annapurna Labs. SGLang-Neuron is an out-of-tree plugin that connects SGLang with AWS Trainium, enabling users to serve models and generate reinforcement learning (RL) rollouts using native PyTorch.

## 🔍 Overview

AWS Trainium is a portfolio of AWS AI chips designed to deliver strong economics for AI training and inference at scale. Key aspects of the integration include:

- Serves models and generates RL rollouts on AWS Trainium using the standard SGLang interface.
- Uses an out-of-tree plugin design, allowing Trainium support and SGLang core to develop independently and iterate faster.
- Runs on native PyTorch beneath the SGLang interface.

## 🧩 How it works

Installing the plugin registers the neuron platform through SGLang’s plugin entry points, and setting `SGLANG_PLATFORM=neuron` selects it when the server starts.

| Component | Responsibility |
| --- | --- |
| SGLang Core | Provides API server, request lifecycle, RadixAttention, and prefix-cache bookkeeping |
| SGLang-Neuron Plugin | Implements Trainium-specific models, attention, mixture of experts (MoE), and graph runner |
| TorchNeuron | Registers Trainium as a native PyTorch device |

Model execution path and execution details:

- Uses standard PyTorch operations for the model execution path.
- Incorporates kernels written with the Neuron Kernel Interface (NKI) for performance.
- Compiles operations and kernels into executable programs using `torch.compile`, which the graph runner prepares and executes during serving.

## ⚙️ Key details

SGLang-Neuron supports PD disaggregation configuration:

- **Prefill Server:** Computes the prompt KV cache and transfers it to the decode server using NIXL over Elastic Fabric Adapter (EFA).
- **Decode Server:** Generates the remaining tokens following KV-cache transfer.
- **Management:** Each server uses SGLang's scheduler and request lifecycle, while the plugin manages Trainium execution and the KV-cache transfer path.

## 🚀 Availability

- Available via the `pytorch-inference-sglang-neuronx` AWS Deep Learning Container.
- Walkthroughs use a Trainium3 Amazon Elastic Compute Cloud (Amazon EC2) instance.
- Users can get started by launching the SGLang-Neuron container and following the quickstart to serve a supported model.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/12/ML-22453-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/12/ML-22453-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/12/ML-22453-3.jpg)

#Amazon #AWSTrainium #SGLang #PyTorch #AIInference

---

*Source: [Deploy frontier AI models on AWS Trainium with SGLang-Neuron | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/deploy-frontier-ai-models-on-aws-trainium-with-sglang-neuron/)*
