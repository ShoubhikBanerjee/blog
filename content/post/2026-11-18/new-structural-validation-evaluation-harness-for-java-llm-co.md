---
title: "New Structural-Validation Evaluation Harness for Java LLM Codegen Service"
slug: "new-structural-validation-evaluation-harness-for-java-llm-codegen-service"
description: "A new structural-validation evaluation harness has been introduced for a Java LLM codegen service, designed to make A/B changes measurable and provide deterministic metrics instead of relying on demo..."
date: 2026-11-18T12:19:35+05:30
tags: [LLM, Evaluation, CodeGeneration, Java, DevOps, Kubernetes]
categories: ["AI", "Machine Learning", "Software Engineering", "Cloud Computing", "AI Evaluation"]
image: "https://avatars.githubusercontent.com/u/181122961?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New Structural-Validation Evaluation Harness for Java LLM Codegen Service

## 📚 Introduction

A new structural-validation evaluation harness has been introduced for a Java LLM codegen service, designed to make A/B changes measurable and provide deterministic metrics instead of relying on demo screenshots or subjective assessments.

## 🔍 Overview

The harness implements a two-tier evaluation approach:

- Runs benchmark prompts against a local Java service
- Captures generated code through SSE
- Evaluates outputs with deterministic structural checks
- Optional browser execution smoke checks
- Records raw JSON plus Markdown reports
- Attributes tokens with per-run Prometheus counter windows

The most important finding was not a token percentage but a discovered issue: an earlier token result was polluted by Redis `MessageWindowChatMemory` carryover on a shared `appId`.

## 🧩 How it Works

The evaluation system operates through several components:

- Kubernetes manifests serve Qwen2.5-Coder-0.5B through vLLM
- Infrastructure spans `infra/azure` (AKS/ACR/node pools) and `infra/workloads` (Terraform-managed inference/evaluation workloads)
- A read-only authenticated GraphQL API queries both legacy Java reports and new serving runs
- A bounded-concurrency benchmark records TTFT, p50/p95 latency, request/token throughput and structural quality

## ⚙️ Key Details

The structural pass@k evaluation found:

| Metric | Result |
|--------|--------|
| Structural pass@3 | `90.0% -> 90.0%` |
| Total tokens | `323,192 -> 317,785` (`-1.7%`) |
| CodeGen-stage input reduction | ~`18%` |

The harness identified a Java product bug: `loadChatHistoryToMemory(...)` returned before `chatMemory.clear()` when MySQL history was empty, causing prompt-composition diagnostics to reveal most of the CodeGen prompt was carried-over history.

Additional capabilities include:

- Optional direct OpenAI-compatible inference reusing HTML evaluators and raw result format
- Execution smoke checker validates known browser fixtures
- One-shot repair path validates on a deterministic fixture
- Replay / fixture mode validates offline report and evaluator paths
- Failure taxonomy classifies report failures by layer

## 🚀 Availability

Documentation is available in three parts:

- [Part 1 deployment and recording guide](docs/serving-demo.md)
- [Part 2 Azure guide](docs/azure-demo.md)
- [Part 3 query and recording guide](docs/graphql-demo.md)

Additional references:

- [RESULTS.md](RESULTS.md) for full claim audit
- [Redis chat-memory carryover postmortem](docs/redis-memory-carryover-postmortem.md) for incident write-up
- [LoRA/QLoRA SFT and held-out evaluation](docs/finetuning-demo.md) for deterministic data preparation and training provenance

## 💡 Why It Matters

The structural-validation pass@k differs from HumanEval-style evaluation:

- It measures deterministic structural correctness, not functional correctness
- Execution smoke validation serves as a thin second layer for narrow browser/build sanity, not full functional testing
- The two layers are reported separately to avoid collapsing into one ambiguous pass number

Implementation tests are offline, and actual GPU deployment and performance measurements are pending. The sample data serves as a pipeline smoke fixture, with GPU training and quality gains remaining unverified.

#LLM #Evaluation #CodeGeneration #Java #DevOps #Kubernetes

---

*Source: [LING-6150/llm-codegen-eval](https://github.com/LING-6150/llm-codegen-eval)*
