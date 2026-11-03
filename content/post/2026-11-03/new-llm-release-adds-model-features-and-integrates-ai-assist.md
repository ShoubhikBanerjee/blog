---
title: "New LLM Release Adds Model Features and Integrates AI-Assisted Fixes"
slug: "new-llm-release-adds-model-features-and-integrates-ai-assisted-fixes"
description: "A new release of the LLM CLI tool and Python library has been issued, bringing together around two months of accumulated features and fixes."
date: 2026-11-03T06:04:06+05:30
tags: [LLM, Python, OpenSource, AI]
categories: ["AI", "Software Development", "Artificial Intelligence", "Open Source"]
author: "Shoubhik Banerjee"
draft: false
---

# New LLM Release Adds Model Features and Integrates AI-Assisted Fixes

A new release of the LLM CLI tool and Python library has been issued, bringing together around two months of accumulated features and fixes.

## ⚙️ Key features and model updates

* **New models**: Added support for `gpt-6.1-sol` and `gpt-6.1-terra`.
* **Default model change**: Switched the default model (for users who have not set their own) to `gpt-6-luna`, which is half the price of the previous default, `gpt-5.6-luna`.
* **New endpoint command**: Introduced the `llm openai endpoint add` command to make configuring additional OpenAI-compatible endpoints easier.
* **Multimodal embedding support**: Updated embeddings support to handle different content-types for binary content, accommodating models like Gemini Embedding 2 that embed text, audio, images, and video.

## 🤖 Handling AI-assisted contributions

This release includes fixes from 12 authors, almost all of which were AI-assisted. While many open source maintainers find floods of AI-assisted PRs problematic, the maintainer used Opus 5.5 or GPT-6 Astra to assist with PR triage to spot useful fixes, treating incoming PRs as bug reports with attached examples.

Contributors recognized for this release include 0d00ciallo0721, ac1982, Allen Flux, Bian Yuhan, Bishop Kammeraad, Chen Yufeiyang, Christopher Krah, Ethan Stoner, Jiachen Xie, Olamide Faniyan, Sharat Chandra Sai Boddu, and nosmile99.

#LLM #Python #OpenSource #AI

---

*Source: [Release: llm 0.37](https://simonwillison.net/2026/Nov/2/llm/)*
