---
title: "NVIDIA FLARE 2.9 Introduces Slurm Support for Flexible Federated Learning Job Execution"
slug: "nvidia-flare-2-9-introduces-slurm-support-for-flexible-federated-learning-job-execution"
description: "NVIDIA FLARE now enables federated learning (FL) deployments across heterogeneous infrastructure through a two-layer architecture that separates federation management from job execution. This design..."
date: 2026-09-15T22:08:30+05:30
tags: [NVIDIA, FederatedLearning, AIInfrastructure]
categories: ["AI", "Federated Learning", "AI Infrastructure", "Machine Learning"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/nvflare-featured-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA FLARE 2.9 Introduces Slurm Support for Flexible Federated Learning Job Execution

NVIDIA FLARE now enables federated learning (FL) deployments across heterogeneous infrastructure through a two-layer architecture that separates federation management from job execution. This design allows participating sites to retain local control over compute resources while maintaining secure federation coordination.

## 🔍 Overview
NVIDIA FLARE addresses the challenge of running FL jobs across diverse environments by decoupling persistent federation services from job execution. This separation lets each site use its preferred execution backend—Docker, Kubernetes, or Slurm—within the same federation.

## 🧩 How It Works
- **Two-layer architecture**: 
  - *Persistent layer*: Long-running parent processes manage federation state, authenticate connections, and coordinate work.
  - *Execution layer*: Transient job workers handle submitted FL tasks.
- When a job is submitted, each site's parent process launches a worker via its configured platform (Docker/Kubernetes/Slurm).
- Jobs specify resource requirements (GPUs, CPUs, memory) separately from platform details. Each site's launcher translates these into platform-specific allocations.

## ⚙️ Key Details
**Supported Execution Backends**:
| Platform   | Key Capabilities                                                                 |
|------------|----------------------------------------------------------------------------------|
| **Docker** | Single-host execution (workstations/edge systems); parent/job containers; GPU exposure via NVIDIA Container Toolkit |
| **Kubernetes** | Helm-deployed parent pods; job pods scheduled with CPU/GPU/memory requirements; supports namespaces, secrets, persistent volumes |
| **Slurm**  | Submit jobs as batch tasks; supports bare execution, Pyxis/Enroot, Apptainer; enforces Slurm policies (QoS, partitions) |

**Site Control**: Each site chooses its runtime and retains authority over:
- Compute allocation
- Datasets, images, secrets
- Scheduling policies
- Resource enforcement

## 🚀 Availability
- Docker/Kubernetes support introduced in FLARE 2.8
- **Slurm support added in FLARE 2.9**

## 💡 Why It Matters
This architecture enables large-scale federated learning across organizations with differing infrastructure. Sites maintain autonomy over resources and security policies while participating in collaborative model training. The platform-agnostic design simplifies federation setup and allows efficient resource utilization.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2023/06/connected-healthcare-facilities-graphic.jpg)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2025/10/nvidia-flare-composite-660x370-jpeg.webp)

#NVIDIA #FederatedLearning #AIInfrastructure

---

*Source: [Scaling Federated Learning Across Docker, Kubernetes, and Slurm with NVIDIA FLARE | NVIDIA Technical Blog](https://developer.nvidia.com/blog/scaling-federated-learning-across-docker-kubernetes-and-slurm-with-nvidia-flare/)*
