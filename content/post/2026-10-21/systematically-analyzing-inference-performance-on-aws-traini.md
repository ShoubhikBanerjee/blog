---
title: "Systematically Analyzing Inference Performance on AWS Trainium with TorchNeuron"
slug: "systematically-analyzing-inference-performance-on-aws-trainium-with-torchneuron"
description: "A new guide provides a walkthrough for ML practitioners to systematically analyze inference performance and identify where time is spent during model execution, starting from scratch with no prior..."
date: 2026-10-21T22:03:49+05:30
tags: [AWSTrainium, TorchNeuron, PyTorch, MLprofiling, InferencePerformance]
categories: ["AI", "Machine Learning", "AI Infrastructure", "Performance Optimization"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6ac67ea29579ea34f1f7e470/hEodPVvQZI24jETLbPooP.png"
author: "Shoubhik Banerjee"
draft: false
---

# Systematically Analyzing Inference Performance on AWS Trainium with TorchNeuron

A new guide provides a walkthrough for ML practitioners to systematically analyze inference performance and identify where time is spent during model execution, starting from scratch with no prior profiling experience.

## 🧩 How it works

The profiling process utilizes AWS Trainium, a purpose-built AI chip for deep learning training and inference, and TorchNeuron, its open source native PyTorch backend. TorchNeuron integrates with PyTorch via the PrivateUse1 extension point, allowing the accelerator to integrate without adding a dedicated dispatch key like cuda. The `torch_neuronx` package registers Neuron as a native backend for PyTorch code.

TorchNeuron supports standard PyTorch workflows with minimal code changes, including:
* Eager execution
* torch.compile
* Standard PyTorch APIs
* Integration with Neuron Kernel Interface (NKI) for custom operators and performance optimization

## ⚙️ Key details

Profiling is managed through `torch.profiler.profile` using a `NeuronConfig` passed as `experimental_config`. 

| Parameter | Function |
| :--- | :--- |
| `modes` | Selects data streams to capture, such as runtime traces and device instructions |
| `capture_enabled_for_nc` | Selects the NeuronCores to trace |
| `correlate_device_time=True` | Propagates device time into the `key_averages()` table to compare CPU and Neuron device time |

To ensure accuracy, `torch.neuron.synchronize()` must be called inside the profiler loop; otherwise, the profiler may export before the device finishes, leaving the Neuron time column empty. The recommended schedule uses `wait=2`, `warmup=1`, and `active=1` across four `prof.step()` calls to record one warm iteration without initial setup overhead.

## 🔍 Analysis and Output

After profiling, the output directory contains system traces and, if device data was captured, paired files identified by a numeric hash:
* **NEFF (Neuron Executable File Format):** Contains the compiled Neuron executable.
* **NTFF:** Contains the hardware instruction trace.

Users can analyze these results using Neuron Explorer, a browser-based viewer for the device timeline, system trace, and per-engine breakdown, accessible via a Visual Studio Code extension or SSH tunnel.

As a practical example, the walkthrough compares a naive RMSNorm (using individual PyTorch operations like multiply, mean, add, reciprocal square root, and multiply) against `torch.rms_norm()`, which is lowered to a single fused Neuron kernel.

#AWSTrainium #TorchNeuron #PyTorch #MLprofiling #InferencePerformance

---

*Source: [Profiling TorchNeuron (Part 1): System-level profiling on AWS Trainium.](https://huggingface.co/blog/amazon/profiling-torchneuron-part-1-system-level-profilin)*
