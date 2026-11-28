---
title: "Nix Sandbox Provides Declarative Security for AI CLI Agents"
slug: "nix-sandbox-provides-declarative-security-for-ai-cli-agents"
description: "A new lightweight, declarative sandboxing tool has been introduced for AI agents operating on Linux and macOS. Built using Nix, the project aims to prevent 'YOLO mode' agents from performing..."
date: 2026-11-28T18:07:42+05:30
tags: [Nix, AIagents, Linux, macOS, Sandboxing, DevOps]
categories: ["AI", "AI Agents", "DevOps", "Linux", "Security"]
image: "https://avatars.githubusercontent.com/u/93987987?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Nix Sandbox Provides Declarative Security for AI CLI Agents

A new lightweight, declarative sandboxing tool has been introduced for AI agents operating on Linux and macOS. Built using Nix, the project aims to prevent "YOLO mode" agents from performing destructive actions such as deleting home directories, force pushing to main branches, or publishing SSH keys online.

## 🧩 How it works
The sandbox supports any CLI-based AI agent and utilizes underlying system tools to create restricted environments:
- **Linux**: Uses [bubblewrap](https://github.com/containers/bubblewrap).
- **macOS**: Uses `sandbox-exec`.

Access controls are defined declaratively, allowing developers to specify exactly what the agent can read, write, or execute. By default, network access is open, but it can be filtered to specific domains. Ports are closed by default unless explicitly exposed or connected to.

## ⚙️ Key details
The sandbox enforces strict boundaries on file system access and environment variables. Only changes to the project directory and declared read/write paths are persisted; all other writes, including to the agent's home directory, are discarded upon exit.

| Category | Behavior |
| :--- | :--- |
| Project Directory | Read/write access to the launch directory or a fixed `workspaceDir`. |
| Declared State | Read/write access via `rwDirs`/`rwFiles`; read-only access via `roDirs`/`roFiles`. |
| Allowed Packages | Binaries listed in `allowedPackages` are added to the PATH, alongside `bash` and `cacert`. |
| Environment | Restricted to declared environment variables only. |
| Git | Supports git commands, including those launched within a worktree. |
| Nix | Disabled by default, though agents can be explicitly permitted to run nix commands. |

## 🚀 Availability
The repository provides templates for common agent CLIs. To get started, users can use a flake template which creates a `flake.nix` in the project directory. For those not using flakes, a plain `shell.nix` setup is available. Users can adapt existing templates or contribute new ones by adjusting parameters such as `pkg`, `binName`, `outName`, `allowedDomains`, and required `rwDirs` for configuration and cache.

#Nix #AIagents #Linux #macOS #Sandboxing #DevOps

---

*Source: [archie-judd/agent-sandbox.nix](https://github.com/archie-judd/agent-sandbox.nix)*
