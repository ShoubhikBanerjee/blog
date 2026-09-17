---
title: "Open Source HCLS Agent Skills Collection Released to Improve Domain Reasoning"
slug: "open-source-hcls-agent-skills-collection-released-to-improve-domain-reasoning"
description: "A new collection of 38 open source agent skills across 11 healthcare and life sciences (HCLS) domains has been released to address a methodology gap where AI agents misapply decision frameworks..."
date: 2026-09-17T22:02:13+05:30
tags: [HCLS, AIAgents, OpenSource, HealthcareAI, Genomics]
categories: ["AI", "AI Agents", "Healthcare and Life Sciences", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-21213-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Open Source HCLS Agent Skills Collection Released to Improve Domain Reasoning

A new collection of 38 open source agent skills across 11 healthcare and life sciences (HCLS) domains has been released to address a methodology gap where AI agents misapply decision frameworks despite having access to guidelines.

## 💡 Why it matters
AI agents built on foundation models often exhibit silent failures in clinical trial design, imaging analysis, claims adjudication, and variant interpretation. While these models know facts, they lack the structured reasoning procedures internalized by domain practitioners. This leads to issues where agents:
* Cite correct frameworks but misapply evidence categories.
* Skip population frequency thresholds.
* Hallucinate computational predictor scores.
* Produce outputs that look correct but apply wrong criteria, creating regulatory and patient safety consequences.

## 🧩 How it works
Agent skills are structured markdown documents (`SKILL.md`) that encode decision procedures for AI agents to consume at inference time through progressive disclosure. Following an open standard, each skill uses YAML frontmatter to declare metadata, dependencies, and triggers.

Unlike Retrieval Augmented Generation (RAG), which retrieves limited passages, skills encode the decision procedure and error conditions themselves. They are not fine-tuning, but structured prompts that activate based on trigger patterns in user queries.

## ⚙️ Key details
Skills are categorized into a dual taxonomy to provide both judgment and technical precision:

| Skill Type | Purpose | Example |
| :--- | :--- | :--- |
| Reasoning Skills | Encode methodology and decision frameworks to guide thinking | `genomic-variant-interpretation` (encodes ACMG/AMP classification framework) |
| Pipeline Skills | Encode tool-specific commands, validated parameters, and code templates | `variant-calling` (provides GATK4 HaplotypeCaller commands) |

Three distinct properties separate these skills from other specialization approaches:
* **Auditable**: Decision criteria are human-readable in markdown rather than hidden in model weights.
* **Portable**: Skills work across over 20 services, including Claude Code, OpenAI Codex, Amazon Bedrock AgentCore, AWS Strands Agents SDK, Kiro, and Amazon Quick Desktop.
* **Maintainable**: Changes to medical policy or experiment criteria can be updated by editing a text file without retraining the model.

## 🚀 Availability
Released under the MIT-0 license, the collection covers 11 HCLS domains, including drug discovery, genomics, medical imaging, and claims operations. Agents equipped with these skills win 70–86 percent of head-to-head comparisons against those without, with the strongest effect seen in critical thinking (78–85 percent win rate).

To use these skills, the following are required:
* Python 3.10+ with uv and Git.
* A supported AWS service: Kiro (or Kiro CLI), AWS Strands Agents SDK with Amazon Bedrock FM access, AgentCore harness, or Quick Desktop.

For Kiro users, an `install.sh` script installs the skills and a pre-configured agent that handles skill routing automatically.

#HCLS #AIAgents #OpenSource #HealthcareAI #Genomics

---

*Source: [Improving HCLS AI reasoning with open-source agent skills | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/improving-hcls-ai-reasoning-with-open-source-agent-skills/)*
