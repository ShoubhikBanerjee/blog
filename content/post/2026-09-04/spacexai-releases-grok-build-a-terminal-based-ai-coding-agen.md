---
title: "SpaceXAI releases Grok Build: a terminal-based AI coding agent"
description: "SpaceXAI has open‑sourced Grok Build, its terminal‑based AI coding agent."
date: 2026-09-04T12:10:15+05:30
tags: [SpaceXAI, AIcoding, Rust, TerminalAI]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/130314967?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# SpaceXAI releases Grok Build: a terminal-based AI coding agent

SpaceXAI has open‑sourced Grok Build, its terminal‑based AI coding agent.

## 🔍 Overview
- Grok Build is a terminal‑based AI coding agent developed by SpaceXAI.
- It runs as a full‑screen text user interface (TUI) that can understand a codebase, edit files, execute shell commands, search the web, and manage long‑running tasks.
- It can be used interactively, headlessly for scripting/CI, or embedded in editors via the Agent Client Protocol (ACP).

## 🛠️ How it works
- The repository contains the Rust source for the `grok` CLI/TUI and its agent runtime.
- The source tree is synced periodically from the SpaceXAI monorepo; a `SOURCE_REV` file records the exact monorepo commit SHA.
- The workspace `Cargo.toml` is generated and should be treated as read‑only.
- Build requirements:
  - Rust toolchain pinned by `rust-toolchain.toml`; `rustup` installs automatically on first build.
  - DotSlash is required so hermetic tools under `bin/` (e.g., `bin/protoc`) can be downloaded and run; ensure `dotslash` is on your `PATH` before building.
  - `protoc` proto codegen resolves `bin/protoc` via DotSlash or falls back to a `protoc` on `PATH` / `$PROTOC`.

## ⚙️ Key details
- Supported build hosts: macOS and Linux; Windows builds are best‑effort and not currently tested from this tree.
- Prebuilt binaries are published for macOS, Linux, and Windows.
- The binary artifact is named `xai-grok-pager`; official installs ship it as `grok`.
- On first launch the tool opens a browser for authentication (see the authentication guide).
- Full online documentation: https://docs.x.ai/build/overview
- User guide location: `crates/codegen/xai-grok-pager/docs/user-guide/` (covers getting started, keyboard shortcuts, slash commands, configuration, theming, MCP servers, skills, plugins, hooks, headless mode, sandboxing, and more).

## 📦 Availability
- Releases include a changelog with fixes, features, and improvements: https://x.ai/build/changelog
- Binaries can be downloaded for the three major platforms.

## 📄 Licensing
- First‑party code in the repository is licensed under the Apache License, Version 2.0.
- Third‑party and vendored code retains its original licenses.
- External contributions are not accepted.

#SpaceXAI #AIcoding #Rust #TerminalAI

---

*Source: [xai-org/grok-build](https://github.com/xai-org/grok-build)*
