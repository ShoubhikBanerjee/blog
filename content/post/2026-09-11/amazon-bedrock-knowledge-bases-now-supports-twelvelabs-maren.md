---
title: "Amazon Bedrock Knowledge Bases Now Supports TwelveLabs Marengo Embed 3.0"
slug: "amazon-bedrock-knowledge-bases-now-supports-twelvelabs-marengo-embed-3-0"
description: "Amazon Bedrock Knowledge Bases has announced the general availability of TwelveLabs Marengo Embed 3.0 as an embedding model. This integration allows for a fully managed Retrieval Augmented Generation..."
date: 2026-09-11T12:15:38+05:30
tags: [AmazonBedrock, TwelveLabs, MultimodalAI, RAG, AWS]
categories: ["AI", "Machine Learning", "Computer Vision", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/10/ML-21835-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Knowledge Bases Now Supports TwelveLabs Marengo Embed 3.0

Amazon Bedrock Knowledge Bases has announced the general availability of TwelveLabs Marengo Embed 3.0 as an embedding model. This integration allows for a fully managed Retrieval Augmented Generation (RAG) service that handles storage, ingestion, embedding, re-ranking, and retrieval.

## 🔍 Overview
Marengo Embed 3.0 is a multimodal embedding model that encodes video, audio, images, and text into a compact 512-dimensional vector space. Amazon Bedrock Knowledge Bases supports the following file types and connectors:

*   **Supported files:** Video (MP4, MOV), images (JPEG, PNG), and audio tracks.
*   **Native connectors:** Amazon Simple Storage Service (Amazon S3), SharePoint, and Confluence.

## 🧩 How it works
Managed Knowledge Bases (Managed MKB) automatically generates multimodal embeddings by capturing audio, speech, textual, and visual signals into a unified vector representation. The workflow is as follows:

1.  Upload video files to an Amazon S3 bucket.
2.  In the Amazon Bedrock console, navigate to Knowledge Bases and choose Create Managed KB.
3.  Select TwelveLabs/Marengo Embed 3.0.
4.  Configure the S3 URI of the bucket containing video assets in the Data source pane.

Managed MKB handles segmentation, frame sampling, and transcription internally, meaning no pre-processing is required. The system extracts frames, transcribes audio, generates embeddings for each segment, and writes vectors to the index. Users can configure audio and video segmentation durations under Advanced configurations, with a default of 4 seconds for both modalities.

## ⚙️ Key details
Applications can query the knowledge base using the Boto SDK Retrieve API or as an Amazon Bedrock Gateway target in Amazon Bedrock AgentCore. The Amazon Bedrock Retrieve API can power downstream applications, returning ranked results with metadata including:

*   Chunk start time
*   Chunk end time
*   Source URI
*   Embedding type

## 💡 Why it matters
This development enables various use cases across different industries:

| Industry | Application |
| :--- | :--- |
| Sports analytics | Finding specific plays, formations, or player actions across seasons of footage |
| Media and entertainment | Media asset management and semantic search through streaming service content or media archives |
| Security and safety | Searching security camera footage for specific activities or incidents |
| Education and training | Locating lecture segments by concept rather than only keywords |
| Retail | Searching product demo videos for feature demonstrations |

## 🚀 Availability
Managed Knowledge Bases for Amazon Bedrock with Marengo Embed 3.0 is available in the following AWS Regions:

*   US East (N. Virginia) (us-east-1)
*   US West (N. California) (us-west-1)

#AmazonBedrock #TwelveLabs #MultimodalAI #RAG #AWS

---

*Source: [Video and image search in Amazon Bedrock Knowledge Base using Marengo 3.0 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/video-and-image-search-in-amazon-bedrock-knowledge-base-using-marengo-3-0/)*
