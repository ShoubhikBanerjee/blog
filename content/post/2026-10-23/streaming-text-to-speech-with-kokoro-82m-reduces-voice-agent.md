---
title: "Streaming Text-to-Speech with Kokoro-82M Reduces Voice Agent Latency"
slug: "streaming-text-to-speech-with-kokoro-82m-reduces-voice-agent-latency"
description: "A customer asks an AI voice agent a question and waits. The agent already has an answer and is midway through generating a long, multi‑paragraph response, but the customer hears nothing for five..."
date: 2026-10-23T22:04:00+05:30
tags: [AI, TextToSpeech, SageMaker, Streaming]
categories: ["AI", "Machine Learning", "AI Agents", "Speech Synthesis", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21706-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Streaming Text-to-Speech with Kokoro-82M Reduces Voice Agent Latency

A customer asks an AI voice agent a question and waits. The agent already has an answer and is midway through generating a long, multi‑paragraph response, but the customer hears nothing for five seconds. By the time an answer arrives, the customer is frustrated, confused, and no longer paying attention. Text‑to‑speech integrations create exactly that gap: a one‑sentence response might generate in 600 ms, but the full response takes five seconds, and the integration waits for all of it before synthesis starts.

## 🔍 Overview
- Problem: Silent gap between language generation and audio playback causes user frustration.
- Solution: Stream each sentence to a hosted **Kokoro‑82M** text‑to‑speech (TTS) model on Amazon SageMaker AI as soon as the agent produces it, so synthesis begins on sentence one instead of after the full response.
- The approach also covers the transport needed to get audio back to a browser and the practical cost considerations.

## 🧩 How it works
1. The AI agent generates text sentence by sentence.
2. Each sentence is sent immediately to a SageMaker real‑time endpoint hosting the Kokoro‑82M model.
3. The TTS model synthesizes the audio for that sentence while the agent continues generating subsequent sentences.
4. Audio streams to the client browser as soon as it is ready, eliminating the initial silent gap.

## ⚙️ Key details
- **Model**: Kokoro‑82M has 82 million parameters, small enough to run cheaply on a single mid‑tier GPU instance.
- **Endpoint**: Runs in a custom container on a SageMaker AI real‑time endpoint (ml.g5.xlarge GPU instance).
- **Container routes**:
  | Route | Description |
  |------|-------------|
  | `POST /invocations` | Streams a response for one complete input |
  | `WS /invocations-bidirectional-stream` | Keeps one connection open across many messages in both directions |
- **Bidirectional transport** uses binary WebSocket frames; a typical Starlette `receive_text()` handler fails because the message lacks a `text` key, raising `KeyError('text')`. A generic exception handler that forwards `str(e)` masks the framing issue as a missing field error.
- **Infrastructure requirements**:
  - AWS account with permissions to create SageMaker AI endpoints and invoke Bedrock models.
  - IAM actions: `sagemaker:CreateEndpoint`, `sagemaker:CreateEndpointConfig`, `sagemaker:CreateModel`, `sagemaker:InvokeEndpointWithBidirectionalStream`, `bedrock:InvokeModelWithResponseStream`.
  - Amazon ECR repository for the container image.
  - AWS CDK v2 (installed and bootstrapped), Python 3.12+, `uv`, Docker, and Boto3 supporting `invoke_endpoint_with_bidirectional_stream`.
  - The sample container pins an older PyTorch version with advisory **PYSEC‑2026‑2286**; review and upgrade before any non‑proof‑of‑value use.

## 🚀 Deployment steps
1. **speech‑infra deploy** – provisions the Kokoro‑82M endpoint:
   - Creates foundation and model‑cache stacks that set up IAM roles and sync model weights to Amazon S3.
   - Builds the container image, creates the SageMaker AI model, endpoint configuration, and the endpoint.
2. **agent‑infra deploy** – provisions the Amazon Bedrock AgentCore runtime that hosts the Strands agent and calls the newly created endpoint (deploy the endpoint first).
3. Ensure the SageMaker AI real‑time endpoint’s Docker image declares `com.amazonaws.sagemaker.capabilities.bidirectional-streaming=true`.
4. Use the provided CLI tools (wrapping AWS CDK stacks) to apply the infrastructure.

## 💡 Why it matters
- **Latency**: Audio playback can start after the first sentence is generated (≈600 ms) instead of waiting for the full response (≈5 s).
- **Cost**: Kokoro‑82M runs on a single ml.g5.xlarge GPU, keeping inference cost low for a voice agent handling real traffic.
- **User experience**: Removes the silent gap, keeping customers engaged and attentive.
- **Reusable transport**: The blog also explains both HTTP and bidirectional WebSocket transports and their practical cost in a browser setting.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21706-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ml-21706-edit-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21706-3.png)

#AI #TextToSpeech #SageMaker #Streaming

---

*Source: [Stream low-latency speech from AI agents using Kokoro TTS on Amazon SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/stream-low-latency-speech-from-ai-agents-using-kokoro-tts-on-amazon-sagemaker-ai/)*
