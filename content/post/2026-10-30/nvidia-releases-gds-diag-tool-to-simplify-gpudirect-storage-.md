---
title: "NVIDIA releases gds-diag tool to simplify GPUDirect Storage diagnostics"
slug: "nvidia-releases-gds-diag-tool-to-simplify-gpudirect-storage-diagnostics"
description: "NVIDIA has introduced **gds‑diag**, an open‑source command‑line utility (with an optional AI‑agent skill) that assesses environments, identifies problems, and suggests improvements for GPUDirect..."
date: 2026-10-30T22:02:41+05:30
tags: [NVIDIA, GPUDirectStorage, AIagents, Linux, Diagnostics]
categories: ["AI", "Hardware Acceleration", "System Administration", "AI Agents"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/inline-image-1-e1793140900880-660x370.webp"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA releases gds-diag tool to simplify GPUDirect Storage diagnostics

NVIDIA has introduced **gds‑diag**, an open‑source command‑line utility (with an optional AI‑agent skill) that assesses environments, identifies problems, and suggests improvements for GPUDirect Storage deployments.

## 🔍 Overview
- GPUDirect Storage (GDS) accelerates GPU storage access in on‑premises and cloud environments.
- It provides a robust, portable, and efficient data path between NVIDIA GPUs and storage targets to increase bandwidth, minimize latency, and reduce CPU and memory utilization across a broad range of platforms, application frameworks, and workload patterns.
- Configuring GDS starts with understanding your environment – which settings and storage paths are appropriate for your platform and workload?

## 🛠️ How gds‑diag works
- **Command‑line mode** – a single Python script with multiple subcommands that focus on different diagnostic tasks.
- **AI‑agent mode** – a natural‑language interface that interprets intent, selects and invokes the appropriate subcommands, and coordinates multi‑step diagnostic workflows.
- The agent skill adds model‑guided reasoning: it can interpret diagnostic results, apply relevant system context, and propose or carry out appropriate remediation.
- The tool runs on Linux systems with Python 3.8 or newer. NVIDIA datacenter‑class GPU and CUDA Toolkit 12.2 or newer are required for GDS itself, but they are **not** dependencies of gds‑diag.

## 🚀 Getting Started
1. Clone the repository: `git clone https://github.com/NVIDIA/MagnumIO.git`
2. Choose a usage model:
   - **Command‑line tool** – deterministic, minimal‑dependency path.
   - **AI agent** – intuitive, flexible, natural‑language interaction (recommended when available).
3. Open the `gds-diag` directory in your preferred AI coding assistant and follow the Agent skill usage guidance (if using the agent mode).
4. Run `./gds-diag.py --help` to browse subcommands, or run `./gds-diag.py all /path/to/check` for an end‑to‑end diagnostic sequence.

## 📋 Diagnostic command categories
| Category                | Example subcommand | Purpose                                                                 |
|--------------------------|--------------------|-------------------------------------------------------------------------|
| End‑to‑end checks        | `all`              | Automatically selects appropriate diagnostics for your environment and runs them in sequence. |
| Preparing for installation | `pre-install`      | Checks GPU support and CUDA Toolkit installation.                     |
| Storage planning          | `support-matrix`   | Views supported storage targets and helps plan your deployment.        |

The tool works in bare‑metal, virtual‑machine, and container environments.

## 📦 Availability
- gds‑diag is bundled with the NVIDIA Magnum IO GitHub repository and has **no additional dependencies** to install.
- It is validated with both Claude and Codex, and may work with other AI tools as well.

## 💡 Why it matters
- Provides a robust, portable, and efficient data path for GPU‑centric workloads.
- Reduces CPU and memory utilization while increasing bandwidth and lowering latency.
- Offers both a deterministic command‑line experience and a flexible natural‑language agent, giving users multiple ways to optimize GDS deployments.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/gds-diag-blog-overview-simpler.drawio-1.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/figure-2-10.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/inline-image-1-e1793140900880-1024x576.webp)

#NVIDIA #GPUDirectStorage #AIagents #Linux #Diagnostics

---

*Source: [How to Check and Configure NVIDIA GPUDirect Storage for Your Platform | NVIDIA Technical Blog](https://developer.nvidia.com/blog/how-to-check-and-configure-nvidia-gpudirect-storage-for-your-platform/)*
