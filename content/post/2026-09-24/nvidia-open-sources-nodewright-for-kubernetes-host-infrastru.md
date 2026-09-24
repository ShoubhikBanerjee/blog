---
title: "NVIDIA Open Sources NodeWright for Kubernetes Host Infrastructure Management"
slug: "nvidia-open-sources-nodewright-for-kubernetes-host-infrastructure-management"
description: "NVIDIA has released NodeWright as an open-source, Kubernetes-native package manager designed to modify and maintain host infrastructure at scale. As part of the NVIDIA DSX OS open-source software..."
date: 2026-09-24T18:02:55+05:30
tags: [NVIDIA, Kubernetes, OpenSource, Infrastructure, CloudNative]
categories: ["AI", "Infrastructure", "Cloud Computing", "Software Development"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/kubernetes-clusters-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Open Sources NodeWright for Kubernetes Host Infrastructure Management

NVIDIA has released NodeWright as an open-source, Kubernetes-native package manager designed to modify and maintain host infrastructure at scale. As part of the NVIDIA DSX OS open-source software layer, NodeWright enables the declarative configuration and safe updating of Kubernetes node operating systems without disrupting workloads.

## 🔍 Overview

NodeWright is a component of the NVIDIA DSX platform, which treats entire facilities as single systems (AI factories) rather than collections of machines. It is part of the supporting infrastructure capabilities that include:

* NVIDIA GPU Operator
* NVIDIA Network Operator
* Topograph
* DRA Driver for NVIDIA GPUs
* NVIDIA Cluster Readiness Engine (NVCRE)
* NVSentinel

## 🧩 How it works

NodeWright consists of three main components:

| Component | Description |
| :--- | :--- |
| Operator | A Kubernetes controller that watches for custom resources and manages the lifecycle of changes across nodes. |
| Custom Resources | Used to define NodeWright packages; these deploy via tools such as kubectl, Helm, Argo CD, or Flux. |
| Packages | Container images containing binaries, configurations, scripts, and verification scripts to surface failures and stop incorrect rollouts. |

When applying changes, NodeWright follows a specific operational flow:
1. **Cordon**: Marks the node as unschedulable.
2. **Wait**: Allows critical workloads to finish gracefully.
3. **Drain**: Evicts remaining pods, honoring PodDisruptionBudgets by default.
4. **Apply and configure**: Runs the package to set kernel parameters, install agents, and configure system services.
5. **Interrupt**: Restarts a service or reboots the node if required.
6. **Uncordon**: Returns the node to the cluster for workloads.

## ⚙️ Key details

NodeWright manages the full lifecycle of host-level changes, including installation, configuration, upgrade, and uninstallation. Key capabilities include:

* **Infrastructure Operations**: Performs tasks that normally require root access without recycling nodes, such as setting sysctl and GRUB parameters, configuring crash dump collection, creating logical volumes, installing security agents, and remediating CVEs.
* **Workload Awareness**: Respects Kubernetes primitives including node selectors, taints, tolerations, and PodDisruptionBudgets.
* **State Tracking**: Tracks the semantic version and state of every package on every node to distinguish between fresh installations, upgrades, and downgrades.
* **Dependency Management**: Uses declared dependencies to determine the correct execution order.

## 🚀 Availability

NodeWright is available as open source and has run in production at NVIDIA under the name Skyhook.

#NVIDIA #Kubernetes #OpenSource #Infrastructure #CloudNative

---

*Source: [Manage Kubernetes Node Fleets with NodeWright | NVIDIA Technical Blog](https://developer.nvidia.com/blog/manage-kubernetes-node-fleets-with-nodewright/)*
