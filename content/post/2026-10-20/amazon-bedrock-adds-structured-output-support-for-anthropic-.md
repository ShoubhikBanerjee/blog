---
title: "Amazon Bedrock Adds Structured Output Support for Anthropic Claude Models"
slug: "amazon-bedrock-adds-structured-output-support-for-anthropic-claude-models"
description: "Amazon Bedrock now supports structured outputs for all Anthropic Claude models, enabling developers to receive schema-compliant JSON responses across both bedrock-runtime and bedrock-mantle endpoints."
date: 2026-10-20T22:03:21+05:30
tags: [AmazonBedrock, AnthropicClaude, JSON, GenerativeAI, API]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-22211-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Adds Structured Output Support for Anthropic Claude Models

Amazon Bedrock now supports structured outputs for all Anthropic Claude models, enabling developers to receive schema-compliant JSON responses across both bedrock-runtime and bedrock-mantle endpoints.

## 🧩 How it works
Structured outputs use constrained decoding to enforce JSON schemas during token generation. This process shifts output formatting from probabilistic to deterministic, ensuring the model does not produce tokens that violate the defined schema.

Key mechanisms include:

| Mechanism | Function | Use Case |
| :--- | :--- | :--- |
| JSON Schema output format | Control response structure | Data extraction, report generation, API responses |
| Strict tool use | Validate tool parameters | Agentic workflows, function calling, multi-step automation |

## ⚙️ Key details
* **Compliance**: Amazon Bedrock validates JSON schemas against the JSON Schema Draft 2020-12 subset.
* **Performance**: The system compiles a grammar artifact for new schemas. These are cached for 24 hours per account to improve subsequent request speeds.
* **Efficiency**: By constraining responses to only defined fields, output token counts are reduced, which can lower inference costs for high-volume workloads.
* **Implementation**: On the bedrock-runtime endpoint, the schema is placed in `output_config.format` as a JSON object.
* **Tooling**: On the bedrock-mantle endpoint, setting `strict: true` constrains tool inputs to match the provided schema exactly.

## 🚀 Availability
* **Endpoints**: Supported on both `bedrock-runtime` and `bedrock-mantle`.
* **Inference**: Works with batch inference for asynchronous processing.
* **Cross-Region**: Supported on the `bedrock-runtime` endpoint for cross-Region inference without additional setup.
* **Real-time**: Structured responses can be streamed as typed events.

## 💡 Why it matters
Structured outputs eliminate common issues such as `JSON.parse()` errors and parsing exceptions. Because responses are type-safe and required fields are guaranteed to be present, developers can build more reliable agentic workflows that interact with server-side tools.

#AmazonBedrock #AnthropicClaude #JSON #GenerativeAI #API

---

*Source: [Structured outputs for Anthropic Claude models on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/structured-outputs-for-anthropic-claude-models-on-amazon-bedrock/)*
