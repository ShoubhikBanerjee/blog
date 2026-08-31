---
title: "NVIDIA Omniverse NuRec Enables Carline Adaptation for Autonomous Vehicle Perception Software"
description: "NVIDIA Omniverse NuRec addresses the carline adaptation challenge by allowing developers to reconstruct real-world drives and render them for new vehicle configurations. This development makes it..."
date: 2026-08-31T22:29:11+05:30
tags: [NVIDIA, Omniverse, AutonomousVehicles, NuRec, GaussianSplatting, Simulation]
categories: [AI]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/NuRec-AV.gif"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Omniverse NuRec Enables Carline Adaptation for Autonomous Vehicle Perception Software

NVIDIA Omniverse NuRec addresses the carline adaptation challenge by allowing developers to reconstruct real-world drives and render them for new vehicle configurations. This development makes it practical to prepare perception software for vehicles that may not yet exist and scale software across different platform variants without collecting and labeling new real-world datasets for every carline.

## 🔍 The Carline Adaptation Challenge
A perception stack is shaped by the vehicle that carries it. When the same software is moved to a new carline—such as from an SUV to a sedan—its perception of the world changes. These shifts are caused by differences in sensor placement, calibration, fields of view, occlusions, body geometry, timing, and coverage. 

Consequences of changing vehicle configurations include:
* Traffic lights appearing in different parts of the frame.
* Curbs becoming harder to see.
* Pedestrians near the edge of coverage becoming ambiguous.

While real-world data remains essential for grounding performance, collecting and labeling new datasets for every variant is expensive and often impossible early in development when fleets are unavailable.

## 🧩 How it Works
NuRec uses 3D Gaussian splatting to reconstruct real-world environments from sensor data and render them for simulation. The process enables developers to reuse real-world data to determine how scenarios would look from a target vehicle rig.

* **Neural Reconstruction:** NuRec reconstructs a real-world drive captured by an existing vehicle.
* **Novel-View Synthesis:** The system renders the scene with gsplat, which projects Gaussians through a specified camera model.
* **Camera Customization:** Users can change camera extrinsics, intrinsics, fields of view, and lens models, including pinhole, fisheye, and f-theta configurations.
* **Data Reuse:** Reconstructed scenes retain original rig trajectories, per-camera calibration, dynamic object tracks, and map data. These assets are used to adapt labels for objects, lanes, traffic lights, and road boundaries in the newly rendered views.

## ⚙️ Key Details
The system uses specific rig configuration files where each sensor entry defines a camera name, image resolution, lens model, intrinsic parameters, and camera-to-rig pose. 

| Feature | Detail |
| :--- | :--- |
| Dataset Name | NVIDIA Physical AI NuRec Dataset |
| Scene Count | 1,500+ neural-reconstructed driving scenes |
| Scene Duration | Approximately 20 seconds each |
| Reconstruction Method | 3D Gaussian splatting |
| Camera View Types | Front-wide (120°), front-telephoto (30°), cross-left/right (120°), rear-left/right (70°) |

In the rig file, NRE converts colon-delimited names to logical camera IDs. For example, a camera named `camera:front:synthetic:120fov` is converted to `camera_front_synthetic_120fov`.

## 🚀 Availability
The NVIDIA Physical AI NuRec Dataset is available on Hugging Face. The dataset is gated, requiring users to accept a license and authenticate with a Hugging Face token before downloading scenes.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/07/nvidia-omniverse-rtx-sensor-ximulation.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/figure-2-optimized.gif)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/figure-3-1.gif)

#NVIDIA #Omniverse #AutonomousVehicles #NuRec #GaussianSplatting #Simulation

---

*Source: [Scale AV Perception Across Vehicle Platforms with NVIDIA Omniverse NuRec | NVIDIA Technical Blog](https://developer.nvidia.com/blog/scale-av-perception-across-vehicle-platforms-with-nvidia-omniverse-nurec/)*
