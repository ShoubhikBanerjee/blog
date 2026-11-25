---
title: "OpenHands Benchmarks Updated for V1 Agent SDK with New Evaluation Pipelines"
slug: "openhands-benchmarks-updated-for-v1-agent-sdk-with-new-evaluation-pipelines"
description: "The OpenHands benchmark repository now runs on the OpenHands Software Agent SDK V1, providing standardized evaluation pipelines for a range of real‑world agent tasks."
date: 2026-11-25T06:12:19+05:30
tags: [OpenHands, AIbenchmarks, SoftwareAgents]
categories: ["AI", "Machine Learning", "AI Agents", "Software Engineering", "Benchmarking"]
image: "https://avatars.githubusercontent.com/u/225919603?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# OpenHands Benchmarks Updated for V1 Agent SDK with New Evaluation Pipelines

The OpenHands benchmark repository now runs on the OpenHands Software Agent SDK V1, providing standardized evaluation pipelines for a range of real‑world agent tasks.

## 🔍 Overview
- Benchmark evaluation infrastructure for OpenHands agents.
- Standardized pipelines test agent capabilities across diverse tasks.
- Migration from OpenHands V0 to V1 SDK is in progress.

## 🧩 How it works
- The repository uses a local git submodule that pins a specific SDK commit (`vendor/software-agent-sdk/`).
- Clone the SDK, check out the exact commit, and run `uv sync` to install from the local folder.
- `uv` must be version >= 0.9.20 to enforce the seven‑day dependency release‑age cutoff.
- All benchmarks require an LLM configuration file defined as JSON following the `LLM` class fields.
- Rich, color‑coded console logs show real‑time tool calls, agent messages, and a summary per instance; file logs (`logs/instance_<id>.log`) remain unchanged.

## ⚙️ Benchmarks
| Benchmark | Description |
|-----------|-------------|
| SWE‑Bench | Software engineering tasks from GitHub issues |
| SWE‑Bench Pro | Long‑horizon software engineering tasks from GitHub issues |
| GAIA | General AI assistant tasks requiring multi‑step reasoning |
| Commit0 | Python function implementation tasks with unit tests |
| OpenAgentSafety | AI agent safety evaluation in workplace scenarios with NPC interactions |
| ProgramBench | Rebuild a program from scratch given only its compiled binary and docs |

## 🚀 Availability
- Clone the repository and the SDK submodule.
- Ensure the SDK commit pinned by the repo is checked out.
- Run `uv sync` to install the `openhands-*` packages from the local workspace declared in `pyproject.toml`.
- Benchmarks support two workspace types:
  - Local Docker containers (images built on‑demand).
  - Remote runtime API for cloud containers, enabling hundreds of parallel workers.
- Agent‑server images must be pre‑built for the specific SDK commit SHA and pushed to a public registry (e.g., `ghcr.io/openhands/eval-agent-server`).

## 💡 Why it matters
- Provides reproducible, version‑locked evaluation environments.
- Enables scalable testing across many workers without local resource limits.
- Offers a unified way to assess safety, reasoning, and software‑engineering capabilities of AI agents.

#OpenHands #AIbenchmarks #SoftwareAgents

---

*Source: [OpenHands/benchmarks](https://github.com/OpenHands/benchmarks)*
