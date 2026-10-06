---
title: "NVIDIA AI Cluster Runtime v1.0 delivers version‑locked GPU‑Kubernetes recipes"
slug: "nvidia-ai-cluster-runtime-v1-0-delivers-versionlocked-gpukubernetes-recipes"
description: "NVIDIA released version 1.0 of the AI Cluster Runtime (AICR), a library of version‑locked, validated recipes that simplify the configuration of GPU‑accelerated Kubernetes clusters."
date: 2026-10-06T22:08:14+05:30
tags: [NVIDIA, Kubernetes, GPU, AICR]
categories: ["AI", "Cloud Computing", "DevOps", "Artificial Intelligence", "Infrastructure"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image1-5-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA AI Cluster Runtime v1.0 delivers version‑locked GPU‑Kubernetes recipes

NVIDIA released version 1.0 of the AI Cluster Runtime (AICR), a library of version‑locked, validated recipes that simplify the configuration of GPU‑accelerated Kubernetes clusters.

## 🔍 Overview
- GPU‑accelerated Kubernetes clusters depend on compatible versions across dozens of components, each on its own release cycle: host kernels, GPU drivers, container runtimes, networking, storage, operators, and workload frameworks.
- A configuration that works for one service, GPU generation, and Kubernetes release may silently fail for another, and tracing version conflicts after deployment is slow and error‑prone.
- AICR addresses this with version‑locked, validated recipes for GPU cluster configuration.

## 🧩 How it works
| AICR element | Purpose |
|--------------|---------|
| **Recipe** | Describes the desired, version‑locked component configuration and the constraints and validation phases that apply to it. |
| **Bundle** | Renders the recipe into deployment artifacts for Helm, Argo CD, Flux, or Helmfile (or other IaC tools). |
| **Snapshot** | Records observed cluster state, including Kubernetes, operating system, kernel, GPU, and topology information. |
| **Validation** | Compares the recipe with observed state and, where declared, runs deployment, conformance, and performance checks; records signed evidence of the result. |

The workflow is:
1. Operator selects criteria (e.g., service, GPU, OS, workload intent) on the validation dashboard.
2. The dashboard resolves those criteria to a pinned recipe.
3. The recipe is rendered as a bundle for the operator’s preferred deployment tool (Argo CD, Helm, Flux, Helmfile, etc.).
4. The bundle is applied to the cluster using the chosen CD tool.
5. AICR validates the running cluster against the same recipe and stores signed evidence.

## ⚙️ Key details
- All recipes are version‑locked and carry signed validation evidence from the hardware they were tested on.
- v1.0 establishes a stable compatibility contract across its CLI, REST API, Go SDK, bundle layout, and artifact schemas.
- The v1.x compatibility policy allows integrators to build against AICR’s public interfaces.
- Contributors can propose recipes, validate them on their own clusters, and submit signed evidence for maintainer review.
- Recent additions include live‑cluster validation, signed evidence, public evidence aggregation, and supply‑chain verification.
- Merge‑blocking checks and committed compatibility baselines protect the public integration surfaces.
- Pulumi Labs exposes AICR through an infrastructure‑as‑code provider, while Mirantis’s k0rdent integration packages it for multi‑cluster management.
- Together they demonstrate the value of defining GPU‑accelerated Kubernetes configuration once and consuming it through different tools.

## 🚀 Availability
- v1.0 is the first stable release of AICR.
- Over the past six months the library grew from a handful of recipes to a collection spanning major Kubernetes services and the current NVIDIA accelerator portfolio, rendered as deployer‑neutral bundles.
- AICR now has over 100 distinct contributors, with almost half from outside of NVIDIA.

## 💡 Why it matters
- Prevents silent failures caused by hidden version mismatches across components.
- Centralises knowledge of working component combinations that previously lived in separate validation systems, deployment scripts, and runbooks.
- Enables teams to discover, reproduce, and update working configurations through a single dashboard and a unified set of public interfaces.
- Provides signed evidence and supply‑chain verification, increasing trust in the deployed cluster configuration.
- Allows operators to keep their existing GitOps or IaC workflows (Helm, Argo CD, Flux, Helmfile) while guaranteeing the intended configuration does not change across tooling.

#NVIDIA #Kubernetes #GPU #AICR

---

*Source: [AICR v1.0: Open, stable, and verifiable GPU cluster configuration | NVIDIA Technical Blog](https://developer.nvidia.com/blog/aicr-v1-0-open-stable-and-verifiable-gpu-cluster-configuration/)*
