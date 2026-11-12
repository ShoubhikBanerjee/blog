---
title: "LLM 0.37 addresses security vulnerabilities in API key handling"
slug: "llm-0-37-addresses-security-vulnerabilities-in-api-key-handling"
description: "On 11th November 2026, a security update was released for LLM to address two vulnerabilities reported by Daniel de Araujo in GHSA-v9h7-jj4g-f862 and GHSA-r639-rr7r-x72w."
date: 2026-11-12T06:14:14+05:30
tags: [LLM, Security, OpenAI, API]
categories: ["AI", "Software Development", "Artificial Intelligence", "Cybersecurity"]
author: "Shoubhik Banerjee"
draft: false
---

# LLM 0.37 addresses security vulnerabilities in API key handling

## 🔍 Overview
On 11th November 2026, a security update was released for LLM to address two vulnerabilities reported by Daniel de Araujo in GHSA-v9h7-jj4g-f862 and GHSA-r639-rr7r-x72w.

## ⚙️ Key details
The security issues involved the accidental transmission of configured OpenAI API keys to external providers when using OpenAI-compatible API endpoints. The report identified two specific scenarios where this exposure could occur:

* When a key named by api_key_name had not been previously stored.
* When a 'responses: true' model was executed with the '-o chat_completions 1' flag.

## 🧩 How it works
LLM utilizes a mechanism known as 'extra-openai-models.yaml' to facilitate the use of OpenAI-compatible API endpoints from other providers. This mechanism is now managed by the new 'llm openai endpoint add' command introduced in version 0.37.

#LLM #Security #OpenAI #API

---

*Source: [Release: llm 0.37.2](https://simonwillison.net/2026/Nov/11/llm/)*
