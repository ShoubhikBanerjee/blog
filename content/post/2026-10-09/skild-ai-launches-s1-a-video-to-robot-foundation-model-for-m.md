---
title: "Skild AI launches S1, a video‑to‑robot foundation model for manipulation"
slug: "skild-ai-launches-s1-a-videotorobot-foundation-model-for-manipulation"
description: "Skild AI unveiled S1 in August 2026 as its flagship foundation model for robotic manipulation. The system can learn a new task from a single video demonstration without any additional task‑specific..."
date: 2026-10-09T22:05:01+05:30
tags: [SkildAI, Robotics, FoundationModel, Simulation]
categories: ["AI", "Artificial Intelligence", "Robotics", "Machine Learning", "Simulation"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image6-2.gif"
author: "Shoubhik Banerjee"
draft: false
---

# Skild AI launches S1, a video‑to‑robot foundation model for manipulation

## 🔍 Overview
Skild AI unveiled S1 in August 2026 as its flagship foundation model for robotic manipulation. The system can learn a new task from a single video demonstration without any additional task‑specific training or weight adjustments.

## 🧩 How S1 Works
- The model receives a video showing a task and then attempts to replicate the observed task using a robot, **without modifying its weights or requiring a specific post‑training phase**.
- S1 is trained using episodes in which a visual demonstration describes the task to be performed.
- It learns to relate what it observes in the video to the current scene and the available motor controls, reconstructing an action policy that achieves the same goal with its own robotic body.
- Pre‑training combines several data types: teleoperation, first‑person human videos, simulation, and experiments conducted on robots.
- Several scenarios did not appear in the pre‑training data; basic gestures are combined into novel sequences.

## 📊 Performance Metrics
- On unseen tasks lasting four to eight minutes, trained on a reported **100,000 hours of data**, S1 achieved an **average cumulative success rate per step of 66 %**, compared with **9 %** for a linguistic baseline.
- The metric aggregates the success rates of the various stages; it does **not** represent a 66 % success rate for each mission.
- Human intervention was used to reset the system after a failure so that all stages could be evaluated.
- A real‑world demonstration is estimated to be equivalent to approximately **380 post‑training sessions** on the tasks studied.

## 🛠️ Supporting Infrastructure
| Component | Role |
|-----------|------|
| Cosmos | Organizes and enriches video data |
| Omniverse | Provides virtual environments |
| Isaac Sim | Provides virtual environments |
| Isaac Lab | Used for reinforcement learning |
| TensorRT | Optimizes inference |

On September 10 2026 NVIDIA detailed this infrastructure, highlighting how Cosmos, Omniverse, Isaac Sim, Isaac Lab, and TensorRT work together to train, simulate, and deploy S1.

## 🚀 Availability
- S1 is **available through select deployments and partnerships**, not as a freely downloadable model.

## 💡 Why It Matters
- Enables robots to acquire new manipulation skills from a single video, dramatically reducing the data collection and training time required for each new task.
- Demonstrated capabilities include repotting a plant, making filter coffee, making pancakes, and assembling a kit, with sequences lasting up to ten minutes and involving several successive gestures.
- For the repotting task, the company reports that it went from recording the demonstration to beginning autonomous execution in **eleven minutes**.
- The same set of weights generates all the examples shown, confirming the model’s ability to generalize across diverse tasks.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/sharpie_simulation_loop_under10mb.gif)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2025/09/OpenUSD-robotics.gif)

#SkildAI #Robotics #FoundationModel #Simulation

---

*Source: [5 Steps to Create SimReady Assets for Robotics with Frontier AI Models | NVIDIA Technical Blog](https://developer.nvidia.com/blog/5-steps-to-create-simready-assets-for-robotics-with-frontier-ai-models/)*
*Source: [Skild AI's S1: Learning a Robotic Task from a Video](https://aivancity.ai/en/blog/s1-skild-ai-apprentissage-robotique-video/)*
