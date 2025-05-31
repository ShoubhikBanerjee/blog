---
title: "🔥 Unlocking the Invisible: How LLMs Process Concurrent Requests Behind the Scenes"
description: "This deep dive explores the critical distinction between prefill and decode phases in LLM token generation—revealing how different batching strategies dramatically impact performance metrics."
date: 2025-05-31T11:50:03.993995+05:30
tags: [LLMPerformance, AIOptimization, ConcurrentProcessing, MachineLearningInfrastructure, GPUComputing, TokenGeneration, BatchProcessing, AIEngineering, ModelInference, LLMScaling]
categories: [AI, MachineLearning, LLM, Performance, Engineering]
image: "https://cdn-uploads.huggingface.co/production/uploads/65263bfb3177c2a794997821/OiBhSOlKQCI2LCAJkZWa1.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🔥 Unlocking the Invisible: How LLMs Process Concurrent Requests Behind the Scenes

**𝙎𝙪𝙢𝙢𝙖𝙧𝙮:** This deep dive explores the critical distinction between prefill and decode phases in LLM token generation—revealing how different batching strategies dramatically impact performance metrics. Learn why chunked prefill can boost throughput by 50% and how to balance the inherent tradeoffs between responsiveness and efficiency in production LLM systems.

## 🧠 The Hidden Duality of LLM Processing

Ever wonder why your LLM chat sometimes pauses mid-sentence when another user joins? Or why the first response takes so much longer than subsequent tokens? The answer lies in understanding a fundamental duality in how Large Language Models process text.

At TNG, we manage a substantial LLM infrastructure—24 H100 GPUs supporting 50 applications, handling 5,000+ inferences hourly and generating over ten million tokens daily. This scale has taught us that performance optimization requires understanding what happens 𝘣𝘦𝘩𝘪𝘯𝘥 the scenes when multiple users interact with these models simultaneously.

When an LLM generates text, it operates in two distinct phases:

- **𝗣𝗿𝗲𝗳𝗶𝗹𝗹 𝗣𝗵𝗮𝘀𝗲:** Processing the entire prompt to generate the first output token
- **𝗗𝗲𝗰𝗼𝗱𝗲 𝗣𝗵𝗮𝘀𝗲:** Generating each subsequent token one by one

📸 *See illustration comparing prefill (parallel processing) versus decode (sequential processing) phases*

This distinction is far more consequential than most developers realize. It shapes everything from user experience to resource utilization to overall system throughput.

## ⏱️ Metrics That Matter: Unpacking Latency and Throughput

The prefill/decode split directly impacts two critical performance metrics:

1. **𝙏𝙞𝙢𝙚 𝙩𝙤 𝙛𝙞𝙧𝙨𝙩 𝙩𝙤𝙠𝙚𝙣** (prefill latency) - The initial response time
2. **𝙏𝙞𝙢𝙚 𝙥𝙚𝙧 𝙤𝙪𝙩𝙥𝙪𝙩 𝙩𝙤𝙠𝙚𝙣** (decode latency) - The cadence of subsequent tokens

For interactive applications, users get frustrated if the first token takes more than 3 seconds to appear (they might think the system is broken) or if tokens generate slower than 3-10 tokens per second (slower than comfortable reading speed).

But there's always a tradeoff. Some non-interactive applications might prioritize total token throughput over per-request latency—like when batch-processing translations or generating summaries for an entire code repository.

🔍 **Resource Utilization Reality:** Prefill is compute-intensive (utilizing parallel processing across all input tokens), while decode is memory-bandwidth-limited (processing just one token at a time).

📸 *See graph showing how throughput increases with concurrency until GPU compute power saturates*

This fundamental difference creates fascinating dynamics when multiple requests compete for resources.

## 🚀 Batching Strategies: Static vs. Continuous

When multiple users hit an LLM service simultaneously, the inference engine must decide how to process these concurrent requests. Two primary approaches exist:

### 1. Static Batching: Simple But Inefficient

Static batching processes requests in rigid groups—waiting for the entire batch to complete before starting the next one.

📸 *See illustration showing how static batching processes batches in sequence*

This approach optimizes "time per output token" since decode phases run uninterrupted, but it creates terrible user experiences for anyone waiting for the next batch. Even worse, it wastes GPU resources since prefill (compute-intensive) and decode (memory-bound) operations can't run concurrently to maximize hardware utilization.

### 2. Continuous Batching: More Complex But Smarter

Most modern inference engines like vLLM implement continuous batching, where:

- Completed requests immediately free up batch slots
- New requests enter as soon as space becomes available
- Prefill and decode operations can run simultaneously

But this creates a new challenge: 𝘩𝘰𝘸 should prefill and decode operations share resources when running concurrently?

## 🧩 The Breakthrough: Chunked Prefill

The default "prefill-first" strategy prioritizes new requests, minimizing time to first token. However, this creates an unfortunate side effect: whenever a new request arrives, ongoing decode operations get interrupted—users experience this as sudden pauses in their text generation.

📸 *See illustration showing how prefill operations interrupt decode operations*

The elegant solution? **𝗖𝗵𝘂𝗻𝗸𝗲𝗱 𝗽𝗿𝗲𝗳𝗶𝗹𝗹** 🔥

Rather than processing an entire prompt in one massive operation, we break it into smaller chunks. This creates multiple benefits:

- Concurrent decode operations can progress between prefill chunks
- Users experience slowdowns rather than complete pauses
- 𝗧𝗼𝘁𝗮𝗹 𝘁𝗵𝗿𝗼𝘂𝗴𝗵𝗽𝘂𝘁 𝗶𝗻𝗰𝗿𝗲𝗮𝘀𝗲𝘀 𝗯𝘆 𝟱𝟬% by better balancing compute and memory resources

📸 *See illustration showing how chunked prefill allows more decode operations to proceed*

Chunk size becomes a tunable parameter to balance competing priorities:
- 𝘚𝘮𝘢𝘭𝘭𝘦𝘳 chunks → Better decode performance (smoother token generation)
- 𝘓𝘢𝘳𝘨𝘦𝘳 chunks → Faster time to first token

Default chunk sizes typically range from 512 to 8192 tokens, but the optimal value depends on your specific workload patterns.

## 🌟 Key Insights for LLM Engineers

This exploration of prefill and decode phases reveals several practical insights:

1. **Measure the right metrics** - Track both time-to-first-token and time-per-output-token to get a complete performance picture

2. **Consider your application type** - Interactive applications need to optimize for latency; batch applications should focus on throughput

3. **Enable chunked prefill** - This single optimization can boost throughput by 50% while improving user experience

4. **Tune chunk size thoughtfully** - Balance responsiveness against smoothness based on your users' needs

The journey to optimized LLM performance doesn't end here. In environments with unpredictable load patterns, finding the perfect chunk size remains challenging—which is why many practitioners stick with defaults that work well across diverse workloads.

What performance bottlenecks are you facing in your LLM deployments? Understanding the prefill/decode dynamic might just hold the key to solving them.

*Credits: Originally posted here: https://huggingface.co/blog/tngtech/llm-performance-prefill-decode-concurrent-requests*

#LLMPerformance #AIOptimization #ConcurrentProcessing #MachineLearningInfrastructure #GPUComputing #TokenGeneration #BatchProcessing #AIEngineering #ModelInference #LLMScaling