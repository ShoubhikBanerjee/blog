---
title: "NVIDIA releases Dynamo 1.4.2 with AICR‑packaged recipes for Kubernetes inference"
slug: "nvidia-releases-dynamo-1-4-2-with-aicrpackaged-recipes-for-kubernetes-inference"
description: "NVIDIA has updated its Dynamo distributed inference framework to version 1.4.2 and delivered it through the NVIDIA AI Cluster Runtime (AICR) as validated recipes that simplify deployment on..."
date: 2026-10-31T22:01:44+05:30
tags: [NVIDIA, Dynamo, Kubernetes, AIInference]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Infrastructure", "Cloud Computing"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/inline-image-1-1-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA releases Dynamo 1.4.2 with AICR‑packaged recipes for Kubernetes inference

NVIDIA has updated its Dynamo distributed inference framework to version 1.4.2 and delivered it through the NVIDIA AI Cluster Runtime (AICR) as validated recipes that simplify deployment on Kubernetes.

## 🔍 Overview
- Dynamo is a distributed inference framework that coordinates model serving across GPU workers.
- It is part of the NVIDIA DSX AI Factory Platform, which helps the ecosystem design, build, and operate more efficient AI factories.
- AICR (AI Cluster Runtime) packages Dynamo and its supporting infrastructure into reproducible recipes.

## 🧩 How it works
- Running a model with Dynamo on Kubernetes begins with a **DynamoGraphDeployment** custom resource that specifies how **vLLM**, **SGLang**, or **NVIDIA TensorRT LLM** should run in pods.
- Frontends, workers, and optional **Gateway API Inference Extension (GAIE) / Endpoint Picker Plugin (EPP)** components discover each other through Kubernetes resources.
- Dynamo routes requests to workers that already hold the relevant KV‑cache blocks via its frontend router or through GAIE/EPP integration at the Gateway API layer.
- The framework can separate prompt processing (prefill) from token generation (decode), a pattern called **disaggregated serving**.  On KV‑cache misses the prefill pool reprocesses the prompt, after which decode workers generate tokens token‑by‑token.
- In Dynamo 1.4.2 the default AICR Kubernetes path uses **TCP** for the request plane and **ZMQ** for KV‑cache events.  Each vLLM worker emits raw KV‑cache events through a local ZMQ publisher.

## ⚙️ Key details
- AICR ships version **1.4.2** of the **dynamo‑platform chart**, which includes the Dynamo operator, runtime images, and the `nvidia.com/v1beta1` **DynamoGraphDeployment** CRD (replacing the former `v1alpha1`).
- The AICR Dynamo recipe **pins component versions** and records configuration values, node selectors, tolerations, checksums, and validation expectations to make deployment reproducible.
- The default path no longer installs **NATS**; it remains available as an opt‑in for deployments that need it.

| Component | Role / Note |
|-----------|-------------|
| DynamoGraphDeployment CRD (v1beta1) | Defines deployment of vLLM, SGLang, or TensorRT LLM pods |
| dynamo‑platform chart 1.4.2 | Packages Dynamo operator, runtime images, and related resources |
| AICR Dynamo recipe | Pins versions, records config, node selectors, tolerations, checksums, validation expectations |
| GAIE / EPP (optional) | Provides Gateway API routing integration |
| NATS (optional) | Message bus that is not installed by default |

## 🚀 Availability
- The AICR distribution includes the **1.4.2** chart and the associated validated recipe.
- Support for **vLLM**, **SGLang**, and **NVIDIA TensorRT LLM** is built into the DynamoGraphDeployment specification.
- Operators can choose between the default TCP + ZMQ transport or opt‑in to NATS if required.

## 💡 Why it matters
- AICR gives platform teams a repeatable way to deploy and validate the runtime, providing developers with a consistent foundation for serving models and testing applications.
- Disaggregated serving lets operators **scale and tune prefill and decode capacity independently**, accommodating different request mixes such as long‑running agentic sessions versus one‑off chat requests.
- By routing requests to workers that already hold the needed KV‑cache blocks, Dynamo reduces the need to reprocess intermediate tokens on cache misses.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/03/inference-press-dynamo-gtc26-4960950-1920x1080-1-660x370.png)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/figure-1-12.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/figure-2-11.webp)

#NVIDIA #Dynamo #Kubernetes #AIInference

---

*Source: [Build a Validated Kubernetes Runtime for NVIDIA Dynamo | NVIDIA Technical Blog](https://developer.nvidia.com/blog/build-a-validated-kubernetes-runtime-for-nvidia-dynamo/)*
