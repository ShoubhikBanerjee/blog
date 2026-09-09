---
title: "AWS Launches Ray Serve Deep Learning Containers for Model Inference"
slug: "aws-launches-ray-serve-deep-learning-containers-for-model-inference"
description: "AWS has launched the Ray Serve Deep Learning Container (DLC), extending the pre-built, performance-optimized Docker image approach used for training workloads to model inference."
date: 2026-09-09T22:05:26+05:30
tags: [AWS, RayServe, DeepLearningContainers, PyTorch, ModelInference]
categories: ["AI", "Machine Learning", "Cloud Computing", "AI Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21647-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Launches Ray Serve Deep Learning Containers for Model Inference

AWS has launched the Ray Serve Deep Learning Container (DLC), extending the pre-built, performance-optimized Docker image approach used for training workloads to model inference.

## 💡 Why it matters
TorchServe is no longer actively maintained, with official notices stating there are no planned updates, bug fixes, new features, or security patches, and that vulnerabilities might not be addressed.

## 🧩 How it works
Ray Serve DLCs provide a container purpose-built for serving models behind an HTTP endpoint with the full inference stack already assembled. The containers are built on the following foundations:

| Variant | Base Image | Included Components |
| :--- | :--- | :--- |
| CPU | Amazon Linux 2023 | PyTorch, Ray Serve (with FastAPI and Uvicorn), common utilities |
| GPU | NVIDIA Amazon Linux 2023 | OS layer, CUDA runtime libraries, PyTorch, Ray Serve (with FastAPI and Uvicorn), common utilities |

Key technical details include:
* **Validated Stack:** All components are tested together before release to prevent version drift between the CUDA runtime, framework, and serving layer.
* **Utilities:** Includes common utilities for multimodal, audio, and vision workloads, including FFmpeg compiled with NVIDIA hardware acceleration for video preprocessing.
* **Security:** Security patches are applied at build time.
* **Flexibility:** Engineers can layer additional libraries on the tested base for models that require them.

## ⚙️ Key details
For a single-node inference setup using the GPU version of the Ray Serve DLC to serve the Qwen3-VL-2B vision-language model:
* **Hardware:** One g5.xlarge instance with one NVIDIA A10G GPU (24 GB VRAM).
* **Configuration:** The model loads in float16 to fit within the available VRAM.
* **Deployment:** The application is injected via a ConfigMap, allowing serving code changes without rebuilding the image.
* **Logic:** A model endpoint is defined as a Python class decorated with `@serve.deployment`, implementing `__call__` for HTTP requests and using `.bind()` for registration.

## 🚀 Availability
The Ray Serve DLC is published as separate images with dedicated entrypoints for the following environments:
* Amazon Elastic Kubernetes Service (Amazon EKS)
* Amazon Elastic Compute Cloud (Amazon EC2)
* Amazon SageMaker

#AWS #RayServe #DeepLearningContainers #PyTorch #ModelInference

---

*Source: [Simplify and support your TorchServe workloads using Ray Serve Deep Learning Containers | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/simplify-and-support-your-torchserve-workloads-using-ray-serve-deep-learning-containers/)*
