---
title: "TwelveLabs Pegasus 1.5 Now Available on Amazon Bedrock"
slug: "twelvelabs-pegasus-1-5-now-available-on-amazon-bedrock"
description: "On Oct 9, 2026, the availability of TwelveLabs’ Pegasus 1.5 was announced on Amazon Bedrock. Pegasus 1.5 is a video language model designed to turn long-form video into structured, timestamped..."
date: 2026-10-20T18:01:41+05:30
tags: [TwelveLabs, AmazonBedrock, VideoAI, AWS, ComputerVision]
categories: ["AI", "Machine Learning", "Computer Vision", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-22008-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# TwelveLabs Pegasus 1.5 Now Available on Amazon Bedrock

On Oct 9, 2026, the availability of TwelveLabs’ Pegasus 1.5 was announced on Amazon Bedrock. Pegasus 1.5 is a video language model designed to turn long-form video into structured, timestamped metadata.

## 🔍 Overview
Pegasus 1.5 analyzes entire videos to find every segment matching user-defined criteria. Key capabilities include:

* **Video-to-text generation**: Creates detailed textual descriptions based on video content.
* **Granular visual comprehension**: Analyzes numerical content, on-screen text, and objects within video frames.
* **Temporal grounding**: Accurately identifies timestamps of specific events.
* **Multimodal understanding**: Combines textual, audio, and visual information for analysis.
* **Language Support**: Full support for English, with partial support for Arabic, Chinese, French, German, Italian, Japanese, Korean, Portuguese, Russian, Spanish, Thai, and Vietnamese.

## 🧩 How it works
Pegasus 1.5 introduces on-the-fly processing, video segmentation, and multimodal prompting with reference images. A segment definition can combine a visual reference with a text description. The model returns every matching segment as JSON, including the requested fields and start and end times.

Users can analyze videos without a pre-indexing step or ingestion pipeline. Videos are sent directly from Amazon S3, and results are returned in the response. Data remains within the AWS data boundary.

## ⚙️ Key details
Pegasus 1.5 can analyze videos up to two hours long in a single request, an increase from the one-hour limit in Pegasus 1.2.

| Input Method | Details | Use Case |
| :--- | :--- | :--- |
| Amazon S3 URI (s3Location) | Takes the bucketOwner account ID and object's uri | Long-form video |
| base64 string | Embeds video in request body (up to 25 MB) | Short clips |

## 🚀 Availability

* **Model ID**: twelvelabs.pegasus-1-5-v1:0
* **AWS Region**: US West (Oregon), us-west-2
* **Inference**: On-demand
* **APIs**: `InvokeModel` or `InvokeModelWithResponseStream` (for streamed responses)
* **Endpoint**: bedrock-runtime
* **Requirements**: Python 3.10 or later with the AWS SDK for Python (Boto3)

| Mode | Input | Output |
| :--- | :--- | :--- |
| general (default) | Text prompt in inputPrompt | Text answer in message, or JSON when supplying a schema |
| time_based_metadata | Segment definitions in responseFormat | Segments list with start/end times and requested fields |

#TwelveLabs #AmazonBedrock #VideoAI #AWS #ComputerVision

---

*Source: [Pegasus 1.5 from TwelveLabs is now available in Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/pegasus-1-5-from-twelvelabs-is-now-available-in-amazon-bedrock/)*
