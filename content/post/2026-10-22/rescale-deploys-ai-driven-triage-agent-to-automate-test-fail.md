---
title: "Rescale Deploys AI-Driven Triage Agent to Automate Test Failure Classification"
slug: "rescale-deploys-ai-driven-triage-agent-to-automate-test-failure-classification"
description: "Rescale, the digital engineering platform built for the AI era, has released an AI‑driven triage agent that automatically classifies and routes nightly end‑to‑end test failures."
date: 2026-10-22T22:11:45+05:30
tags: [AI, DevOps, Automation, AWS]
categories: ["AI", "Artificial Intelligence", "DevOps", "Cloud Computing", "Software Engineering"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/How-Rescale-built-an-AI-triage-agent-with-Strands-Agents-and-AI-DLC.png"
author: "Shoubhik Banerjee"
draft: false
---

# Rescale Deploys AI-Driven Triage Agent to Automate Test Failure Classification

Rescale, the digital engineering platform built for the AI era, has released an AI‑driven triage agent that automatically classifies and routes nightly end‑to‑end test failures.

## 🔍 Overview
- The agent is part of Rescale’s AI‑Driven Development Lifecycle (AI‑DLC) framework and runs on AWS.
- It integrates with Rescale’s existing Argo Workflows CI/CD pipeline on Amazon Elastic Kubernetes Service (EKS).

## 🛠️ Problem
- Every engineering team knows the ritual of a nightly test suite that fails.
- An on‑call engineer pulls logs, classifies the root cause, and routes it to the right team, only to repeat the process the next morning.
- At scale, across distributed services and dozens of repositories, this ritual becomes a full‑time job hidden inside an on‑call rotation.
- Hundreds of test cases run in the suite; each failure requires classification, prioritization, and routing to the appropriate team.
- After routing, engineers must gather evidence from multiple logging and monitoring systems and several source repositories before debugging can begin.
- Unresolved failures can block weekly production releases and pull several teams into hours of coordination.

## 🤖 Solution – AI‑Driven Development Lifecycle (AI‑DLC)
- AI generates work plans, writes code, and proposes architecture, but it surfaces decision points and asks clarifying questions rather than guessing.
- Humans validate and steer at each step; AI executes, humans decide.
- Development is organized into focused group sessions:
  - **Mob Elaboration** – defining requirements together.
  - **Mob Construction** – building together while AI handles implementation.
- In mob sessions, Rescale engineers answer the AI’s questions collectively and approve each plan before the AI proceeds, eliminating assumptions.

## ⚙️ Implementation
- The triage agent automates classification and routing of nightly end‑to‑end test failures.
- It runs as a step within Rescale’s Argo Workflows CI/CD pipeline on Amazon EKS.
- When a nightly Playwright suite of hundreds of test cases produces failures, the pipeline triggers the triage agent pod.
- The team moved from problem definition to a staging deployment in **five days** and to production within **weeks**.

## 🚀 Impact
- Engineers no longer spend significant time on the repetitive but critical task of manually classifying test failures.
- Automation frees engineers to focus on architecture, product judgment, and the context required to operate complex distributed systems.
- The solution demonstrates how AI can be applied across the engineering lifecycle—from planning and design through testing and operations—while keeping engineers accountable for the result.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21405-1-3.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21405-2-3.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21405-3-3.jpg)

#AI #DevOps #Automation #AWS

---

*Source: [How Rescale built an AI triage agent with Strands Agents and AI-DLC | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-rescale-built-an-ai-triage-agent-with-strands-agents-and-ai-dlc/)*
