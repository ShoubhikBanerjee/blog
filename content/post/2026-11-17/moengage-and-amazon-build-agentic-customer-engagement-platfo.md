---
title: "MoEngage and Amazon Build Agentic Customer Engagement Platform with MCP"
slug: "moengage-and-amazon-build-agentic-customer-engagement-platform-with-mcp"
description: "MoEngage, an agentic customer engagement platform used by more than 1,350 consumer brands, has built a new layer of AI agents called Merlin AI that allows marketing and product teams to draft,..."
date: 2026-11-17T12:12:52+05:30
tags: [MoEngage, AmazonBedrock, MCP, AIAgents, LegacyModernization]
categories: ["AI", "AI Agents", "Marketing Technology", "Cloud Architecture", "Legacy Modernization"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-21091-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# MoEngage and Amazon Build Agentic Customer Engagement Platform with MCP

MoEngage, an agentic customer engagement platform used by more than 1,350 consumer brands, has built a new layer of AI agents called Merlin AI that allows marketing and product teams to draft, analyze, and adjust campaigns through a single conversation. The system is built on Amazon Bedrock and Amazon Bedrock AgentCore, leveraging the Model Context Protocol (MCP) to provide secure, tenant-scoped access to live platform data.

## 🔍 Overview
The traditional customer engagement workflow requires teams to navigate multiple tools—analytics dashboards, content libraries, and campaign builders—across channels like email, push, SMS, and WhatsApp. MoEngage addressed this by creating a third layer of software interaction where users describe an outcome in plain language and an agent executes the steps across the platform. This approach treats the platform's existing API capabilities as tools for agents to call, reducing the need to switch between separate interfaces.

## 🧩 How it works
Merlin AI operates using a foundation of Amazon Bedrock for reasoning and generation, the AgentCore runtime for hosting, and MCP for standardized data access. The system utilizes Anthropic Claude Sonnet 4.6, Claude Sonnet 5, and Claude Sonnet 5.5 models for tool-call planning and content generation. The architecture is designed to keep each tenant’s data isolated while giving agents secure access to segments, campaign history, and content libraries.

## ⚙️ Key details
Merlin AI Studio places purpose-built agents at specific points in the marketing workflow:

*   **Copywriter:** Generates personalized push and transactional copy consistent with brand voice.
*   **Designer:** Produces marketing banners or images from text descriptions.
*   **Segment Assist:** Converts plain-language audience descriptions into specific attribute filters (e.g., users who abandoned a cart in the last two hours).
*   **Jinja Assist:** Translates natural language into working Jinja and Liquid markup for dynamic content.
*   **In-app Template Builder:** Creates responsive, accessible HTML templates for in-app messages, including gamified formats and surveys.
*   **Flow Assist:** Transforms high-level ideas into ready-to-deploy customer journeys by interpreting requests, proposing paths, and refining structures with historical data.

Conversational agents operate across campaigns, analytics, segments, and flows, allowing teams to manage complex interactions through a single dialogue.

## 💡 Why it matters
This development represents a shift in software platforms from user interfaces for business users and APIs for engineering teams to an agentic layer. A customer of MoEngage, Glance, reported a 38% uplift in push notification click-through rates as a result of using these AI agents. The architecture allows marketing teams to spend less time navigating tools and more time making decisions.

## 🏢 Legacy Modernization Context
In parallel developments, the evidence describes a methodology for transforming legacy mainframe Assembler applications into Java Spring Boot services on AWS. This process uses Amazon Bedrock and Kiro IDE for AI-assisted code analysis and business rule extraction, followed by AWS Transform for automated COBOL-to-Java conversion. The multi-stage approach converts Assembler to COBOL as an intermediate step to preserve business logic before final modernization, addressing the challenge of retiring critical code that few experts can read.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-21091-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-21091-3-1.jpg)

#MoEngage #AmazonBedrock #MCP #AIAgents #LegacyModernization

---

*Source: [How MoEngage built agentic customer engagement on Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-moengage-built-agentic-customer-engagement-on-amazon-bedrock-agentcore/)*
*Source: [Modernizing mainframe Assembler to Java using Amazon Bedrock and AWS Transform | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/modernizing-mainframe-assembler-to-java-using-amazon-bedrock-and-aws-transform/)*
