---
title: "EyeDiT: Advancing 3D Eye Generation for AR/VR Applications"
slug: "eyedit-advancing-3d-eye-generation-for-ar-vr-applications"
description: "Synthetic eye data are critical for rapid development of eye tracking (ET) in AR/VR applications. However, existing synthetic eye generators are largely image-centric and lack a high-quality..."
date: 2026-11-19T18:06:46+05:30
tags: [EyeTracking, ARVR, SyntheticData, 3DEyeGeneration]
categories: ["AI", "Computer Vision", "Artificial Intelligence", "Augmented Reality", "Virtual Reality"]
author: "Shoubhik Banerjee"
draft: false
---

# EyeDiT: Advancing 3D Eye Generation for AR/VR Applications

Synthetic eye data are critical for rapid development of eye tracking (ET) in AR/VR applications. However, existing synthetic eye generators are largely image-centric and lack a high-quality underlying 3D anatomy of the eye, which limits their control mainly to the gaze and provides no anatomical labels.

## 🔍 Overview
- Synthetic eye data are critical for rapid development of eye tracking (ET) in AR/VR applications.
- Existing synthetic eye generators are largely image-centric and lack a high-quality underlying 3D anatomy of the eye.

## 🧩 How it works
- EyeDiT is an anatomy-grounded, multi-modal 3D eye generation and simulation model trained with optical coherence tomography (OCT), labeled anatomy point clouds and near-eye images.
- The pipeline first trains a Multi-Modal Anatomy Variational Autoencoder (VAE), which encodes an anatomy-aware latent representation from all input modalities.
- Then, Eye Latent DiT is trained to generate latent samples conditioned on the optical axis, the pupil position and radius, and the subject identity.
- The model enables control over the pupil, subject identity and viewpoint for data synthesis.

## ⚙️ Key details
- The model outperforms previous eye image synthesis models in novel-view synthesis (24.9 against 21.8 dB PSNR from a single view).
- A public ET neural network trained on EyeDiT's synthetic data shows a smaller sim-to-real gap than when trained on data from other generators (3.5° vs. 8.4° gaze error).
- The network approaches a network trained on real data, and further improves ET performance when combined with real data (2.3° vs. 2.6°).

## 🚀 Availability
- More information is available on the project page: [EyeDiT Project Page](https://this-url.com)

## 💡 Why it matters
- EyeDiT addresses the limitations of existing synthetic eye generators by providing a high-quality underlying 3D anatomy of the eye.
- The model enables control over the pupil, subject identity and viewpoint for data synthesis, which is critical for rapid development of eye tracking (ET) in AR/VR applications.
- The model outperforms previous eye image synthesis models and shows a smaller sim-to-real gap when used to train a public ET neural network.

#EyeTracking #ARVR #SyntheticData #3DEyeGeneration

---

*Source: [EyeDiT: Anatomy-Grounded Multi-Modal Eye Generation and Simulation](https://arxiv.org/abs/2611.23670v1)*
