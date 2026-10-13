---
title: "NVIDIA Open‑Sources the Full Run:ai Platform via DSX AI Factory"
slug: "nvidia-opensources-the-full-run-ai-platform-via-dsx-ai-factory"
description: "NVIDIA today announced that the complete NVIDIA Run:ai platform is now available as open source software, giving customers, developers, and ecosystem partners access to production‑grade AI workload..."
date: 2026-10-13T22:07:53+05:30
tags: [NVIDIA, OpenSource, AIInfrastructure, GPUOrchestration]
categories: ["AI", "Artificial Intelligence", "Open Source Software", "Cloud Computing", "Machine Learning"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/01/run-ai-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Open‑Sources the Full Run:ai Platform via DSX AI Factory

NVIDIA today announced that the complete NVIDIA Run:ai platform is now available as open source software, giving customers, developers, and ecosystem partners access to production‑grade AI workload and GPU orchestration capabilities.

## 🔍 Overview
- The release expands the NVIDIA DSX AI Factory Platform by establishing Run:ai as an open foundation for the broader ecosystem.
- Over several years, Run:ai has enabled organizations to run AI workloads on Kubernetes at scale by dynamically allocating GPU resources and managing the full lifecycle from data processing and training to inference.

## 🧩 How it works
- The open source release includes the integrated Run:ai platform **and** four modular components that can be adopted independently:
  - **KAI Scheduler** – the Kubernetes‑native scheduler powering Run:ai; released under Apache 2.0 and contributed to CNCF as a Sandbox project.
  - **GPU Fractioning Operator** – allows fractional allocation of GPUs.
  - **KAI Resource Management** – handles resource tracking and policies.
  - **Workload Map** – provides visibility into workload placement.
- Platform teams can adopt the full stack, build on it for their own products, or integrate individual components based on their requirements.

## ⚙️ Key details
- Source code is hosted in the **NVIDIA Run:ai** repository inside the NVIDIA DSX AI Factory GitHub organization.
- The complete platform is also published on **NVIDIA NGC** as a Community Product, with a Helm chart for installation.
- The code is governed by its applicable open‑source licenses; downloading from NGC requires acceptance of the NVIDIA Software License Agreement and Product‑Specific Terms.
- No paid Run:ai subscription or NVIDIA support entitlement is required for the Community Product; enterprise support is not included.

## 🚀 Availability
- Run:ai can be adopted directly as open‑source software or through offerings from NVIDIA DSX ecosystem partners.
- For NVIDIA Enterprise AI Factory deployments, Run:ai remains available through NVIDIA‑supported commercial offerings, including standalone products, NVIDIA Mission Control, NVIDIA AI Enterprise, and select cloud marketplaces. Availability, licensing, and support terms vary by offering.

## 💡 Why it matters
- Open‑source Run:ai gives DSX ecosystem partners direct access to GPU orchestration innovations they can embed in their own AI factory solutions.
- By adopting the whole platform or individual components, partners can bring innovations to market faster and respond more quickly to evolving customer and operational requirements.

### Partner integrations (selected examples)
| Partner | Integration description |
|---------|--------------------------|
| Crusoe | Integrates Run:ai with Crusoe Managed Kubernetes, combining GPU workload orchestration with managed Kubernetes and GPU infrastructure. |
| Mirantis | Extends k0rdent AI with Run:ai to deliver a lifecycle‑managed, Metal‑to‑Model AI factory stack that automates infrastructure provisioning and maximizes GPU utilization. |
| Nebius | Offers Run:ai as a one‑click application deployment in Nebius AI Cloud, streamlining deployment and operation on Nebius Managed Service for Kubernetes. |
| OpenNebula Systems | Integrates Run:ai with the OpenNebula AI Cloud Platform via OneKS, combining GPU orchestration with infrastructure provisioning for open and sovereign AI clouds. |
| Rafay | Expands its Run:ai integration into a fully managed service, automating GPU infrastructure, clusters, the Run:ai control plane, and tenant provisioning for self‑service catalogs. |
| Saturn Cloud | Uses Run:ai to help AI cloud operators launch white‑label inference services through its Token Factory platform, adding GPU orchestration, multi‑tenant model serving, per‑token metering, and automated billing. |
| Spectro Cloud | Embeds Run:ai into PaletteAI, enabling deployment through PaletteAI Studio and lifecycle automation across AI infrastructure. |
| vCluster | Provides Run:ai via pre‑validated deployment templates that create isolated environments per tenant while Run:ai schedules across a shared GPU fleet. |

---
*All statements are derived from NVIDIA’s official announcement and partner descriptions.*

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/01/run-ai-1024x576.jpg)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2025/10/runai-azure-660x370-png.webp)

#NVIDIA #OpenSource #AIInfrastructure #GPUOrchestration

---

*Source: [NVIDIA Run:ai Is Now Open Source as Part of NVIDIA DSX AI Factory Platform | NVIDIA Technical Blog](https://developer.nvidia.com/blog/nvidia-runai-is-now-open-source-as-part-of-nvidia-dsx-ai-factory-platform/)*
