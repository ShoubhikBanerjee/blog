---
title: "SageMaker HyperPod integrates with Unified Studio and adds Spaces for governed GPU workloads"
slug: "sagemaker-hyperpod-integrates-with-unified-studio-and-adds-spaces-for-governed-gpu-workloads"
description: "Amazon SageMaker HyperPod gives machine learning (ML) teams access to large pools of accelerated compute for training and fine‑tuning models. When several teams share a single cluster the technical..."
date: 2026-10-06T22:08:14+05:30
tags: [SageMaker, HyperPod, MLOps, AIInfrastructure, MachineLearning]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence", "DevOps"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/02/ML-21129-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# SageMaker HyperPod integrates with Unified Studio and adds Spaces for governed GPU workloads

Amazon SageMaker HyperPod gives machine learning (ML) teams access to large pools of accelerated compute for training and fine‑tuning models. When several teams share a single cluster the technical setup is straightforward, but governance becomes the challenging part.

## 🔍 Overview
- **SageMaker HyperPod** is a capability of Amazon SageMaker AI that provides purpose‑built infrastructure for foundation model training and inference at scale.
- **SageMaker Unified Studio** is the data and AI development environment where teams build with their data and tools.
- Unified Studio can **connect a HyperPod cluster to a project**, letting team members launch workloads, review cluster and task information, and open a JupyterLab workflow.
- The integration keeps cluster management in SageMaker AI interfaces and APIs, allowing infrastructure teams to use established cloud‑operations processes while presenting approved compute to ML teams in their project context.

## ⚙️ Governance Model
- Governance decisions include:
  - Which teams may use the cluster.
  - How much capacity each team receives.
  - How to handle competition for resources.
  - Who is accountable when usage drifts from policy.
- When multiple teams share visibility into the same cluster, **controls that govern who can do what become even more important**.
- A well‑governed environment separates:
  - **Organizational administration**
  - **Project access**
  - **Cluster operations**
  - **Workload execution**
- Each layer answers a different question and uses different controls.

## 🏗️ Four Layers of Control
1. **Organization layer** – identity and capacity policies that apply across the entire account.
2. **Project layer** – collaboration boundaries defined in SageMaker Unified Studio (not strong runtime security boundaries).
3. **Cluster layer** – AWS IAM, Amazon EKS, and Slurm controls that govern cluster‑level access.
4. **Workload layer** – workload identity, data and KMS key policies, network policy, task‑view restrictions, and scheduler policy.

> “A SageMaker HyperPod connection adds an approved cluster to a project. It doesn’t replace the cluster’s AWS Identity and Access Management (IAM), Amazon Elastic Kubernetes Service (Amazon EKS), or Slurm controls.”

All four layers must be aligned before the cluster is made available.

## 🧩 SageMaker Spaces on HyperPod
- Earlier this year Amazon launched **SageMaker Spaces for HyperPod**, an add‑on that lets developers create interactive development environments directly on HyperPod EKS clusters.
- **Benefits**:
  - Run JupyterLab or Code Editor environments without leaving the browser or using CLI tools.
  - Reduce time from cluster access to productive development to a few clicks.
  - Run interactive workloads alongside training jobs and model deployment, with support for fractional GPU allocations.
- **Management UI**:
  - The new **IDE and Notebooks tab** on the HyperPod cluster detail page provides a complete user interface for Space management, removing the need for daily CLI commands.
  - Create Spaces with configurable compute, namespaces, storage, and HyperPod Task Governance for compute‑quota management via a guided form.
  - View all Spaces in a searchable table showing name, application type, status, access type, storage, GPU, and vCPU allocations.
  - Start or stop Spaces with a single selection to free compute when not in use.
  - Open Spaces directly in the browser (JupyterLab or Code Editor) or connect through a remote IDE such as VS Code.

## 🚀 Installing and Using Spaces
1. **Install the Spaces add‑on** on the HyperPod EKS cluster from the SageMaker AI console → IDE and Notebooks tab. Choose **Quick install** (one‑click defaults) or **Custom install** (required for web UI access).
2. **Configure EKS access entries** by attaching the managed policies:
   - `AmazonSagemakerHyperpodSpacePolicy`
   - `AmazonSagemakerHyperpodUserClusterPolicy`
   - `AmazonSagemakerHyperpodSpaceTemplatePolicy`
   to the IAM roles used by data scientists.
3. **Enable per‑user identity propagation** on the Studio domain if it existed before the integration. This ensures each Studio user’s actions on the cluster are attributed in EKS access entries and AWS CloudTrail, enforcing strict Space ownership.
4. **Create and launch a Space**:
   - In Studio, go to **Compute → HyperPod**, select the **IDE and Notebooks** tab.
   - After the Space status shows **Running** (a few minutes on a cold cluster, ~30–40 seconds with over‑provisioning), click **Open** to launch JupyterLab or Code Editor, or **Open in VS Code** for a remote IDE experience.

## 📚 Summary
- By connecting SageMaker HyperPod clusters to Unified Studio projects, organizations can provide approved, high‑performance GPU compute to ML teams while retaining strong governance through four layered controls.
- The new SageMaker Spaces UI gives data scientists a visual, click‑based workflow to create, manage, and use interactive development environments on the same HyperPod infrastructure that powers large‑scale training and inference.
- This combination delivers a repeatable, governed model that separates infrastructure operations from project‑level development, enabling efficient use of shared GPU resources.

#SageMaker #HyperPod #MLOps #AIInfrastructure #MachineLearning

---

*Source: [Best practices for Amazon SageMaker HyperPod administration and governance | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/best-practices-for-amazon-sagemaker-hyperpod-administration-and-governance/)*
*Source: [Manage Amazon SageMaker HyperPod Spaces directly from SageMaker Studio | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/manage-amazon-sagemaker-hyperpod-spaces-directly-from-sagemaker-studio/)*
