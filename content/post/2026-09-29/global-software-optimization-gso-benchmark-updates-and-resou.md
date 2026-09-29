---
title: "Global Software Optimization (GSO) Benchmark Updates and Resource Releases"
slug: "global-software-optimization-gso-benchmark-updates-and-resource-releases"
description: "The Global Software Optimization (GSO) benchmark, designed to evaluate the capabilities of language models in developing high-performance software, has released several new integrations, datasets,..."
date: 2026-09-29T18:01:58+05:30
tags: [GSO, LLM, SoftwareOptimization, Benchmarking]
categories: ["AI", "Machine Learning", "Software Engineering", "AI Evaluation"]
image: "https://avatars.githubusercontent.com/u/210908921?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Global Software Optimization (GSO) Benchmark Updates and Resource Releases

The Global Software Optimization (GSO) benchmark, designed to evaluate the capabilities of language models in developing high-performance software, has released several new integrations, datasets, and tools.

## 🔍 Overview
GSO evaluates language models on software performance optimization using more than 100 challenging tasks across 10 codebases. These codebases span diverse domains and programming languages.

## 🧩 How it works
Each task in the benchmark consists of the following components:
- A codebase containing a specific performance bottleneck
- A performance test serving as a precise specification
- A requirement for agents to generate a patch that improves runtime efficiency
- A success metric measured against expert developer optimizations

## ⚙️ Key details
GSO includes a collection framework for creating new tasks through a four-step pipeline:

| Step | Process | Description |
| :--- | :--- | :--- |
| 1 | Commit Extraction & Filtering | Extract performance-related commits using LLMs |
| 2 | API Identification | Identify affected high-level APIs for each commit |
| 3 | Performance Test Generation | Generate tests for API-Commit pairs |
| 4 | Test Execution | Execute tests to identify performance improvements |

## 🚀 Availability
New resources and integrations have been released:
- **Dataset**: Now available on HuggingFace at [gso-bench/gso](https://huggingface.co/datasets/gso-bench/gso).
- **Docker Images**: Prebuilt images for GSO tasks are available on [Docker Hub](https://hub.docker.com/repository/docker/slimshetty/gso/general).
- **Framework Integrations**: Scaffolds for frameworks like Harbor are available at [gso-bench/scaffolds](https://github.com/gso-bench/scaffolds).
- **Evaluation Logs**: Transcripts with [Docent](https://transluce.org/docent) support are available at [gso-bench/gso-experiments](https://github.com/gso-bench/gso-experiments).
- **HackDetector**: A tool to catch model reward hacking is detailed on the [GSO Blog](https://gso-blog.notion.site/gso-hackdetector).
- **License**: Released under the MIT license.
- **Main Site**: [gso-bench.github.io](https://gso-bench.github.io/)

#GSO #LLM #SoftwareOptimization #Benchmarking

---

*Source: [gso-bench/gso](https://github.com/gso-bench/gso)*
