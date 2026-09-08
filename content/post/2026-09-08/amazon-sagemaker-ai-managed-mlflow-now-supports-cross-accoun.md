---
title: "Amazon SageMaker AI Managed MLflow Now Supports Cross-Account Governance Topologies"
description: "Amazon SageMaker AI has expanded the capabilities of managed MLflow to support cross-account governance. This update allows larger organizations to separate development and production environments at..."
date: 2026-09-09T00:16:34+05:30
tags: [SageMaker, MLflow, AWS, MLOps, CloudGovernance]
categories: ["Machine Learning", "Cloud Computing", "Data Governance"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21407-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker AI Managed MLflow Now Supports Cross-Account Governance Topologies

Amazon SageMaker AI has expanded the capabilities of managed MLflow to support cross-account governance. This update allows larger organizations to separate development and production environments at the account level while maintaining a central governance function through two distinct topologies.

## 🧩 Architecture Topologies

Organizations can now implement cross-account governance using two primary patterns:

*   **Hub-and-Spoke Pattern:** This model centralizes governance by sharing a single MLflow app from a hub account across multiple development (spoke) accounts using AWS Resource Access Manager (AWS RAM).
*   **Hybrid Pattern:** Designed for regulated environments, this pattern keeps development accounts fully isolated from the governance hub, requiring model owners to approve models locally before they are promoted to the central hub.

## ⚙️ Key Details

The system utilizes AWS RAM to share the MLflow app, enabling it to work even when accounts are not within the same organization by using external principals. 

| Role | Environment/Tooling | Responsibility |
| :--- | :--- | :--- |
| Data Scientist | Jupyter notebook | Registers models against the shared MLflow app from a spoke account |
| Governance Officer | Amazon SageMaker Studio Models UI | Validates synced metrics and lineage; approves models centrally |
| Administrator | Console or CLI | Performs one-time setup of RAM shares, bucket policies, and destination groups |
| ML Engineer | CI/CD pipeline | Deploys approved models to Amazon SageMaker endpoints in the spoke account |

## 🔄 Implementation and Workflow

The technical setup requires configuring named AWS CLI profiles for both the spoke and hub accounts. A CloudFormation template provisions the necessary SageMaker AI Studio domain, user profile, and Managed MLflow app with `AutoModelRegistrationEnabled`.

When a data scientist in a spoke account registers a model, a Model Package Group and version are created synchronously in the hub account. To facilitate deployment, the hub attaches a resource policy to the group and shares it back to the spoke with `AllowDeploy` permissions. Model artifacts are stored in the hub account's S3 bucket, with bucket policies granting the spoke account necessary permissions for artifact access during deployment.

## 🚀 Availability

Administrators can configure these topologies using the AWS Management Console or CLI. Working notebooks for these cross-account governance implementations are available in the accompanying GitHub repository.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21407-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21407-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21407-3.png)

#SageMaker #MLflow #AWS #MLOps #CloudGovernance

---

*Source: [Govern models with MLflow and Amazon SageMaker AI Model Registry sync: Part 2 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/govern-models-with-mlflow-and-amazon-sagemaker-ai-model-registry-sync-part-2/)*
