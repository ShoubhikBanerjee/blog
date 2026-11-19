---
title: "Radar Doppler Measurement Improves Safety Control for Dynamic Obstacles"
slug: "radar-doppler-measurement-improves-safety-control-for-dynamic-obstacles"
description: "Researchers present a radar-native control barrier function that uses FMCW radar Doppler measurements directly as the derivative of a range-based barrier function, reducing estimation delay in safe..."
date: 2026-11-19T18:06:46+05:30
tags: [Radar, ControlBarrierFunctions, Robotics, Safety, FMCW, Doppler]
categories: ["AI", "Robotics", "Control Systems", "Sensor Fusion", "Safety Engineering"]
author: "Shoubhik Banerjee"
draft: false
---

# Radar Doppler Measurement Improves Safety Control for Dynamic Obstacles

Researchers present a radar-native control barrier function that uses FMCW radar Doppler measurements directly as the derivative of a range-based barrier function, reducing estimation delay in safe robot control around dynamic obstacles.

## 🔍 Overview
- Safe control around dynamic obstacles requires both distance and relative motion information.
- Traditional range-based filters reconstruct range rate from successive range measurements or obstacle-state estimators, introducing estimator delay or sensitivity to range noise when obstacle motion changes.
- FMCW radar measures radial relative velocity directly through Doppler.
- This work uses the Doppler measurement as the derivative of an ego-centered range control barrier function (CBF), yielding a closed-form filter on the robot's forward velocity.

## 🧩 How It Works
- Direct Doppler measurement replaces the need to reconstruct range rate in the safety loop.
- A measurement margin constructed from sensor error bounds accounts for errors in range, Doppler, ego velocity, and bearing.
- The guarantee covers the longitudinal range channel under bounded measurement errors and continuously available detections.

## ⚙️ Key Details
- In 508 paired encounters within the platform's retreat capability:
  - Direct Doppler: 2 buffer incursions
  - Constant-acceleration Kalman filter: 15 buffer incursions
  - Constant-velocity Kalman filter: 25 buffer incursions
- On a Unitree Go1 quadruped, the controller stops at 0.777 ± 0.015 m (predicted 0.758 m) and reacts to a farther approaching object while a nearer static return remains.

## 💡 Why It Matters
- Direct Doppler removes the need to reconstruct range rate in the safety loop, reducing the delay between a change in obstacle motion and its effect on the safety command.
- This approach improves safety performance in dynamic environments with fewer buffer incursions compared to estimator-based methods.

#Radar #ControlBarrierFunctions #Robotics #Safety #FMCW #Doppler

---

*Source: [Radar-Native Control Barrier Functions: Doppler Range Rate as a Measured Barrier Derivative](https://arxiv.org/abs/2611.23654v1)*
