---
title: "DiDi Open-Sources HUATUO for Kernel-Level OS Observability"
slug: "didi-open-sources-huatuo-for-kernel-level-os-observability"
description: "DiDi has open-sourced HUATUO, a cloud-native OS observability project incubated under the CCF. HUATUO provides kernel-level insights for cloud-native, AI, and bare-metal environments, enhancing..."
date: 2026-11-18T18:09:03+05:30
tags: [OpenSource, CloudNative, Observability, DiDi]
categories: ["AI", "Open Source Software", "Cloud Computing", "AI Infrastructure", "DevOps"]
image: "https://avatars.githubusercontent.com/u/96813578?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# DiDi Open-Sources HUATUO for Kernel-Level OS Observability

DiDi has open-sourced HUATUO, a cloud-native OS observability project incubated under the CCF. HUATUO provides kernel-level insights for cloud-native, AI, and bare-metal environments, enhancing system reliability and performance.

## 🔍 Overview
HUATUO enables kernel-wide visibility using technologies like kprobes, tracepoints, ftrace, and eBPF. Deployed in DiDi's production, it helps troubleshoot failures and improve high availability.

## 🧩 How it works
- Leverages eBPF for low performance overhead (<1%)
- Captures detailed data on kernel events (page faults, scheduling delays)
- Automatically resolves performance issues (CPU jitter, I/O surges)
- Profiles OS and applications comprehensively

## ⚙️ Key details
- Supports Linux kernel 4.18+ and integrates with tools like Prometheus and Grafana
- Uses zero-instrumentation for broad compatibility
- Tested on various hardware and Linux distributions

## 🚀 Availability
Deploy with Docker:
```
$ docker run --privileged --pid=host --cgroupns=host --network=host -v /sys:/sys -v /run:/run huatuo/huatuo-bamai:latest
```
Use formal release images for production.

## 💡 Why it matters
HUATUO provides critical insights for improving cloud-native and AI infrastructure reliability, supporting business innovation through advanced observability.

#OpenSource #CloudNative #Observability #DiDi

---

*Source: [ccfos/huatuo](https://github.com/ccfos/huatuo)*
