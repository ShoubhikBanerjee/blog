---
title: "Synthetic Data Augmentation Pipeline Improves Industrial Safety Person Detection"
slug: "synthetic-data-augmentation-pipeline-improves-industrial-safety-person-detection"
description: "A new end-to-end synthetic data augmentation pipeline has been developed to improve person-detection models for industrial safety AI. The system generates labeled training images to address the..."
date: 2026-09-17T22:02:13+05:30
tags: [IndustrialSafety, ComputerVision, SyntheticData, AmazonSageMaker, PersonDetection]
categories: ["AI", "Machine Learning", "Computer Vision", "Industrial AI"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/01/ML-20809-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Synthetic Data Augmentation Pipeline Improves Industrial Safety Person Detection

A new end-to-end synthetic data augmentation pipeline has been developed to improve person-detection models for industrial safety AI. The system generates labeled training images to address the scarcity of images showing people in dangerous proximity to heavy machinery.

## 💡 Why it matters
Industries using autonomous equipment in agriculture, construction, mining, and manufacturing require reliable person-detection models. These models must run on edge devices co-located with equipment—such as cameras on railcars, forklifts, or tractors—which necessitates lightweight architectures where every training example is disproportionately important. 

Traditional data collection poses significant challenges:
* Manual annotation and collection can cost an estimated $3–$5 per image.
* Scaling is difficult, with annotation teams typically processing around 2,000 images per day.
* Obtaining images of people in hazardous positions often requires hazardous photography sessions.

## 🧩 How it works
Rather than generating synthetic scenes from scratch, this approach edits real images that contain equipment but no people. 

| Component | Function |
| :--- | :--- |
| Qwen-Image-Edit-2509 | A diffusion-based model that inserts synthetic people into real scenes while preserving lighting, scale, and background. |
| Amazon SageMaker AI | Hosts the diffusion model using an ml.g5.12xlarge instance (4× NVIDIA A10G GPUs, 96 GB total VRAM). |
| Amazon Rekognition DetectLabels API | Automatically generates bounding-box annotations for the inserted people. |

The pipeline follows these steps:
1. **Prompting**: The model receives a structured prompt specifying a person with randomized gender for demographic diversity, hazardous positioning (e.g., on tracks, hanging from edges, or in a vehicle's path), and constraints to ensure sharp focus and no distortion.
2. **Labeling**: The Rekognition DetectLabels API processes images with a minimum confidence threshold of 80 percent.
3. **Refinement**: Bounding boxes are deduplicated using non-maximum suppression (NMS) with an IoU threshold > 0.5 and converted to YOLO format.
4. **Merging**: These pseudo-labels are merged with original equipment annotations and combined with real training data.
5. **Automation**: Image filtering, resizing, prompt assembly, and label processing are handled as an automated workflow.

## ⚙️ Key details
Experiments using this pipeline showed up to 160 percent improvement in person detection mAP50 (mean Average Precision at an Intersection over Union threshold of 0.5) without requiring manual annotation or hazardous photography.

#IndustrialSafety #ComputerVision #SyntheticData #AmazonSageMaker #PersonDetection

---

*Source: [Enhancing industrial safety AI with synthetic data on Amazon SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/enhancing-industrial-safety-ai-with-synthetic-data-on-amazon-sagemaker-ai/)*
