---
title: "Scaling Machine Learning Workloads with Amazon SageMaker HyperPod and Cloud Data Fabric"
slug: "scaling-machine-learning-workloads-with-amazon-sagemaker-hyperpod-and-cloud-data-fabric"
description: "Amazon SageMaker HyperPod now offers infrastructure for large-scale machine learning workloads on Amazon Elastic Kubernetes Service (EKS). By integrating with Cloud Native Qumulo (CNQ) and Qumulo’s..."
date: 2026-09-25T22:04:20+05:30
tags: [MachineLearning, AmazonSageMaker, CloudComputing, DataEngineering]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "Data Management"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/23/ML-21828-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Scaling Machine Learning Workloads with Amazon SageMaker HyperPod and Cloud Data Fabric

Amazon SageMaker HyperPod now offers infrastructure for large-scale machine learning workloads on Amazon Elastic Kubernetes Service (EKS). By integrating with Cloud Native Qumulo (CNQ) and Qumulo’s Cloud Data Fabric (CDF), developers can now run training compute in one AWS Region while accessing datasets stored in another without the need to copy data or modify existing code.

## 🧩 How it works

Cloud Data Fabric maintains a single authoritative copy of a dataset on a hub cluster and projects it to spoke clusters as a unified POSIX namespace. Through predictive caching via NeuralCache, the system learns data loader access patterns and serves data from local NVMe storage. After an initial warmup period, this architecture allows spoke clusters to achieve throughput performance equivalent to locally co-located clusters, even across high-latency network links.

## ⚙️ Key details

* **Resiliency**: The infrastructure continuously monitors node health and automatically replaces faulty nodes to prevent hardware failures from impacting the entire cluster.
* **Performance**: Training jobs using this setup reach 98–100 percent GPU utilization after a brief warmup of 100–150 batches.
* **Integration**: The solution supports remote job submission via the `sagemaker_ray://` protocol and provides pre-built Amazon Managed Grafana dashboards through the HyperPod Observability EKS add-on.
* **Training Frameworks**: The platform supports frameworks such as SkyRL, enabling advanced techniques like Group Relative Policy Optimization (GRPO) for tasks like vision-language model navigation.

## 📊 Performance Comparison

| Cluster Configuration | Throughput (samples/sec) | Training Time |
| :--- | :--- | :--- |
| Hub (Local) | 116–117 | 18.5 minutes |
| Spoke (Warm Cache) | 115–116 | 18.5 minutes |
| Spoke (Cold Start) | 95–116 | ~19–20 minutes |

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/23/ML-21828-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/23/ML-21828-2.png)

#MachineLearning #AmazonSageMaker #CloudComputing #DataEngineering

---

*Source: [Accelerate multimodal RL training with SkyRL on Amazon SageMaker HyperPod | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/accelerate-multimodal-rl-training-with-skyrl-on-amazon-sagemaker-hyperpod/)*
*Source: [Multi-Region training with Amazon SageMaker HyperPod and Qumulo | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/multi-region-training-with-amazon-sagemaker-hyperpod-and-qumulo/)*
