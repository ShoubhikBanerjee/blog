---
title: "Integrating NVIDIA Resiliency Extension with PyTorch FSDP on Amazon EKS"
slug: "integrating-nvidia-resiliency-extension-with-pytorch-fsdp-on-amazon-eks"
description: "NVIDIA Resiliency Extension (NVRx) has been integrated into PyTorch Fully Sharded Data Parallel (FSDP) training on Amazon Elastic Kubernetes Service (Amazon EKS) to address training interruptions and..."
date: 2026-09-17T06:05:39+05:30
tags: [PyTorch, NVIDIA, AmazonEKS, FSDP, GPU]
categories: ["AI", "Machine Learning", "Cloud Computing", "Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-20900-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Integrating NVIDIA Resiliency Extension with PyTorch FSDP on Amazon EKS

NVIDIA Resiliency Extension (NVRx) has been integrated into PyTorch Fully Sharded Data Parallel (FSDP) training on Amazon Elastic Kubernetes Service (Amazon EKS) to address training interruptions and I/O bottlenecks in large-scale distributed jobs.

## 💡 Why it matters
Large-scale distributed training jobs running across dozens of nodes for hours or days face statistically inevitable interruptions such as network partitions, memory errors, software exceptions, or infrastructure events. A single GPU fault can trigger a cascade where NVIDIA Collective Communication Library (NCCL) timeouts propagate to healthy workers and pods crash, resulting in expensive GPU hours with zero training progress. Additionally, synchronous checkpointing can consume up to 40% of total wall time by blocking all ranks on I/O.

## 🧩 How it works
NVRx is a pip-installable Python layer (`pip install nvidia-resiliency-ext`) that adds fault-tolerance primitives to PyTorch without requiring custom kernels, a PyTorch fork, or recompilation. These primitives drop into existing FSDP scripts as ordinary imports, leaving the model and training code untouched.

| Feature | Function | Fault Class Handled |
| :--- | :--- | :--- |
| **Async Checkpointing** | Uses `TorchAsyncCheckpoint` to replace `torch.save` with `async_save()`, handing state dicts to a background process to overlap I/O with training. | I/O Bottlenecks |
| **In-process Restart** | Uses `inprocess.Wrapper` to wrap the train function; it aborts the active process group, runs health checks, and re-rendezvouses survivors. | Soft faults (unhandled exceptions, NCCL hangs) |
| **ft_launcher** | An in-job restart launcher that uses `RankMonitorClient` to check heartbeats and respawn fresh workers on stall or death. | Hard faults (SIGKILL, OOM kill, OS-level hangs) |

## ⚙️ Key details
* **Async Checkpointing:** Paired with FSDP `LOCAL_STATE_DICT`, each rank writes its own shard directly to avoid all-gather and rank-0 bottlenecks. A `finalize_async_save()` call commits the write before the next save.
* **In-process Recovery:** The CUDA allocator, interpreter, and outer-scope objects survive the restart.
* **In-job Recovery:** The launcher kills survivors, reclaims GPU memory, and respawns workers who reload from the latest checkpoint.
* **Infrastructure:** The solution runs on Amazon EKS using self-managed node groups of p5.48xlarge instances, featuring 8 NVIDIA H100 80 GB GPUs and 32 Elastic Fabric Adapter (EFA) network interfaces per instance.
* **Validation:** Benchmark results were collected on H100 GPUs at a scale of 2 to 8 nodes.

#PyTorch #NVIDIA #AmazonEKS #FSDP #GPU

---

*Source: [Fault tolerant distributed training on Amazon EKS using NVRx | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/fault-tolerant-distributed-training-on-amazon-eks-using-nvrx/)*
