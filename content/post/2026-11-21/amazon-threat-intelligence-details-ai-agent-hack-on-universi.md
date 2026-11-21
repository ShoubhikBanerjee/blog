---
title: "Amazon Threat Intelligence details AI agent hack on universities"
slug: "amazon-threat-intelligence-details-ai-agent-hack-on-universities"
description: "Amazon Threat Intelligence shared findings from an investigation into a Chinese-nexus threat actor who used autonomous AI agents to conduct hacking operations with minimal human involvement. The..."
date: 2026-11-21T18:08:57+05:30
tags: [Cybersecurity, AIAgents, ThreatIntelligence, Amazon, Zeroday, AutonomousHacking]
categories: ["AI", "Cybersecurity", "AI Agents", "Threat Intelligence", "Network Security"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2021/12/20/networked-system-computer.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Threat Intelligence details AI agent hack on universities

Amazon Threat Intelligence shared findings from an investigation into a Chinese-nexus threat actor who used autonomous AI agents to conduct hacking operations with minimal human involvement. The investigation revealed a campaign targeting IP addresses associated with universities in East Asia outside mainland China over a 48-hour period beginning September 8, 2026.

## 🔍 Overview

On September 10, 2026, Amazon Threat Intelligence identified a server with a publicly hosted instance of Cairn, an open-source autonomous AI penetration-testing framework, running without authentication. Because the operator left the server publicly accessible, the operational history of the platform was visible to anyone on the internet. This visibility included project configurations, actor prompts, and AI output. The operator wrote prompts in Simplified Chinese, and the timestamps in executed scripts were configured to China Standard Time.

## 🧩 How it works

Cairn is built as a research and problem-solving engine for defenders. Operating it is simple: given a starting point and an objective in plain language, it coordinates multiple AI agents to find a path to that goal. The actor in this campaign gave the agents a simple goal: “obtain shell access.” Based on a list of targeted IP addresses and that goal, the AI agents planned, executed, and adjusted their approach as they learned, without the operator choosing each next step.

## ⚙️ Key details

The campaign included several operations that varied widely in complexity and outcome. During the campaign, the agents found a zero-day in an open-source application and used it to gain full control of a server. 

| Operation Target | Duration | Key Actions |
| :--- | :--- | :--- |
| Redis instance at one university | ~16 hours | 148 sequential actions; abused replication feature, escaped scripting sandbox, wrote to config files, corrupted memory, attempted Log4Shell injection |
| University GPU server | > 6 hours | Researched public presence to build list of ~80 usernames; tested > 30,000 credential combinations against SSH, admin dashboard, network storage, VPN, and campus portal |
| Open-source medical imaging AI application | Not specified | Identified framework, mapped API endpoints, found upload endpoint with a filename parameter |

In the Redis operation, when initial attempts to take control failed, the agents mapped the internal Docker network topology through a server-side request forgery (SSRF) vulnerability in a co-located Qdrant instance and launched credential sprays against PostgreSQL, SSH, and several other services. None of these attempts succeeded. In the GPU server operation, the agents never found a working login. Against the medical imaging application, the agents successfully identified the framework and mapped its API endpoints.

## 💡 Why it matters

These findings show that agentic offensive operations are already happening. Defenders should prepare for the speed and persistence these tools enable, as the agents kept adapting for nearly a full day without human direction, even when specific operations did not succeed.

#Cybersecurity #AIAgents #ThreatIntelligence #Amazon #Zero-day #AutonomousHacking

---

*Source: [Chinese-nexus actor’s Cairn AI agents found a zero-day on their own | Amazon Web Services](https://aws.amazon.com/blogs/security/chinese-nexus-actors-cairn-ai-agents-found-a-zero-day-on-their-own/)*
