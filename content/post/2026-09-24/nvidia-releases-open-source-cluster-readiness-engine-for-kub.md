---
title: "NVIDIA Releases Open Source Cluster Readiness Engine for Kubernetes"
slug: "nvidia-releases-open-source-cluster-readiness-engine-for-kubernetes"
description: "NVIDIA has introduced the Cluster Readiness Engine (NVCRE), an open source Kubernetes controller designed to identify hardware and configuration issues in GPU clusters before production workloads are..."
date: 2026-09-24T12:10:10+05:30
tags: [NVIDIA, Kubernetes, GPU, OpenSource, ClusterManagement]
categories: ["AI", "Infrastructure", "Machine Learning", "Cloud Computing"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2025/12/cybersecurity.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases Open Source Cluster Readiness Engine for Kubernetes

NVIDIA has introduced the Cluster Readiness Engine (NVCRE), an open source Kubernetes controller designed to identify hardware and configuration issues in GPU clusters before production workloads are deployed.

## 💡 Why it matters
Standard diagnostics can report that every GPU, network link, and pod is healthy, yet a 512-GPU training job may still underperform or fail. Potential causes include:

* A single slow GPU.
* A link that degrades under load.
* A configuration that routes traffic over a slower path.

Without specialized tooling, operators may only discover these problems hours into a run or via customer tickets, leading to days of manual cluster bisection while capacity remains idle. NVCRE transforms readiness from an assumption into a proven property by running real distributed workloads that expose hardware problems.

## ⚙️ Key details
On Slurm, testing readiness requires a single srun command, but Kubernetes lacks a built-in equivalent. Running such tests on Kubernetes typically requires manual GPU and RDMA resource requests, NCCL settings matched to the network fabric, large shared-memory volumes, and mechanisms to ensure pods start together. NVCRE fills these gaps, removing the need for operators to:

* Write NVIDIA Collective Communications Library (NCCL) manifests by hand.
* Bisect racks manually.
* Rely on customer tickets to learn about degraded hardware.

NVCRE supports a staged readiness process where clusters move through bring-up, burn-in, preproduction, and production, with each stage setting a different bar. This replaces the need for platform teams to maintain custom runbooks, spreadsheets, or shell scripts wrapped around NCCL tests.

## 🧩 How it works
NVCRE uses an API based on Custom Resource Definitions (CRDs), allowing management through GitOps workflows and inspection via kubectl. The system uses a three-resource hierarchy to attribute failures to specific nodes and categories:

| Resource | Function |
| :--- | :--- |
| Certification | The top-level resource that names the nodes to test and the categories to run. |
| Workflow | Manages one category; applies overrides, manages iteration count, sets the orchestration target, and creates the child job. |
| Job | Runs the workload for the target node group, monitors health, and records measurements and failures. |

Results propagate upward from the Job to the Workflow and finally to the Certification. This allows the system to name exactly which node caused a failure, such as reporting that one GPU hit a hardware fault during NCCL while another missed its bandwidth target.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/kubernetes-clusters-660x370-jpg.webp)

#NVIDIA #Kubernetes #GPU #OpenSource #ClusterManagement

---

*Source: [Validate GPU Cluster Readiness Before AI Workloads Land | NVIDIA Technical Blog](https://developer.nvidia.com/blog/validate-gpu-cluster-readiness-before-ai-workloads-land/)*
