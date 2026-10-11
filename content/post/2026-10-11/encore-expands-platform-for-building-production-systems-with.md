---
title: "Encore expands platform for building production systems with real infrastructure"
slug: "encore-expands-platform-for-building-production-systems-with-real-infrastructure"
description: "Encore released an update that adds new capabilities for building, testing, and deploying production‑grade systems using real infrastructure throughout the development lifecycle."
date: 2026-10-11T12:03:14+05:30
tags: [Encore, Infrastructure, DevOps, AIAgents]
categories: ["AI", "Cloud Computing", "Infrastructure as Code", "Software Engineering", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/50438175?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Encore expands platform for building production systems with real infrastructure

Encore released an update that adds new capabilities for building, testing, and deploying production‑grade systems using real infrastructure throughout the development lifecycle.

## 🔍 Overview
Encore is the infrastructure platform for the intelligence era, where engineers and AI agents build production systems without waiting on infrastructure.

## 🧩 How It Works
- Run and validate with real infrastructure locally and in preview environments, then deploy to your own AWS or GCP account.
- Declare the resources your app needs (databases, Pub/Sub, object storage, caches, cron jobs, secrets) directly in your code, and `encore run` starts the whole system locally with real Postgres, real Pub/Sub semantics, and distributed tracing.
- Each declaration becomes a node in Encore's application graph.
- Encore runs the migrations and stands up local equivalents on `encore run`, and provisions the cloud equivalents on deploy.
- When you push a change that adds or modifies a resource, Encore diffs the application graph against the environment, provisions whatever is missing in your AWS or GCP account, and rolls out the new code against it.
- Encore separates application semantics from environment-specific configuration.
- In code, you define what resources your app needs, not how each environment should configure them.
- That keeps services portable across clouds, regions, accounts, scale profiles, and local development.
- Encore provisions every resource with sane production defaults, then helps you manage configuration separately from your application code.

## ⚙️ Key Features
- Encore platform dashboard: easy to use knobs for all common settings like process allocation, instance sizes, replicas, etc.
- Your AWS or GCP console: tweak anything directly in your cloud provider console.
- Encore picks up the changes on the next deploy.
- IaC: manage config for Encore‑provisioned resources alongside the rest of your infrastructure via the Terraform provider.
- The same infrastructure model runs locally, in per‑PR preview environments, and in production.
- Local: `encore run` starts the whole system locally: real Postgres, real Pub/Sub semantics, type‑safe service‑to‑service calls, plus a local dashboard with distributed tracing.
- Infrastructure namespaces let multiple branches or agents work in parallel with isolated state.
- Open a pull request and Encore sets up an ephemeral environment and (optionally) branches databases from a seed environment.
- This Lets you do end‑to‑end validation against before merging to a shared staging environment.
- Production: Push to deploy.
- Encore diffs the application graph against the environment, provisions what is missing in your AWS or GCP account, wires up least‑privilege IAM based on the application's code paths, and rolls out the new code.

## 🚀 Availability
The update is available to users who already have Encore set up on AWS or GCP and can be accessed through the standard `encore run` and deployment commands.

## 💡 Why It Matters
By letting developers define *what* resources are needed rather than *how* each environment configures them, Encore makes services portable across clouds, regions, and accounts while keeping configuration separate from application code. This reduces waiting time for infrastructure, enables safe end‑to‑end validation in preview environments, and enforces least‑privilege permissions automatically.

#Encore #Infrastructure #DevOps #AIAgents

---

*Source: [encoredev/encore](https://github.com/encoredev/encore)*
