---
title: "Executing Isaac Sim Pick-and-Place Tasks Using SimReady Assets and Agent Controls"
slug: "executing-isaac-sim-pick-and-place-tasks-using-simready-assets-and-agent-controls"
description: "A walkthrough demonstrates a beverage can pick-and-place task in Isaac Sim using the UR17G arm, Robotiq 2F-140 gripper, and AI agent-generated controls. The workflow shows how to compose the scene,..."
date: 2026-11-14T06:11:11+05:30
tags: [Robotics, IsaacSim, OpenUSD, SimReady, AIAgents]
categories: ["AI", "Robotics", "Artificial Intelligence", "Simulation", "Machine Learning"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6abfe9e7d7cf09a9b38ef308/HFZWtQ2i9VN_agjeUw2HB.gif"
author: "Shoubhik Banerjee"
draft: false
---

# Executing Isaac Sim Pick-and-Place Tasks Using SimReady Assets and Agent Controls

A walkthrough demonstrates a beverage can pick-and-place task in Isaac Sim using the UR17G arm, Robotiq 2F-140 gripper, and AI agent-generated controls. The workflow shows how to compose the scene, verify asset behaviors, and execute automated pick-and-place maneuvers.

## 🔍 Overview of SimReady Assets

For robotics workflows, a SimReady designation indicates an OpenUSD asset is prepared with properties needed for defined simulation use cases. Key aspects of the asset ecosystem include:

* **SimReady Foundation:** Defines the required features an OpenUSD asset needs for a specific simulation use case.
* **SimReady Central:** An open asset library hosted on Hugging Face that offers reusable robot and object assets along with authored simulation properties and profile-validation evidence.
* **Search Endpoints:** Allows users to leverage the SimReady Central Space search service endpoint or USD Search endpoint to find OEM-curated content.

## ⚙️ Component Profiles and Settings

The pick-and-place example utilizes assets with validated simulation properties to establish a shared baseline for asset reuse:

| Asset | Profile | Validated Properties | Role in Simulation |
| --- | --- | --- | --- |
| UR17G Arm | Robot-Body 4.0.0 | Passing PhysX driven-joint checks (joint-drive settings) | Executes arm movement and positioning |
| Robotiq 2F-140 Gripper | Robot-Gripper 3.0.0 | Passing PhysX driven-joint checks (joint-drive settings) | Grasps and releases the beverage can |
| Beverage Can | N/A | Authored collisions and mass properties | Rests on the work surface and serves as target object |

## 🧩 Setup and Task Execution

The simulation workflow integrates scene assembly, system validation, and agent execution:

* **Asset Preparation:** Download complete asset folders from SimReady Central (via direct download or Hugging Face CLI) so Isaac Sim can locate supporting files without missing-file errors.
* **Environment Launch:** Start Isaac Sim version 6.2 from its installation directory with the remote Python server enabled (`./isaac-sim.sh --enable isaacsim.code_editor.python_server`).
* **Agent Configuration:** Set up an agent configured with skills from the Agent Skills documentation. The model—such as GPT-6 Sol—executes Python against Isaac Sim to create and run the task code.
* **Scene & Task Definition:** Assemble the work surface, arm-gripper assembly, and initial positions. Review joint limits, confirm the can rests on the surface without falling through, and configure controls to grasp, lift, move, and release the can.

![figure](https://cdn-uploads.huggingface.co/production/uploads/6abfe9e7d7cf09a9b38ef308/J7YL_C3mUh7MWUNJ_pVtN.png)

#Robotics #IsaacSim #OpenUSD #SimReady #AIAgents

---

*Source: [Build a Robot Pick-and-Place Simulation with SimReady Assets](https://huggingface.co/blog/nvidia/simready-assets-robot-pick-and-place)*
