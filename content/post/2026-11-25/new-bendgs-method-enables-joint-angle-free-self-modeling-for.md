---
title: "New BendGS Method Enables Joint-Angle-Free Self-Modeling for Continuum Robots"
slug: "new-bendgs-method-enables-joint-angle-free-self-modeling-for-continuum-robots"
description: "A new AI development called BendGS enables continuum robots to predict their next 3D shape, appearance, and tip pose from observed images without relying on measured joint angles or fixed link..."
date: 2026-11-25T18:07:47+05:30
tags: [Robotics, ComputerVision, AIResearch, SelfModeling, 3DGaussians]
categories: ["AI", "Robotics", "Computer Vision", "Machine Learning"]
author: "Shoubhik Banerjee"
draft: false
---

# New BendGS Method Enables Joint-Angle-Free Self-Modeling for Continuum Robots

## Intro
A new AI development called BendGS enables continuum robots to predict their next 3D shape, appearance, and tip pose from observed images without relying on measured joint angles or fixed link geometry, addressing a key limitation in existing visual self-modeling approaches.

## 🔍 Overview
- Visual self-models learn from images how a robot moves under motor commands.
- Continuum robots need them even more, as they bend continuously without measured joint angles or fixed link geometry.
- Existing continuum self-models predict point clouds, image-space curves, or future images, but not the next 3D shape, appearance, and tip pose together from an observed body.
- 3D Gaussians offer a renderable representation of shape and appearance, yet articulated Gaussian self-models rely on joint angles to drive deformation.

## 🧩 How it works
- BendGS uses a virtual backbone estimated from observation to drive command-conditioned Gaussian deformation, enabling next-state prediction for continuum robots without measured joint angles.
- In Gaussian modeling, a feed-forward network reconstructs the robot as 3D Gaussians from multi-view images, and the backbone, a chain of coordinate frames, is fitted to back-projected depth points to estimate the bending state.
- In transition, a network predicts its change under a relative motor command to deform the bound Gaussians.
- The deformed Gaussians render the next images and the 3D shape, and the distal frame gives the tip pose.

## ⚙️ Key details
- Training losses use RGB-D images and masks, without bending or tip labels.
- On simulated and real robots, BendGS achieves the lowest Chamfer distance, best image quality, and lowest tip errors among the compared methods.

## 🚀 Availability
- BendGS: Observation-Conditioned Gaussian Self-Modeling for Continuum Robots
- [Submitted on 24 Nov 2026]
- Computer Science > Robotics

#Robotics #ComputerVision #AIResearch #SelfModeling #3DGaussians

---

*Source: [BendGS: Observation-Conditioned Gaussian Self-Modeling for Continuum Robots](https://arxiv.org/abs/2611.31844v1)*
