---
title: "osgVerse adds native 3D Gaussian Splatting rendering and training"
slug: "osgverse-adds-native-3d-gaussian-splatting-rendering-and-training"
description: "osgVerse, a complete 3D engine solution based on OpenSceneGraph, now includes built‑in support for 3D Gaussian Splatting rendering and training."
date: 2026-11-17T22:09:21+05:30
tags: [osgVerse, 3DRendering, GaussianSplatting, OpenGL, Vulkan]
categories: ["AI", "Computer Graphics", "Rendering", "Game Development", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/1410005?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# osgVerse adds native 3D Gaussian Splatting rendering and training

osgVerse, a complete 3D engine solution based on OpenSceneGraph, now includes built‑in support for 3D Gaussian Splatting rendering and training.

## 🔍 Overview
- Supports 3D Gaussian Splatting rendering and related formats: PLY, SPZ, SPLAT, PlayCanvas SOG and XGrids LCC.
- Enables training from COLMAP datasets using a vendored Vulkan‑compute backend (VkSplat).
- Allows exporting results to PLY or GaussianGeometry.

## 🧩 Capabilities
- Real‑time rendering of Gaussian splats with the engine’s existing PBR‑based and deferred pipelines.
- Integration with the engine’s multi‑backend graphics stack (OpenGL, OpenGLES, Vulkan, DirectX, Metal, WebGPU via Emscripten).

## ⚙️ Technical Details
- Vulkan‑compute backend (VkSplat) is used for training.
- WebAssembly support through Emscripten 5.0.0+ enables WebGPU paths that require GLES3.
- The engine requires CMake 3.0 or higher and a C++ compiler supporting at least C++14.
- OpenSceneGraph version 3.1.1 or later is required; the current project uses OSG 3.7.0.

## 🚀 Availability
- Works on modern browsers using WASM (WebGL1/2 and WebGPU).
- Supports major embedded devices with GPU, including ARM and RISC‑V.
- Available alongside other engine features such as physics (Box3D/Bullet3), animation (OZZ), media streaming, and database plugins.

## 💡 Why it matters
- Provides a native pipeline for neural‑style Gaussian splatting within a full‑featured 3D engine, simplifying integration for developers who need real‑time or offline neural rendering capabilities.

#osgVerse #3DRendering #GaussianSplatting #OpenGL #Vulkan

---

*Source: [xarray/osgverse](https://github.com/xarray/osgverse)*
