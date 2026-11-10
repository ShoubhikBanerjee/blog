---
title: "NVIDIA Upstreams Agent Substrate and Introduces Snapshot, NVKE, and NVKR"
slug: "nvidia-upstreams-agent-substrate-and-introduces-snapshot-nvke-and-nvkr"
description: "NVIDIA is contributing upstream to Agent Substrate—an open-source agent runtime donated to the Cloud Native Computing Foundation (CNCF) Sandbox—while introducing NVIDIA Snapshot, NVIDIA Kubernetes..."
date: 2026-11-10T22:09:41+05:30
tags: [Kubernetes, NVIDIA, AIAgents, GPUInfrastructure, CloudNative]
categories: ["AI", "AI Infrastructure", "Kubernetes", "AI Agents", "GPU Computing"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image2-5-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Upstreams Agent Substrate and Introduces Snapshot, NVKE, and NVKR

NVIDIA is contributing upstream to Agent Substrate—an open-source agent runtime donated to the Cloud Native Computing Foundation (CNCF) Sandbox—while introducing NVIDIA Snapshot, NVIDIA Kubernetes Engine (NVKE), and NVIDIA Kubernetes Recipes (NVKR) as part of the NVIDIA DSX AI Factory Platform.

## 🔍 Overview

Agent Substrate, NVIDIA Snapshot, NVKE, and NVKR address infrastructure needs across AI agent session management, GPU workload startup times, and managed Kubernetes cluster operations.

| Component | Description | Status / License |
| --- | --- | --- |
| Agent Substrate | Security-hardened runtime that multiplexes sandboxed agent sessions over worker Pods | Donated to CNCF Sandbox |
| NVIDIA Snapshot | Checkpoint and restore system for GPU workloads on Kubernetes | Open-source (DSX AI Factory) |
| NVKE | Software to run managed Kubernetes clusters on factory infrastructure | Apache 2.0 (Public Preview) |
| NVKR | Reproducible builds for OS images, container images, and Helm charts | Apache 2.0 (Public Preview) |

## 🧩 How Agent Substrate Works

Agent Substrate provides a security-hardened, zero-trust runtime engineered to run agents and tools with 10x higher density than standard containers by decoupling actor state from worker Pods:

* **Session Multiplexing:** Idle sessions are snapshotted out of gVisor or microVM sandboxes—including memory and filesystem state—freeing the underlying worker Pod.
* **Bypassing Control Plane Latency:** Restoring an actor onto a free worker Pod skips API server, admission, etcd, scheduler, and kubelet roundtrips.
* **Kubernetes Integration:** Worker Pods remain standard Kubernetes Pods, ensuring cluster scheduling, placement policies, and quotas continue to apply.
* **Upstream Capabilities:** Public developments include router request parking (#221), request line protection for running actors (#1229), and Kubernetes Dynamic Resource Allocation (DRA) device pluggability (#752), with NVIDIA GPUs designated as the first supported device.

## ⚡ NVIDIA Snapshot GPU Checkpoint and Restore

NVIDIA Snapshot eliminates repeated workload initialization by saving fully initialized CPU and GPU memory states into portable artifacts:

* **Operations:** Checkpointing is managed via `PodSnapshot` or `SnapshotJob` custom resources, while restoration uses the `nvidia.com/restore-from` Pod annotation.
* **Workload Compatibility:** Features examples for vLLM, SGLang, and NVIDIA TensorRT LLM, and supports single-node multi-GPU workloads across tensor parallelism (TP), data and expert parallelism (DEP), and decode context parallelism (DCP).
* **Restoration Speed:** Across tested configurations, Snapshot restores replicas in 3.6 to 42.7 seconds—8x to 36x faster than cold starts. Crusoe reduced GLM-5.3 Pod readiness from ~8 minutes to 31 seconds on NVIDIA HGX B300, while Saturn Cloud cut vLLM startup from 2–8.5 minutes to 6–34 seconds.

## 🛠️ NVKE and NVKR Infrastructure Tools

NVKE and NVKR allow AI factories to construct and operate managed Kubernetes services:

* **NVKR (NVIDIA Kubernetes Recipes):** Builds validated operating system images, container images, binaries, and Helm charts based on specific GPU generations and software versions.
* **NVKE (NVIDIA Kubernetes Engine):** Deploys management and workload clusters using artifacts produced by NVKR, leveraging Cluster API infrastructure provider CAPNICo and NVIDIA Infra Controller (NICo).
* **Node Identity & Observability:** Requires nodes to present an attested SPIFFE identity before receiving join credentials, and exports telemetry via an OpenTelemetry-based Helm chart over OTLP.
* **Certification:** NVKE is a Certified Kubernetes AI Platform and Certified Kubernetes Installer tested on Kubernetes 1.36.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/nvidia-snapshot-gpu-checkpoint-restore-1024x576-jpg.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/figure-1-1-e1793906343701.webp)

#Kubernetes #NVIDIA #AIAgents #GPUInfrastructure #CloudNative

---

*Source: [Agent Substrate: Advancing Kubernetes for Agents at Scale | NVIDIA Technical Blog](https://developer.nvidia.com/blog/agent-substrate-advancing-kubernetes-for-agents-at-scale/)*
*Source: [Start and Restore GPU Workloads in Seconds with NVIDIA Snapshot | NVIDIA Technical Blog](https://developer.nvidia.com/blog/start-and-restore-gpu-workloads-in-seconds-with-nvidia-snapshot/)*
*Source: [Manage Kubernetes Clusters for GPU Infrastructure with NVIDIA Kubernetes Engine | NVIDIA Technical Blog](https://developer.nvidia.com/blog/manage-kubernetes-clusters-for-gpu-infrastructure-with-nvidia-kubernetes-engine/)*
