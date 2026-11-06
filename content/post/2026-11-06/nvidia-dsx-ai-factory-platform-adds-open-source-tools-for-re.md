---
title: "NVIDIA DSX AI Factory Platform adds open‑source tools for reliable GPU‑Kubernetes clusters"
slug: "nvidia-dsx-ai-factory-platform-adds-opensource-tools-for-reliable-gpukubernetes-clusters"
description: "One underperforming GPU can slow an entire distributed training job, so measuring **goodput** – the volume of work successfully completed – is a more useful way to gauge cluster efficiency. NVIDIA’s..."
date: 2026-11-06T06:03:11+05:30
tags: [NVIDIA, Kubernetes, AIInfrastructure, GPUClusters]
categories: ["AI", "Machine Learning", "Infrastructure", "Open Source", "Kubernetes"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/dsx-os-cluster-readiness-featured-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA DSX AI Factory Platform adds open‑source tools for reliable GPU‑Kubernetes clusters

One underperforming GPU can slow an entire distributed training job, so measuring **goodput** – the volume of work successfully completed – is a more useful way to gauge cluster efficiency. NVIDIA’s DSX AI Factory Platform bundles the technologies needed to design, build, and operate efficient, resilient AI factories.

## 🔍 Overview
- The platform’s open‑source software layer, **NVIDIA DSX OS**, provides tools for configuring, certifying, and maintaining the health of accelerated Kubernetes infrastructure.
- It aims to keep every GPU, node, and network component in a ready state so that goodput remains high across large training jobs.

## 🛠️ Components
| Component | What it does |
|---|---|
| **NVIDIA DSX OS** | Configures, certifies, and maintains accelerated Kubernetes clusters. |
| **NVIDIA AI Cluster Runtime (AICR)** | Establishes a reproducible, version‑locked baseline for GPU‑optimized Kubernetes infrastructure; renders configuration recipes as bundles for existing deployment tools. |
| **NVIDIA Cluster Readiness Engine (NVCRE)** | Validates cluster readiness for production workloads; tests GPUs, networking, and storage with AI workloads and diagnostics; records certification results and flags faulty nodes. |
| **NVSentinel** | Monitors cluster health; publishes node conditions based on GPU, node, and network health; cordons or taints unhealthy nodes, drains workloads, remediates faults, and can trigger re‑validation with NVCRE before returning nodes to service. |

All three projects are licensed under Apache 2.0 and welcome external contributions.

## ⚙️ How it works
- **AICR** defines the cluster’s software baseline in version‑controlled files and renders them into artifacts that any deployment tool can apply.
- Declarative templates detect configuration drift from manual changes and keep node configurations consistent after repairs.
- Each recipe entry pins a component version, declares required healthy dependencies, and includes a `healthCheckAsserts` block that runs after installation.
- The health assertions filter on the container *waiting* reason rather than the pod phase alone.
- The bundle command produces ready‑to‑use artifacts:
  ```
  aicr bundle --recipe recipe.yaml --deployer argocd --output ./bundles
  ```
- The `--deployer` flag accepts **helm**, **argocd**, **argocd‑helm**, **flux**, or **helmfile**, so the same validated recipe can become Argo CD Application manifests, Flux resources, a Helmfile release graph, or plain Helm commands.
- Because the recipe is a file, standard version‑control workflows (history, code review, drift detection) manage the baseline.
- Drift detection can be enforced as a CI gate:
  ```
  aicr diff --baseline ./golden.yaml --target cm://default/aicr-snapshot --fail-on-drift
  ```

## 📊 Measuring Efficiency
- Goodput focuses on the actual work completed, highlighting the impact of any slow GPU on overall training performance.

## 🚀 Availability
- The DSX OS, AICR, NVCRE, and NVSentinel projects are all open source under the Apache 2.0 license.
- External contributions are encouraged, and the tools integrate with common GitOps deployment pipelines.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/dsx-os-cluster-readiness-featured-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/kubernetes-clusters-660x370-jpg.webp)

#NVIDIA #Kubernetes #AIInfrastructure #GPUClusters

---

*Source: [Configure, Certify, and Operate Kubernetes GPU Clusters with NVIDIA DSX OS | NVIDIA Technical Blog](https://developer.nvidia.com/blog/configure-certify-and-operate-kubernetes-gpu-clusters-with-nvidia-dsx-os/)*
