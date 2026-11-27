---
title: "Gondolin introduces secure, isolated micro-VMs for AI agents running generated code"
slug: "gondolin-introduces-secure-isolated-micro-vms-for-ai-agents-running-generated-code"
description: "Gondolin is a new agent sandbox that runs AI-generated code inside local Linux micro-VMs, providing programmable network and filesystem control. It addresses security risks from autonomous code..."
date: 2026-11-27T18:08:33+05:30
tags: [AIagents, Security, Virtualization, MicroVM, TypeScript, Rust]
categories: ["AI", "AI Agents", "Security", "Virtualization", "Software Development"]
image: "https://avatars.githubusercontent.com/u/207902832?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Gondolin introduces secure, isolated micro-VMs for AI agents running generated code

Gondolin is a new agent sandbox that runs AI-generated code inside local Linux micro-VMs, providing programmable network and filesystem control. It addresses security risks from autonomous code execution by isolating agents while maintaining controlled access to network resources and credentials.

## 🧩 How it works

The system uses a TypeScript Control Plane with Linux microvm setup. Generated code is executed inside a fast local Linux micro-VM (using `libkrun` when available, with QEMU fallback) that keeps network and filesystem access under host-side policy control.

## 🔍 Architecture

A key security feature is that the guest VM only sees placeholder tokens, while the real secret is injected by the host only for allowed destinations, including `Authorization: Basic ...` flows.

## ⚙️ Key details

### Platform Support

- Node.js 22.19 or newer required
- `npm install @earendil-works/gondolin` installs the Gondolin daemon (`gondolind`) and platform packages
- Works on macOS and Linux on arm64 and x64

### Execution Backend

- Uses `libkrun` on Apple silicon and Linux x86_64 with read/write `/dev/kvm`
- Falls back to QEMU on other hosts or when `qemu` backend is selected

### Policy Control

- Programmable HTTP/TLS egress policy with allowlists and request/response hooks
- Daemon-side policies via self-contained JavaScript (`createDjsHooks()`, `--hooks-script`)
- Configurable DNS behavior, rootfs modes, and runtime sizing

### Session Management

Useful session commands include:

- List running sessions
- Attach to an existing session
- Snapshot a running session (stops it)
- Resume from snapshot id/path

### Guest Images and Storage

- Default guest image: `alpine-base:latest` (downloaded from built-in registry on first use)
- Images cached locally (~200MB+)
- Disk checkpoints (snapshots) with resume support
- Custom image builds via Alpine-based pipeline with optional OCI rootfs source

### File System and Network Features

- Programmable VFS mounts allowing custom file system behavior in JavaScript
- Ingress gateway to expose guest HTTP services on host (`--listen`, `vm.enableIngress()`)
- SSH support: host -> guest access (`vm.enableSsh()`) and optional guest -> upstream allowlisted SSH egress (proxied, exec-oriented)

### Daemon Architecture

The VM runs under a static Rust daemon (`gondolind`) that can operate on another machine without Node.js, while policy, hooks, and credentials remain local.

#AIagents #Security #Virtualization #MicroVM #TypeScript #Rust

---

*Source: [earendil-works/gondolin](https://github.com/earendil-works/gondolin)*
