---
title: "OpenHack v2.0.0 adds local AI security scanning to your source code"
slug: "openhack-v2-0-0-adds-local-ai-security-scanning-to-your-source-code"
description: "OpenHack, a local AI security scanner for source code, has released version 2.0.0, introducing a new harness that maps codebases and assigns focused source reviews."
date: 2026-11-23T22:18:20+05:30
tags: [OpenHack, SecurityScanner, SourceCode, AISecurity, v200]
categories: ["AI", "Security", "Developer Tools", "Software Engineering"]
image: "https://avatars.githubusercontent.com/u/244944567?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# OpenHack v2.0.0 adds local AI security scanning to your source code

OpenHack, a local AI security scanner for source code, has released version 2.0.0, introducing a new harness that maps codebases and assigns focused source reviews.

## 🔍 Overview
OpenHack is a local AI security scanner designed for source code. The v2 harness maps your codebase, assigns focused source reviews, challenges candidate findings, and judges the evidence. All scan history, findings, notes, and configuration remain in your local workspace.

## 🧩 How it works
The standalone executable includes the Bun runtime and dashboard assets, meaning no separate Bun, Node.js, Python, or package installation is required to run it. An AI provider is required to perform a scan, and API-key mode functions without additional provider software. OpenHack retains control of the scanning workflow and source tools. Subscription adapters invoke the provider CLI in an isolated temporary directory with its native execution tools disabled, reusing the CLI's authentication without copying login tokens.

## ⚙️ Key details
- Dashboard access: OpenHack opens the dashboard at http://127.0.0.1:6969. It runs in the background, so closing the browser does not stop it. Running `openhack` again reopens it. Use `openhack --no-open` to start without a browser or `openhack --port 6970` to select a different port.
- Provider configuration: Switching the saved provider changes the default model, while a model specified for an individual scan applies only to that scan. Resumed scans retain their original provider, model, and configuration.
- Scan status: Scans with useful results but unfinished work are marked Partial. Findings remain available, and resuming retries the unfinished tasks. A partial status does not indicate a clean codebase.
- Installation: The installer detects your OS and processor, downloads the matching GitHub release archive, verifies the SHA-256 checksum, and installs `openhack` in `~/.local/bin`. It requires no sudo, does not modify shell profiles, and does not start the app automatically. License notices are preserved in `~/.local/bin/openhack-licenses`.

## 🚀 Availability
v2.0.0 is currently available for macOS and Linux. Both macOS builds are Developer ID signed and Apple notarized. Windows downloads are deferred until publisher signing is ready. The Linux archives target glibc systems; Alpine/musl is not supported by these builds.

#OpenHack #SecurityScanner #SourceCode #AISecurity #v2.0.0

---

*Source: [openhackai/OpenHack](https://github.com/openhackai/OpenHack)*
