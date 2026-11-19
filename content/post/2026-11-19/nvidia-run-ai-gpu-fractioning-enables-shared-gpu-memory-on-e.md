---
title: "NVIDIA Run:ai GPU Fractioning Enables Shared GPU Memory on EKS"
slug: "nvidia-run-ai-gpu-fractioning-enables-shared-gpu-memory-on-eks"
description: "NVIDIA has open-sourced Run:ai, an AI workload orchestration platform for Kubernetes, and validated a GPU Fractioning capability that allows multiple Pods to share a single GPU on Amazon Elastic..."
date: 2026-11-19T22:12:49+05:30
tags: [NVIDIA, Kubernetes, GPU, EKS, AI, Runai]
categories: ["AI", "Machine Learning", "Cloud Computing", "Kubernetes", "GPU Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22238-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Run:ai GPU Fractioning Enables Shared GPU Memory on EKS

NVIDIA has open-sourced Run:ai, an AI workload orchestration platform for Kubernetes, and validated a GPU Fractioning capability that allows multiple Pods to share a single GPU on Amazon Elastic Kubernetes Service (Amazon EKS). In the validated example, two Pods successfully shared one NVIDIA A10G Tensor Core GPU on an EC2 g5.xlarge instance, each allocating 6 GiB within an 8 GiB memory limit while an allocation above the limit was rejected as expected.

## 🔍 Overview
GPU sharing is not new — Multi-Instance GPU (MIG), time-slicing, and Multi-Process Service (MPS) address different isolation and utilization needs. NVIDIA Run:ai GPU Fractioning builds on MPS with Kubernetes-integrated scheduling, per-Pod memory contracts, enforcement, and metrics. The GPU Fractioning Operator helps several teams share one or two GPUs, addressing scenarios where notebooks, model evaluations, and small inference services leave teams waiting even when GPU memory remains available.

## 🧩 How it works
In the baseline configuration, the NVIDIA device plugin exposes a single GPU as one `nvidia.com/gpu` resource with GPU sharing disabled. Two Pods each requesting `nvidia.com/gpu: 1` cannot run concurrently on that node, even when their combined GPU-memory demand fits. NVIDIA Run:ai GPU Fractioning adds:
- Kubernetes scheduling integration via the KAI Scheduler
- Enforced GPU-memory limits per Pod
- Per-Pod GPU-memory metrics

The approach applies to NVIDIA GPUs that meet the GPU Fractioning Operator's hardware and software requirements, including GPUs without MIG. It uses NvFractions annotations, not Dynamic Resource Allocation (DRA).

## ⚙️ Key details
| Component | Detail |
|---|---|
| Validated GPU | NVIDIA A10G Tensor Core GPU (23,028 MiB) |
| Validated instance | Amazon EC2 g5.xlarge |
| System node | m7i.large hosting operator controllers and KAI Scheduler |
| GPU worker OS | Custom Amazon Linux 2023 (AL2023) |
| GPU driver | NVIDIA R615 driver branch |
| Container runtime | containerd with NVIDIA Container Toolkit |
| Sharing mechanism | MPS via fractiond with Node Resource Interface (NRI) integration |
| Metrics collection | metricsd daemon exports per-Pod GPU-memory metrics |
| Compute modes | Time-slicing (default) or sm-sharing |
| Error domains | Separate workload error domains for default mode; shared error domain for sm-sharing (not security guarantees) |

Each Pod receives an 8 GiB GPU-memory limit and allocates 6 GiB. The KAI Scheduler places both Pods on a tainted g5.xlarge node. The walkthrough establishes a whole-GPU baseline, verifies 6 GiB allocations, inspects per-Pod metrics, tests rejection of a 9 GiB allocation, and cleans up the disposable environment.

## 🚀 Availability
NVIDIA announced the open source release of NVIDIA Run:ai on October 13, 2026. This walkthrough uses two of its four modular components: KAI Scheduler and GPU Fractioning Operator. KAI Resource Management and Workload Map address organizational governance and additional workload types, outside this walkthrough's scope. Other configurations require compatibility checks and validation.

## 💡 Why it matters
Choose GPU fractioning when you need enforced per-Pod GPU-memory limits on GPUs without MIG and can run fixed-size GPU node groups. A memory limit does not reserve proportional compute. This walkthrough tests memory limits, not fault containment or compute performance. The solution enables better GPU utilization for workloads that don't require a full GPU, reducing wait times for development and inference tasks.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22238-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22238-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22238-3.jpg)

#NVIDIA #Kubernetes #GPU #EKS #AI #Run:ai

---

*Source: [Using NVIDIA Run:ai GPU Fractioning on Amazon EKS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/using-nvidia-runai-gpu-fractioning-on-amazon-eks/)*
