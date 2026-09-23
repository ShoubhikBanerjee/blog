---
title: "NVIDIA Releases Topograph Open Source Toolkit for Topology-Aware GPU Scheduling"
slug: "nvidia-releases-topograph-open-source-toolkit-for-topology-aware-gpu-scheduling"
description: "NVIDIA has introduced Topograph, an open source toolkit designed to identify cluster network topology to enable workload managers to make topology-aware scheduling decisions."
date: 2026-09-23T22:05:40+05:30
tags: [NVIDIA, GPU, Kubernetes, Slurm, AIInfrastructure]
categories: ["AI", "AI Infrastructure", "Cloud Computing", "Hardware Optimization"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2025/09/inference-nvidia-dynamo-blog-1280x680-1-e1758728822171-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases Topograph Open Source Toolkit for Topology-Aware GPU Scheduling

NVIDIA has introduced Topograph, an open source toolkit designed to identify cluster network topology to enable workload managers to make topology-aware scheduling decisions.

## 💡 Why it matters
AI factories are power-limited systems that require full optimization to deliver maximum value. Because GPUs exchange data continuously during training and inference, distributed workloads benefit from communication locality. Poor workload placement can lead to:

* Fragmented topology domains
* Increased traffic across shared links
* Reduced throughput and higher job costs
* GPUs consuming provisioned power while waiting for data without advancing the workload

Topograph prevents these bottlenecks by mapping how cluster hardware is connected, allowing schedulers to favor nearby resources and avoid spreading tightly coupled workloads across distant domains.

## 🧩 How it works
Topograph solves the problem of maintaining an accurate view of GPU and fabric relationships as a cluster changes. It uses two primary concepts:

* **Providers**: These discover topology from cloud APIs or on-premises systems and normalize it into a canonical model.
* **Engines**: These translate the normalized model into formats expected by various workload managers.

Within the NVIDIA DSX OS cluster orchestration layer, Topograph works alongside KAI Scheduler and Dynamic Resource Allocation (DRA) to enable topology-aware gang scheduling.

## ⚙️ Key details
Topograph supports a variety of hardware and software integrations to ensure the scheduler works from current data rather than a manually maintained snapshot.

| Component | Supported Integration/Requirement |
| :--- | :--- |
| **Cloud Providers** | Google Cloud, Lambda, Nebius, Nscale, and OCI |
| **On-Premises Providers** | InfiniBand (with ibnetdiscover), NetQ (for Spectrum-X or Multi-Node NVLink domains) |
| **Engines/Outputs** | Kubernetes node labels, Slurm topology configuration, Slinky ConfigMaps, Node Feature Discovery (NFD) resources, instance-oriented topology JSON |
| **Slurm Engine** | Requires a writable volume for its configured topology.conf output path |
| **NFD Engine** | Requires the alpha NodeFeatureGroupAPI feature gate |
| **Crusoe Provider** | Runs in Kubernetes; reads fabric and accelerator-domain labels from Crusoe Managed Kubernetes nodes |

## 🚀 Availability
Topograph is an open source toolkit with an open provider interface, allowing operators to add and contribute providers for their own environments upstream. As of September 16, 2026, the toolkit supports various provider-to-engine output combinations, though requirements may vary by version and configuration.

#NVIDIA #GPU #Kubernetes #Slurm #AIInfrastructure

---

*Source: [Topology-Aware Workload Scheduling with NVIDIA Topograph | NVIDIA Technical Blog](https://developer.nvidia.com/blog/topology-aware-workload-scheduling-with-nvidia-topograph/)*
