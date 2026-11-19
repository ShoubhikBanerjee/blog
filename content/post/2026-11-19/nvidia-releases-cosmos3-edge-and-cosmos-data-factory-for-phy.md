---
title: "NVIDIA Releases Cosmos3-Edge and Cosmos Data Factory for Physical AI Development"
slug: "nvidia-releases-cosmos3-edge-and-cosmos-data-factory-for-physical-ai-development"
description: "NVIDIA has released Cosmos3-Edge, a 4B parameter model tier optimized for on-device, real-time deployment on Jetson AGX Orin, Thor, and RTX Pro 6000. This follows the release of Cosmos 3, an open..."
date: 2026-11-19T18:06:46+05:30
tags: [NVIDIA, Cosmos, PhysicalAI, SyntheticData, Robotics]
categories: ["AI", "Artificial Intelligence", "Computer Vision", "Machine Learning"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/cosmos-gif.gif"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases Cosmos3-Edge and Cosmos Data Factory for Physical AI Development

NVIDIA has released Cosmos3-Edge, a 4B parameter model tier optimized for on-device, real-time deployment on Jetson AGX Orin, Thor, and RTX Pro 6000. This follows the release of Cosmos 3, an open platform of world models, datasets, frameworks, and tools designed to enable physical AI applications across robotics, autonomous vehicles, smart infrastructure, manufacturing, healthcare, and agriculture.

## 🔍 Overview

NVIDIA Cosmos is an open platform developed to provide physical AI developers with better data, a better environment, a better starting point, and better tooling. The underlying Cosmos 3 model family is built on a unified Mixture-of-Transformers architecture. These omnimodal world models are capable of seeing, reasoning, simulating, and acting, allowing them to render physical momentum, perform forward dynamics, and reason in complex real-world scenarios.

## 🛠️ Cosmos Data Factory Blueprints

As part of this platform, NVIDIA Cosmos Data Factory (CDF) provides five cloud-native blueprints and six composable skills to accelerate data curation, processing, and synthetic data generation (SDG). AI agents can orchestrate these blueprints for prompt-to-data workflows without human steering.

| Blueprint | Function | Key Components Used |
| :--- | :--- | :--- |
| **Autonomous Vehicle Dataset Generation** | Searches databases of driving scenarios and generates novel datasets for model training and validation. | Cosmos Curator, Dataset Search, Cosmos3-Super-Image2Video, Cosmos Evaluator |
| **Image Attribute Augmentation** | Generates variations of person-crops with controlled changes to attributes like clothing, accessories, and color. | LLM, Cosmos Evaluator |
| **Video Data Augmentation** | Transforms existing footage across weather, lighting, and environmental conditions while preserving scene structure. | VLM, Cosmos3-Nano, Cosmos Evaluator |
| **Event Video Generation** | Uses a source image to create videos of rare events like fires, falls, or shoplifting. | VLM, Cosmos3-Super-Image2Video, Cosmos Evaluator |

## ⚙️ Key details

The workflows and blueprints within Cosmos Data Factory are powered by several core tools and skills:

*   **CDF Orchestration Core Skill**: Coordinates workflow steps, deploys required services, and manages execution on your cluster.
*   **Preflight and Setup**: Preflight checks the cluster environment without making changes to flag missing components, while setup configures the environment to run the blueprints.
*   **NVIDIA Cosmos Curator**: Extracts metadata for video dataset inputs, and works with Cosmos Dataset Search to locate relevant videos through embeddings.
*   **Cosmos Evaluator**: Reviews generated content to verify the requested attributes or conditions appear, and evaluates whether motion is physically plausible without artifacts.
*   **Cosmos Framework**: Provides training infrastructure supporting supervised fine-tuning (SFT), LoRA, reinforcement learning (RL), and distillation.

## 🚀 Availability

*   **Cosmos 3**: Released in May 2026, comprising the unified Mixture-of-Transformers model family.
*   **Cosmos3-Edge**: Released in July 2026, offering a 4B parameter tier for on-device, real-time deployment on Jetson AGX Orin, Thor, and RTX Pro 6000 hardware platforms.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/cosmos-av-dataset-workflow.gif)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image-attribute-augmentation-reference-blueprint.gif)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/video-data-augmentation-reference-blueprint.gif)

#NVIDIA #Cosmos #PhysicalAI #SyntheticData #Robotics

---

*Source: [Build Training-Ready Physical AI Datasets with Two Prompts in NVIDIA Cosmos | NVIDIA Technical Blog](https://developer.nvidia.com/blog/build-training-ready-physical-ai-datasets-with-two-prompts-in-nvidia-cosmos/)*
*Source: [NVIDIA/cosmos](https://github.com/NVIDIA/cosmos)*
