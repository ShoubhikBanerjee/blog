---
title: "AWS adds automated remediation workflow using Lambda Durable Functions, EventBridge, and Bedrock"
slug: "aws-adds-automated-remediation-workflow-using-lambda-durable-functions-eventbridge-and-bedrock"
description: "AWS announced an update that extends the AWS DevOps Agent with an automated remediation workflow built on AWS Lambda Durable Functions, Amazon EventBridge, and Amazon Bedrock. The new flow keeps the..."
date: 2026-10-07T22:09:50+05:30
tags: [AWS, DevOpsAgent, LambdaDurable, Bedrock, Automation]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "DevOps", "Systems Engineering"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-20995-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS adds automated remediation workflow using Lambda Durable Functions, EventBridge, and Bedrock

AWS announced an update that extends the AWS DevOps Agent with an automated remediation workflow built on AWS Lambda Durable Functions, Amazon EventBridge, and Amazon Bedrock. The new flow keeps the DevOps Agent in its safe observe‑and‑report mode while adding a controlled, programmable step that can apply fixes after a single approval.

## 🔍 Overview
- Reducing the time between incident detection, investigation, and remediation is a critical priority for organizations running production workloads on AWS.
- When an issue arises, on‑call engineers often need to diagnose the problem across components, identify the root cause, and apply a fix, sometimes in the middle of the night.
- AWS DevOps Agent automatically triages incidents, provides root‑cause analysis (RCA) and recommended actions, but typically does **not** modify production resources directly.
- The update demonstrates how to combine AWS Lambda Durable Functions, Amazon EventBridge, and Amazon Bedrock to automate the remediation step, turning investigation summaries into pre‑validated fixes ready for a single approval.

## 🧩 How it works
1. **Investigation completed** – AWS DevOps Agent emits an event containing symptoms, findings, and RCA.
2. **Event receipt** – Amazon EventBridge receives the investigation‑completion event and triggers the `devops-agent-trigger` Lambda function with the investigation content.
3. **Orchestration start** – The trigger function packages the summary and starts the `devops-agent-remediation-durable` durable function.
4. **Bedrock analysis** – The durable function sends the investigation context to Amazon Bedrock. Bedrock analyzes the findings and searches an allowlist of approved Lambda tools (e.g., `devops-agent-lambda-tool`).
5. **Tool selection** – Bedrock proposes specific remediation actions based on the findings and the available tools.
6. **Read‑only execution** – For read‑only actions, the durable function runs the selected tools autonomously.
7. **Mutating actions** – For infrastructure‑changing actions, the workflow pauses and waits for a human approval signal.
8. **Approval & execution** – After approval, the durable function applies the remediation actions using the selected tools.
9. **Iterative loop** – The function operates as an agentic loop, repeatedly invoking Bedrock, executing approved tools, and feeding results back until remediation is complete.

## ⚙️ Key details
- **Lambda Durable Functions** can run for up to one year without extra infrastructure, automatically checkpoint progress, suspend during long‑running tasks, and recover from failures.
- The orchestrator enforces a **curated allowlist** of remediation tools; each tool is a purpose‑built Lambda function that performs a single, well‑scoped action (e.g., reading a Lambda configuration or updating an IAM policy statement).
- **Read‑only tools** run autonomously; **mutating tools** cause the durable function to pause and wait for an approve/reject signal.
- The approval signal accepts an arbitrary JSON payload, allowing parameter overrides or reviewer observations to be fed back into the Bedrock conversation before execution.

| Tool (allowlist) | Purpose |
|-------------------|---------|
| `devops-agent-lambda-tool` | Performs a specific, well‑scoped action such as reading a Lambda configuration or updating an IAM policy statement |

## 🚀 Benefits
- Reduces mean time to resolution (MTTR) by preparing pre‑validated changes that require only a single approval click.
- Frees on‑call engineers from repetitive diagnostic and manual remediation steps.
- Keeps automated actions auditable and safe by limiting execution to an approved set of Lambda tools.
- Allows the workflow to pause for minutes, hours, or days without consuming compute resources, then resume exactly where it left off.

## 📈 Real‑world impact – Cornerstone Orion AI
- Cornerstone OnDemand’s Orion AI, built with Amazon Bedrock and Strands Agents, reduced database incident diagnosis time from **45 minutes** to **10 minutes** (a 78 % reduction).
- A three‑person team delivered Orion AI in six months.
- Orion AI also eliminated a 15‑minute reporting lag between SRE and data teams, reduced redundant alerts by a median of 65 %, and collapsed a four‑step manual handoff into a single interaction.
- The system illustrates the same principles: AI‑driven investigation, curated tool execution, and human‑in‑the‑loop approval.

The updated workflow shows how AWS services can be combined to automate the full incident‑response loop while preserving control and auditability.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-20995-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-20995-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-20995-3.png)

#AWS #DevOpsAgent #LambdaDurable #Bedrock #Automation

---

*Source: [Automate remediation post AWS DevOps Agent investigation | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/automate-remediation-post-aws-devops-agent-investigation/)*
*Source: [How Cornerstone OnDemand cut database diagnosis by 78% with Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-cornerstone-ondemand-cut-database-diagnosis-by-78-with-amazon-bedrock/)*
