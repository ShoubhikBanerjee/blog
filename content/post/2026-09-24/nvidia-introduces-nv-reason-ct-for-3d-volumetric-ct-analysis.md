---
title: "NVIDIA Introduces NV-Reason-CT for 3D Volumetric CT Analysis"
slug: "nvidia-introduces-nv-reason-ct-for-3d-volumetric-ct-analysis"
description: "NVIDIA has developed NV-Reason-CT, a vision language model (VLM) specifically designed for 3D CT analysis. This foundation model extends chain-of-thought reasoning to full volumetric CT scans to..."
date: 2026-09-24T18:02:55+05:30
tags: [NVIDIA, MedicalAI, ComputerVision, CTAnalysis, VLM]
categories: ["AI", "Machine Learning", "Healthcare AI", "Computer Vision"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/ct-scan-image-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Introduces NV-Reason-CT for 3D Volumetric CT Analysis

NVIDIA has developed NV-Reason-CT, a vision language model (VLM) specifically designed for 3D CT analysis. This foundation model extends chain-of-thought reasoning to full volumetric CT scans to support the generation of structured diagnostic reports and multistep follow-up conversations.

## 🔍 Overview
NV-Reason-CT is an open research and development foundation model intended for researchers and developers to post-train for specialized CT analysis applications. It is not a cleared clinical product or an autonomous diagnostic system.

Key capabilities include:
* Generating detailed structured diagnostic reports.
* Emulating the internal thinking process of radiologists, including systematic examination of anatomical regions, surfacing findings, considering differential diagnoses, and articulating uncertainty.
* Supporting multistep follow-up conversations where clinicians and researchers can request clarifications on differential diagnoses or probe the model's reasoning.

## 🧩 How it works
NV-Reason-CT processes CT volumes as native 3D inputs rather than independent 2D slices. This approach allows the model to reconstruct anatomical context across three spatial dimensions, which is necessary for studies that can comprise 300–600 axial slices.

* **Architecture**: The model combines a Qwen3.5-4B LLM with a 3D Vision Transformer (ViT) encoder (Primus/Colipri).
* **3D Encoding**: The encoder, adapted from Primus 3D ViT and initialized with Colipri weights, processes CT volumes resampled to 192³ voxels at 2 mm isotropic resolution using non-overlapping 8x8x8 patch tokens. This results in a vision token context of 13,824 (24x24x24).
* **Spatial Integration**: All vision tokens and their 3D grid coordinates are passed to the LLM. The LLM utilizes 3D MRoPE to account for the spatial inter-token relationships.
* **Training**: Weights are retrained end-to-end using a large cohort of CT data featuring structured reports, reasoning traces, and internally designed multistep VQA.

## ⚙️ Key details
To guide and evaluate the model, the NVIDIA team curated a CT ontology covering 59 total abnormalities in a format mapping to clinical documentation workflows:

| Region | Number of Abnormalities | Examples |
| :--- | :--- | :--- |
| Chest | 30 | Lung nodules, pneumothorax |
| Abdomen | 29 | Hepatic lesions, renal cysts |

## 💡 Why it matters
NV-Reason-CT builds on the reasoning methodology of NV-Reason-CXR. That preceding model was validated in a multireader clinical study accepted at RSNA 2026, which confirmed that the approach maintained diagnostic accuracy while providing radiologist time savings.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/ct-scan-image-1024x576.jpg)

#NVIDIA #MedicalAI #ComputerVision #CTAnalysis #VLM

---

*Source: [Introducing NV-Reason-CT Open 3D CT VLM for Radiologist Chain-of-Thought Reasoning | NVIDIA Technical Blog](https://developer.nvidia.com/blog/introducing-nv-reason-ct-open-3d-ct-vlm-for-radiologist-chain-of-thought-reasoning/)*
