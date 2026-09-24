---
title: "Agentic AI Solution for Natural Language Video Querying on AWS"
slug: "agentic-ai-solution-for-natural-language-video-querying-on-aws"
description: "A new AI agent implementation allows users to upload videos and ask natural language questions about their content to receive answers within seconds."
date: 2026-09-24T18:02:55+05:30
tags: [AWS, AIAgents, AmazonBedrock, VideoIntelligence]
categories: ["AI", "AI Agents", "Computer Vision", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/17/ML-21279-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Agentic AI Solution for Natural Language Video Querying on AWS

A new AI agent implementation allows users to upload videos and ask natural language questions about their content to receive answers within seconds.

## 🔍 Overview
The solution uses an agentic architecture to make video content instantly queryable through natural conversation. Built with the Strands Agents SDK, the system orchestrates multiple AWS AI services to synthesize coherent answers without requiring separate processing pipelines for each use case.

## 🧩 How it works
The agent orchestrator determines at runtime which services to invoke based on the user's request. The model handles the routing rather than application code.

| Service | Function |
| :--- | :--- |
| Amazon Bedrock | Powers the agent using LLMs that support tool use, such as Claude Sonnet |
| Amazon Rekognition | Provides visual analysis, including detecting faces, objects, scenes, and activities |
| Amazon Transcribe | Converts spoken audio to text with speaker diarization and support for over 100 languages |
| Amazon Bedrock Data Automation (BDA) | Alternative path for video summary, chapter detection, and full transcription in one API call |
| Amazon S3 | Stores uploaded videos and cached analysis outputs with per-user prefixes |

## ⚙️ Key details
* **Performance:** Initial analysis of new videos takes 5–10 minutes depending on length and services. Responses for previously analyzed content return in under a second.
* **Memory:** The agent maintains conversation history, allowing follow-up questions to build on prior analysis using cached results.
* **Technical Requirements:** 
    * Python 3.11 or later with `strands-agents` and `strands-agents-tools` installed.
    * AWS account with access to Amazon S3 and Amazon Bedrock (Claude Sonnet enabled).
    * AWS CLI configured with necessary IAM permissions.

## 💡 Why it matters
A major media and entertainment company adopted this approach during an AWS Professional Services engagement. Based on the customer's internal before-and-after comparison of analyst hours per recording (not independently verified), the company saw a reduction in manual review time of approximately 80 percent across a backlog of more than 200 multi-hour recordings.

## 🚀 Availability
The complete implementation is available in a companion GitHub repository.

#AWS #AIAgents #AmazonBedrock #VideoIntelligence

---

*Source: [Agentic conversational video intelligence built on AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/agentic-conversational-video-intelligence-built-on-aws/)*
