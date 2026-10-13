---
title: "ShipStation Deploys Deckhand AI Agent for Slack Help Desk on Amazon Bedrock"
slug: "shipstation-deploys-deckhand-ai-agent-for-slack-help-desk-on-amazon-bedrock"
description: "ShipStation Global Engineering launched Deckhand, an AI‑powered IT help‑desk agent that lives in Slack and runs on Amazon Bedrock AgentCore."
date: 2026-10-13T22:07:53+05:30
tags: [ShipStation, AIAgents, Slack, AmazonBedrock, ITAutomation]
categories: ["AI", "Artificial Intelligence", "Enterprise Software", "Cloud Computing", "IT Operations"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/08/ML-21795-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# ShipStation Deploys Deckhand AI Agent for Slack Help Desk on Amazon Bedrock

ShipStation Global Engineering launched Deckhand, an AI‑powered IT help‑desk agent that lives in Slack and runs on Amazon Bedrock AgentCore.

## 🔍 Overview
- Repetitive IT questions, error‑message screenshots, and off‑hours tickets consumed time that could be spent elsewhere.
- Knowledge was scattered across Confluence articles, intranet pages, PDFs, IT‑maintained guides, and the Slack channel history.
- In the 12 months before launch employees posted more than 1,500 threads, with over a fifth of questions arriving outside US business hours.
- Deckhand resolves 97.5 % of incoming channel queries and earned a 96 % positive‑feedback rating (Figure 1).

## 🧩 How it works
- When an employee posts in a channel where Deckhand is present, the Slack service assembles the full thread history and user context (name, email, time zone, manager).
- The request is sent to the AgentCore runtime API.
- The agent searches an Amazon Bedrock knowledge base (indexed content from Confluence, the intranet, Slack, and marketing pages stored in Amazon S3) and calls tools as needed.
- If the answer is not found, the agent asks a clarifying question or offers to create a Jira Service Management ticket.

| Component | Description |
|---|---|
| Slack service | FastAPI + Slack Bolt app hosted on AWS App Runner; receives Slack events, builds user‑context payload |
| Agent service | Strands agent deployed as a container on Amazon Bedrock AgentCore runtime; uses Anthropic Claude via Bedrock |
| Tools & knowledge | Single AWS Lambda exposed as Model Context Protocol tools; classifies requests, creates/updates Jira tickets, analyzes images |
| Knowledge base | Amazon S3‑backed index of Confluence, intranet, Slack, and marketing content |
| Operations | Amazon DynamoDB stores feedback; AWS X‑Ray traces request paths; Amazon CloudWatch logs |

## ⚙️ Key details
- Runs on Amazon Bedrock AgentCore runtime, which hosts the agent in isolated sessions—no servers or containers to manage.
- Integrates with Jira Service Management to create fully contextualized tickets with one click.
- Can read error‑message screenshots and respond directly in the Slack conversation.
- Operates like a teammate: joins channels, reads conversation history, and draws context from Slack profiles.

## 🚀 Impact
- Repetitive questions that previously required manual lookup are now answered on the spot.
- Employees receive help by simply asking a question in Slack, eliminating the need to fill out ticket forms.
- The IT team is freed from repeatedly saying “please file a ticket,” reducing operational friction.

## 💡 Why it matters
- Shows that AI agents can consolidate fragmented knowledge sources and provide instant support for globally distributed teams.
- Improves employee experience and operational efficiency for a leading intelligent shipping and logistics platform.

#ShipStation #AIAgents #Slack #AmazonBedrock #ITAutomation

---

*Source: [How ShipStation Global built an AI IT help desk on Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-shipstation-global-built-an-ai-it-help-desk-on-amazon-bedrock-agentcore/)*
*Source: [Build long-horizon agents with Grok 4.7 on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-long-horizon-agents-with-grok-4-7-on-amazon-bedrock/)*
