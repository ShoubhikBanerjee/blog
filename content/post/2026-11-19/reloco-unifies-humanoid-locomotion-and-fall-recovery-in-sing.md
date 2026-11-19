---
title: "ReLoco Unifies Humanoid Locomotion and Fall Recovery in Single Policy"
slug: "reloco-unifies-humanoid-locomotion-and-fall-recovery-in-single-policy"
description: "A new framework called ReLoco enables humanoid robots to walk, run, recover from falls, and resume commanded motion using a single proprioceptive policy without controller switching or on-robot..."
date: 2026-11-19T12:23:35+05:30
tags: [Robotics, Humanoid, Locomotion, FallRecovery, ReinforcementLearning, Sim2Real]
categories: ["AI", "Robotics", "Machine Learning", "Artificial Intelligence", "Control Systems"]
author: "Shoubhik Banerjee"
draft: false
---

# ReLoco Unifies Humanoid Locomotion and Fall Recovery in Single Policy

A new framework called ReLoco enables humanoid robots to walk, run, recover from falls, and resume commanded motion using a single proprioceptive policy without controller switching or on-robot fine-tuning. The approach was validated on the 64.5-kg Tiangong 3.0 humanoid platform.

## 🔍 Overview
- **Paper title**: ReLoco: Unified Humanoid Locomotion and Fall Recovery via Behavior-Conditioned Motion Priors
- **Submission date**: 18 Nov 2026
- **Domain**: Computer Science > Robotics
- **Core contribution**: One policy handles locomotion, get-up from arbitrary fallen postures, and command resumption
- **Deployment platform**: 64.5-kg Tiangong 3.0 humanoid

## 🧩 How it works
- Uses **behavior-conditioned adversarial motion priors** to learn diverse behaviors
- Robot posture selects the expert pool and conditions a **shared discriminator with two behavior-specific outputs**
- **Task rewards and shared regularization** support command tracking and recovery
- **Temporary assistance** facilitates exploration during training
- **Simulation-based refinement stage** supplies robot-executed motion references for supervision
- Ablations examine conditional supervision, output separation, and reference quality under matched settings

## ⚙️ Key details
| Capability | Result |
|------------|--------|
| Independent get-up success | 96.80% |
| Push-recovery success (with command resumption) | 96.96% |
| Torso planar velocity RMSE | 0.1266 m/s |
| Improvement over conditional single-output variant | 14.7% lower RMSE |
| Joint-angle discrepancy (dynamic time warping) | Similar to variant |

- Achieves walking, running, get-up, and locomotion resumption after falls
- Operates with **one proprioceptive actor** — no controller switching
- Requires **no on-robot policy fine-tuning**

## 🚀 Availability
- Paper available via arXiv (PDF and experimental HTML views)
- Associated code and media linked through alphaXiv, CatalyzeX, DagsHub, Gotit.pub, Hugging Face, and ScienceCast
- Demos referenced in paper metadata

## 💡 Why it matters
ReLoco demonstrates that a single learned policy can unify continuous locomotion and discrete fall recovery — traditionally handled by separate controllers — while transferring from simulation to a physical 64.5-kg humanoid without additional tuning. The behavior-conditioned adversarial motion prior structure and simulation-based refinement stage provide a template for learning diverse, contact-rich behaviors under a shared architecture.

#Robotics #Humanoid #Locomotion #FallRecovery #ReinforcementLearning #Sim2Real

---

*Source: [ReLoco: Unified Humanoid Locomotion and Fall Recovery via Behavior-Conditioned Motion Priors](https://arxiv.org/abs/2611.23916v1)*
