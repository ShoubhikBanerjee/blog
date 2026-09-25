---
title: "Deploy Qwen3-TTS-12Hz-1.7B-Base for Voice Cloning on Amazon SageMaker JumpStart"
slug: "deploy-qwen3-tts-12hz-1-7b-base-for-voice-cloning-on-amazon-sagemaker-jumpstart"
description: "The Qwen3-TTS-12Hz-1.7B-Base text-to-speech model is now available for deployment to fully managed, real-time inference endpoints via Amazon SageMaker JumpStart."
date: 2026-09-25T22:04:20+05:30
tags: [AmazonSageMaker, Qwen3, TextToSpeech, VoiceCloning, MachineLearning]
categories: ["AI", "Machine Learning", "Generative AI", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-20646-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Deploy Qwen3-TTS-12Hz-1.7B-Base for Voice Cloning on Amazon SageMaker JumpStart

The Qwen3-TTS-12Hz-1.7B-Base text-to-speech model is now available for deployment to fully managed, real-time inference endpoints via Amazon SageMaker JumpStart.

## 🔍 Overview
Qwen3-TTS is a publicly available text-to-speech model family developed by the Qwen team at Alibaba Cloud. The model family supports streaming generation for low-latency, interactive scenarios and uses the Qwen3-TTS-Tokenizer-12Hz speech tokenizer. It covers 10 languages:
* Chinese
* English
* Japanese
* Korean
* German
* French
* Russian
* Portuguese
* Spanish
* Italian

## ⚙️ Key details
The Qwen3-TTS-12Hz-1.7B-Base variant specializes in voice cloning, which reproduces the vocal identity of a specific speaker without retraining. 

| Model Variant | Primary Function |
| :--- | :--- |
| Qwen3-TTS-12Hz-1.7B-Base | Performs voice cloning from a user-supplied reference audio clip and transcript |
| Qwen3-TTS-12Hz-1.7B-CustomVoice | Generates speech from a fixed set of predefined speakers |

Capabilities of the Base variant include:
* **Rapid Cloning:** Captures timbre, pitch, and cadence from only a few seconds of user audio.
* **Cross-lingual Cloning:** Captures a voice from a reference in one language and generates speech in another while preserving vocal identity.

## 🧩 How it works
Amazon SageMaker JumpStart provides the model artifacts and a pre-built serving container, removing the need to write a custom inference handler. 

1. **Request:** A client sends an HTTP request to the Amazon SageMaker AI endpoint containing target text, base64-encoded reference audio, and the reference audio's transcript.
2. **Routing:** Amazon SageMaker AI routes the request to a vLLM-Omni serving container running on a GPU instance.
3. **Generation:** The "talker stage" generates speech tokens from the text and reference voice, and the "code2wav stage" renders them into a waveform.
4. **Output:** The container generates 24 kHz audio output, returned to the client in the requested format (such as WAV).

## 🚀 Availability
Qwen3-TTS-12Hz-1.7B-Base is available in Amazon SageMaker JumpStart alongside Qwen3-TTS-12Hz-1.7B-CustomVoice and Qwen3-ASR-1.7B. Using Amazon SageMaker AI, users can manage infrastructure provisioning, health monitoring, and automatic scaling for the real-time endpoint.

#AmazonSageMaker #Qwen3 #TextToSpeech #VoiceCloning #MachineLearning

---

*Source: [Deploying real-time personalized speech with Qwen3-TTS on Amazon SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/deploying-real-time-personalized-speech-with-qwen3-tts-on-amazon-sagemaker-ai/)*
