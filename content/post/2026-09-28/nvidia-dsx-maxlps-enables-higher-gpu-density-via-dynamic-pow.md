---
title: "NVIDIA DSX MaxLPS Enables Higher GPU Density via Dynamic Power Sharing"
slug: "nvidia-dsx-maxlps-enables-higher-gpu-density-via-dynamic-power-sharing"
description: "NVIDIA and Nscale have evaluated DSX MaxLPS, a system that uses policy-governed power sharing to dynamically allocate power across resources, allowing customers to deploy up to 40% more GPUs within..."
date: 2026-09-28T12:02:59+05:30
tags: [NVIDIA, DataCenter, GPU, EnergyEfficiency, AIInfrastructure]
categories: ["AI", "AI Infrastructure", "Hardware Engineering", "Data Center Management"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/MaxLPS-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA DSX MaxLPS Enables Higher GPU Density via Dynamic Power Sharing

NVIDIA and Nscale have evaluated DSX MaxLPS, a system that uses policy-governed power sharing to dynamically allocate power across resources, allowing customers to deploy up to 40% more GPUs within the same approved power budget.

## 💡 Why it matters
AI factories operate within a hierarchy of electrical limits, including utility service, substations, power-distribution equipment, racks, nodes, and GPUs. Traditional static power planning reserves enough power for every node to reach its specified peak simultaneously. However, AI workloads rarely draw constant power:

* **Training workloads:** Move through compute, communication, synchronization, and checkpointing.
* **Inference workloads:** Alternate between prefill, decode, memory-bound work, network activity, and idle intervals.
* **Variable requests:** Even identical models draw different power based on concurrencies and request shapes.

Static reservations prevent unused capacity in one reservation from being applied to another node, leaving valuable infrastructure underused during normal operation.

## 🧩 How it works
DSX MaxLPS combines chip, system, thermal, and software technologies to maximize output within land, power, and shell (LPS) constraints. The Dynamic Power Software provides the control layer for the following process:

* **Infrastructure Mapping:** Operators organize nodes into a managed group with an aggregate power budget.
* **Telemetry Collection:** The system collects power telemetry from GPUs, nodes, racks, and groups at intervals sufficient to detect emerging power events and available headroom.
* **Policy Governance:** Operator-defined rules establish group and node limits, allocation priorities, reserve requirements, and emergency or maintenance responses.
* **Dynamic Allocation:** When some resources draw less than their allocation, the software adjusts GPU power limits so other resources can use that capacity, while maintaining the aggregate budget.

## ⚙️ Key details
A joint evaluation of this approach was conducted at Nscale’s data center at the Verne campus in Keflavík, Iceland, which is powered entirely by renewable energy. The technical walkthrough utilized the following configuration:

| Component | Detail |
| :--- | :--- |
| Systems | NVIDIA GB300 NVL72 |
| GPUs | NVIDIA Blackwell Ultra |
| Workload | Kimi K2.5 in FP4 |
| Software | NVIDIA Dynamo and NVIDIA TensorRT LLM |
| Sequence Length | 8K input / 1K output |
| Workload Mix | High-throughput and low-latency inference instances |

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/MaxLPS-1024x576-jpg.webp)

#NVIDIA #DataCenter #GPU #EnergyEfficiency #AIInfrastructure

---

*Source: [How NVIDIA DSX MaxLPS Maximizes AI Factory Throughput and Efficiency | NVIDIA Technical Blog](https://developer.nvidia.com/blog/how-nvidia-dsx-maxlps-maximizes-ai-factory-throughput-and-efficiency/)*
