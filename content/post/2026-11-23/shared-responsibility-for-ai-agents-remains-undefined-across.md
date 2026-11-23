---
title: "Shared Responsibility for AI Agents Remains Undefined Across Major Vendors"
slug: "shared-responsibility-for-ai-agents-remains-undefined-across-major-vendors"
description: "Five organizations have published guidance on responsibility for AI agents, but no consensus has emerged on who is ultimately responsible for agent behavior. While traditional cloud security has..."
date: 2026-11-23T22:18:20+05:30
tags: [AIAgents, CloudSecurity, Microsoft, AWS, Anthropic, SharedResponsibility]
categories: ["AI", "AI Agents", "Cloud Security", "Enterprise AI", "Cybersecurity"]
image: "https://www.bleepstatic.com/content/posts/2026/11/20/ai-shared-responsibility-gap.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Shared Responsibility for AI Agents Remains Undefined Across Major Vendors

Five organizations have published guidance on responsibility for AI agents, but no consensus has emerged on who is ultimately responsible for agent behavior. While traditional cloud security has clear separation of duties between vendors and customers, AI agents act as non-deterministic intermediaries, making the separation of responsibilities less clean. The available guidance approaches the issue from different angles, ranging from specific task assignments to descriptions of broader security layers. To address this, organizations need to determine who owns each agent, what permissions it holds, and how it operates across systems.

## 🧩 How it works

In cloud security, models like the AWS Shared Responsibility Model establish a clear division: vendors handle infrastructure security, while customers are responsible for the data and the actions taken. For example, if data is copied from AWS to SFDC, each vendor secures their infrastructure, but the customer owns the action.

AI agents complicate this framework. They send authenticated, authorized requests that can be compromised or rogue. A rogue agent has either misunderstood its instructions or acted inappropriately—a type of error that is not necessarily a mistake in the human sense. Because agents act as intermediaries between the user and the request, and they are not deterministic by nature, the line between vendor and customer responsibility becomes blurred.

## ⚙️ Key details

Five specific organizations have published guidance on this topic:

* **Microsoft**: Published an AI agent shared responsibility model featuring a matrix for IaaS, PaaS, and SaaS deployments.
* **CSA and CoSAI**: Published shared responsibility models.
* **AWS**: Provided security guidance for AgentCore, applying its general shared responsibility model without a specific agent-specific model.
* **Anthropic**: Published guidance titled "Trustworthy agents in practice."

Only two of these organizations assign ownership of an agent's identity, and they split that ownership differently. No publication agrees on who is responsible for the agent's behavior. Approaches vary: some assign specific tasks to providers and customers, while others describe security layers or broader stakeholder roles.

## 💡 Why it matters

Frontier AI labs are clear about their immediate responsibilities: making models more robust, better guarded, and harder to hijack. They are equally clear about their limitations: they cannot understand the specific business context of an action. For instance, an agent deleting files from Google Drive could be acting maliciously or performing a normal task; the system cannot distinguish between the two. Consequently, builders bear final responsibility for the behavior and permissions of the systems they assemble. While tools like Claude Code include checks such as automated classifiers to block actions driven by hostile content, and vendors like OpenAI, Cursor, and GitHub offer approval prompts and sandboxes, these capabilities do not automatically resolve the question of accountability. As new protocols like MCP are introduced, they may conceptually denote expanded responsibility for those who built them, but the lack of unified ownership remains a critical gap for organizations deploying agents.

#AIAgents #CloudSecurity #Microsoft #AWS #Anthropic #SharedResponsibility

---

*Source: [AI Agents Are Creating a Shared Responsibility Gap](https://www.bleepingcomputer.com/news/security/ai-agents-are-creating-a-shared-responsibility-gap/)*
