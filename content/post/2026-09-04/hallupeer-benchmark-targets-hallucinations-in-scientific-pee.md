---
title: "HalluPeer Benchmark Targets Hallucinations in Scientific Peer Reviews"
description: "The growing scale of academic peer review has prompted the use of large language models (LLMs) as review assistants, but these models can produce fluent yet unsupported claims that threaten review..."
date: 2026-09-04T12:10:15+05:30
tags: [AI, peerreview, hallucination, benchmark, LLM]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# HalluPeer Benchmark Targets Hallucinations in Scientific Peer Reviews

The growing scale of academic peer review has prompted the use of large language models (LLMs) as review assistants, but these models can produce fluent yet unsupported claims that threaten review reliability. To address this gap, researchers introduced **HalluPeer**, a benchmark specifically designed to detect hallucinations in scientific peer reviews.

## 🔍 Overview
- Existing hallucination benchmarks are not suited for peer review because verification requires grounding claims in long, technical papers.
- HalluPeer supplies aligned triples consisting of:
  1. Paper content
  2. Human‑written review
  3. Review with injected hallucinations
- Each triple is annotated for **detection**, **classification**, and **localization** of hallucinated statements.

## 🧩 How it works
- The pipeline first builds a **peer‑review‑specific hallucination taxonomy** and identifies the contexts in which reviews are written.
- Hallucinations are then **injected automatically** into human reviews, followed by automated filtering to ensure realistic errors.
- The resulting dataset supports training and evaluating models that can flag unsupported claims within reviews.

## 📊 Results
- Experiments covering **12 K papers** and **38 K reviews** show that currently available detectors struggle to distinguish hallucinations from legitimate critique.
- Evaluation on authentic reviews confirms that the hallucination patterns defined by HalluPeer do appear in real peer‑review texts, underscoring the need for source‑aware verification mechanisms.

## 🌐 Availability
- The HalluPeer project page and dataset are publicly accessible via the provided URL.

#AI #peerreview #hallucination #benchmark #LLM

---

*Source: [HalluPeer: A Taxonomy-driven Benchmark for Detecting Hallucinations in Scientific Peer Reviews](https://arxiv.org/abs/2609.03580v1)*
