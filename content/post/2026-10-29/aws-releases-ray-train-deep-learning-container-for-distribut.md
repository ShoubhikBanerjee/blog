---
title: "AWS releases Ray Train Deep Learning Container for distributed PyTorch training"
slug: "aws-releases-ray-train-deep-learning-container-for-distributed-pytorch-training"
description: "AWS has released the Ray Train Deep Learning Container (DLC), a pre-integrated software stack designed to simplify distributed machine learning training. The image is built, tested as a single unit,..."
date: 2026-10-29T12:01:24+05:30
tags: [AWS, Ray, PyTorch, MachineLearning, Kubernetes]
categories: ["AI", "Machine Learning", "Cloud Computing", "Distributed Systems"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-22002-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS releases Ray Train Deep Learning Container for distributed PyTorch training

AWS has released the Ray Train Deep Learning Container (DLC), a pre-integrated software stack designed to simplify distributed machine learning training. The image is built, tested as a single unit, and maintained by AWS to ensure compatibility across the various libraries required for multi-node workloads.

## 🔍 Overview
The Ray Train DLC is a PyTorch training image with Ray’s training libraries layered on top. It includes the full HuggingFace training stack, allowing users to run fine-tuning jobs without building or pushing new images. AWS publishes these images to the Amazon Elastic Container Registry (Amazon ECR) Public, where they can be pulled without credentials.

| Component | Function |
| :--- | :--- |
| CUDA Runtime | Provides the foundational environment for GPU acceleration. |
| PyTorch | Compiled against the specific CUDA runtime in the image. |
| NCCL | NVIDIA Collective Communications Library for GPU communication. |
| EFA Libraries | Userspace libraries for the Elastic Fabric Adapter. |
| AWS OFI NCCL Plugin | Connects NCCL to EFA for high-performance networking. |
| Ray | Coordinates the cluster and manages training libraries. |

## 🧩 How it works
Ray runs a job across machines as a single cluster with two distinct roles, both of which use the same tagged image. Whether running on Amazon Elastic Kubernetes Service (Amazon EKS) via KubeRay or on Amazon Elastic Compute Cloud (Amazon EC2), the container's role is determined by the startup command.

*   **Ray Head:** Coordinates the cluster, tracks state in the global control store, and runs the dashboard and job server.
*   **Ray Worker:** Supplies GPUs and executes the training processes, connecting to the head’s address at startup.

On Kubernetes, the KubeRay operator adds a RayCluster resource that builds and maintains these groups from a single manifest.

## ⚙️ Key details
The Ray Train DLC is designed to be configured entirely from outside the image. Users specify instance types, GPU counts, and network transport settings through external configuration files rather than by modifying the container.

*   **Compatibility:** The image entrypoint automatically enables bundled CUDA forward-compatibility libraries if the host's NVIDIA driver is older than the image's CUDA version.
*   **Performance:** Collective operations between instances run over EFA automatically as soon as pods request it, as the EFA stack is pre-installed.
*   **Testing:** AWS gates each release on multi-node EFA and multi-node KubeRay training tests.

## 🚀 Availability
The Ray Train DLC is available in the Amazon ECR repository under the `train-ml` tag prefix, sharing a repository with Ray Serve and Ray LLM DLCs. 

A provided sample demonstrates the DLC's capabilities by fine-tuning a Qwen2.5-1.5B model using PyTorch Fully Sharded Data Parallel (FSDP) across eight NVIDIA L4 GPUs on two g6.12xlarge instances.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-22002-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-22002-2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-22002-3-1.png)

#AWS #Ray #PyTorch #MachineLearning #Kubernetes

---

*Source: [Distributed training with Ray Train DLCs and EFA on EKS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/distributed-training-with-ray-train-dlcs-and-efa-on-eks/)*
