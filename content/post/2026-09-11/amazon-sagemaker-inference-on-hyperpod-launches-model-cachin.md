---
title: "Amazon SageMaker Inference on HyperPod Launches Model Caching"
slug: "amazon-sagemaker-inference-on-hyperpod-launches-model-caching"
description: "Amazon SageMaker Inference on HyperPod has launched model caching, a feature that pre-loads model weights and container images onto cluster nodes before pods require them."
date: 2026-09-11T12:15:38+05:30
tags: [AmazonSageMaker, HyperPod, ModelCaching, MachineLearning, MLOps]
categories: ["AI", "Machine Learning", "Cloud Computing", "AI Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21820-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker Inference on HyperPod Launches Model Caching

Amazon SageMaker Inference on HyperPod has launched model caching, a feature that pre-loads model weights and container images onto cluster nodes before pods require them.

## 💡 Why it matters

Model caching eliminates latency sources associated with downloading data over the network. Without caching, start times can take tens of minutes due to:

* **Container Images:** Multi-gigabyte inference server images (such as LMI or vLLM) typically take 5–7 minutes to pull.
* **Model Weights:** A 145 GB model on Amazon S3 can take 20+ minutes, while a 600+ GB model like DeepSeek-R1 can take upwards of 30 minutes.

With model caching enabled, pods can typically start serving traffic in seconds, reading from local NVMe storage at approximately 7 GB/s.

## 🧩 How it works

Model caching is managed via two Custom Resource Definitions (CRDs) introduced by the operator:

| Feature | Mechanism | Function |
| :--- | :--- | :--- |
| Weights Cache | ModelDataCacheConfig | Downloads model weights to local NVMe on target nodes from sources including Amazon S3, Amazon FSx for Lustre, HuggingFace Hub, or JumpStart. |
| Image Cache | DaemonSet | Pre-pulls inference server container images onto nodes to avoid ECR downloads. |

### Deployment Process
1. Users add `modelCacheConfig` with `weightsCache` or `imageCache` enabled to their `InferenceEndpointConfig` or `JumpStartModel` resource.
2. For weights, the HyperPod Inference Operator creates a `ModelDataCacheConfig` resource and downloads weights to local NVMe. Once complete, the node is labeled as cache-ready.
3. The operator waits for all target nodes to be cache-ready before creating the inference deployment.
4. For images, the operator creates a DaemonSet to pull the image. Multiple deployments using the same image share a single image cache resource.

## ⚙️ Key details

* **Persistence:** Configured caches remain available across pod restarts on the same node.
* **Scheduling:** Caching uses preferred scheduling rather than required scheduling. If a pod is placed on a node without a warm cache—such as during rapid scale-out—it pulls the image from Amazon ECR and reads weights from the original Amazon S3/Amazon FSx source.
* **Fallback:** Pods started before the image cache is complete on a node will pull from ECR normally.

#AmazonSageMaker #HyperPod #ModelCaching #MachineLearning #MLOps

---

*Source: [Reduce inference cold starts on Amazon SageMaker HyperPod with model caching | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/reduce-inference-cold-starts-on-amazon-sagemaker-hyperpod-with-model-caching/)*
