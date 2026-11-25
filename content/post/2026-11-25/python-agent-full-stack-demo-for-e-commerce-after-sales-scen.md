---
title: "Python Agent Full-Stack Demo for E-Commerce After-Sales Scenarios"
slug: "python-agent-full-stack-demo-for-e-commerce-after-sales-scenarios"
description: "A new full-stack Python Agent demonstration for e-commerce after-sales scenarios has been released, migrating a Dify prototype into a code implementation."
date: 2026-11-25T12:10:39+05:30
tags: [Python, FastAPI, LangGraph, LangChain, Vue3, AIagents]
categories: ["AI", "Artificial Intelligence", "Software Development", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/275657804?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Python Agent Full-Stack Demo for E-Commerce After-Sales Scenarios

A new full-stack Python Agent demonstration for e-commerce after-sales scenarios has been released, migrating a Dify prototype into a code implementation.

## 🔍 Overview
- The project is a personal learning and technical demonstration utilizing fictional data and fixed demo identities, rather than a production customer service system.
- It covers FastAPI, SQLite, LangChain, LangGraph, Chroma RAG, Langfuse, pytest, Docker Compose, and Vue 3.
- Current test status includes 157 passed pytest tests locally, successful Vue production builds, and an accepted synthetic policy request on Langfuse Cloud v4.86.0.

## 🧩 How it works
- Verifiable policy QA features include policy source citations, evidence display, safe fallback without evidence, and constraint rules for refund time limits, quality issues, logistics, and privacy boundaries.
- Tracked model links record requests, LangGraph nodes, and model generations using the Langfuse Python SDK and LangChain CallbackHandler.
- Security and authentication features map tokens to subjects, while the server reads roles and customer bindings from the SQLite tenant membership table instead of trusting caller-supplied values.

## ⚙️ Key details
| Component | Technology / Detail |
| --- | --- |
| Backend & Architecture | FastAPI, SQLite (`data/support_agent.db`), LangChain, LangGraph, Chroma RAG |
| Frontend & UI | Vue 3, Vite, Dashboard, Intelligent Customer Service, Orders, Approvals, Knowledge Base, Evaluation, and Observability pages |
| Observability & Testing | Langfuse, pytest, Docker Compose, GitHub Actions |
| Constraints | Read-only order queries; approval records `approved_demo` without executing real refunds, address changes, or deletions |

## 🚀 Availability
- Source code and learning materials are available, including five chapters of code walkthroughs, a fault case library, a requirements traceability matrix, and run verification records.
- Run locally using Docker Compose to automatically start mock services and connect the agent, with Vite forwarding `/api` requests to the local FastAPI backend.

#Python #FastAPI #LangGraph #LangChain #Vue3 #AIagents

---

*Source: [KaelLee335/enterprise-support-agent-v2](https://github.com/KaelLee335/enterprise-support-agent-v2)*
