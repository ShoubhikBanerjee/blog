---
title: "NVIDIA Holoscan 5 Adds Integrated Robotic Control and Streamlined Sensor Processing"
slug: "nvidia-holoscan-5-adds-integrated-robotic-control-and-streamlined-sensor-processing"
description: "NVIDIA announced Holoscan SDK version 5, introducing built‑in robotic control alongside its existing low‑latency sensor‑processing capabilities."
date: 2026-11-10T06:04:38+05:30
tags: [NVIDIA, Holoscan, Robotics, EdgeAI]
categories: ["AI", "Artificial Intelligence", "Robotics", "Edge Computing", "SDKs"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/featured-image-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Holoscan 5 Adds Integrated Robotic Control and Streamlined Sensor Processing

NVIDIA announced Holoscan SDK version 5, introducing built‑in robotic control alongside its existing low‑latency sensor‑processing capabilities.

## 🔍 Overview
- Holoscan 5 combines low‑latency control with high‑throughput perception in a single programming model.
- The SDK supports both CPU‑centric motor‑control loops and heavy‑throughput GPU algorithms, including AI inference.
- A new, lightweight programming model makes it easy to integrate Holoscan into existing code bases and to move data in and out of Holoscan graphs.

## 🧩 How it works
- **Operators & Graphs** – The core concepts remain Operators and Graphs.
- **Partitions** – Chains of operators are grouped on a single thread, avoiding cross‑thread handoffs and unnecessary syscalls, which reduces latency and jitter.
- **Timing contracts** – Operators express when work should run using clock and data‑arrival triggers; bounded, drop‑oldest queues prevent stale work from building up.
- **Compiled plan** – Before the first run, the plan reveals the execution strategy and catches configuration errors.
- **NVTX annotations** – Built‑in annotations expose operator execution and message transfers in Nsight Systems, and the SDK also provides Nsight Systems annotations for latency and jitter inspection.

## ⚙️ Key details
- **Robotic control** is now a first‑class feature, demonstrated on the Seeed Studio reBot Arm B601‑DM, which uses quasi‑direct‑drive actuators for high torque bandwidth.
- The tutorial uses **Pinocchio** as the inverse‑dynamics solver (URDF model + Recursive Newton–Euler Algorithm) and the **motorbridge** library for joint feedback and motor commands.
- Both libraries implement the same three‑operator control loop.
- Supports **10 kHz** CPU‑centric motor‑control loops while maintaining stable torque‑oriented performance.
- Tested on:
  | Platform | OS |
  |----------|----|
  | Jetson Orin Nano | Ubuntu 24.04 |
  | Jetson Thor | Ubuntu 24.04 |
  | x86 | Ubuntu 24.04 |
- Requires **Python 3.12** or newer on Linux.
- Configuration includes checking the serial device and motor IDs in the arm’s configuration file.
- The tutorial repository’s technical guide covers configuration, math, and hardware startup.

## 🚀 Availability
- The walkthrough can be run on a real robot, with the SDK’s Nsight Systems annotations used to inspect latency and jitter.
- All supported platforms (Jetson Orin Nano, Jetson Thor, x86 Ubuntu 24.04) are ready for deployment.

## 💡 Why it matters
- Torque‑oriented projects such as haptic devices and collaborative robots need rapid, consistent feedback at hundreds or thousands of hertz; any runtime overhead or thread handoff can introduce phase lag and destabilize the system.
- By eliminating cross‑thread handoffs, providing deterministic timing contracts, and exposing execution plans early, Holoscan 5 gives developers a clear path to stable, high‑performance robotic control on edge hardware.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/featured-image-1024x576-jpg.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image6-4.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/image3-5.webp)

#NVIDIA #Holoscan #Robotics #EdgeAI

---

*Source: [Make a Robot Arm Feel Weightless with NVIDIA Holoscan 5 | NVIDIA Technical Blog](https://developer.nvidia.com/blog/make-a-robot-arm-feel-weightless-with-nvidia-holoscan-5/)*
