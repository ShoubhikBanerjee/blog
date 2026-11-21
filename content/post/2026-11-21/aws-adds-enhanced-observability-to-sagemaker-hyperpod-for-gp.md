---
title: "AWS Adds Enhanced Observability to SageMaker HyperPod for GPU Training"
slug: "aws-adds-enhanced-observability-to-sagemaker-hyperpod-for-gpu-training"
description: "Amazon has announced enhanced observability capabilities for Amazon SageMaker HyperPod, a new feature designed to help users diagnose GPU training issues more quickly. This update introduces..."
date: 2026-11-21T06:15:51+05:30
tags: [AWS, SageMaker, HyperPod, GPU, Observability, CloudWatch]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "DevOps", "Monitoring"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22438-featured-image-1.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Adds Enhanced Observability to SageMaker HyperPod for GPU Training

Amazon has announced enhanced observability capabilities for Amazon SageMaker HyperPod, a new feature designed to help users diagnose GPU training issues more quickly. This update introduces diagnostic and profiling tools for training workloads running on both Amazon Elastic Kubernetes Service (Amazon EKS) and Slurm orchestrators.

## 🧩 How it works
The new observability layer combines automated outlier detection with static diagnostic rules to surface common failure patterns before they impact training performance.

- **Diagnostic Summary:** Utilizes Amazon CloudWatch’s `DetectGroupOutliers` API to compare each GPU in a training job. It flags GPUs that deviate from their peers based on utilization, memory, temperature, power, and SM clock.
- **Static Diagnostic Rules:** Evaluate known failure patterns and organize detected issues by type:
  - **Hardware:** GPU ECC memory errors, XID faults, and accelerator failures.
  - **Network:** EFA throughput degradation, packet drops, and retransmissions.
  - **Throttling:** GPU clock throttling due to heat, board, or reliability limits.
  - **Overheating:** GPU temperatures exceeding configured limits.

## ⚙️ Key details
Enhanced observability collects telemetry at two distinct levels, with options for metric storage that have been updated to include CloudWatch as a default choice.

| Metric Level | Inclusion | Coverage |
| :--- | :--- | :--- |
| **Default Metrics** | Enabled automatically | Cluster health, CPU/disk/OS-level usage, GPU utilization and temperature, and per-job resource utilization. Collected every 30 seconds with ~1–2% CPU overhead and 250–300 MB memory usage. |
| **Advanced Metrics** | Opt-in | Full node exporter suite (host-level), all NVIDIA GPU DCGM and AWS Neuron metrics (clock speeds, power, PCIe, errors), and Elastic Fabric Adapter (EFA) metrics (throughput, drops, retransmissions). |

Previously, only Amazon Managed Service for Prometheus was supported for metrics. CloudWatch is now the default, offering lower pricing compared to Prometheus and tighter integration with the SageMaker console through CloudWatch SageMaker Insights. Users can still choose Amazon Managed Service for Prometheus if they standardize on Prometheus and Grafana for observability.

## 💡 Why it matters
This capability is delivered as an add-on for EKS-orchestrated clusters and as an extension for Slurm-orchestrated clusters. This structure allows users to control who can install or change the observability layer through AWS Identity and Access Management (IAM). The "Enable HyperPod Observability" setting is checked by default.

#AWS #SageMaker #HyperPod #GPU #Observability #CloudWatch

---

*Source: [Introducing enhanced infrastructure observability in Amazon SageMaker HyperPod | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-enhanced-observability-in-amazon-sagemaker-hyperpod-to-diagnose-gpu-training-issues/)*
