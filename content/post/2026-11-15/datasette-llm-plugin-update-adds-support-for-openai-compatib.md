---
title: "Datasette-llm Plugin Update Adds Support for OpenAI-Compatible Endpoints and Local Models"
slug: "datasette-llm-plugin-update-adds-support-for-openai-compatible-endpoints-and-local-models"
description: "On 14th November 2026, the `datasette-llm` plugin was updated to include support for OpenAI-compatible endpoints. This release allows Datasette to be configured with Large Language Models (LLMs)..."
date: 2026-11-15T22:02:44+05:30
tags: [Datasette, LLM, OpenAI, LocalAI, OpenSource]
categories: ["AI", "Data Science", "Software Development", "Large Language Models"]
image: "https://static.simonwillison.net/static/2026/lmstudio-datasette-agent.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Datasette-llm Plugin Update Adds Support for OpenAI-Compatible Endpoints and Local Models

On 14th November 2026, the `datasette-llm` plugin was updated to include support for OpenAI-compatible endpoints. This release allows Datasette to be configured with Large Language Models (LLMs) hosted on any platform that utilizes the OpenAI pseudo-standard web protocol.

## 🔍 Overview
`datasette-llm` serves as an intermediate plugin for Datasette. Its primary function is to support the configuration of LLMs for use with other plugins within the Datasette ecosystem.

## ⚙️ Key details
This release enables the use of various local and remote model hosting solutions:
*   Supports any endpoint talking the OpenAI pseudo-standard web protocol.
*   Compatible with local model runners including LM Studio, Ollama, and llama.cpp.
*   Note that llama.cpp has recently reached version 1.0.0.
*   Datasette can be initiated via `uvx` to utilize these models.

## 🧩 How it works
By configuring Datasette to connect to a local model, users can run a local server that hosts a Datasette Agent instance. For example, a user can download a database file like `content.db` and use `uvx` to run Datasette powered by a model hosted through LM Studio or Ollama. This setup allows the local model to power the Datasette Agent instance directly.

## 🚀 Availability
The update to `datasette-llm` was released on 14th November 2026.

#Datasette #LLM #OpenAI #LocalAI #OpenSource

---

*Source: [Release: datasette-llm 0.1a11](https://simonwillison.net/2026/Nov/14/datasette-llm/)*
