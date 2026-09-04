---
title: "Building a Physical AI Model Factory with NVIDIA Cosmos 3 on Amazon SageMaker"
description: "Developing a Physical AI system, such as a robot or autonomous vehicle (AV) that translates real-world data into physical actions, cannot be achieved in a single training job. Instead, it requires a..."
date: 2026-09-04T22:05:53+05:30
tags: [NVIDIA, AmazonSageMaker, PhysicalAI, Cosmos3, Robotics]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21222-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Building a Physical AI Model Factory with NVIDIA Cosmos 3 on Amazon SageMaker

Developing a Physical AI system, such as a robot or autonomous vehicle (AV) that translates real-world data into physical actions, cannot be achieved in a single training job. Instead, it requires a continuous pipeline that generates synthetic data, performs post-training on perception and policy models so the system can understand its surroundings and act, and evaluates both in a closed-loop simulation. A Physical AI model factory continuously runs this loop to turn streams of real-world data into improved models.

This development outlines how to build a Physical AI model factory using NVIDIA Cosmos 3 on Amazon SageMaker HyperPod with Amazon Elastic Kubernetes Service (Amazon EKS).

## 🧩 How it works

NVIDIA Cosmos 3 is an open omnimodal world foundation model that treats video, image, action, and sound as a single token stream. Unlike common patterns that pair a diffusion-transformer video generator with a separate vision-language model for text conditioning, Cosmos 3 integrates both capabilities into a single trunk at every layer. 

Key architectural aspects of Cosmos 3 include:
* **Mixture-of-Transformers (MoT) Design:** Features per-layer joint attention and a deliberate train-versus-inference asymmetry.
* **Single Shared Sequence:** Every modality feeds into a single shared sequence, enabling one model to both read and generate across different modalities.
* **Sequential Processing:** The model sequence positions an autoregressive (AR) zone (for the text and vision it reads) ahead of a diffusion zone (for the video, audio, and action it produces).

## ⚙️ Key details

Cosmos 3 runs the same transformer trunk in three distinct modes and processes input modalities with specialized encoders:

| Component / Mode | Function / Details |
| :--- | :--- |
| **Forward-dynamics world model** | Used for synthetic video generation |
| **Inverse-dynamics action labeler** | Used for labeling actions |
| **Deployable action policy** | Acts as the final policy for system deployment |
| **Vision Transformer (ViT)** | Handles image understanding for the images the model reads |
| **Frozen Wan2.2 video VAE** | Handles pixel generation |
| **Per-embodiment vector** | Encodes pose deltas and grasp state, allowing the same model to drive both an AV and a robot arm |

Because one model family covers generation, post-training, and evaluation, separate GPU capacity for each stage is unnecessary. Instead of provisioning isolated nodes for each stage, these workloads are scheduled onto a single persistent, resilient GPU node pool under a single cluster control plane using time-shared capacity.

### Capacity and Cost Metrics
Running a continuous pipeline requires a committed capacity plan. Acquiring GPUs stage by stage introduces availability and lead-time variability, and risks landing capacity in an Availability Zone or AWS Region away from your data. Committing to the entire loop—either through a flexible training plan for bounded campaigns or a capacity reservation for open-ended ones—avoids this churn.

Since you pay for capacity continuously, the primary metric governing cost is not the peak throughput of any individual job. Instead, the system is optimized for **GPU goodput**: the useful pipeline progress per reserved GPU-hour across the entire loop.

## 🚀 Availability

NVIDIA has released Cosmos 3 under the Linux Foundation’s OpenMDW-1.1 license. Detailed architectural information can be found in the Cosmos 3 technical report.

To help developers get started, the `awsome-distributed-ai` GitHub repository contains the runnable code, including:
* Infrastructure templates and job manifests to set up the working cluster.
* Deployment configurations for Amazon SageMaker HyperPod and Amazon EKS.
* A shared multi-terabyte storage layer setup.
* Distributed post-training setups for three representative workloads, featuring an end-to-end walkthrough of the robot-policy stage using the public DROID dataset.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21222-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21222-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21222-3.png)

#NVIDIA #AmazonSageMaker #PhysicalAI #Cosmos3 #Robotics

---

*Source: [Build a Physical AI model factory with NVIDIA Cosmos 3 on SageMaker HyperPod | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-a-physical-ai-model-factory-with-nvidia-cosmos-3-on-sagemaker-hyperpod/)*
