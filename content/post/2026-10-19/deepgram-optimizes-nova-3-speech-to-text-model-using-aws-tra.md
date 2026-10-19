---
title: "Deepgram Optimizes Nova-3 Speech-to-Text Model Using AWS Trainium2"
slug: "deepgram-optimizes-nova-3-speech-to-text-model-using-aws-trainium2"
description: "Deepgram has collaborated with AWS to port its Nova-3 speech-to-text model to AWS Trainium2 to improve inference efficiency for offline batch workloads, such as medical transcription and..."
date: 2026-10-19T22:04:08+05:30
tags: [Deepgram, AWS, Trainium2, SpeechToText, InferenceOptimization]
categories: ["AI", "Machine Learning", "Cloud Computing", "Speech AI"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/12/ML-21906-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Deepgram Optimizes Nova-3 Speech-to-Text Model Using AWS Trainium2

Deepgram has collaborated with AWS to port its Nova-3 speech-to-text model to AWS Trainium2 to improve inference efficiency for offline batch workloads, such as medical transcription and contact-center analytics.

## ⚙️ Key details
Deepgram and the AWS Forward Deployed Engineering (FDE) team transitioned Nova-3 from standard PyTorch code to AWS Trainium2 using the following process:

* **Initial Porting:** Used TorchNeuron, the native PyTorch integration of the Neuron Compiler, supporting both eager execution and `torch.compile`.
* **Compilation:** The model was first run in eager mode to identify CPU fallbacks, then compiled with `torch.compile` as separate static-shape graphs for the encoder and decoder, resulting in no CPU fallbacks.
* **Accuracy Validation:** Numerical accuracy was verified via layer-level output consistency against CPU and end-to-end Word Error Rate (WER).
* **Kernel Optimization:** Replaced several layers with fused kernels from the public NKI Library (NKILib), including:
    * Fused QKV projections
    * Fused feed-forward network (FFN) layers
    * Depthwise 1D convolution
* **Infrastructure:** The final configuration runs eight model replicas on a single Amazon EC2 `trn2.3xlarge` instance.

## 💡 Why it matters
Serving efficiency determines the amount of audio Deepgram can process within a specific infrastructure budget. By utilizing AWS AI chips, Deepgram achieved the following:

* **Cost Efficiency:** Processed 11–70 percent more audio per dollar on offline, throughput-oriented batch workloads compared to previous compute options.
* **Scalability:** These gains allow Deepgram to scale more efficiently and provide models to customers at lower prices.
* **Customer Benefit:** These improvements extend to customers self-hosting Deepgram models in their own virtual private cloud (VPC) on Amazon SageMaker AI.

## 🚀 Availability
Deepgram models are available through:

* The Deepgram API
* Self-hosted environments, including Amazon SageMaker AI

#Deepgram #AWS #Trainium2 #SpeechToText #InferenceOptimization

---

*Source: [How Deepgram optimized voice AI at scale with AWS Trainium | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-deepgram-optimized-voice-ai-at-scale-with-aws-trainium/)*
