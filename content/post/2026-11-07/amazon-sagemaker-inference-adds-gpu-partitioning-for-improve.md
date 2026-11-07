---
title: "Amazon SageMaker Inference Adds GPU Partitioning for Improved Utilization and Isolation"
slug: "amazon-sagemaker-inference-adds-gpu-partitioning-for-improved-utilization-and-isolation"
description: "Amazon SageMaker Inference now supports GPU partitioning, a feature that uses NVIDIA Multi-Instance GPU (MIG) technology to divide a physical GPU into independent partitions. This update allows..."
date: 2026-11-07T22:01:49+05:30
tags: [AmazonSageMaker, NVIDIA, GPU, MachineLearning, CloudInfrastructure]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/05/ML-22216-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker Inference Adds GPU Partitioning for Improved Utilization and Isolation

Amazon SageMaker Inference now supports GPU partitioning, a feature that uses NVIDIA Multi-Instance GPU (MIG) technology to divide a physical GPU into independent partitions. This update allows developers to host multiple models on a single accelerator with hardware-enforced isolation, addressing previous constraints where the smallest deployable unit was an entire GPU.

## 🔍 Overview
Previously, model deployment was limited by the number of physical accelerators available on an instance. For example, an ml.p4d.24xlarge instance with eight A100s could only hold eight models, even if those models only required a fraction of the available 40 GB of memory. This often forced a choice between using an older instance that might be under-powered or a newer instance where the model could not utilize the full capability, leading to higher costs or under-served workloads.

## 🧩 How it works
GPU partitioning utilizes NVIDIA MIG to split a single GPU into as many as seven instances, depending on the specific accelerator. Each partition operates as an independent unit with its own dedicated resources:
* **Fixed Resources:** Each partition receives a dedicated block of memory and a fixed share of compute units.
* **Hardware Isolation:** Isolation is enforced at the hardware level, ensuring compute, cache, and memory bandwidth are not shared across partitions.
* **Fault Isolation:** Memory errors or crashes are contained within a single partition, preventing one model's failure from affecting others on the same physical GPU.

## ⚙️ Key details
SageMaker AI now manages the GPU configuration, placement, and scaling that previously required users to maintain their own Kubernetes stacks. 

| Deployment Aspect | Requirement / Limitation |
| :--- | :--- |
| Supported Endpoints | Endpoints using inference components |
| Unsupported Endpoints | Single-model, serverless, and heterogeneous instance pools |
| Configuration Timing | Layouts must be chosen when the endpoint is created while partitions are idle |
| Large Models | Models requiring more than one GPU still require whole devices |

## 💡 Why it matters
Before this update, users seeking GPU partitioning often moved to self-managed Kubernetes to utilize MIG, which required managing driver versioning, device plugins, and fleet-wide consistency. The alternative, multi-model endpoints, allowed sharing but lacked isolation, meaning heavy traffic for one model could impact others on the same device.

Salesforce participated in defining the requirements and validating this implementation. According to Salesforce, many inference workloads do not require an entire GPU, and this capability allows them to "consolidate workloads safely, significantly improve GPU utilization, reduce inference costs, and maintain predictable performance and strong isolation."

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/05/ML-22216-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/05/ML-22216-2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/05/ML-22216-4-1.jpg)

#AmazonSageMaker #NVIDIA #GPU #MachineLearning #CloudInfrastructure

---

*Source: [SageMaker Inference now supports Multi-Instance GPU to maximize GPU utilization for model endpoints | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/sagemaker-inference-now-supports-multi-instance-gpu-to-maximize-gpu-utilization-for-model-endpoints/)*
