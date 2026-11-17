---
title: "Ax Ships a TypeScript-First, Multi-Language LLM Toolkit"
slug: "ax-ships-a-typescript-first-multi-language-llm-toolkit"
description: "Ax is a TypeScript-first development toolkit that ships as `@ax-llm/ax`. Its shared semantic core is also compiled into generated Python, Java, C++, Go, and Rust libraries."
date: 2026-11-17T18:10:30+05:30
tags: [AI, LLMDevelopment, TypeScript, AIAgents, OpenSource]
categories: ["AI", "Artificial Intelligence", "Software Development", "Machine Learning", "AI Agents"]
image: "https://avatars.githubusercontent.com/u/172865539?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Ax Ships a TypeScript-First, Multi-Language LLM Toolkit

Ax is a TypeScript-first development toolkit that ships as `@ax-llm/ax`. Its shared semantic core is also compiled into generated Python, Java, C++, Go, and Rust libraries.

## 🔍 Overview

Ax provides typed structured generation, deployment profiles, agents, flows, and optimizers. The TypeScript package is the source implementation and current published package.

## 🧩 How it works

Signatures for typed structured generation can be written using:

- A string DSL
- The fluent `f()` builder
- Any Standard Schema v1 validator, including Zod, Valibot, and ArkType

The deployment name selects wire behavior, while the model ID is resolved inside that deployment. Named deployment profiles cover native APIs, routers, hosted inference, configurable runtimes, audio, and realtime event streams.

For example:

```ts
const llm = ai({ name: "openai", apiKey: process.env.OPENAI_APIKEY });
const classify = ax('review:string -> sentiment:class "positive, negative, neutral"',);
await classify.forward(llm, { review: "This product is amazing!" })
```

The evidence describes this example as requiring no prompt engineering. The provider name can be switched from `"openai"` to `"anthropic"`, `"google-gemini"`, `"meta"`, `"together"`, `"fireworks"`, `"deepseek"`, or `"grok"`, among others.

## ⚙️ Key details

- **Agents:** runtime execution, context budgets, checkpoints, action-log replay, discovery, memory, skills, and delegation.
- **Flows:** typed program graphs supporting branches, loops, feedback, cache behavior, parallel execution, and `.returns(...)` projection.
- **Optimizers:** GEPA, few-shot bootstrapping, portable optimizer artifacts, and evaluation/apply flows.
- **Runtime path:** Ax is designed to stay in the same latency class as direct provider calls while adding typed outputs, validation, retries, tools, tracing, and memory. Its hot path renders the signature, calls the provider, parses the result, and returns a typed value.
- **Streaming:** Streaming is the default. Ax can parse fields as they arrive, run streaming assertions, fail early, cancel an in-flight stream, and start correction.

## 🚀 Availability

| Language | Package or distribution | Availability |
|---|---|---|
| TypeScript / JavaScript | `@ax-llm/ax` | Published on npm |
| Python | `axllm` | Published on PyPI |
| Java | `dev.axllm:ax` | Published on Maven Central |
| C++ | `axllm::axllm` | CMake `FetchContent` source build |
| Go | `github.com/ax-llm/ax/packages/go` | Installable with `go get` |
| Rust | `axllm` | Published on crates.io |

The same signatures, provider mappings, agents, flows, runtime contracts, and optimizers are compiled into verified generated Python, Java, C++, Go, and Rust libraries.

#AI #LLMDevelopment #TypeScript #AIAgents #OpenSource

---

*Source: [ax-llm/ax](https://github.com/ax-llm/ax)*
