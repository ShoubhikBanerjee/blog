---
title: "Development of CRISS RAG Assistant for Cancer Registry Guidance"
slug: "development-of-criss-rag-assistant-for-cancer-registry-guidance"
description: "Researchers have developed the Cancer Registry Intelligent Support System (CRISS), a retrieval-augmented generation (RAG) conversational assistant designed to provide rapid, citation-supported access..."
date: 2026-09-25T22:04:20+05:30
tags: [RAG, CancerRegistry, LLM, HealthcareAI]
categories: ["AI", "Machine Learning", "Health Informatics", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# Development of CRISS RAG Assistant for Cancer Registry Guidance

Researchers have developed the Cancer Registry Intelligent Support System (CRISS), a retrieval-augmented generation (RAG) conversational assistant designed to provide rapid, citation-supported access to registry guidance.

## 🔍 Overview
The study evaluated CRISS based on three primary goals:
* Supporting accurate and citation-supported responses.
* Improving the access to and interpretation of relevant guidance.
* Supporting training and helpdesk use while maintaining human oversight of final abstraction decisions.

## 🧩 How it works
CRISS utilizes a domain-specific knowledge base built from national cancer registry standards. The process involves:
* Segmenting standards into metadata-tagged passages.
* Indexing those passages as dense embeddings.
* Using retrieved passages to generate citation-grounded responses via a large language model (LLM).

## ⚙️ Key details
Evaluations compared RAG configurations against non-RAG baseline models from the Gemini and GPT families using LLM-as-a-Judge protocols across easy, medium, and hard questions.

| Model Type | Grounding Performance | Specialization/Behavior |
| :--- | :--- | :--- |
| RAG (Overall) | Mean scores: 0.62 (easy), 0.56 (medium), 0.59 (hard) | Outperformed non-RAG, especially as difficulty increased |
| Non-RAG | Mean scores: 0.29 (easy), 0.26 (medium), 0.29 (hard) | Lower semantic-similarity and grounding scores |
| Proprietary RAG | Strongest on easy and medium questions | Generally more cautious |
| Local RAG | Ranked highest on hard questions | High performance on complex queries |

## 💡 Why it matters
Domain-specific RAG improves evidence grounding and response quality for cancer registry questions. CRISS demonstrates the potential for human-centered, citation-grounded AI to support cancer registrars while preserving human oversight for final coding decisions.

#RAG #CancerRegistry #LLM #HealthcareAI

---

*Source: [CRISS: A Retrieval-Augmented AI Chatbot for Assisting Cancer Registrars](https://arxiv.org/abs/2609.29075v1)*
