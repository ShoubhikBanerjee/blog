---
title: "NVIDIA DAQIRI Enhances High-Speed Data Acquisition and Processing"
slug: "nvidia-daqiri-enhances-high-speed-data-acquisition-and-processing"
description: "NVIDIA DAQIRI, a software-defined data acquisition library, enables real-time processing of high-bandwidth instrument and sensor data directly into GPU memory, eliminating the need to first write..."
date: 2026-11-20T18:09:02+05:30
tags: [NVIDIA, DAQIRI, DataAcquisition, GPUProcessing, HighSpeedData]
categories: ["AI", "Data Acquisition", "GPU Computing", "Scientific Computing", "AI Inference"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/electron-energy-loss-spectroscopy-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA DAQIRI Enhances High-Speed Data Acquisition and Processing

NVIDIA DAQIRI, a software-defined data acquisition library, enables real-time processing of high-bandwidth instrument and sensor data directly into GPU memory, eliminating the need to first write data to disk. This advancement is illustrated by a high-dynamic-range electron microscopy camera developed at Lawrence Berkeley National Laboratory's Molecular Foundry, which captures strong and faint signals together, generating over 500 gigabits of data per second.

## 🔍 Overview
- NVIDIA DAQIRI is a Holoscan platform library that bridges sensors with programmable GPU platforms for scientific analysis, AI inference, and feedback applications.
- It enables processing measurements during acquisition without first writing them to disk.
- The latest DAQIRI release includes hardware packet reordering, performance and throughput improvements, and a low-latency NIC polling mode for time-sensitive packet processing.

## 🧩 How it works
- DAQIRI can offload packet reordering tasks to supported NVIDIA ConnectX-7 or newer NICs, preserving CPU and GPU resources for analysis.
- For compatible sequence formats, the NIC parses sequence fields and places each payload directly into its ordered position in memory.
- The application receives the assembled, ordered data without requiring a separate software reorder copy step.

## ⚙️ Key details
- DAQIRI enables real-time inspection and adjustment of data during measurement, processing high bandwidth data incoming at more than 500 Gbps.
- The collaboration between Berkeley Lab and NVIDIA brings together the camera, DAQIRI, and GPU-accelerated processing.
- FPGA readout electronics transmit detector data over Ethernet, DAQIRI receives the packets directly into GPU memory, and GPU processing assembles and corrects detector frames before reducing them to energy-loss spectra.

## 💡 Why it matters
- DAQIRI simplifies experimental setups and microscope optics by capturing strong and faint signals together.
- It enhances the raw detector information available for further processing and analysis.
- The advancement enables submicron spatial resolution from sensor pixels measuring 5 micrometers across.

## 🚀 Availability
- DAQIRI is part of the NVIDIA Holoscan platform library.
- The latest release includes hardware packet reordering, an optimized library backend for improved throughput, and direct polling for low-latency packet transmission and reception.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/electron-microscope-gpu-accelerated-eels-workflow.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/eels-workflow-gpu-native-acquisition-scientific-processing.webp)

#NVIDIA #DAQIRI #DataAcquisition #GPUProcessing #HighSpeedData

---

*Source: [Enabling Real-Time AI for Scientific Instruments with GPU-Native Data Acquisition | NVIDIA Technical Blog](https://developer.nvidia.com/blog/enabling-real-time-ai-for-scientific-instruments-with-gpu-native-data-acquisition/)*
