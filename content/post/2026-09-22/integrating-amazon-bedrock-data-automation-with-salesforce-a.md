---
title: "Integrating Amazon Bedrock Data Automation with Salesforce Agentforce via MCP"
slug: "integrating-amazon-bedrock-data-automation-with-salesforce-agentforce-via-mcp"
description: "An updated implementation demonstrates how to combine Amazon Bedrock Data Automation with the Model Context Protocol (MCP) to transform unstructured data into structured insights accessible through..."
date: 2026-09-22T22:03:42+05:30
tags: [AmazonBedrock, Salesforce, Agentforce, MCP, AIagents]
categories: ["AI", "AI Agents", "Cloud Computing", "Data Automation"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-20933-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Integrating Amazon Bedrock Data Automation with Salesforce Agentforce via MCP

An updated implementation demonstrates how to combine Amazon Bedrock Data Automation with the Model Context Protocol (MCP) to transform unstructured data into structured insights accessible through Salesforce Agentforce.

## 🔍 Overview
This solution allows Salesforce users to upload files, ask questions, and receive AI-powered insights directly within the Salesforce console without managing AWS resources or switching systems. An example implementation utilizes the External Storage of Files with Amazon S3 integration from Agentforce Public Sector (formerly Public Sector Solutions).

## 🧩 How it works
The process follows a two-part flow involving data processing and insight retrieval:

**Data Processing Flow**
1. Unstructured media files and documents are moved into Amazon S3 via the External Storage of Files with Amazon S3 for Public Sector connector.
2. An S3 event notification invokes an AWS Lambda function, which generates a document ID, stores it with metadata in Amazon DynamoDB, and starts an Amazon Bedrock Data Automation job.
3. Amazon Bedrock Data Automation extracts structured insights based on the media type.
4. Upon completion, an Amazon EventBridge rule triggers a second Lambda function to save results to a dedicated Amazon S3 output bucket.

**Insight Retrieval Flow**
1. A user chat in Agentforce triggers an action that calls AWS over MCP.
2. The request routes through Amazon Bedrock AgentCore Gateway—a platform for building, connecting, and optimizing agents—which authenticates the request and invokes an MCP server on AWS Lambda.
3. The Lambda function queries DynamoDB to locate results and retrieves them from Amazon S3.
4. The data returns through AgentCore Gateway to Agentforce, where it is loaded into the agent's context for a natural language response.

## ⚙️ Key details
Amazon Bedrock Data Automation applies different extraction capabilities based on the file type, which can be customized in the Amazon Bedrock Data Automation console:

| Media Type | Extraction Capabilities |
| :--- | :--- |
| Documents | Extracts text, identifies key fields, and generates structured summaries |
| Images | Produces descriptions and identifies objects or text within the frame |
| Video and Audio | Generates transcriptions and scene-level summaries |

The serverless infrastructure consists of:
* Amazon EventBridge rules
* Amazon Bedrock Data Automation configuration
* AWS Lambda functions
* Amazon DynamoDB tables
* Amazon Bedrock AgentCore Gateway

## 🚀 Availability
Registering external MCP servers is available for the following Salesforce editions:
* Developer
* Enterprise
* Performance
* Unlimited

Users must confirm their Salesforce org supports registering and calling external MCP servers through the Agentforce Registry.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/15/Solution_Overview.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/15/Solution_OverviewMCP.png)

#AmazonBedrock #Salesforce #Agentforce #MCP #AIagents

---

*Source: [Extending public sector intelligence with Agentforce and AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/extending-public-sector-intelligence-with-agentforce-and-aws/)*
