---
title: "Testing NPU LLM Inference on Windows-on-ARM with Foundry Local"
description: "An attempt was made to run the same model on a Copilot+ Surface's 45-TOPS Hexagon NPU and its CPU to demonstrate speedup using Microsoft's Foundry Local."
date: 2026-09-06T22:07:38+05:30
tags: [NPU, WindowsonARM, LLM, FoundryLocal, Hexagon]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# Testing NPU LLM Inference on Windows-on-ARM with Foundry Local

An attempt was made to run the same model on a Copilot+ Surface's 45-TOPS Hexagon NPU and its CPU to demonstrate speedup using Microsoft's Foundry Local.

## 🔍 Overview
While the NPU is reachable and Foundry Local loads QNN models onto the Hexagon, the shipping NPU build fails. It produces errors on the first attention layer of every prompt, a layer type shared by every modern small model.

## ⚙️ Key details
During the process of moving a local automation brain to the NPU, an alternative speedup was discovered on the CPU by optimizing token usage:

* **Problem**: Feeding the model twice the tokens it needed.
* **Solution**: Swapping verbose JSON candidates for a terse line format.
* **Results**: 
    * Prompt length reduced by 63%
    * Prefill reduced by 65%
    * 2.7× fewer tokens
    * 2.9× faster performance
    * No accuracy trade-off

## 💡 Why it matters
Prefill-heavy automation workloads are specifically what an NPU is built to handle, as prefill on a CPU represents the whole cost and scales with the number of tokens sent.

#NPU #Windows-on-ARM #LLM #FoundryLocal #Hexagon

---

*Source: [All topics](https://www.jocheojeda.com/topics)*
