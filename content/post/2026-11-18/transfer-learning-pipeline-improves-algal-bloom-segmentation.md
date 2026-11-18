---
title: "Transfer-Learning Pipeline Improves Algal Bloom Segmentation with Expanded Corpus"
slug: "transfer-learning-pipeline-improves-algal-bloom-segmentation-with-expanded-corpus"
description: "Researchers present a transfer-learning pipeline that adapts a Swin Transformer U-Net with SCSE decoder attention for harmful algal bloom segmentation, expanding the labeled dataset from 145 to 655..."
date: 2026-11-18T22:09:17+05:30
tags: [ComputerVision, TransferLearning, EnvironmentalMonitoring, SemanticSegmentation, RemoteSensing]
categories: ["AI", "Machine Learning", "Computer Vision", "Environmental Science", "Remote Sensing"]
author: "Shoubhik Banerjee"
draft: false
---

# Transfer-Learning Pipeline Improves Algal Bloom Segmentation with Expanded Corpus

Researchers present a transfer-learning pipeline that adapts a Swin Transformer U-Net with SCSE decoder attention for harmful algal bloom segmentation, expanding the labeled dataset from 145 to 655 images.

## 🔍 Overview
- Transfer-learning pipeline adapts Swin Transformer U-Net with SCSE decoder attention from ImageNet-1K to water-body segmentation (RIWA, LaRS) then to algal blooms
- Model-assisted annotation protocol expands labeled algae corpus from 145 to 655 images
- Harmful algal blooms threaten water quality and public health; automated segmentation limited by scarce pixel-level annotations

## 🧩 How It Works
- Pipeline stages: ImageNet-1K pretraining → water-body segmentation (RIWA, LaRS) → algal bloom segmentation
- Model-assisted annotation protocol used to expand corpus
- Architecture: Swin Transformer U-Net with SCSE decoder attention

## ⚙️ Key Details
### Ablation Results (41-image validation split, checkpoint S2-A4)
- Corpus expansion: +11 mIoU points (dominant factor)
- Water-body pretraining: +1.1 mIoU points over ImageNet initialization (only on expanded corpus)
- SCSE attention: +0.3 mIoU points
- Learnable positional encoding: -0.6 mIoU points (omitted)

### Corpus Expansion Impact
- Added 476 images (188 algae-free)
- Reduced false-positive area on non-water scenes from 22.6% to 4.9%

### Test Set Performance (256-image test split, checkpoint S2-A13)
- mIoU: 0.919
- Algae IoU: 0.902 (highest among nine baselines)
- Near-duplicate audit indicates train/test overlap; scores likely optimistic

## 💡 Why It Matters
- Addresses scarcity of pixel-level annotations for freshwater algal bloom segmentation
- Demonstrates corpus expansion is more impactful than architectural tweaks
- Model-assisted annotation protocol enables efficient dataset scaling
- Reduces false positives on non-water scenes, improving practical deployment

#ComputerVision #TransferLearning #EnvironmentalMonitoring #SemanticSegmentation #RemoteSensing

---

*Source: [Data-Efficient Algal Bloom Segmentation in Freshwater Bodies Using a Three-Stage Transfer Learning Pipeline with Attention-Enhanced Decoding](https://arxiv.org/abs/2611.22064v1)*
