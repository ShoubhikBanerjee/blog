---
title: "LawGlance Transitions to Agentic Retrieval Pipeline for Legal Guidance"
slug: "lawglance-transitions-to-agentic-retrieval-pipeline-for-legal-guidance"
description: "LawGlance, formerly known as Niyam SahaAI, has updated its open-source, people-centric platform to utilize an agentic retrieval pipeline. This initiative provides legal guidance through AI-powered..."
date: 2026-09-22T22:03:42+05:30
tags: [LawGlance, AIAgents, LangGraph, LegalTech, OpenSource]
categories: ["AI", "Artificial Intelligence", "Legal Technology", "Software Development"]
image: "https://avatars.githubusercontent.com/u/182550481?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LawGlance Transitions to Agentic Retrieval Pipeline for Legal Guidance

LawGlance, formerly known as Niyam SahaAI, has updated its open-source, people-centric platform to utilize an agentic retrieval pipeline. This initiative provides legal guidance through AI-powered Retriever-Augmented Generation (RAG) and is developed with support from the Data Science Academy and Curvelogics.

## 🧩 How it works

The platform has moved from a fixed RAG chain to an agentic loop powered by LangGraph. Instead of a single process, the agent autonomously decides when to retrieve documentation, loops until sufficient context is gathered, and then generates a cited final answer. The system utilizes Redis for caching chat history and LLM responses to improve scalability and performance.

## ⚙️ Key details

The backend architecture is organized as follows:

| Component | Function |
| :--- | :--- |
| backend/graph.py | LangGraph agent loop (llm_call, tool_node, final_answer) |
| backend/nodes.py | LangGraph agent loop logic |
| backend/tools.py | Vector-store retrieval tool for the agent |
| backend/retrieval.py | Entry point for the Streamlit application |
| backend/main.py | Optional FastAPI HTTP API |

## 🚀 Availability

LawGlance currently provides support for the following Indian laws, with future plans for international expansion:

* The Indian Constitution
* The Bharatiya Nyaya Sanhita, 2023
* The Bharatiya Nagarik Suraksha Sanhita, 2023
* The Bharatiya Sakshya Adhiniyam, 2023
* The Consumer Protection Act, 2019
* The Motor Vehicles Act, 1988
* Information Technology Act, 2000
* The Protection of Children from Sexual Offences Act (POCSO), 2012
* The Sexual Harassment of Women at Workplace (Prevention, Prohibition and Redressal) Act, 2013

#LawGlance #AIAgents #LangGraph #LegalTech #OpenSource

---

*Source: [lawglance/lawglance](https://github.com/lawglance/lawglance)*
