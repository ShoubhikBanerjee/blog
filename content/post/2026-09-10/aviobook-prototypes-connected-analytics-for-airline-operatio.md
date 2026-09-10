---
title: "AvioBook Prototypes Connected Analytics for Airline Operations Using Amazon Bedrock AgentCore"
slug: "aviobook-prototypes-connected-analytics-for-airline-operations-using-amazon-bedrock-agentcore"
description: "AvioBook, a Thales Group Company, has prototyped Connected Analytics to allow airline managers and operations control center dispatchers to query flight data using plain language."
date: 2026-09-10T22:04:27+05:30
tags: [AvioBook, AmazonBedrock, AIagents, Aviation, FlightOperations]
categories: ["AI", "AI Agents", "Aviation Technology", "Enterprise Software"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/13/ML-21410-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AvioBook Prototypes Connected Analytics for Airline Operations Using Amazon Bedrock AgentCore

AvioBook, a Thales Group Company, has prototyped Connected Analytics to allow airline managers and operations control center dispatchers to query flight data using plain language.

## 🧩 How it works
Connected Analytics sits on top of AvioBook Connect, a communication platform that organizes flight operations into "flightrooms" (one live chat per flight). The system utilizes two specialized agents to retrieve information:

* **Data Retrieval:** Agents pull relevant flight events and check them against logs in the flightroom.
* **Evidence-Based Answers:** The agents return direct answers supported by the underlying evidence.
* **Infrastructure:** The system was prototyped on Amazon Bedrock AgentCore, an agentic platform for building and operating agents using any foundation model and framework.

## ⚙️ Key details
AvioBook Connect's API platform, launched in 2025, provides a durable, timestamped record of the following:

* Automated events (aircraft changes, delays, new flight plans, and boarding progress).
* Messages exchanged by operational teams.
* Data processed entirely within the airline's own controlled data environment.

## 💡 Why it matters
Time lost at the gate costs an airline approximately $20 per minute. For a mid-size carrier with 200 flights daily, reducing average turnaround by 2 minutes is worth roughly $240,000 a month.

| Role | Focus | Example Queries |
| :--- | :--- | :--- |
| Airline Managers | On-time performance (OTP) and historical patterns | "What are the most common non-weather sources of delay?" or "Are the procedures for process X being followed?" |
| OCC Dispatchers | Live data and network-wide disruptions | "What downstream effects will there be from the disruption at X airport?" or "Which flights with the highest Value at Risk (VaR) index are flying today?" |

#AvioBook #AmazonBedrock #AIagents #Aviation #FlightOperations

---

*Source: [How AvioBook builds turnaround insights from operational data with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-aviobook-uses-generative-ai-to-drive-airline-turnaround-insights/)*
