---
title: "NVIDIA Launches Workload Map to Standardize Distributed AI Workloads on Kubernetes"
slug: "nvidia-launches-workload-map-to-standardize-distributed-ai-workloads-on-kubernetes"
description: "NVIDIA has introduced Workload Map as part of the NVIDIA DSX AI Factory Platform, providing a common description for Kubernetes workload structures to help the ecosystem design, build, and operate..."
date: 2026-11-02T22:02:19+05:30
tags: [NVIDIA, Kubernetes, AIInfrastructure, DSX, WorkloadMap]
categories: ["AI", "Infrastructure", "Artificial Intelligence", "Cloud Computing"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/AdobeStock_1f14ed65-d635-4fac-a472-570887464326-e1793050942456-660x370.webp"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Launches Workload Map to Standardize Distributed AI Workloads on Kubernetes

NVIDIA has introduced Workload Map as part of the NVIDIA DSX AI Factory Platform, providing a common description for Kubernetes workload structures to help the ecosystem design, build, and operate more efficient AI factories.

## 🔍 Overview
Operating an AI factory requires a shared understanding of distributed workloads, including their pod templates, replica counts, and status. Currently, each framework on Kubernetes encodes this information differently. Distributed training jobs or multi-node inference servers are often structured as trees of resources where groups of pods have specific roles and statuses. Until now, tools like schedulers, dashboards, and controllers required separate, framework-specific adapters to interpret these various custom resources.

## 🧩 How it works
Workload Map (formerly known as Karta) consists of a Kubernetes CRD and a Go library that resolves live objects into a uniform structural view. Instead of maintaining separate parsing code for every framework, developers can describe a workload type once using a YAML definition. This definition specifies where to find pod templates, replica counts, and status fields.

Key features include:
* **Shared Structural View:** Supplies a common description that can be reused across different frameworks and tools.
* **Data-Driven Logic:** Moves workload knowledge out of compiled adapters and into data manifests that can be reviewed and applied to a cluster.
* **Reduced Development Time:** Eliminates the need to wait for platform releases to support new workload types, as users can add support by writing a new YAML definition.

## ⚙️ Key details
Workload Map enables integrated platforms to interpret supported workload types without separate parsing code. For example, the KAI Scheduler uses these definitions for pod grouping and gang-scheduling instructions, while NVIDIA Run:ai utilizes them for workload management and visibility.

| Feature | Description |
| :--- | :--- |
| **Resource Kind** | Karta (CRD) |
| **Components** | Kubernetes CRD and a Go library |
| **Platform Integration** | NVIDIA DSX AI Factory Platform, KAI Scheduler, and NVIDIA Run:ai |
| **Management** | Supports multi-tenant operations and scaling |

## 📋 Supported Frameworks
Workload Map includes a catalog of prebuilt and tested definitions for a variety of frameworks and services, including:
* **Training & Batch:** JobSet, PyTorchJob, MPIJob, and LeaderWorkerSet.
* **Orchestration & Services:** RayCluster, RayJob, RayService, KServe, and Knative.
* **Specialized Tools:** NVIDIA NIM, Milvus, Grove PodCliqueSet, and NVIDIA Dynamo.

## 💡 Why it matters
Previously, supporting a new framework was a roadmap item that required a per-CRD adapter. For instance, a JobSet manifest describing a leader job and two worker jobs (totaling 12 GPUs) would typically require JobSet-aware code to aggregate resource requests. By using Workload Map, teams building schedulers, controllers, or cost tools can interpret these complex distributed workloads through a single, shared definition, reducing the ongoing cost of adapter development.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/figure-2-8.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/figure-3-7.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/figure-5-6.webp)

#NVIDIA #Kubernetes #AIInfrastructure #DSX #WorkloadMap

---

*Source: [Support New AI Frameworks Faster Using NVIDIA Workload Map | NVIDIA Technical Blog](https://developer.nvidia.com/blog/support-new-ai-frameworks-faster-using-nvidia-workload-map/)*
