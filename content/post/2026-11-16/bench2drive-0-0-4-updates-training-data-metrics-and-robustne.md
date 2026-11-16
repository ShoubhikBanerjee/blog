---
title: "Bench2Drive 0.0.4 updates training data, metrics, and robustness tests"
slug: "bench2drive-0-0-4-updates-training-data-metrics-and-robustness-tests"
description: "Bench2Drive version 0.0.4 has been released, introducing significant updates to the training data, evaluation protocols, and new modalities for autonomous driving research. The release accompanies..."
date: 2026-11-16T22:14:27+05:30
tags: [Bench2Drive, AutonomousDriving, NeurIPS2024, Benchmark, CARLA]
categories: ["AI"]
image: "https://avatars.githubusercontent.com/u/55233859?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Bench2Drive 0.0.4 updates training data, metrics, and robustness tests

Bench2Drive version 0.0.4 has been released, introducing significant updates to the training data, evaluation protocols, and new modalities for autonomous driving research. The release accompanies the acceptance of Bench2Drive at the NeurIPS 2024 Datasets and Benchmarks Track.

## 🧩 How it works

The update introduces a new Think2Drive-collected training set consisting of 44 scenarios and 25 routes, totaling 1,100 routes. Unlike the previous Base set, which had an uneven scenario distribution, the new set is strictly uniform over scenarios. Additionally, a new 3D occupancy (3D occ) modality has been added. 

A separate validation set of 220 routes is now available for more reliable evaluation. For quicker model development and ablation studies, a tiny validation set called Dev10 has been proposed. These 10 clips were carefully selected from the official 220 routes to be both difficult and representative with low variance, helping to avoid overfitting the full dataset.

## ⚙️ Key details

The evaluation protocol has been refined with two new metrics: Driving Efficiency and Driving Smoothness. The penalty for minimum speed in calculating the Drive Score has been removed, and the TickRunTime has been extended from 2000 to 4000 to allow for a more lenient driving evaluation. 

Specific bugs and errors have been addressed in this release:

* **Camera Projection:** The team_code agents for UniAD and VAD were updated to fix a bug where the back camera's extrinsic parameters were incorrect during evaluation.
* **Ability Calculation:** Typos in the ability calculation were corrected, and multi-ability results were updated. This correction does not affect the driving score or success rate.
* **Dataset Consistency:** A bug in the B2D_vad_dataset was identified but left in place to maintain consistency with existing results, as no major influence is anticipated.
* **Python Version Conflict:** Bench2Drive-VL enables closed-loop QA for VLM4AD. It provides an efficient communication interface between the VLM environment (Python 3.9+) and CARLA, which is only available for Python 3.7 and 3.8. Users encountering Python version errors should consider this protocol discrepancy.

| Component | Description |
| :--- | :--- |
| **Bench2Drive-Robust** | Analyzes model performance under real deployment issues, including camera-stream failures, ego-state estimation errors, and compute-control latency. |
| **Bench2Drive-Speed** | Estimates a new functionality for AD systems: speed customization. |
| **Bench2Drive-VL** | Enables closed-loop QA of VLM4AD and provides a communication bridge between Python 3.9+ and CARLA. |

## 💡 Why it matters

The update addresses methodological concerns in the field by stating that L2 error is not a meaningful indicator and that authors should stop reporting results on nuScenes open-loop planning. The release notes argue that these numbers are not persuasive and can lead to unjustified conclusions that impede field development. By providing a uniform training set, separate validation splits, and new metrics focused on efficiency and smoothness, the update aims to provide a more reliable and realistic evaluation framework for autonomous driving models.

#Bench2Drive #AutonomousDriving #NeurIPS2024 #Benchmark #CARLA

---

*Source: [Thinklab-SJTU/Bench2Drive](https://github.com/Thinklab-SJTU/Bench2Drive)*
