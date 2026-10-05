---
title: "Amazon Bedrock Adds Agentic Retrieval to Managed Knowledge Base"
slug: "amazon-bedrock-adds-agentic-retrieval-to-managed-knowledge-base"
description: "Amazon Bedrock’s Managed Knowledge Base now supports agentic retrieval, an advanced RAG capability that plans and iterates over search steps automatically."
date: 2026-10-05T22:07:36+05:30
tags: [AmazonBedrock, AgenticRetrieval, RAG, LangChain, AWS]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Cloud Computing", "Natural Language Processing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-21691-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Adds Agentic Retrieval to Managed Knowledge Base

Amazon Bedrock’s Managed Knowledge Base now supports agentic retrieval, an advanced RAG capability that plans and iterates over search steps automatically.

## 🔍 Overview
- Agentic retrieval is available on Amazon Bedrock Managed Knowledge Base.
- Instead of one search, Amazon Bedrock Managed Knowledge Base plans the retrieval.
- It breaks the question into sub‑queries, runs them, judges whether it has enough evidence, and searches again if it doesn't.
- Two APIs are provided:
  - **Retrieve** – runs one hybrid search and returns scored chunks.
  - **AgenticRetrieveStream** – runs a planning loop and streams the steps back to you as trace events.

## 🧩 How it works
- The planner splits the user query into sub‑queries.
- Each sub‑query is executed against the knowledge base.
- After each step the system checks whether the accumulated evidence is sufficient.
- If not, additional sub‑queries are generated and the process repeats.
- When a passage lacks enough context, a FullDocumentExpansion step calls `bedrock:GetDocumentContent` to fetch the whole document.

## ⚙️ Integration with LangChain
- The `langchain-aws` package exposes both retrieval modes.
  - The standard Retrieve API appears as a normal LangChain retriever that can be dropped into a chain.
  - The AgenticRetrieveStream API is exposed as a function retrieval directly from a knowledge base.
- Both paths return document chunks from the knowledge base, which the application then uses to generate a grounded response.

## 📦 Key Details
- Amazon Bedrock Managed Knowledge Base removes the self‑managed vector store, embeddings, and re‑ranking models from the RAG architecture.
- You configure a data source (e.g., an Amazon S3 bucket); the service handles chunking, embedding, storage, and retrieval.
- Boto3 version 1.43.32 or later is required; `agentic_retrieve_stream` did not exist before that version.
- The knowledge base assumes a service role with the following permissions:
  - `bedrock:GetDocumentContent` (often overlooked)
  - `s3:ListBucket` on the bucket and `s3:GetObject` on its contents, both conditioned on `aws:ResourceAccount`
  - If guardrails are used, also `bedrock:GetGuardrail` and `bedrock:ApplyGuardrail`
- A policy with only `bedrock:Retrieve` works until the planner reaches a whole‑document fetch, then fails.

## 🚀 Availability & Costs
- The walkthrough uses the US East (N. Virginia) Region (`us-east-1`).
- Running the walkthrough may incur costs for document storage, ingestion, retrieval calls, and foundation model inference.
- Delete the resources when you complete the experiment to avoid ongoing charges.

## 📊 API Comparison
| API | Behavior |
| --- | -------- |
| Retrieve | Runs one hybrid search and returns scored chunks. |
| AgenticRetrieveStream | Executes a planning loop, streams each step as trace events, and returns document chunks after iterative retrieval. |


#AmazonBedrock #AgenticRetrieval #RAG #LangChain #AWS

---

*Source: [Agentic retrieval with LangChain and Amazon Bedrock Knowledge Bases | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/agentic-retrieval-with-langchain-and-amazon-bedrock-knowledge-bases/)*
