---
title: "Ai2 Open-Sources AstaBrief 8B for Fast Scientific Reports"
slug: "ai2-open-sources-astabrief-8b-for-fast-scientific-reports"
description: "The Allen Institute for AI (Ai2) has introduced AstaBrief 8B, an open-weights language model designed to generate cited scientific reports from research questions and retrieved literature. The model..."
date: 2026-10-02T22:04:29+05:30
tags: [Ai2, AstaBrief, opensource, scientificAI, LLM, languageModels]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Scientific Research", "Natural Language Processing"]
image: "https://cdn-uploads.huggingface.co/production/uploads/638e39b249de7ae552d977b5/AdqLEBgtQnaDXKLdylC3l.png"
author: "Shoubhik Banerjee"
draft: false
---

# Ai2 Open-Sources AstaBrief 8B for Fast Scientific Reports

The Allen Institute for AI (Ai2) has introduced AstaBrief 8B, an open-weights language model designed to generate cited scientific reports from research questions and retrieved literature. The model is available as a fast generation option within Ai2's Asta platform and has been open-sourced alongside its training data.

## 🔍 Overview
AstaBrief 8B is a small, open model trained specifically for scientific report generation. It was developed to match the report quality of proprietary models while significantly reducing generation time and serving costs. The model turns a research question and retrieved literature excerpts into a cited report in a single pass, bypassing the more expensive multi-stage processes used by other systems.

## 🧩 How It Works
- Development began with tens of thousands of real research queries, citation-focused filtering, preference data, and a redesigned report-generation pipeline.
- The model is built on Qwen3-8B, with most effort focused on post-training data, evaluation, and report-generation scaffolding.
- It directly generates the final report in one pass given a user query and relevant retrieved snippets, bypassing snippet summarization and clustering stages.
- The training pipeline used real user queries from the system described in the paper “Synthesizing scientific literature with retrieval-augmented LMs” and ScholarQA.
- Training used supervised fine-tuning (SFT) and direct preference optimization (DPO), rather than reinforcement learning, to keep the process cheaper and easier to debug.

## ⚙️ Key Details
The following table summarizes the speed comparison between AstaBrief's Fast mode and the Thinking mode:

| Feature | Fast Mode (AstaBrief) | Thinking Mode |
| --- | --- | --- |
| Average report generation time (full pipeline) | 51.1 seconds | 178.5 seconds |

- The result is an approximate 3.5× reduction in report generation time compared to the proprietary models used in Thinking mode.
- The model produces reports in one pass rather than section by section.

## 🚀 Availability
- AstaBrief is available in Asta's "Generate a report" feature as Fast mode, alongside the Claude-powered Thinking mode.
- Alongside the model weights, Ai2 is releasing an example workflow that researchers can adapt to create reports from their own PDFs.
- Open weights allow institutions to run AstaBrief on their own infrastructure, which is necessary when research questions reveal sensitive or unpublished work.
- The model and training data are open-sourced so others can study, reproduce, and build on the approach.

## 💡 Why It Matters
- The model addresses specific demands of scientific work: answers must stay grounded in evidence, preserve what evidence supports, and allow verification.
- Users often bring substantial context and constraints to queries, such as comparing approaches across literature while accounting for method, population, or setting.
- Many users return to generated reports later, treating them as working research artifacts rather than one-off answers.
- The project serves as a test case for building open language models that can be adapted to the specific demands of scientific work.
- Through NSF OMAI, a U.S. national initiative led by Ai2 to build fully open AI infrastructure for scientific discovery, researchers are working with scientific communities to understand future needs.

![figure](https://cdn-uploads.huggingface.co/production/uploads/638e39b249de7ae552d977b5/nBB2ourke1eQYpjq2mGD5.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/638e39b249de7ae552d977b5/3dI-e2nnf6FDQw6ay-x9N.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/638e39b249de7ae552d977b5/Ek19fGImhqROo_qSUt5LV.png)

#Ai2 #AstaBrief #opensource #scientificAI #LLM #languageModels

---

*Source: [Open-sourcing AstaBrief, the fast report-generation model in Asta](https://huggingface.co/blog/allenai/astabrief)*
