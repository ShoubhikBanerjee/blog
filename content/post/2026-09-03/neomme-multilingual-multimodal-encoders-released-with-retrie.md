---
title: "NeoMME multilingual multimodal encoders released with retrieval variants"
description: "NeoMME, a new family of multilingual multimodal encoders, has been released in 260M and 800M parameter sizes, including a specialized NeoMME-Retriever variant for document image retrieval. The models..."
date: 2026-09-03T22:06:46+05:30
tags: [multimodalAI, informationretrieval, documentAI, openweights, transformers]
categories: [AI]
image: "https://cdn-uploads.huggingface.co/production/uploads/6264f9655f6f2e14d6ac981c/GJ6FUbgFpq1x8RNOqzmz-.webp"
author: "Shoubhik Banerjee"
draft: false
---

# NeoMME multilingual multimodal encoders released with retrieval variants

NeoMME, a new family of multilingual multimodal encoders, has been released in 260M and 800M parameter sizes, including a specialized NeoMME-Retriever variant for document image retrieval. The models are trained from scratch using a masked discrete-diffusion objective and are available under the Apache 2.0 license.

## 🔍 Overview

NeoMME (pronounced "nee-oh-me", IPA /ˈniː.oʊmi/) is a multilingual, multimodal foundation encoder that generates vector representations for text and/or images using a single Transformer encoder. Key characteristics include:

- Not based on any existing pretrained vision tower, text encoder, or text decoder
- Images and text share the same computational path
- Supports pretraining, fine-tuning, parallelization, and serving across both modalities
- Two model sizes: 260M and 800M parameters
- Context length of 16,384 tokens (enough for up to two standard 3840×2160 4K UHD images)
- Available in Hugging Face Transformers
- All model checkpoints released under Apache 2.0 license

## 🧩 How it works

NeoMME processes both modalities through a single bidirectional Transformer:

- **Text inputs**: factorized token embeddings using a BPE tokenizer with 131k-token vocabulary trained from scratch on multilingual text, code, mathematics, and machine-produced image transcripts
- **Image inputs**: divided into a grid of non-overlapping 32×32 patches, projected with a small MLP

The encoder architecture incorporates several recent improvements:

- Grouped-query attention
- Query-key normalization
- Gated attention
- 2D rotary position embeddings
- Squared-ReLU MLPs
- Most layers use symmetric sliding-window attention
- Every sixth layer and the final layer use global attention

Training uses a masked discrete-diffusion objective:

- Pretrained from scratch as a discrete masked-diffusion text denoiser
- Multimodal examples use corruption rates between 0.3 and 1
- Pretraining mix includes multilingual text, code, mathematics, natural images, and document images
- Each model processes about 524 billion packed input tokens, including 290 billion tokens from text-only examples
- NorMuon optimizer used to improve data efficiency during training

## 🚀 NeoMME-Retriever

NeoMME-Retriever reuses the NeoMME backbone with two jointly trained heads added on top:

| Head | Function |
|------|----------|
| Dense head | Averages backbone hidden state vectors into a normalized vector (mean pooling) |
| Late-interaction head | Projects each text token or image patch from backbone output hidden states to a 128-dimensional normalized vector |

NeoMME-Retriever returns both dense and late-interaction embeddings in a single forward pass. It ranks document page screenshots directly, bypassing OCR preprocessing. This approach preserves layout, charts, tables, font type and size, and other visual clues that OCR cannot capture.

## ⚙️ Performance and efficiency

Both model sizes lie on the ViDoRe v3 Pareto frontier for nDCG@10 and model size.

Throughput at matched 2048×2048 image input size on NVIDIA L40S GPU:

- 260M model: ~51 pages per second
- Approximately 2× ColModernVBERT's throughput

Storage optimization through hierarchical token pooling and asymmetric quantization:

| Metric | Value |
|--------|-------|
| Late-interaction index reduction | ~1.5 MB → 6 kB per page |
| Compression factor | 255× smaller |
| nDCG@10 retained | >95% of baseline |

## 💡 Why it matters

NeoMME offers a unified architecture for multimodal understanding without relying on pretrained unimodal components. The shared computational path for text and images simplifies deployment and enables flexible use across pretraining, fine-tuning, and serving. For retrieval applications, NeoMME-Retriever's ability to process raw page images while maintaining competitive efficiency metrics provides an alternative to OCR-dependent document search pipelines.

![figure](https://github.com/tonywu71/colpali-cookbooks/blob/481c6ec8866f6f5d39d2d9dd06b5547c2d9a67fa/assets/neomme/architecture.webp?raw=true)

![figure](https://github.com/tonywu71/colpali-cookbooks/blob/481c6ec8866f6f5d39d2d9dd06b5547c2d9a67fa/assets/neomme/retrieval-heads.webp?raw=true)

![figure](https://github.com/tonywu71/colpali-cookbooks/blob/c5e737e7e474363822b6f2d95290c0120e0fa993/assets/neomme/vidore-v3-model-size.webp?raw=true)

#multimodalAI #informationretrieval #documentAI #openweights #transformers

---

*Source: [NeoMME: an efficient Multimodal-native and Multilingual Encoder](https://huggingface.co/blog/Hcompany/neomme)*
