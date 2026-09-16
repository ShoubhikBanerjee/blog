---
title: "NVIDIA Resiliency Extension Adds Fault-Tolerance Primitives to PyTorch"
slug: "nvidia-resiliency-extension-adds-fault-tolerance-primitives-to-pytorch"
description: "The NVIDIA Resiliency Extension (NVRx) has been introduced as a pip-installable Python layer (`pip install nvidia-resiliency-ext`) that provides fault-tolerance primitives for PyTorch without..."
date: 2026-09-17T00:45:10+05:30
tags: [NVIDIA, PyTorch, AWS, FaultTolerance, MachineLearning]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "Software Development"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-20900-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Resiliency Extension Adds Fault-Tolerance Primitives to PyTorch

The NVIDIA Resiliency Extension (NVRx) has been introduced as a pip-installable Python layer (`pip install nvidia-resiliency-ext`) that provides fault-tolerance primitives for PyTorch without requiring custom kernels, a PyTorch fork, or recompilation.

## 🧩 How it works

NVRx provides three primary features to handle different types of failures during training:

| Feature | Function |
| :--- | :--- |
| **Async Checkpointing** | Replaces `torch.save` with `async_save()` via `TorchAsyncCheckpoint`, handing the state dict to a background process to return immediately. |
| **In-process Restart** | Uses `inprocess.Wrapper` to wrap the train function, preventing transient faults like unhandled exceptions or NCCL hangs from killing the Python process. |
| **ft_launcher** | An in-job restart launcher that handles OS-level hangs, SIGKILL, and out-of-memory (OOM) kills. |

When using `ft_launcher`, each rank runs a `RankMonitorClient`. The launcher monitors heartbeats against CLI-set timeouts; if a stall or death is detected, it kills survivors, reclaims GPU memory, and respawns workers in the same job, which then reload from the latest checkpoint.

## ⚙️ Key details

*   **Checkpointing Efficiency:** When paired with FSDP `LOCAL_STATE_DICT`, each rank writes its own shard directly, eliminating the rank-0 bottleneck and the need for all-gather.
*   **Infrastructure Requirements:** 
    *   **Compute:** Amazon EC2 p5.48xlarge instances featuring 8x NVIDIA H100 80 GB GPUs and 32x Elastic Fabric Adapter (EFA) network interfaces.
    *   **Orchestration:** Amazon EKS (v1.28+) managing the control plane, pod scheduling, and Job lifecycle. Training pods run as Kubernetes Jobs with headless Services for DNS-based peer discovery.
    *   **Storage:** Amazon FSx for Lustre (SCRATCH_2) mounted via the FSx CSI driver for distributed checkpoint I/O.
    *   **Networking:** EFA provides 3,200 Gbps network bandwidth for NCCL all-reduce operations.
    *   **Software:** Container images containing PyTorch 2.9+ and NVRx 0.4.1.

## 🚀 Availability

To reproduce benchmark results, the following environment is required:
*   AWS account with service quota for p5.48xlarge (or p4de.24xlarge) instances.
*   Amazon EKS cluster with EFA-enabled self-managed GPU node groups and the NVIDIA device plugin.
*   Amazon FSx for Lustre filesystem in the same Availability Zone as the GPU nodes.
*   Container image stored in Amazon ECR.

#NVIDIA #PyTorch #AWS #FaultTolerance #MachineLearning

---

*Source: [Fault tolerant distributed training on Amazon EKS using NVRx | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/fault-tolerant-distributed-training-on-amazon-eks-using-nvrx/)*
