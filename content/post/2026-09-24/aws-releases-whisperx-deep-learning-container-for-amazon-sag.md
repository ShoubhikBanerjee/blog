---
title: "AWS Releases WhisperX Deep Learning Container for Amazon SageMaker AI"
slug: "aws-releases-whisperx-deep-learning-container-for-amazon-sagemaker-ai"
description: "AWS has introduced a Deep Learning Container (DLC) for WhisperX, an open source project that extends OpenAI's Whisper for production workloads. This DLC allows users to deploy WhisperX to Amazon..."
date: 2026-09-24T22:03:57+05:30
tags: [AWS, WhisperX, AmazonSageMaker, ASR, SpeechToText]
categories: ["AI", "Machine Learning", "Speech Recognition", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/22/ML-21846-featured-image-1.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Releases WhisperX Deep Learning Container for Amazon SageMaker AI

AWS has introduced a Deep Learning Container (DLC) for WhisperX, an open source project that extends OpenAI's Whisper for production workloads. This DLC allows users to deploy WhisperX to Amazon SageMaker AI real-time or asynchronous endpoints without building a custom image.

## 🔍 Overview
Whisper is a popular open source automatic speech recognition (ASR) model family from OpenAI used to transcribe spoken audio into text across many languages. WhisperX builds on this foundation to provide faster transcription and structured, analyzable transcripts by adding:

* Per-word timestamps via wav2vec2 forced alignment
* Speaker labels via speaker diarization
* Batched inference

## ⚙️ Key details
The AWS WhisperX DLC is a maintained, GPU-ready image containing Whisper, alignment models, and diarization weights without requiring a Hugging Face token. It follows the standard Amazon SageMaker AI serving contract, serving on port 8080 with the following endpoints:

* `POST /invocations`: Used for inference
* `GET /ping`: Used for health checks

**Request and Response Specifications**

| Component | Detail |
| :--- | :--- |
| Request Format | `multipart/form-data` (audio as the `file` part) |
| Optional Fields | `language`, `diarize`, and `response_format` |
| Output Formats | `json`, `verbose_json`, `srt`, and `vtt` |

## 🚀 Availability
Users can deploy the DLC to Amazon SageMaker AI using two patterns:

* **Asynchronous endpoints**: Recommended for long audio where transcription, alignment, and diarization require more time; brokers input and output through Amazon S3.
* **Real-time endpoints**: Reserved for short, interactive clips that finish within the 60-second response cap; operates synchronously.

**Deployment Requirements**

* **Instances**: `ml.g4dn.xlarge` (for cost) or `ml.g5.2xlarge` (for headroom) with the required GPU AMI pin.
* **Permissions**: An AWS account and an Amazon SageMaker AI execution role with `create_model` and `create_endpoint` permissions. Asynchronous inference additionally requires read and write access to an S3 bucket whose name contains "sagemaker."
* **Resources**: GPU service quota for the chosen instance type and the WhisperX DLC image URI from Amazon ECR.

## 💡 Why it matters
WhisperX enables media and e-learning teams to generate accurate captions in SubRip Subtitle (SRT) and Web Video Text Tracks (VTT) formats for large content libraries. Because the same endpoint can output both JSON and subtitle formats, it can simultaneously feed analytics pipelines and video editors.

#AWS #WhisperX #AmazonSageMaker #ASR #SpeechToText

---

*Source: [Speaker-labeled transcription with WhisperX on SageMaker AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/speaker-labeled-transcription-with-whisperx-on-sagemaker-ai/)*
