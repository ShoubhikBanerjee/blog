---
title: "NVIDIA TensorRT 11.1 Introduces Global Performance Tuner for Automatic Model Optimization"
slug: "nvidia-tensorrt-11-1-introduces-global-performance-tuner-for-automatic-model-optimization"
description: "The Global Performance Tuner (GPT) is a new feature for automatic performance tuning released in NVIDIA TensorRT 11.1."
date: 2026-10-24T06:05:12+05:30
tags: [TensorRT, PerformanceTuning, AIInference, DeepLearning]
categories: ["AI", "Machine Learning", "Deep Learning", "Performance Optimization", "Software Development"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/desktop-computer-overlay-light-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA TensorRT 11.1 Introduces Global Performance Tuner for Automatic Model Optimization

The Global Performance Tuner (GPT) is a new feature for automatic performance tuning released in NVIDIA TensorRT 11.1.

## 🔍 Overview
- The Global Performance Tuner is a feature for automatic performance tuning released in NVIDIA TensorRT 11.1.
- It provides automatic, accuracy‑aware and end‑to‑end performance tuning by customizing different optimizations for different models.

## 🧩 How it works
- **Central design idea**: represent alternative scheduling strategies as explicit and searchable build routes.
- **Compiler knob**: a configuration setting that changes some aspect of the compilation pipeline (heuristic, fusion decision, or code‑generation path).
  - Each tunable knob exposes a finite set of allowed values and has a default value.
- **Build route**: a concrete combination of knob values.
  - When no build route is specified, TensorRT uses the default build route, where every knob retains its default value.
- Fusion strategies (horizontal vs. vertical) are not universally better; the better route may depend on the model, tensor shapes, and target GPU.
- Selecting the better route therefore requires building candidate engines for each route, measuring end‑to‑end performance, and choosing the fastest engine that satisfies accuracy requirements.
- The knob combination is a build‑route specification, not a complete description of the resulting engine; TensorRT still performs later stages such as tactic selection and may reconcile knob values with network constraints.

## ⚙️ Key details
- **API surface** (C++):
  | API | Description |
  |---|---|
  | `bool IBuilderConfig::setBuildRoute(const char* buildRoute);` | Apply a fixed route to the builder configuration |
  | `const char* IBuilderConfig::getBuildRoute() const;` | Return the currently specified route |
  | `const char* IBuilderConfig::getAllBuildRoutes() const;` | Describe the available knobs, their allowed values, defaults, and purposes |
- These APIs can be used to implement custom tuners. A sample C++ implementation is provided in `trtexec`.
- **`trtexec` workflow**:
  1. User supplies a model and a regex‑like tunable build‑route expression.
  2. The expression is expanded into a list of concrete build routes.
  3. For each route, the model is built, then accuracy and performance are measured.
  4. Routes that crash during building or fail accuracy are excluded.
  5. The engine with the best measured end‑to‑end performance is selected.
- TensorRT 11.1 provides **more than 200 knobs** for tuning.
- The same implementation will be released in Python with **Torch‑TensorRT 2.15**.
- Across ten evaluated workloads, tuning delivered performance improvements ranging from **1.14× to 1.63×**.

## 🚀 Availability
- The Global Performance Tuner ships with NVIDIA TensorRT 11.1.
- A Python version will be available in Torch‑TensorRT 2.15.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/global-performance-tuner-comparison.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/two-parallel-paths-model-quantization-inference.webp)

#TensorRT #PerformanceTuning #AIInference #DeepLearning

---

*Source: [Scaling NVIDIA TensorRT Performance Optimization Beyond a Single Build Route with the Global Performance Tuner, Part 2 | NVIDIA Technical Blog](https://developer.nvidia.com/blog/scaling-nvidia-tensorrt-performance-optimization-beyond-a-single-build-route-with-the-global-performance-tuner-part-2/)*
