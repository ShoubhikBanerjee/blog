---
title: "Forge Neo Remi introduces a Gradio-free, Anima-first Stable Diffusion workbench"
slug: "forge-neo-remi-introduces-a-gradio-free-anima-first-stable-diffusion-workbench"
description: "Forge Neo Remi is a new downstream distribution of Forge Neo, built as an Anima-first Stable Diffusion WebUI workbench. It replaces the traditional Gradio interface with a fast, Gradio-free React 19..."
date: 2026-11-28T22:07:57+05:30
tags: [StableDiffusion, AIImageGeneration, ForgeNeo, ReactJS, OpenSourceAI]
categories: ["AI", "Generative AI", "Developer Tools", "Software Architecture", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/98527099?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Forge Neo Remi introduces a Gradio-free, Anima-first Stable Diffusion workbench

Forge Neo Remi is a new downstream distribution of Forge Neo, built as an Anima-first Stable Diffusion WebUI workbench. It replaces the traditional Gradio interface with a fast, Gradio-free React 19 single-page application (SPA) powered by FastAPI, aiming to provide a zero-node, conflict-safe environment for studio-grade AI image creation on consumer hardware.

## 🔍 Overview
Remi is an independent downstream branch, not an official release of Forge Neo or any bundled model family. It pairs Forge Neo's runtime and modern DiT model stack with a reimagined web workbench. The system is designed to be Anima-first and multi-DiT capable, utilizing a persistent job queue managed via SQLite and exposed through a REST API.

## 🧩 How it works
The core of Remi is its shift away from node-based graph wiring toward integrated, conflict-safe workflows. 
* **Remi.UI Architecture:** The interface uses declarative, capability-driven controls defined in `remi.ui v1`. It features refined light and dark themes, phone layouts, full keyboard control, and reload-free language switching between English and Simplified Chinese.
* **Model Capability Logic:** The `ModelCapability` system automatically hides panels that do not apply to the loaded model family, providing clear reasons for exclusion. It displays quantization and capability badges (including Diffusers, GGUF, INT8-ConvRot, FP8, NVFP4, Turbo, RGBA, and Control) and offers actionable pre-submit workflow advice with one-click fixes.
* **Workflows:** Users can execute Linear Multi-Stage Pipelines (Prompt Upsample → Generate → Refine → Finish) with content-addressed upstream stage caching. This allows downstream parameter changes to reuse earlier outputs without manual node wiring. Cross-model "Recipes" allow saving and applying conflict-checked parameter subsets.

## ⚙️ Key details
Remi is engineered to run on 8–24 GB consumer GPUs and Apple Silicon unified memory. 

| Component | Description |
| :--- | :--- |
| **UI Framework** | React 19 SPA with FastAPI backend; no Gradio dependency. |
| **Inference Workers** | Supports in-process execution by default, or isolated inference via `WorkerProtocol` flags (`--worker-process`, `--worker-gpus`, `--worker-mlx`). |
| **Model Support** | Full support for 2B, 2.9B, and 3.8B models (28/40/52-block layouts) with native Qwen3.5 semantic connector. |
| **Apple Silicon** | Includes MPS dequantized-weight caching, unified-memory awareness, and optional MLX/mflux sidecar via `--worker-mlx`. |

*Note: While worker process flags are available, the queue currently does not dispatch to isolated workers and still runs every job in-process.*

## 🎨 Features and Tools
* **Asset Management:** Gallery Boards for organization, Asset Lineage for tracing parent/child outputs, and a pixel slider for comparing two runs via structured Parameter Diff.
* **Transparency:** Lightbox allows switching between four backdrops to inspect alpha transparency.
* **Reference Integration:** Send-to-Reference-Image function with model-aware slot badges (`<image_1>`, `ref_image_0`, `ref_0`).
* **Prompting:** Multimodal/Local Prompt Upsampler (PUP) and a JSON Builder for composing structured layouts in MOSS-Image, FLUX.3 Layout, and Bria Fibo 2.0 VGL 2.0.
* **Control & LoRA:** Supports cross-depth LoRA, ControlNet-LLLite remapping, Control-LoRA, VACE, and native samplers/guidance. "Anima Remi Presets" provide safe baselines with mutually exclusive stacks locked before sampling.
* **Testing & Diagnostics:** Includes versioned `remi.ui` APIs, per-extension diagnostics (load times, errors), and a `remi.testing` contract verifier. Frequently used extensions are ported to `remi.ui` and guarded by automated Python, Vitest, and Playwright + axe gates.

## 🚀 Availability
Remi favors integrated workflows over compatibility with every legacy extension. Third-party extensions built for the old Gradio UI must be ported to `remi.ui` to function within this environment.

#StableDiffusion #AIImageGeneration #ForgeNeo #ReactJS #OpenSourceAI

---

*Source: [beautifulrem/forge-neo-remi](https://github.com/beautifulrem/forge-neo-remi)*
