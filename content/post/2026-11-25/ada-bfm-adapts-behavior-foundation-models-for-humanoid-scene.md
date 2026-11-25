---
title: "Ada-BFM Adapts Behavior Foundation Models for Humanoid Scene Interaction"
slug: "ada-bfm-adapts-behavior-foundation-models-for-humanoid-scene-interaction"
description: "Ada-BFM, a post-training framework, adapts behavior foundation models for humanoid scene interaction while preserving pretrained whole-body control capabilities."
date: 2026-11-25T12:10:39+05:30
tags: [Robotics, MachineLearning, SceneInteraction]
categories: ["AI", "Robotics", "Machine Learning", "Foundation Models"]
author: "Shoubhik Banerjee"
draft: false
---

# Ada-BFM Adapts Behavior Foundation Models for Humanoid Scene Interaction

Ada-BFM, a post-training framework, adapts behavior foundation models for humanoid scene interaction while preserving pretrained whole-body control capabilities.

## 🔍 Overview
- BFMs emerged as a promising paradigm for general-purpose humanoid control through pretraining on large-scale behavioral data.
- Their proficiency in whole-body coordination does not readily extend to scene interaction, which requires adapting motion to scene-dependent geometric constraints and contact dynamics.
- Ada-BFM is introduced as a post-training framework that adapts pretrained BFMs for humanoid scene interaction.

## 🧩 How it works
- Ada-BFM augments the original architecture with a lightweight adapter, enabling interaction-specific adjustments while leveraging pretrained control capabilities.
- Rather than producing a separate controller for each task, the framework yields a shared model for each interaction domain.
- This shared model supports diverse tasks involving terrain or object interaction.

## ⚙️ Key details
- Extensive experiments in simulation and the real world demonstrate that Ada-BFM enables diverse scene interaction behaviors.
- Ada-BFM accelerates learning compared with training from scratch.
- Ada-BFM largely preserves pretrained behavioral competence.

## 💡 Why it matters
- These findings establish Ada-BFM as an effective and efficient approach to extending the capabilities of BFMs beyond their pretraining settings.
- The approach retains the strengths of BFMs in general whole-body control.
- Title: Ada-BFM: Adapting Behavior Foundation Models for Humanoid Scene Interaction
- Submitted on 24 Nov 2026

#Robotics #MachineLearning #SceneInteraction

---

*Source: [Ada-BFM: Adapting Behavior Foundation Models for Humanoid Scene Interaction](https://arxiv.org/abs/2611.31863v1)*
