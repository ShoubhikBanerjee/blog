---
title: "Amazon Polly Generative Engine Upgrade Adds New Voices and Low‑Latency Streaming"
slug: "amazon-polly-generative-engine-upgrade-adds-new-voices-and-lowlatency-streaming"
description: "Amazon Polly’s Generative engine has been upgraded and is now generally available, bringing more natural, expressive speech and low‑latency streaming."
date: 2026-10-23T18:02:55+05:30
tags: [AmazonPolly, TextToSpeech, AWS, GenerativeAI]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Speech Synthesis", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/21/ML-22197-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Polly Generative Engine Upgrade Adds New Voices and Low‑Latency Streaming

Amazon Polly’s Generative engine has been upgraded and is now generally available, bringing more natural, expressive speech and low‑latency streaming.

## 🔍 Overview
- The upgrade delivers more expressive, more accurate speech output with low latency.
- It is a drop‑in upgrade for existing generative voices; voice names and API calls remain unchanged.

## ⚙️ Key Details
- More natural and accurate speech output.
- Low‑latency streaming for real‑time applications.
- 14 new voices across 9 locales.
- Hindi and Finnish generative voices are now generally available for the first time.
- No changes to code, voice names, or API calls are required.
- Same pay‑as‑you‑go pricing; no cost increase or new SKU.
- Speech Synthesis Markup Language (SSML) support for fine‑grained control.
- Fully managed AWS service reliability.

## 🚀 Availability
- Generally available in production.
- Existing applications continue to work unchanged.
- New applications use the same SynthesizeSpeech API to access the larger voice catalog.

## 🧩 How it Works
- Uses a standard Amazon Polly API call to build speech applications.
- The Bi‑Di Streaming API `StartSpeechSynthesisStream` streams text and receives audio simultaneously.
- Voices can reflect emotion and prosody based on text input without manual setup.
- Well‑suited for real‑time use cases like voice agents and bespoke characters in games.

## 💡 Why it Matters
- Improved voice quality and accuracy at the same price.
- Supports contact centers, LLM‑based agentic applications, media, e‑learning, accessibility, and other production use cases.
- Allows caching and replay of static prompts with no additional cost.
- Combines quality, performance, and cost efficiency for a wide range of production workloads.

| Locale | Availability |
|--------|--------------|
| Hindi  | General Availability |
| Finnish| General Availability |

#AmazonPolly #TextToSpeech #AWS #GenerativeAI

---

*Source: [Amazon Polly delivers a major upgrade to its Generative engine | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/amazon-polly-delivers-a-major-upgrade-to-its-generative-engine/)*
