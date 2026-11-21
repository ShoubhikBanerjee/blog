---
title: "SageMaker HyperPod Adds Cluster Extensions and Global Inference Gateway"
slug: "sagemaker-hyperpod-adds-cluster-extensions-and-global-inference-gateway"
description: "Amazon SageMaker HyperPod has introduced two new capabilities: cluster extensions for managing software on running nodes and the Global Inference Gateway for routing requests across multiple clusters..."
date: 2026-11-21T18:08:57+05:30
tags: [SageMaker, HyperPod, Slurm, AWS, Inference, MachineLearning]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "MLOps", "AI Engineering"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/20/l-ml-22428.png"
author: "Shoubhik Banerjee"
draft: false
---

# SageMaker HyperPod Adds Cluster Extensions and Global Inference Gateway

Amazon SageMaker HyperPod has introduced two new capabilities: cluster extensions for managing software on running nodes and the Global Inference Gateway for routing requests across multiple clusters and regions. These updates aim to reduce configuration drift and simplify the management of distributed AI inference workloads.

## 🧩 Cluster Extensions for Node Consistency
Managing a shared Slurm cluster for foundation model development involves keeping configuration, software, network topology, and user rosters in sync with the actual nodes. Over time, these elements drift apart, and there is no automated way to detect when they do. 

In November 2026, AWS launched cluster extensions to address the software and settings on running nodes. These are software packages managed by AWS that administrators can install, configure, update, and remove through APIs or the Amazon SageMaker AI console.

Key features of cluster extensions include:
- **Managed Extensions:** Initial support includes observability and user management (including directory integration).
- **Automatic Application:** HyperPod applies extensions to every node, including those added via scale-up or replacement, maintaining consistency as the cluster scales and heals.
- **Simplified Updates:** Settings can be changed or versions upgraded via API calls or the console, eliminating the need to edit scripts and replace nodes.
- **Visibility:** Each extension reports its status and per-node health.

Administrators should use cluster extensions for managed software capabilities. Custom AMIs and lifecycle scripts remain the correct approach for organization-specific software or initialization not covered by available extensions.

## 🌐 Global Inference Gateway
Previously, the SageMaker HyperPod Inference Gateway provided a single, GPU-aware endpoint for individual clusters. However, during traffic peaks, requests could queue on a saturated cluster while GPUs on another cluster, potentially in a different AWS Region, sat idle. Managing this required building and maintaining load balancers, DNS, and cross-Region networking manually.

The Global Inference Gateway is a SageMaker-managed gateway that routes across every registered cluster, whether in a single Region or across multiple Regions. 

**How it works:**
- **Routing:** The gateway picks the best cluster and carries the request over the AWS backbone.
- **Failover:** If a cluster fails, the gateway moves traffic to the next-best cluster automatically.
- **Endpoint Consolidation:** Clients call a single SageMaker-managed endpoint instead of tracking one endpoint per cluster or model. 
- **Security:** Every request is authenticated with AWS Signature Version 4 (SigV4) and IAM, and reaches clusters only over AWS PrivateLink.

For example, a team serving four models across five HyperPod clusters in two Regions would normally track 20 endpoints (one per model per cluster). The Inference Gateway cuts this to five, and the Global Inference Gateway consolidates further by handling cross-region overflow during peaks.

## ⚙️ Integration with Existing HyperPod Features
The Global Inference Gateway is the second tier of the architecture described in the initial Inference Gateway launch. It integrates with existing HyperPod infrastructure:
- **Configuration:** Administrators enable global routing by turning on the `spec.globalRouting` block in the cluster’s existing `InferenceGatewayConfig`.
- **Creation:** The `CreateGlobalInferenceGateway` API call registers clusters to route across, and SageMaker returns one endpoint.
- **Publishing:** The HyperPod Inference controller publishes the cluster privately from the user's account, creating a Network Load Balancer, publishing a VPC endpoint service, and uploading the listener’s certificate to the user’s TLS bucket.
- **Request Flow:** Clients sign requests with SigV4 and send them to the gateway’s regional endpoint. The gateway authenticates the caller, selects the best cluster, and uses AWS PrivateLink to carry the request to that cluster, where the local Inference Gateway routes it to the appropriate model pod.

## 💡 Why It Matters
These developments address two major pain points in large-scale AI infrastructure. First, they eliminate the "drift" between desired cluster state and actual node software by using managed extensions that automatically apply to new nodes. Second, they solve the inefficiency of idle GPUs during regional traffic peaks by enabling global routing that balances load across regions without manual load balancer management. For users like Bagelcode, who run LLM inference services on AWS, the Global Inference Gateway allows serving models across multiple regions through a single endpoint while maintaining high availability.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/20/ML-22428-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/20/ml-22428-figure-3.png)

#SageMaker #HyperPod #Slurm #AWS #Inference #MachineLearning

---

*Source: [Introducing managed cluster extensions for observability and user management in Amazon SageMaker HyperPod Slurm | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-managed-cluster-extensions-for-observability-and-user-management-in-amazon-sagemaker-hyperpod-slurm/)*
*Source: [Introducing Amazon SageMaker HyperPod Global Inference Gateway: One endpoint across Regions and clusters | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-amazon-sagemaker-hyperpod-global-inference-gateway-one-endpoint-across-regions-and-clusters/)*
