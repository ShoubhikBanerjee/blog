---
title: "LLMKube Unifies LLM Inference Across GPU Fleets"
slug: "llmkube-unifies-llm-inference-across-gpu-fleets"
description: "LLMKube is a Kubernetes operator that manages LLM inference across heterogeneous GPU fleets, including NVIDIA, AMD, Intel, and Apple Silicon hosts. It turns deployment into a two-resource YAML setup..."
date: 2026-11-17T12:12:52+05:30
tags: [Kubernetes, LLM, Inference, GPUs, OpenAIAPI]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Cloud Computing", "Open Source"]
image: "https://avatars.githubusercontent.com/u/69058620?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LLMKube Unifies LLM Inference Across GPU Fleets

LLMKube is a Kubernetes operator that manages LLM inference across heterogeneous GPU fleets, including NVIDIA, AMD, Intel, and Apple Silicon hosts. It turns deployment into a two-resource YAML setup and can expose models through an OpenAI-compatible API.

## 🔍 Overview

Define a `Model` and an `InferenceService`; the operator handles model downloading and caching, GPU scheduling, health checks, scaling, and API exposure. Linux GPU pods and Apple Silicon hosts both appear as `InferenceService` objects to `kubectl`.

## 🧩 How it works

The system has two cooperating processes:

- An in-cluster controller manages Kubernetes-side desired state.
- An optional out-of-cluster metal-agent is used for Apple Silicon hosts. It supervises OS-level processes and registers authenticated ingress with the cluster. An in-cluster relay fronts that ingress, so Metal `InferenceService` objects are ordinary Services.

On Apple Silicon, inference runs as native macOS processes rather than containers, allowing full Metal GPU access.

## ⚙️ Supported hardware and runtimes

| Hardware or runtime | Details in the evidence |
| --- | --- |
| NVIDIA | CUDA support |
| AMD | Vulkan support |
| Intel | Listed among supported heterogeneous fleet hosts |
| Apple Silicon | Metal support; native macOS inference processes |
| Runtimes | llama.cpp, vLLM, TGI, and mlx-server |
| Apple Silicon processes | The Metal Agent runs llama-server, mlx-server, and vllm-swift |

Other capabilities include multi-GPU sharding, model caching, and running models across NVIDIA, Apple Silicon, and AMD from one spec.

## 🔐 Routing and policy

Adding a `ModelRouter` enables policy-aware routing between local models and external providers, including Anthropic, OpenAI, and LiteLLM. A rule matching requests labeled `pii/phi` by header can route only to local-tier backends. Content detection is planned (#441).

## 🚀 Availability and maturity

LLMKube is Apache-2.0 licensed, actively developed, and intended to run across homelab and on-prem fleets. It is pre-1.0: every CRD is `v1alpha1`, and fields can change between minor releases. For running one model on one laptop, Ollama is simpler.

#Kubernetes #LLM #Inference #GPUs #OpenAIAPI

---

*Source: [defilantech/LLMKube](https://github.com/defilantech/LLMKube)*
