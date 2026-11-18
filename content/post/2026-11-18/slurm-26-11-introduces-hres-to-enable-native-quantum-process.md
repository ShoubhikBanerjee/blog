---
title: "Slurm 26.11 Introduces HRES to Enable Native Quantum Processor Scheduling"
slug: "slurm-26-11-introduces-hres-to-enable-native-quantum-processor-scheduling"
description: "Slurm 26.11 adds Hierarchical Resources (HRES) plugins that enable quantum processing units (QPUs) to be scheduled as native cluster resources, allowing HPC centers to integrate quantum accelerators..."
date: 2026-11-18T18:09:03+05:30
tags: [Slurm, QuantumComputing, HPC, Supercomputing, QPU, Scheduling]
categories: ["AI", "High Performance Computing", "Quantum Computing", "System Administration"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/hybrid-quantum-classical-computing-architecture-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# Slurm 26.11 Introduces HRES to Enable Native Quantum Processor Scheduling

Slurm 26.11 adds Hierarchical Resources (HRES) plugins that enable quantum processing units (QPUs) to be scheduled as native cluster resources, allowing HPC centers to integrate quantum accelerators alongside traditional supercomputing systems.

## 🔍 Overview
National programs across North America, Europe, and Asia are integrating quantum processing units (QPUs) into supercomputing centers worldwide. These QPUs operate as cluster-wide accelerators, distinct from node-attached GPUs.

## 🧩 How it works
The HRES plugin interface uses short, portable Lua scripts to manage QPU scheduling:

- Reports device health to the scheduler
- Accepts device options as part of resource requests
- Runs setup and teardown code at each job stage
- Describes QPUs to HPC software via QRMI and QDMI open source efforts

## ⚙️ Key details
The architecture differs fundamentally from GPU scheduling:

| Feature | GRES (GPUs) | HRES (QPUs) |
|---------|-------------|-------------|
| Scope | Per compute node | Cluster-wide |
| Management | Built into Slurm | Plugin-based |
| Access | Jobs on specific node | Jobs on allowed nodes |

A QPU is modeled using a single layer in resources.yaml covering nodes that can reach the device, with a count of one. The plugin logic is separate from site configuration, allowing vendors to distribute it across installations.

## 🚀 Availability
HRES entered Slurm in version 25.05 as a beta feature and reached production maturity in version 26.11, representing an evolution of the licensing mechanism with similar counting semantics but node-specific associations.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/slurm-schedules-qpu-hres-integration-architecture.webp)

#Slurm #QuantumComputing #HPC #Supercomputing #QPU #Scheduling

---

*Source: [Integrating QPUs into Supercomputing Centers Using Slurm HRES Plugins | NVIDIA Technical Blog](https://developer.nvidia.com/blog/integrating-qpus-into-supercomputing-centers-using-slurm-hres-plugins/)*
