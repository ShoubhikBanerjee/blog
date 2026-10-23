---
title: "Deploying Kokoro-82M TTS on Amazon SageMaker AI with Data-Driven Auto Scaling"
slug: "deploying-kokoro-82m-tts-on-amazon-sagemaker-ai-with-data-driven-auto-scaling"
description: "This project demonstrates the deployment of Kokoro-82M, an 82-million-parameter text-to-speech (TTS) model, as a custom container on an Amazon SageMaker AI real-time endpoint using AWS Cloud..."
date: 2026-10-23T12:04:45+05:30
tags: [AmazonSageMaker, TTS, Kokoro82M, AWSCDK, AutoScaling]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "Text to Speech"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21705-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Deploying Kokoro-82M TTS on Amazon SageMaker AI with Data-Driven Auto Scaling

This project demonstrates the deployment of Kokoro-82M, an 82-million-parameter text-to-speech (TTS) model, as a custom container on an Amazon SageMaker AI real-time endpoint using AWS Cloud Development Kit (AWS CDK) stacks.

## 🧩 How it works

Kokoro-82M is a non-autoregressive StyleTTS2 derivative with an ISTFTNet decoder. Unlike models based on autoregressive next-token prediction or iterative denoising, it produces a full utterance from one duration-aligned pass, meaning there is no generation loop to instrument with a per-token metric.

To avoid the risks of guesswork in auto scaling—which can lead to idle GPU instances or latency breaching service level objectives (SLOs) during traffic spikes—this deployment replaces guesses with two specific measurements:

| Metric | Description |
| :--- | :--- |
| Q_max | The highest concurrency one instance sustains before breaching the SLO |
| T_total | How long a scale-out takes end to end |

From these two numbers, the scale-out threshold, scale-in threshold, and both cooldowns are derived by arithmetic.

## ⚙️ Key details

* **Scaling Metric**: The policy uses `ConcurrentRequestsPerModel`, a native Amazon SageMaker AI metric. This removes failures associated with custom metric configurations that may not actually publish data.
* **Measurement Handling**: `ConcurrentRequestsPerModel` publishes a Maximum statistic over a 10-second window, which differs from the mean in-flight count measured by benchmarking clients. The tooling records the ratio between these two quantities at every rung of the concurrency ladder to convert client-measured thresholds into Amazon CloudWatch units.
* **Observation**: In the Kokoro-82M run, the measured ratio was exactly 1.0 at every rung, resulting in a direct match between client-measured and Amazon CloudWatch-reported thresholds.

## 💡 Why it matters

Most public guidance for Amazon SageMaker AI auto scaling focuses on short synchronous request/response calls or large language model (LLM) serving. TTS synthesis does not fit these patterns because a single request holds a connection open for several seconds without a token-generation loop. In these scenarios, instance overload is determined by how many requests are queued and executing simultaneously.

#AmazonSageMaker #TTS #Kokoro82M #AWSCDK #AutoScaling

---

*Source: [Stop guessing auto scaling targets for TTS on Amazon SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/stop-guessing-auto-scaling-targets-for-tts-on-amazon-sagemaker-ai/)*
