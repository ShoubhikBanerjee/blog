---
title: "Release of Open Source Agent Skills for HCLS Domains"
slug: "release-of-open-source-agent-skills-for-hcls-domains"
description: "A collection of 38 open source agent skills spanning 11 Health Care and Life Sciences (HCLS) domains has been released to help close the methodology gap for AI agents."
date: 2026-09-17T00:45:10+05:30
tags: [AIagents, HCLS, OpenSource, AWS, Genomics]
categories: ["AI", "AI Agents", "Health Care and Life Sciences", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-21213-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Release of Open Source Agent Skills for HCLS Domains

A collection of 38 open source agent skills spanning 11 Health Care and Life Sciences (HCLS) domains has been released to help close the methodology gap for AI agents.

## 🔍 Overview
The collection includes 38 skills across 11 HCLS domains, such as medical imaging, claims operations, drug discovery, and genomics. All skills are released under the MIT-0 license.

## 🧩 How it works
Agent skills are structured markdown documents (SKILL.md) that encode domain decision procedures for AI agents to consume at inference time through progressive disclosure. 

* **Structure:** Each skill uses YAML frontmatter to declare metadata, dependencies, and triggers. The remaining content includes validation criteria, code patterns, parameter tables, and decision frameworks.
* **Mechanism:** Skills are structured prompts that activate based on trigger patterns in user queries. They are not fine-tuning and differ from Retrieval Augmented Generation (RAG) because they encode the error conditions and decision procedure itself rather than retrieving limited passages from indexed documents.
* **Transparency:** Every decision criterion is human-readable in markdown format and is not hidden in model weights.

## ⚙️ Key details
Skills are categorized into two primary types:

| Skill Type | Description | Example |
| :--- | :--- | :--- |
| Reasoning | Encodes methodology and decision frameworks that guide how the agent thinks. | `genomic-variant-interpretation` (encodes ACMG/AMP classification framework) |
| Pipeline | Encodes tool-specific commands, validated parameters, and code templates for runnable artifacts. | `variant-calling` (provides GATK4 HaplotypeCaller commands) |

## 💡 Why it matters
Agents equipped with these skills show a 70–86 percent win rate in head-to-head comparisons against agents without skills, depending on the agent harness setup. The most significant effect is observed in critical thinking, with a win rate of 78–85 percent (d = 0.65–1.03).

## 🚀 Availability
The skills work across more than 20 services without individual customization, including OpenAI Codex, Claude Code, Amazon Quick Desktop, Amazon Bedrock AgentCore, AWS Strands Agents SDK, and Kiro.

To use these skills, users need Git, Python 3.10+ with uv, and one of the following supported AWS services:
* **Kiro or Kiro CLI:** For interactive skill use and multi-agent orchestration.
* **AWS Strands Agents SDK:** Requires Amazon Bedrock foundation model access.
* **AgentCore harness:** A capability of Amazon Bedrock AgentCore for those with an existing agent implementation; provides observability, security boundaries, auto scaling, and managed hosting.
* **Quick Desktop:** For GUI-based skill management.

Installation is managed via an `install.sh` script with targets for Kiro (including a `--mode multiagent` option) and Quick Desktop.

#AIagents #HCLS #OpenSource #AWS #Genomics

---

*Source: [Improving HCLS AI reasoning with open-source agent skills | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/improving-hcls-ai-reasoning-with-open-source-agent-skills/)*
