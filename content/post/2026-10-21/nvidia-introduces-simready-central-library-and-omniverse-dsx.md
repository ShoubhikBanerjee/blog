---
title: "NVIDIA Introduces SimReady Central Library and Omniverse DSX Blueprint for AI Factory Digital Twins"
slug: "nvidia-introduces-simready-central-library-and-omniverse-dsx-blueprint-for-ai-factory-digital-twins"
description: "NVIDIA has expanded its simulation ecosystem with the launch of the SimReady Central Library on Hugging Face and the NVIDIA Omniverse DSX Blueprint. These developments provide developers with a..."
date: 2026-10-21T22:03:49+05:30
tags: [OpenUSD, DigitalTwin, Robotics]
categories: ["AI", "Digital Twins", "Robotics", "Artificial Intelligence"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/omniverse-overall-dsx-sim-gtc-berlin-26-5796136-600x338-r2.gif"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Introduces SimReady Central Library and Omniverse DSX Blueprint for AI Factory Digital Twins

NVIDIA has expanded its simulation ecosystem with the launch of the SimReady Central Library on Hugging Face and the NVIDIA Omniverse DSX Blueprint. These developments provide developers with a foundation for building AI factory digital twins by connecting engineering requirements, site plans, and equipment assets into consistent, simulation-ready models. Built on OpenUSD and NVIDIA Omniverse libraries, the new tools allow teams to explore design alternatives and incorporate engineering feedback as factory designs evolve.

## 🔍 Overview

The NVIDIA Omniverse DSX Blueprint provides reference digital twin assets, sample scripts, and workflows for developing AI factory digital twins. This foundation helps developers assemble facility and equipment models using SimReady assets and connect them with engineering simulation tools. To guide architectural design, teams can use existing references; for example, the NVIDIA Santa Clara Headquarters building was used as inspiration for an AI factory campus site based on the DSX reference design.

## 🧩 How it works

The workflow uses a frontier AI model running in an agent harness to manage context, instructions, and tool calls. This system supports grounded design proposals by incorporating project-specific data:

*   **Data Integration:** The process combines existing geometry, architectural references, aerial imagery, and elevation data from sources like the USGS.
*   **Agent Skills:** Repeatable tasks and domain knowledge are encoded as skills, allowing agents to propose design changes like equipment placement or architectural additions.
*   **Tool Interfaces:** Developers connect operations through interfaces including the Model Context Protocol (MCP) and USD Content Agents.
*   **Layered Composition:** New geometry and design changes are kept in additive USD layers, ensuring modifications remain separate from source assets.

## ⚙️ Key details

The SimReady Central Library features more than 2,000 assets on Hugging Face, providing a free starting point for physical AI training and digital twins. These assets include metadata required for simulation, such as mass, friction, collision geometry, and thermal or electrical properties.

| OEM or Provider | Available Asset Types |
| :--- | :--- |
| Vertiv | Warehouse equipment racks, server racks, cooling equipment, and infrastructure |
| Comau, FANUC, Franka Robotics, Robotiq, Standard Bots, Universal Robots | Robot arms and grippers |
| LG Electronics (LGE) | Household appliances including refrigerators and dishwashers |
| Palatial | NVIDIA Robotics 1K Dataset and complex articulated assets |
| ForgeCAD | Articulated robotics props with high-quality textures |

## 🚀 Availability

SimReady Central Library is available as a free, ungated repository on Hugging Face. Original Equipment Manufacturers (OEMs) can contribute to the library by using a submission skill to validate their CAD equipment models against SimReady profiles. These profiles define the specific features and capabilities an asset needs for particular simulation use cases, such as robot manipulation or factory cooling analysis.

## 💡 Why it matters

Building high-fidelity digital twins requires more than just 3D geometry; assets must behave according to physical laws. By providing assets pre-configured with mass, collision, and sensor interaction data, the library reduces manual work for developers. This ecosystem allows manufacturers to reach teams building robotics simulations while enabling end customers to test scenarios and accelerate decision-making for complex facilities.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/reference-workflow-openusd-digital-twin-engineering-simulation.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/ai-factory-campus-site-rendering.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/nvidia-dsx-system-architecture-simready-openusd-agents.webp)

#OpenUSD #DigitalTwin #Robotics

---

*Source: [Developing an AI Factory Digital Twin with an Agent-Assisted Workflow | NVIDIA Technical Blog](https://developer.nvidia.com/blog/developing-an-ai-factory-digital-twin-with-an-agent-assisted-workflow/)*
*Source: [Announcing SimReady Central: An Open Library of Simulation-Ready 3D Assets for Robotics and AI Factories](https://huggingface.co/blog/nvidia/simready-central-assets-robotics-ai-factories)*
