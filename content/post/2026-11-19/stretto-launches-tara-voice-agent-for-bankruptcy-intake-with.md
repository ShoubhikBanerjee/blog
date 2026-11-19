---
title: "Stretto launches Tara: voice agent for bankruptcy intake with Amazon Nova 2 Sonic"
slug: "stretto-launches-tara-voice-agent-for-bankruptcy-intake-with-amazon-nova-2-sonic"
description: "Stretto, together with CI&T and the AWS Generative AI Innovation Center, has launched Tara, an AI voice agent that conducts bankruptcy intake interviews over the phone."
date: 2026-11-19T22:12:49+05:30
tags: [AWS, VoiceAI, BankruptcyTech, GenerativeAI]
categories: ["AI", "Artificial Intelligence", "Voice Agents", "Cloud Computing", "Financial Technology"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21890-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Stretto launches Tara: voice agent for bankruptcy intake with Amazon Nova 2 Sonic

Stretto, together with CI&T and the AWS Generative AI Innovation Center, has launched Tara, an AI voice agent that conducts bankruptcy intake interviews over the phone.

## 🔍 Overview
- Tara is an AI voice agent that conducts bankruptcy intake interviews over the phone.
- It guides callers through a structured conversation, collects personal and financial details, and adapts tone to the caller’s emotional state.
- After the call, Stretto’s system applies attorney‑defined rules to label the lead as qualified, disqualified, or needs‑more‑information.

## 🧩 How it works
- Caller dials the Bankruptcy.com number; Tara picks up, introduces herself, and begins the interview.
- The call is received through Twilio, which opens a WebSocket connection into AWS.
- Audio streams through AWS WAF and an Application Load Balancer to a voice bridge running on Amazon ECS on AWS Fargate.
- The voice bridge streams audio to Amazon Nova 2 Sonic via Amazon Bedrock; the model processes speech input and generates speech output in a single step.
- At the end of the conversation, Stretto’s backend sorts the lead against attorney‑defined rules.

## ⚙️ Technical details
- **Model**: Amazon Nova 2 Sonic, a speech‑to‑speech foundation model available through Amazon Bedrock.
- **Architecture**: Single model reduces latency compared with chaining speech‑to‑text, language model, and text‑to‑speech components.
- **Latency**: Tested previous solution had time‑to‑first‑audio latency > 500 ms; Nova 2 Sonic is designed for low latency and handles interruptions without breaking the session.
- **Security**: Access governed by AWS IAM; traffic stays on the AWS network via VPC endpoints (AWS PrivateLink); AWS WAF protects the endpoint.
- **Region availability**: Amazon Nova 2 Sonic and Amazon Bedrock are not available in all AWS Regions.

| Component | Role |
|-----------|------|
| Amazon Nova 2 Sonic | Speech‑to‑speech model that processes input and generates output in one step |
| Amazon Bedrock | Managed service that provides access to Nova 2 Sonic and Claude; handles security, IAM, VPC endpoints |
| Twilio | Receives inbound calls and opens WebSocket connection to AWS |
| AWS WAF & Application Load Balancer | Protects and routes traffic to the voice bridge |
| Amazon ECS on AWS Fargate | Hosts the voice bridge that streams audio to Nova 2 Sonic |
| IAM & VPC Endpoints (PrivateLink) | Enforce access control and keep traffic on the AWS network |

## 📉 Results
- Stretto reports a 95 % reduction in per‑minute voice cost compared with its previous solution, based on Amazon Bedrock on‑demand pricing in us‑east‑1 as of April 2026.

## 🚀 Why it matters
- The solution replaces a costly human intake team with an automated voice agent that can collect detailed financial data, which attorneys value more highly than minimal web‑form leads.
- Low latency, natural conversation flow, and emotional awareness improve caller experience for sensitive bankruptcy discussions.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21890-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21890-3.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21890-4.jpg)

#AWS #VoiceAI #BankruptcyTech #GenerativeAI

---

*Source: [How Stretto built an AI voice agent with Amazon Nova 2 Sonic | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-stretto-built-an-ai-voice-agent-with-amazon-nova-2-sonic/)*
