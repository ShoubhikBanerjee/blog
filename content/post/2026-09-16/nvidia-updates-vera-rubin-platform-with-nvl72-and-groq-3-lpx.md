---
title: "NVIDIA Updates Vera Rubin Platform with NVL72 and Groq 3 LPX Integration"
slug: "nvidia-updates-vera-rubin-platform-with-nvl72-and-groq-3-lpx-integration"
description: "NVIDIA has released updates for its Vera Rubin platform, a full-stack AI factory designed to enable power-efficient AI at scale. The platform includes the Vera Rubin NVL72 compute engine and the..."
date: 2026-09-16T06:07:24+05:30
tags: [NVIDIA, VeraRubin, DataCenter, NVLink, EnergyEfficiency, AIInfrastructure]
categories: ["AI", "AI Infrastructure", "Hardware Engineering", "Data Centers"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/gpu-architecture-groq3-lpx-rack-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Updates Vera Rubin Platform with NVL72 and Groq 3 LPX Integration

NVIDIA has released updates for its Vera Rubin platform, a full-stack AI factory designed to enable power-efficient AI at scale. The platform includes the Vera Rubin NVL72 compute engine and the addition of the Groq 3 LPX low-latency accelerator to manage diverse AI workloads from large batches to high-interactivity tiers.

## 🔍 Overview
The NVIDIA Vera Rubin platform is built as a fungible compute environment for training and inference. The Vera Rubin NVL72, the core rack-scale engine, connects 72 Rubin GPUs into a single scale-up domain using the NVIDIA NVLink 6 fabric. This architecture is designed to deliver training with one-quarter the GPUs and provide the highest inference throughput per watt with the lowest token cost.

## 🧩 How it works
The platform utilizes a combination of hardware determinism and intelligent software to maximize power efficiency:
*   **Deterministic Execution**: The Groq 3 LPX features a deterministic execution model that allows its compiler to create a cycle-exact schedule for data movement and operations across 256 LPU chips. 
*   **Power Prediction**: By generating a workload execution schedule in advance, the platform can predict the electrical current draw for every cycle. This helps reduce the "voltage guardband," the excess power typically supplied to prevent chips from dropping below their minimum operating voltage (Vmin).
*   **Dynamic Power Shifting**: NVIDIA DSX MaxLPS software shifts power between racks as workloads demand, allowing operators to provision up to 40% more GPUs within the same power envelope and deliver 35% higher token throughput.
*   **Intelligent Power Smoothing**: Rack-level capacitors and specialized software absorb the bursty power spikes associated with AI training and inference, allowing factories to be planned around sustained demand rather than worst-case peaks.

## ⚙️ Key details
### Networking and Resiliency
The platform utilizes NVIDIA NVLink 6, a natively lossless fabric designed for uncompromising reliability. It achieves 3X lower end-to-end latency and 10X higher packet rates than generic Ethernet alternatives.

| Feature | Function |
| :--- | :--- |
| Forward Error Correction (FEC) | Appends codes to data streams to mathematically reconstruct corrupted bits inline with near-zero latency. |
| Physical Layer Retry (PLR) | Handles retransmissions directly at the physical layer to reduce packet drops to zero. |
| UPHY Recovery | Rapidly recalibrates physical parameters while packets are held in a hardware replay buffer. |
| Credit-Based Flow Control (CBFC) | Manages network congestion at the link layer to mathematically eliminate packet drops. |

### Architecture and Reliability
The architecture is built with zero single points of failure. Key reliability features include:
*   Redundant switch trays and distributed NMX Controllers.
*   Dual out-of-band management paths.
*   **Dynamo Shadow Engine Recovery**: Utilizes pre-warmed replica processes for near-instant failovers.
*   Application-level checkpoint and restore mechanisms to preserve long-running jobs.

## 💡 Why it matters
Complex AI operations like matrix multiplications cause high transistor switching, leading to rapid changes in current demand known as voltage droops. Because power is proportional to the square of voltage, a 10% increase in voltage results in 21% more power consumption. By using deterministic scheduling (PEP and CPS) to reduce the required electrical safety margin, the Vera Rubin platform ensures a greater proportion of scarce power is spent directly on the AI workload rather than being wasted as excess guardband.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/gpu-architecture-groq3-lpx-rack-1024x576.jpg)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/pep-cps-lower-voltage-guardband-groq-3-lpx.gif)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/voltage-droop.gif)

#NVIDIA #VeraRubin #DataCenter #NVLink #EnergyEfficiency #AIInfrastructure

---

*Source: [How NVIDIA Groq 3 LPX Deterministic Execution Drives Power-Efficient High-Interactivity Inference on NVIDIA Vera Rubin | NVIDIA Technical Blog](https://developer.nvidia.com/blog/how-nvidia-groq-3-lpx-deterministic-execution-drives-power-efficient-high-interactivity-inference-on-nvidia-vera-rubin/)*
*Source: [How NVIDIA NVLink 6 Delivers Multi-Layer Resiliency for AI Factories | NVIDIA Technical Blog](https://developer.nvidia.com/blog/how-nvidia-nvlink-6-delivers-multi-layer-resiliency-for-ai-factories/)*
