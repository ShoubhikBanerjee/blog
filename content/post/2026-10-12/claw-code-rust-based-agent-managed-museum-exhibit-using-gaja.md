---
title: "Claw Code: Rust‑Based Agent‑Managed Museum Exhibit Using Gajae‑Code and LazyCodex"
slug: "claw-code-rustbased-agentmanaged-museum-exhibit-using-gajaecode-and-lazycodex"
description: "An agent-managed museum exhibit called **Claw Code** has been released. It is a public Rust implementation of the `claw` CLI agent harness, built with the Gajae-Code and LazyCodex toolchains and..."
date: 2026-10-12T06:06:07+05:30
tags: [Rust, AIagents, AgentManagement, OpenSource]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Software Engineering", "Open Source"]
image: "https://avatars.githubusercontent.com/u/272961631?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Claw Code: Rust‑Based Agent‑Managed Museum Exhibit Using Gajae‑Code and LazyCodex

An agent-managed museum exhibit called **Claw Code** has been released. It is a public Rust implementation of the `claw` CLI agent harness, built with the Gajae-Code and LazyCodex toolchains and designed to run without any human intervention.

## 🔍 Overview
- The repository is described as a **museum exhibit** rather than a commercial product.
- It is “closer to a museum exhibit than a product pitch,” kept alive by “crab‑run” artifact processes and automatically maintained by agents.
- The project philosophy explicitly states it is **not meant to be hand‑operated** like a normal product repo.

## 🛠️ How It Works
- The exhibit is **agent‑managed**: harnesses **plan, execute, verify, label, and preserve** the artifact while “crabs keep the tank running.”
- The canonical source lives in the `rust/` directory, with the current source of truth being **ultraworkers/claw-code**.
- `claw` is the CLI agent harness; Claw Code provides its public Rust implementation.

## 📦 Getting Started
- Start with **[LazyCodex](https://github.com/code-yeongyu/lazycodex)** or **[Gajae‑Code](https://github.com/Yeachan-Heo/gajae-code)** if you want to run work.
- For build, authentication, CLI usage, session handling, and parity‑harness workflows, consult **[`USAGE.md`](./USAGE.md)**.
- After building, run `claw doctor` as the first health check.
- Detailed crate information is in **[`rust/README.md`](./rust/README.md)**; the Rust‑port checkpoint is documented in **[`PARITY.md`](./PARITY.md)**.
- Container‑first workflow instructions are in **[`docs/container.md`](./docs/container.md)**.
- Windows users can follow the PowerShell‑first quickstart in **[`docs/windows-install-release.md`](./docs/windows-install-release.md)**.
- For file submission or navigation questions, see **[`docs/navigation-file-context.md`](./docs/navigation-file-context.md)**.
- Setup for local OpenAI‑compatible models and offline skill installs is covered in **[`docs/local-openai-compatible-providers.md`](./docs/local-openai-compatible-providers.md)**.

## 📡 Integration & Status
- **ACP / Zed**: Claw Code does **not ship an ACP/Zed daemon or JSON‑RPC entrypoint** yet.
- Use `claw acp` (or `claw --acp`) to query the current status; `claw acp serve` is a discoverability alias that returns status with exit code 0.
- Real ACP support remains tracked in **[`ROADMAP.md`](./ROADMAP.md)**.
- The public JSON contract is defined in **[`docs/g011-acp-json-rpc-status-contract.md`](./docs/g011-acp-json-rpc-status-contract.md)**.

## 🚀 Availability & Community
- Repository: **ultraworkers/claw-code** (GitHub).
- Join the development discussion on Discord:
  - **Harness Lab** – *Discord‑join the harness lab*
  - **Crab Tank** – *Discord‑join the crab tank*
- Star history for the repository is publicly visible.
- For a longer public explanation of the project philosophy, see the linked tweet in the source material.

---
*All details are drawn directly from the project documentation and announcements.*

#Rust #AIagents #AgentManagement #OpenSource

---

*Source: [ultraworkers/claw-code](https://github.com/ultraworkers/claw-code)*
