---
title: "New Release 1.0.31: Enhancements and Fixes in AI Model Development"
slug: "new-release-1-0-31-enhancements-and-fixes-in-ai-model-development"
description: "The latest release, version 1.0.31, introduces several enhancements and fixes across various AI models, including ViT, EVA, BEiT, NaFlexViT, RepViT, and iFormer. These updates ensure normalization..."
date: 2026-11-17T18:10:30+05:30
tags: [AI, MachineLearning, ModelDevelopment, DeepLearning, ComputerVision]
categories: ["AI", "Machine Learning", "AI Models", "Deep Learning", "Computer Vision"]
image: "https://avatars.githubusercontent.com/u/25720743?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New Release 1.0.31: Enhancements and Fixes in AI Model Development

## 🔍 Overview
The latest release, version 1.0.31, introduces several enhancements and fixes across various AI models, including ViT, EVA, BEiT, NaFlexViT, RepViT, and iFormer. These updates ensure normalization placement and distillation settings are preserved when exporting or reloading models after changing the classifier or pooling.

## 🧩 How it works
- **Fixes and Improvements**:
  - `reset_classifier()` and checkpoint reconstruction fixes for multiple models.
  - Support for SwiGLU alignment in DINOv3 and Lingbot checkpoints.
  - Preservation of grayscale/non-RGB input channels in data loaders.
  - Layer-wise LR decay grouping fixes for RepViT, HGNet, MViTv2, and pre-norm ViTs.
  - InceptionNeXt feature sizes with `output_stride=8/16`.

- **New Features**:
  - `forward_intermediates()` and `prune_intermediate_layers()` support for various models.
  - `features_only` support for CoaT, ConViT, ConvMixer, CrossViT, and Visformer.
  - `prune_head=True` removes the whole head, while `prune_head=False` keeps it.
  - Pruning a hierarchical model to an earlier stage removes the final norm and head sized for the last stage.
  - `head_hidden_size` is the actual pre-logits (pooled) width in all models.
  - Pool types a model can't apply now raise at creation / reset instead of being silently ignored or failing in forward.
  - VOLO `num_classes=0` output is the class token embedding.
  - Hyperparameter sweeps via a new `sweep.py` for grid/random search over any `train.py` argument.
  - WSD sweeps train one stable trunk per hyperparameter combination.
  - `train.py` enhancements for resuming, stopping, and saving epochs.
  - Add CSPNeXt with ImageNet-1k classification weights converted from OpenMMLab.
  - Foreach steps are chunked by device L2 cache size.
  - RMS update clipping for AdamWLegacy / NAdamW.
  - New decoupled/corrected weight decay NovoGrad variants.
  - Foreach (multi-tensor) impls for RMSpropTF, LaProp, LAMB, LARS, AdaBelief.

## ⚙️ Key details
- **Model Fixes**:
  - `reset_classifier()` and checkpoint reconstruction fixes for ViT, EVA, BEiT, NaFlexViT, RepViT, and iFormer.
  - Unpooled PiT export and EfficientFormerV2 with distillation disabled.
  - NaFlex: fix ViT / EVA norm placement during conversion.
  - Layer-wise LR decay grouping for RepViT, HGNet, MViTv2, and pre-norm ViTs.
  - InceptionNeXt feature sizes with `output_stride=8/16`.

- **New Features**:
  - `forward_intermediates()` and `prune_intermediate_layers()` support for CSPNet, NFNet, DLA, DenseNet, CoaT, ConViT, ConvMixer, CrossViT, HRNet, Inception-v3, Inception-ResNet-v2, NASNet, PNASNet, SelecSLS, SENet, Sequencer2d, VGG, Visformer, Xception, and Aligned Xception.
  - `features_only` support for CoaT, ConViT, ConvMixer, CrossViT, and Visformer.
  - `prune_head=True` removes the whole head.
  - `prune_head=False` keeps the head.
  - Pruning a hierarchical model to an earlier stage removes the final norm and head sized for the last stage.
  - `head_hidden_size` is the actual pre-logits (pooled) width in all models.
  - Pool types a model can't apply now raise at creation / reset instead of being silently ignored or failing in forward.
  - VOLO `num_classes=0` output is the class token embedding.
  - Hyperparameter sweeps via a new `sweep.py` for grid/random search over any `train.py` argument.
  - WSD sweeps train one stable trunk per hyperparameter combination.
  - `train.py` enhancements for resuming, stopping, and saving epochs.
  - Add CSPNeXt with ImageNet-1k classification weights converted from OpenMMLab.
  - Foreach steps are chunked by device L2 cache size.
  - RMS update clipping for AdamWLegacy / NAdamW.
  - New decoupled/corrected weight decay NovoGrad variants.
  - Foreach (multi-tensor) impls for RMSpropTF, LaProp, LAMB, LARS, AdaBelief.

## 🚀 Availability
- Release 1.0.31 is now available with these enhancements and fixes.

## 💡 Why it matters
These updates ensure better model performance, stability, and flexibility, making it easier for developers to work with various AI models and configurations.

#AI #MachineLearning #ModelDevelopment #DeepLearning #ComputerVision

---

*Source: [huggingface/pytorch-image-models](https://github.com/huggingface/pytorch-image-models)*
