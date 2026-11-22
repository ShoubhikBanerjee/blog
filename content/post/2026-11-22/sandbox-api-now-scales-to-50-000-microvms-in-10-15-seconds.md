---
title: "Sandbox API now scales to 50,000 microVMs in 10-15 seconds"
slug: "sandbox-api-now-scales-to-50-000-microvms-in-10-15-seconds"
description: "The `Sandbox` API now supports a high-performance serving path that scales to 50,000 running microVMs in 10–15 seconds by scatter-gathering per-node inventory instead of storing per-sandbox objects."
date: 2026-11-22T06:08:21+05:30
tags: [Kubernetes, MicroVMs, Sandboxing, AIInfrastructure, Performance]
categories: ["AI", "Cloud Infrastructure", "AI Agents", "Developer Tools", "Kubernetes"]
image: "https://avatars.githubusercontent.com/u/272786924?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Sandbox API now scales to 50,000 microVMs in 10-15 seconds

The `Sandbox` API now supports a high-performance serving path that scales to 50,000 running microVMs in 10–15 seconds by scatter-gathering per-node inventory instead of storing per-sandbox objects.

## 🔍 Overview
The system introduces three distinct serving paths for the `Sandbox` API:
- **Pod path:** An upstream controller translates a `Sandbox` into a standard Pod.
- **L3 path:** A custom `sandbox-apiserver` serves the `sandboxes.agents.x-k8s.io/v1beta1` API directly from `NodeInventory`.
- **e2b path:** An optional REST surface compatible with the e2b SDK, accessible via Kubernetes or an external mesh.

## 🧩 How it works
The L3 path utilizes a scatter-gather methodology for node inventory. Rather than creating a Kubernetes object for every single sandbox, the system claims sandboxes from a node's warm pool during creation. This approach significantly reduces load on the control plane; in a specific test environment, patching a `SandboxWarmPool` took 20 bare-metal nodes to 50,000 running microVMs in 10–15 seconds, with etcd seeing approximately 2 writes per second.

### Serving Paths Details
- **Pod path:** Routing Pods to microVM nodes is handled via an explicit pod-template contract written by the template author.
- **L3 path:** The `sandbox-apiserver` adds subresources for pause, resume, fork, and snapshot operations.
- **e2b path:** The `sandbox-envd-proxy` carries SDK traffic for files, commands, and PTY into the sandbox. Outside of Kubernetes, `sandbox-e2b` can serve the same interface on a sandboxd mesh using gossip-based node discovery.

## ⚙️ Key details
The deployment chart includes a warm-pool driver and an `APIService` that shadows the `Sandbox` CRD for `agents.x-k8s.io/v1beta1`. This design ensures that an L3 cluster does not run the upstream controller or install its `Sandbox` CRD. Users selecting the Pod path must instead apply the upstream `sandbox-with-extensions.yaml`.

| Component | Function |
| :--- | :--- |
| `sandbox-apiserver` | Serves the L3 API and e2b REST surface from NodeInventory |
| `sandbox-envd-proxy` | Carries e2b SDK data plane traffic into the sandbox |
| `sandbox-e2b` | Serves e2b surface on a sandboxd mesh outside Kubernetes |
| `sandboxd` | Node-local daemon used by the L3 apiserver and proxy |

## 💡 Why it matters
By decoupling the high-frequency sandbox lifecycle operations from etcd storage, this architecture enables rapid scaling of microVMs. It also provides flexibility for developers to use either standard Kubernetes Pod abstractions or a specialized L3 API for lower-latency sandbox management, while maintaining compatibility with the e2b developer experience.

#Kubernetes #MicroVMs #Sandboxing #AIInfrastructure #Performance

---

*Source: [cocoonstack/sandbox-operator](https://github.com/cocoonstack/sandbox-operator)*
