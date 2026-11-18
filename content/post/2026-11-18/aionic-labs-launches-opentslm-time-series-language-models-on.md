---
title: "Aionic Labs Launches OpenTSLM Time-Series Language Models on Amazon SageMaker JumpStart"
slug: "aionic-labs-launches-opentslm-time-series-language-models-on-amazon-sagemaker-jumpstart"
description: "Aionic Labs has made OpenTSLM, an open source family of time-series language models (TSLMs), available in Amazon SageMaker JumpStart, enabling organizations to deploy these models in their own AWS..."
date: 2026-11-18T18:09:03+05:30
tags: [OpenTSLM, AionicLabs, SageMaker, TimeSeries, AIagents]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21774-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Aionic Labs Launches OpenTSLM Time-Series Language Models on Amazon SageMaker JumpStart

Aionic Labs has made OpenTSLM, an open source family of time-series language models (TSLMs), available in Amazon SageMaker JumpStart, enabling organizations to deploy these models in their own AWS environment. This release helps organizations utilize temporal foundation models to interpret operational measurements alongside text context without consuming the large numbers of tokens that general-purpose language models require when processing long histories as text or images.

## 🧩 How it works

OpenTSLM and other temporal foundation models are designed to understand how systems change and help people act on that understanding.

* **Data Input:** The model receives numerical measurements alongside text context, interpreting how the signals change over a specific observation window.
* **Operational Measurements:** The model interprets measurement data ranging from equipment sensor data to supply and demand, alongside contextual information such as maintenance records, market news, and engineer observations.
* **IT Telemetry Analysis:** When evaluating device performance, the workflow combines recent time-series data—including CPU activity, memory use, available disk space, application stability, and connectivity—with timestamped events, device configuration, and software versions.

## ⚙️ System Components

| Component | Role |
| :--- | :--- |
| **OpenTSLM** | An open source family of time-series language models developed by Aionic Labs to interpret operational measurements and context. |
| **TimeNet** | Shared data infrastructure for time-series data that provides a single format and API to find, build, and load training and evaluation datasets. |
| **Spark** | Nexthink's personal IT agent, enhanced with TSLMs to connect device telemetry and context to problems employees experience. |
| **Amazon SageMaker JumpStart** | A machine learning model hub used to evaluate, compare, and deploy pretrained foundation models to Amazon SageMaker AI inference endpoints. |
| **Amazon Bedrock** | An AWS offering that provides serverless API foundation model inference, customizations, knowledge bases, agents, and guardrails. |

## 🚀 Practical Application

Nexthink and Aionic Labs are building toward a digital workplace where employees get help before they need to ask for it. At the center is Spark, Nexthink’s personal IT agent, which uses TSLMs to recognize emerging IT problems and guide employees toward a solution.

* **Issue Investigation:** Spark uses device telemetry to investigate issues like slow performance under high CPU or memory load, recurring application freezes, and file synchronization failures.
* **Automated Remediation Workflow:** In an illustrative low-disk scenario, the TSLM connects declining free space and a rising disk queue with likely employee symptoms like a slow computer. Spark checks remaining space, proposes an IT-approved cleanup of temporary files, runs the cleanup after employee confirmation, checks the space now available, and offers to pass findings to IT support if the issue persists.

This workflow and deployment architecture provide a reusable pattern for time-series applications across AWS infrastructure.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21774-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/16/ML-21774-3.png)

#OpenTSLM #AionicLabs #SageMaker #TimeSeries #AIagents

---

*Source: [Reason over time-series data with OpenTSLM on Amazon SageMaker JumpStart | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/reason-over-time-series-data-with-opentslm-on-amazon-sagemaker-jumpstart/)*
