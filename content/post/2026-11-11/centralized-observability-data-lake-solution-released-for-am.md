---
title: "Centralized Observability Data Lake Solution Released for Amazon Bedrock Model Invocations"
slug: "centralized-observability-data-lake-solution-released-for-amazon-bedrock-model-invocations"
description: "A centralized observability data lake solution has been introduced for Amazon Bedrock model invocations. Built using AWS CloudFormation, AWS Lambda, Amazon Data Firehose, and Amazon Athena, the..."
date: 2026-11-11T22:05:42+05:30
tags: [AmazonBedrock, AWS, CloudObservability, DataLake, CloudWatch]
categories: ["AI", "Cloud Computing", "Data Observability", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-21645-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Centralized Observability Data Lake Solution Released for Amazon Bedrock Model Invocations

A centralized observability data lake solution has been introduced for Amazon Bedrock model invocations. Built using AWS CloudFormation, AWS Lambda, Amazon Data Firehose, and Amazon Athena, the solution consolidates raw invocation logs across multiple AWS accounts into a single querying location.

## 🔍 Overview

Amazon Bedrock offers model invocation logging to record requests and responses sent to Amazon Simple Storage Service (Amazon S3) or Amazon CloudWatch. The centralized data lake pulls raw invocation logs from linked source accounts into a central account, providing an organization-wide clean table that can be queried using ordinary SQL.

## ⚙️ Captured log details

When an application calls an Amazon Bedrock model, invocation logging records specific request and metadata details:

- **Prompt**: The prompt sent by the user or application.
- **Model response**: The response returned by the model.
- **Token counts**: Input and output token counts to measure invocation weight.
- **Model**: The model used, allowing teams to track model utilization.
- **Stop reason**: The reason a response concluded (such as `max_tokens`).
- **Account and timestamp**: Attributes used for timing and attribution.
- **IAM identity**: The AWS Identity and Access Management (IAM) role that initiated the prompt.

## 🧩 Architecture and pipeline

The centralized observability pipeline is deployed repeatably across accounts using two AWS CloudFormation templates as Infrastructure as Code. The pipeline operates as follows:

1. **Logging activation**: Invocation logging is enabled per account with a single API call, pointing Amazon Bedrock to a local CloudWatch log group with write permissions.
2. **Subscription filters**: Each source account log group uses a subscription filter to forward records to a CloudWatch Logs destination in the central account. Source accounts do not receive permissions on the central pipeline.
3. **Lambda processing**: A small AWS Lambda function unwraps batch records into individual log entries and lifts fields to the top level for simple querying.
4. **Buffering and conversion**: Amazon Data Firehose buffers the log records, converts them from JSON to Parquet format, files objects under date paths (such as `year=2026/month=08/day=27/`), and writes them to an Amazon S3 bucket.
5. **Data querying**: An AWS Glue table defines the schema so Amazon Athena can expose the data as one clean SQL-queryable table.

| Pipeline Component | Role in Data Lake Architecture |
| --- | --- |
| Amazon CloudWatch | Collects raw logs in source accounts and receives forwarded logs in the central account |
| Subscription Log Filters | Routes log records from source accounts to the central CloudWatch destination |
| AWS Lambda | Unwraps record batches and lifts nested fields to top-level attributes |
| Amazon Data Firehose | Buffers data, converts JSON to Parquet, applies date partitioning, and writes to S3 |
| Amazon S3 | Stores converted Parquet log data |
| AWS Glue | Defines table schemas for Athena |
| Amazon Athena | Provides single-table SQL query access across the organization |

## 💡 Key capabilities

Using the centralized data lake, organizations can analyze model usage pattern metrics across accounts:

- Identify which users consume the highest number of tokens.
- Determine commonly selected models and review prompt text.
- Connect logging data with the AWS Cost and Usage Report (CUR) to track daily user prompt spend.

Templates, Lambda code, and SQL queries are available in the AWS Sample Bedrock Invocation Data Lake GitHub repository.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-21645-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-21645-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-21645-3.jpg)

#AmazonBedrock #AWS #CloudObservability #DataLake #CloudWatch

---

*Source: [Amazon Bedrock tokenomics data lake | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/amazon-bedrock-tokenomics-data-lake/)*
