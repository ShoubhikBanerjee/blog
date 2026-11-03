---
title: "Amazon Bedrock Knowledge Bases adds Crawl4AI‑driven scheduled web ingestion"
slug: "amazon-bedrock-knowledge-bases-adds-crawl4aidriven-scheduled-web-ingestion"
description: "Amazon Bedrock Knowledge Bases is the fully managed RAG capability of Amazon Bedrock."
date: 2026-11-03T22:02:32+05:30
tags: [AmazonBedrock, RAG, Crawl4AI, ManagedKnowledgeBase, AWS]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/27/ML-21438-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Knowledge Bases adds Crawl4AI‑driven scheduled web ingestion

Amazon Bedrock Knowledge Bases is the fully managed RAG capability of Amazon Bedrock.

For that class of source material, you can extend the reach of your knowledge base with a preparation step built with Crawl4AI, an open source Python crawler.

## 🔍 Overview
- With Amazon Bedrock Managed Knowledge Base, you connect your data sources, and Amazon Bedrock manages ingestion, storage, indexing, and retrieval for you.
- You don’t provision or scale a vector store, and embedding and reranking use service-managed models by default.

## 🧩 How it works
- Amazon EventBridge starts the Amazon Elastic Container Service (Amazon ECS) task on AWS Fargate on the configured schedule.
- The task reads its non‑secret pipeline configuration from AWS Systems Manager Parameter Store at startup.
- The task crawls the public websites you configured and prepares Markdown with a metadata sidecar for each page.
- The crawl step performs bounded crawling and writes a Markdown file with a metadata sidecar for each successfully prepared page.
- Crawl4AI’s role ends once it has prepared the source documents and metadata sidecars.
- The task uploads the prepared files to the Amazon S3 bucket that backs the knowledge base data source.
- The task starts an Amazon Bedrock Knowledge Bases ingestion job.
- Amazon Bedrock Knowledge Bases reads the new and changed objects, parses them, and applies the chunking strategy you selected.
- It creates embeddings and indexes them in the knowledge base’s vector store, which Amazon Bedrock manages for a managed knowledge base.
- From ingestion onward, Amazon Bedrock Knowledge Bases handles parsing, chunking, embedding, indexing, and retrieval.
- Your generative AI application queries the knowledge base for relevant chunks or for a generated response with citations.

## ⚙️ Key details
- Scheduled syncs keep your knowledge base current as pages change, and the connector can wait for content that loads with JavaScript.
- It respects robots.txt, and after the first full crawl, each sync captures only added, updated, and deleted content.
- Because managed and customer‑managed knowledge bases both support Amazon S3 data sources, the Crawl4AI path works with either type.
- This is batch ingestion of known web properties, not real‑time web access at inference time such as Web Grounding with Amazon Nova.
- The workflow processes public pages only and doesn’t implement authenticated sessions.
- For sites that require sign‑in, evaluate the Amazon Bedrock Web Crawler authentication options first, which include basic, form‑based, and SAML authentication.
- Extending the sample with authentication requires session handling, credentials in AWS Secrets Manager, and a security review.
- The companion aws‑samples repository provides the complete workflow as a sample implementation.
- By default, the sample runs the AWS Fargate task in a public subnet, where it reaches your configured websites through an internet gateway.
- The AWS Cloud Development Kit (AWS CDK) app packages the implementation in a container image during deployment.
- When the schedule fires, the container runs scripts/container_entrypoint.py and executes crawl, upload, and ingestion in sequence.

## 🚀 Availability
- The companion aws‑samples repository provides the complete workflow as a sample implementation.
- Because managed and customer‑managed knowledge bases both support Amazon S3 data sources, the Crawl4AI path works with either type.

## 💡 Why it matters
- You don’t provision or scale a vector store, and embedding and reranking use service‑managed models by default.
- Scheduled syncs keep your knowledge base current as pages change.
- All ingestion, parsing, chunking, embedding, indexing, and retrieval are handled by Amazon Bedrock Knowledge Bases, reducing operational overhead.


#AmazonBedrock #RAG #Crawl4AI #ManagedKnowledgeBase #AWS

---

*Source: [Prepare web content for Amazon Bedrock Knowledge Bases with Crawl4AI | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/prepare-web-content-for-amazon-bedrock-knowledge-bases-with-crawl4ai/)*
