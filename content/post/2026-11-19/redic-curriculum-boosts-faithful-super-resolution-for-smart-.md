---
title: "ReDiC Curriculum Boosts Faithful Super-Resolution for Smart‑Glasses Images"
slug: "redic-curriculum-boosts-faithful-super-resolution-for-smartglasses-images"
description: "Smart‑glasses captures often suffer degradations that hide small text and fine details needed by vision‑language models. A new training curriculum, ReDiC, improves super‑resolution (SR) fidelity..."
date: 2026-11-19T22:12:49+05:30
tags: [SuperResolution, SmartGlasses, ComputerVision, CurriculumLearning]
categories: ["AI", "Computer Vision", "Machine Learning", "Imaging Technology"]
author: "Shoubhik Banerjee"
draft: false
---

# ReDiC Curriculum Boosts Faithful Super-Resolution for Smart‑Glasses Images

Smart‑glasses captures often suffer degradations that hide small text and fine details needed by vision‑language models. A new training curriculum, ReDiC, improves super‑resolution (SR) fidelity while keeping the same SR architecture.

## 🔍 Overview
- Introduces a high‑resolution (HR)‑referenced semantic evaluation protocol that compares VLM outputs on restored images with those on HR references.
- Evaluation uncovers two failure modes:
  - Generative SR may synthesize misleading details.
  - Restoration‑oriented SR may leave critical evidence blurred or ambiguous.
- These findings drive the need for more faithful detail recovery.

## 📉 Problem
- Degradations in smart‑glasses images obscure small text and fine‑grained structures required for visual assistance.
- Training must present inputs that are challenging yet still recoverable.

## 🛠️ Method
- Proposes **ReDiC** (Recoverability‑Difficulty Curriculum).
- Combines a model‑independent recoverability proxy with a model‑relative restoration difficulty metric to adapt degradation severity during training.
- Adjusts severity:
  - **Increase** when inputs are recoverable and restoration is easy.
  - **Maintain** challenging but recoverable conditions.
  - **Decrease** when estimated recoverability is low.
- Changes only the training degradation generation; the SR architecture and reconstruction objective stay unchanged.

## 📊 Results
- Improves average PSNR by ~2.5 dB.
- Boosts HR‑referenced semantic scores by ~3 points.
- Gains observed across **NAFNet**, **SwinIR**, and **MambaIR**.
- Confirmed on synthetic benchmarks, LLM‑based evaluations, and human evaluations.
- Evaluations performed on 200 real smart‑glasses captures.

## 💡 Why it matters
- Enhances the reliability of visual assistance systems that rely on VLMs.
- Provides a curriculum that keeps SR training both challenging and recoverable, leading to more trustworthy restored images.

#SuperResolution #SmartGlasses #ComputerVision #CurriculumLearning

---

*Source: [Learning What to Degrade: A Recoverability-Aware Curriculum for Reliable Smart-Glasses Super-Resolution](https://arxiv.org/abs/2611.23674v1)*
