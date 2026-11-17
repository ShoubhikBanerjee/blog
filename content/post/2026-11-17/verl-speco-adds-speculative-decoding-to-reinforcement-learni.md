---
title: "verl-SpeCo adds speculative decoding to reinforcement learning loops"
slug: "verl-speco-adds-speculative-decoding-to-reinforcement-learning-loops"
description: "`verl-SpeCo` is a lightweight overlay for the `verl` reinforcement learning framework that enables the training and integration of speculative decoding drafters. It operates as an import-only..."
date: 2026-11-17T22:09:21+05:30
tags: [ReinforcementLearning, SpeculativeDecoding, vLLM, SGLang, MachineLearning]
categories: ["AI", "Machine Learning", "Reinforcement Learning", "Infrastructure", "LLM"]
image: "https://avatars.githubusercontent.com/u/212961691?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# verl-SpeCo adds speculative decoding to reinforcement learning loops

## 🧩 Overview

`verl-SpeCo` is a lightweight overlay for the `verl` reinforcement learning framework that enables the training and integration of speculative decoding drafters. It operates as an import-only dependency, keeping upstream `verl` unpatched while adding drafter collection, training, and hot-update logic through the `verl_speco` module. The tool is run via `python -m verl_speco.main` and composes upstream PPO/GRPO configurations. It supports multiple drafter backends—including EAGLE-1, EAGLE-2, EAGLE3, DFlash, DSpark, Domino, and P-EAGLE—along with integration for both vLLM and SGLang rollout engines.

## ⚙️ How It Works

The overlay performs drafter co-training directly within the reinforcement learning loop. It collects hidden states during rollout or old-logprob computation, periodically trains the drafter, and publishes the updated weights back to the rollout engine. A key mechanism, known as "Bubble Time" training, utilizes rollout idle workers to run drafter optimizer steps. This approach publishes the trained drafter to all replicas, preserving generation benefits while keeping the drafter training time off the main critical path.

The tool maintains architectural flexibility; the drafter trainer runs on FSDP2, while the main actor can utilize verl's FSDP/FSDP2 or VeOmni model engine.

## 📊 Performance Metrics

The overlay exposes step-level observability, including drafter timing and vLLM speculative decoding acceptance metrics such as `drafter/spec_decode/mean_acceptance_length`. Recent results cover both NPU EAGLE3 co-training and GPU DFlash Bubble Time training. 

- **Qwen3-8B on vLLM-Ascend/NPU:** Using an EAGLE3 drafter for 100 steps, co-training increased mean acceptance length compared to a fixed-drafter setup. Relative to the baseline, this yielded approximately 20% faster rollout and 11% faster end-to-end training without accuracy regression.
- **Qwen3-4B GPU run:** In a DFlash run utilizing Bubble Time, the drafter training quota remained aligned with the synchronous path while shifting most drafter work off the main critical path. Excluding checkpoint-save steps, the end-to-end step time improved by about 6.7% compared with synchronous training, with similar acceptance length.

## 🛠️ Backend and Runtime Details

Specific configurations govern how different backends operate. EAGLE-1 and EAGLE-2 share vLLM's native draft method, with EAGLE-2 adding a dynamic-tree decoding policy. Domino is trained using the `DOMINO` speculative algorithm but served as a DFlash projector sub-mode. 

When serving a Domino checkpoint for rollout, `speculative_algorithm=DFLASH` must be used on an engine version supporting the Domino projector. Additionally, LK loss is not supported for Domino; `dflash_lk_loss_alpha` and `dspark_lk_loss_alpha` must be set to zero, as positive values are rejected during layout resolution. While P-EAGLE training is available, its vLLM parallel-drafting rollout runtime is not yet integrated into the overlay, requiring users to keep rollout drafter serving disabled and manage training or serving separately. Standalone smoke tests for GPU training are maintained under `tests/special_standalone/` and can be executed via scheduled or manual workflows.

#ReinforcementLearning #SpeculativeDecoding #vLLM #SGLang #MachineLearning

---

*Source: [verl-project/verl-SpeCo](https://github.com/verl-project/verl-SpeCo)*
