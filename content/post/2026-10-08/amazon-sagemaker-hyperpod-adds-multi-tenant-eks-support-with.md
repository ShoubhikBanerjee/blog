---
title: "Amazon SageMaker HyperPod adds multi‑tenant EKS support with Identity Center integration"
slug: "amazon-sagemaker-hyperpod-adds-multitenant-eks-support-with-identity-center-integration"
description: "Amazon SageMaker HyperPod now supports purpose‑built, multi‑tenant AI clusters that simplify the management of large‑scale gen‑AI workloads while providing per‑team isolation, cost visibility, and..."
date: 2026-10-08T22:04:21+05:30
tags: [SageMaker, HyperPod, AWS, Kubernetes]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/01/ML-22020-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker HyperPod adds multi‑tenant EKS support with Identity Center integration

Amazon SageMaker HyperPod now supports purpose‑built, multi‑tenant AI clusters that simplify the management of large‑scale gen‑AI workloads while providing per‑team isolation, cost visibility, and automated operations.

## 🔍 Overview
- HyperPod delivers resilient, optimized clusters orchestrated by **Amazon Elastic Kubernetes Service (EKS)** or **Slurm**.
- The service automatically handles **node health monitoring, fault recovery, and cluster lifecycle management**.
- It is designed for distributed training, interactive development, and model inference at scale.

## 🧩 Architecture Overview
- **AWS IAM Identity Center** provides centralized authentication and federates with external providers such as **Microsoft Entra ID**.
- Each team gets a dedicated **SageMaker AI domain** that hosts a private **SageMaker Studio** GUI.
- Workloads run in separate **Kubernetes namespaces**, ensuring isolation.
- **HyperPod Task Governance** enforces fair resource allocation and compute‑quota management.
- **HyperPod Observability** supplies monitoring dashboards for the entire cluster.
- Storage is split into two tiers:
  - A POSIX‑compliant file system (Amazon FSx for Lustre or OpenZFS) with per‑team shared directories (`/fsx/TeamA`, `/fsx/TeamB`) and per‑user home directories (`/home/User1`, `/home/User2`).
  - Per‑team or shared Amazon S3 buckets governed by the team’s IAM execution role.

## ⚙️ Key Details
| Component | Role |
|---|---|
| AWS IAM Identity Center | Centralized authentication; federates with external IdP; provisions permission‑set roles (e.g., `TeamA-permissionset-role`). |
| SageMaker AI domain (per team) | Dedicated Studio GUI; uses team‑specific execution role (e.g., `TeamA-role`). |
| Kubernetes namespace (per team) | Isolates workloads; scoped RBAC policies restrict access to the team’s resources. |
| HyperPod Task Governance | Provides compute‑quota management and scheduling priorities across teams. |
| HyperPod Observability | Offers monitoring dashboards and health metrics for the cluster. |

### Authentication Paths
- **CLI path**: Users run `aws sso login`, are redirected to the Identity Center portal, obtain temporary credentials from their team’s permission set, and submit tasks to the EKS cluster with `kubectl` using the provisioned `TeamA-permissionset-role` or `TeamB-permissionset-role`.
- **Studio path**: Users select the SageMaker Studio application in the Identity Center portal, which routes them to their team‑specific SageMaker AI domain. The domain’s execution role (`TeamA-role` or `TeamB-role`) authorizes GUI‑driven tasks.
- Access entries map both the Studio execution roles and the CLI/Console roles to Kubernetes permissions, all tied to managed or custom RBAC policies scoped to the appropriate namespace.

## 🚀 Usage Example
- Two teams, **Team A** and **Team B**, share a single HyperPod EKS cluster.
- Each team operates within its own isolated namespace (`Namespace A`, `Namespace B`).
- Within a namespace, teams can launch:
  - **HyperPod Spaces** – interactive development environments.
  - **HyperPod PyTorch jobs** – distributed training workloads.
  - **HyperPod Inference endpoints** – model serving services.
- Cost allocation is performed at the namespace level, giving each team visibility into spend and supporting charge‑back.

## 💡 Why it matters
- Provides a single, managed compute platform that reduces the operational overhead of large‑scale AI workloads.
- Guarantees workload isolation and security through namespace‑scoped RBAC and distinct IAM roles.
- Enables per‑team cost tracking and fair resource distribution via Task Governance.
- Integrates with existing AWS identity and storage services, allowing teams to use familiar tools (CLI, SageMaker Studio) without custom configuration.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/02/multi-tenant-hp-eks.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/02/teama-domain.png)

#SageMaker #HyperPod #AWS #Kubernetes

---

*Source: [Share GPU clusters across teams with isolation and fairness using Amazon SageMaker HyperPod | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/share-gpu-clusters-across-teams-with-isolation-and-fairness-using-amazon-sagemaker-hyperpod/)*
