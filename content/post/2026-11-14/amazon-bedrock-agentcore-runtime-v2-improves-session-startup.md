---
title: "Amazon Bedrock AgentCore Runtime V2 Improves Session Startup and Billing"
slug: "amazon-bedrock-agentcore-runtime-v2-improves-session-startup-and-billing"
description: "Amazon Bedrock AgentCore runtime provides a fully managed, serverless environment where each session runs in its own isolated microVM, scales to zero when idle, and you only pay for the resources..."
date: 2026-11-14T06:11:11+05:30
tags: [AmazonBedrock, AgentCore, Serverless]
categories: ["AI", "Cloud Computing", "AI Agents", "Serverless Architecture"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/13/ML-22099-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore Runtime V2 Improves Session Startup and Billing

Amazon Bedrock AgentCore runtime provides a fully managed, serverless environment where each session runs in its own isolated microVM, scales to zero when idle, and you only pay for the resources your sessions consume.

## 🔍 Overview
- AgentCore runtime runs each session in a new microVM.
- The platform scales to zero when there’s no work and charges only for consumed resources.

## 🧩 How V2 Starts a Session
- Setting `platformVersion` to **"V2"** changes how sessions start.
- When you create or update a runtime, AgentCore starts your container in a fresh microVM and waits for the first healthy ping (`GET /ping`) within 120 seconds.
- It then clears the operating system’s file cache, freezes the microVM, and stores its memory and disk as a snapshot. Building this snapshot takes a few minutes during create or update.

## ⚙️ Session Execution
- On a new session, AgentCore restores the snapshot into a new microVM.
- Your process resumes exactly where it was frozen, with imports, objects, and clients in place.
- Files from the image are loaded lazily; each block is fetched the first time a session reads it and then cached closer to the host.
- Anything held at snapshot time, including RAM‑backed file systems such as `/dev/shm`, is available at memory speed from the first access.
- The file cache is cleared before the freeze, so reads during init do not speed up restored sessions.
- A CLI that runs as a separate process and exits, or a browser binary, is read during init and then fetched again from the image for each restored session.

## 🚀 Performance Benefits
- Session start times are faster and more consistent.
- V2 reclaims memory that sessions don’t use, so billing tracks what the agent actually uses.
- For most agents, switching to V2 is all it takes.

## 📏 Measuring Startup Time
- AgentCore publishes CloudWatch metrics in the `AWS/Bedrock-AgentCore` namespace.
- **Latency**: time to first byte.
- **OverheadLatency**: platform overhead such as microVM start and snapshot restore on a new session.

## 🛠️ Tips for Agents
- With the AgentCore Python SDK, *init* means everything before `app.run()`.
- If you run your own HTTP server (Node.js or another language), report healthy only after your initialization finishes.
- Build hooks are now supported to keep work off the first request.


#AmazonBedrock #AgentCore #Serverless

---

*Source: [Architecture patterns for fast session startup on Amazon Bedrock AgentCore runtime | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/architecture-patterns-for-fast-session-startup-on-amazon-bedrock-agentcore-runtime/)*
