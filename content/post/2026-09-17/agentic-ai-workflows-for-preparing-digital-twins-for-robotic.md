---
title: "Agentic AI Workflows for Preparing Digital Twins for Robotics Simulation"
slug: "agentic-ai-workflows-for-preparing-digital-twins-for-robotics-simulation"
description: "Agentic AI workflows are being used to prepare and validate digital twins for physical AI systems, moving scenes from Blender to simulation-ready OpenUSD handoffs for NVIDIA Isaac Sim or NVIDIA Isaac..."
date: 2026-09-17T12:07:20+05:30
tags: [NVIDIA, OpenUSD, AIagents, Robotics, DigitalTwins]
categories: ["AI", "AI Agents", "Robotics Simulation", "Digital Twins"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/classroom-ovrtx-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# Agentic AI Workflows for Preparing Digital Twins for Robotics Simulation

Agentic AI workflows are being used to prepare and validate digital twins for physical AI systems, moving scenes from Blender to simulation-ready OpenUSD handoffs for NVIDIA Isaac Sim or NVIDIA Isaac Lab.

## 🧩 How it works

The process follows a pattern where a main agent coordinates, NemoClaw agents reason, and Omniverse Libraries act. The workflow operates as follows:

* **Input**: A Blender scene.
* **Goal**: Preparation for robotics simulation.
* **Output**: A USD-based simulation-ready world.
* **Destination**: NVIDIA Isaac Sim or NVIDIA Isaac Lab.
* **Validation**: Visual preflight and SimReady validation.

## ⚙️ Key details

The architecture utilizes a main orchestrator and specialized subagents:

* **Main Agent**: A general-purpose agent such as Codex (powered by OpenAI GPT-6 Astra) or Claude Cowork (by Anthropic) recognizes the need for simulation readiness and coordinates the overall task.
* **Subagents**: Specialized subagents, built with harnesses like Hermes, OpenClaw, or LangChain and deployed through NVIDIA NemoClaw, perform specific jobs using NVIDIA Nemotron models for reasoning, vision, and tool use.
* **Blender Integration**: The first subagent uses a Model Context Protocol (MCP) server to provide a controlled tool interface to inventory the scene.

| Component | Function |
| :--- | :--- |
| **OpenUSD operations** | Establish the shared scene structure |
| **ovphysx** | Author and check physics properties |
| **ovrtx** | Render visual preflight views |
| **SimReady validation** | Evaluate assets against a target simulation profile |
| **NVIDIA Omniverse Libraries** | Provide the tools subagents call to act on the scene |

## 💡 Why it matters

These agents can inspect 3D scenes, author simulation-relevant data in OpenUSD, add physics properties, render preflight views, and validate results against simulation-ready (SimReady) requirements.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/reference-workflow-omniverse-libraries-blender-ai-agents.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/codex-orchestrating-nvidia-nemoclaw.webp)

#NVIDIA #OpenUSD #AIagents #Robotics #DigitalTwins

---

*Source: [How to Use AI Agents to Prepare 3D Scenes for Simulation | NVIDIA Technical Blog](https://developer.nvidia.com/blog/how-to-use-ai-agents-to-prepare-3d-scenes-for-simulation/)*
