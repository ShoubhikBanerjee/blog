---
title: "Amazon Bedrock Adds GPT-6 Models with Global Cross-Region Inference"
slug: "amazon-bedrock-adds-gpt-6-models-with-global-cross-region-inference"
description: "Amazon Bedrock now offers OpenAI GPT-6 models with global cross-Region inference to improve availability and manage capacity. This update allows users to route requests across multiple AWS Regions to..."
date: 2026-10-13T06:08:42+05:30
tags: [O, p, e, n, A, I, A, m, a, z, o, n, B, e, d, r, o, c, k, A, I, M, o, d, e, l, s, C, l, o, u, d, I, n, f, r, a, s, t, r, u, c, t, u, r, e, I, n, f, e, r, e, n, c, e]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "C", "l", "o", "u", "d", "I", "n", "f", "r", "a", "s", "t", "r", "u", "c", "t", "u", "r", "e", ",", "A", "I", "D", "e", "v", "e", "l", "o", "p", "m", "e", "n", "t", ",", "E", "n", "t", "e", "r", "p", "r", "i", "s", "e", "S", "o", "f", "t", "w", "a", "r", "e"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/09/ML-21759-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Adds GPT-6 Models with Global Cross-Region Inference

Amazon Bedrock now offers OpenAI GPT-6 models with global cross-Region inference to improve availability and manage capacity. This update allows users to route requests across multiple AWS Regions to avoid throttling and access broader capacity.

## 🌍 Overview
Amazon Bedrock offers OpenAI GPT-6 Sol and GPT-6 Luna through global cross-Region inference from all five AWS Regions. GPT-6 Astra is available from Asia Pacific (Singapore). All three models are accessible via the bedrock-runtime endpoint.

## 🧠 Model Capabilities
The GPT-6 models offer distinct capabilities suited for different workflows:

| Model | Capabilities |
| :--- | :--- |
| GPT-6 Sol | Strong reasoning and coding capabilities for complex tasks performed throughout the week. |
| GPT-6 Luna | Focused, repeatable tasks practical at high volume. |
| GPT-6 Astra | Complex reasoning, coding, and long-document work. |

All three models accept text and image input, client-side tool use, and prompt caching.

## ⚙️ How it Works
Global cross-Region inference routes requests across supported commercial AWS Regions where the model is deployed. This mechanism gives you broad access to Amazon Bedrock capacity.

To invoke the models, you pass a global cross-Region inference profile ID in place of a model ID. Your source Region is where you make the API call, and Amazon Bedrock selects the destination Region for processing.

**Note:** Single-Region inference can throttle when demand exceeds local capacity. Cross-Region inference helps mitigate this issue.

## 📊 Reasoning Effort
The models differ in their reasoning effort settings:

*   **GPT-6 Sol and GPT-6 Luna:** Accept none, low, medium, high, xhigh, and max.
*   **GPT-6 Astra:** Accepts the same levels except none.

## ⚠️ Availability and Pricing
Inference profile availability and Region support change as AWS adds Regions and profiles. Confirm both on the model card before you build. For per-token rates, see Amazon Bedrock pricing.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/09/ML-21759-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/09/ML-21759-2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/09/ML-21759-3-1.jpg)

#O #p #e #n #A #I #, # #A #m #a #z #o #n # #B #e #d #r #o #c #k #, # #A #I # #M #o #d #e #l #s #, # #C #l #o #u #d # #I #n #f #r #a #s #t #r #u #c #t #u #r #e #, # #I #n #f #e #r #e #n #c #e

---

*Source: [Accessing OpenAI GPT models on Amazon Bedrock with global cross-Region inference in Thailand, Malaysia, Singapore, Indonesia, and Taiwan | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/accessing-openai-gpt-models-on-amazon-bedrock-with-global-cross-region-inference-in-thailand-malaysia-singapore-indonesia-and-taiwan/)*
