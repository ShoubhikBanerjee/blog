---
title: "Nebius Workbench Unifies Agent Control for Physical AI Workflows"
slug: "nebius-workbench-unifies-agent-control-for-physical-ai-workflows"
description: "Nebius has established the Workbench endpoint as its agent control plane for Physical AI, providing a centralized infrastructure for managing robot policy training, simulation, and evaluation. This..."
date: 2026-11-17T22:09:21+05:30
tags: [Nebius, PhysicalAI, Robotics, AIInfrastructure, CodingAgents]
categories: ["AI", "AI Infrastructure", "Robotics", "Developer Tools", "Simulation"]
image: "https://avatars.githubusercontent.com/u/107546677?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Nebius Workbench Unifies Agent Control for Physical AI Workflows

Nebius has established the Workbench endpoint as its agent control plane for Physical AI, providing a centralized infrastructure for managing robot policy training, simulation, and evaluation. This setup allows operators and coding agents to share authenticated connections for provisioning resources and executing complex AI workflows.

## 🧩 How it works
Workbench integrates a shared-access system where operators install the HTTPS service once, and users or coding agents connect using `npa login` with personal keys or Nebius human sign-in. The CLI and agents reuse this saved connection through a standardized API. For Kubernetes management, operators can utilize team namespaces and private SkyPilot contexts via the `npa workbench namespace` command.

## ⚙️ Key details
The agent control plane covers several core functions of the Physical AI stack:
- Infrastructure setup and management
- Simulation environments
- Robot policy training
- Synthetic data generation
- Evaluation of model performance

Access to Workbench adds personal namespaces, GPU caps, and scoped storage. The architecture maps selected NVIDIA and open-ecosystem solutions to NPA's public GHCR container catalog, specifically `ghcr.io/nebius/nebius-physical-ai`. Some images fetch models or vendor runtimes at execution time, with the packaging contract recording these boundaries.

| Component | Function |
| :--- | :--- |
| Workflow Engine | Plans execution waves and submits them through SkyPilot |
| Token Factory | Separate hosted inference API that supports direct calls without a cluster |
| Artifact Inspection | Uses Rerun, Foxglove, media viewers, or reports to examine results |
| Simulation Environment | Runs Unitree G1 policy rollouts in MJLab simulation |

## 🚀 Availability
Developers can start with a shared-access quickstart for the Workbench endpoint. Coding agents such as Codex or Claude Code, when equipped with terminal access, use repository skills and `npa` to configure projects, provision GPU clusters and object storage, and run containerized tools. Operators managing Kubernetes directly can select namespaces and private SkyPilot contexts. Users remain in the loop for choices and human-bound approvals, such as accepting model terms.

#Nebius #PhysicalAI #Robotics #AIInfrastructure #CodingAgents

---

*Source: [nebius/nebius-physical-ai](https://github.com/nebius/nebius-physical-ai)*
