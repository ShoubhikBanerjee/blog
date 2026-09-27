---
title: "Update to Agent Development Kit with Go Toolkit Support"
slug: "update-to-agent-development-kit-with-go-toolkit-support"
description: "The Agent Development Kit (ADK) has been updated with an open-source, code-first Go toolkit designed for building, evaluating, and deploying AI agents."
date: 2026-09-27T18:01:26+05:30
tags: [GoLang, AIAgents, OpenSource, CloudNative]
categories: ["AI", "AI Agents", "Software Development", "Cloud Computing"]
image: "https://avatars.githubusercontent.com/u/1342004?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Update to Agent Development Kit with Go Toolkit Support

The Agent Development Kit (ADK) has been updated with an open-source, code-first Go toolkit designed for building, evaluating, and deploying AI agents.

## 🔍 Overview
ADK is a modular framework that applies software development principles to the creation of AI agents. It simplifies the orchestration of agent workflows, ranging from simple tasks to complex systems. While optimized for Gemini, the framework is model-agnostic, deployment-agnostic, and compatible with other frameworks.

## ⚙️ Key details
The Go version of ADK leverages Go's performance and concurrency strengths for cloud-native agent applications. Key features include:

* **Idiomatic Go:** Designed to feel natural to Go developers.
* **Code-First Development:** Agent logic, tools, and orchestration are defined directly in Go to provide flexibility, versioning, and testability.
* **Rich Tool Ecosystem:** Supports custom functions, pre-built tools, or the integration of existing tools.
* **Modular Multi-Agent Systems:** Allows for the composition of multiple specialized agents to create scalable applications.
* **Deploy Anywhere:** Supports easy containerization and deployment, specifically for cloud-native environments such as Google Cloud Run.

## 🚀 Availability
Developers can add ADK Go to a project using the following command:
`go get google.golang.org/adk/v2`

Machine-readable documentation is available at `adk.dev/llms.txt` and `adk.dev/llms-full.txt`, both of which are generated from the `adk-docs` repository and include samples and the Go API reference.

## 🧩 Ecosystem Support
ADK is available across several languages and platforms:

| Language/Platform | Link |
| :--- | :--- |
| Python | https://github.com/google/adk-python |
| Java | https://github.com/google/adk-java |
| Kotlin | https://github.com/google/adk-kotlin |
| TypeScript | https://github.com/google/adk-js |
| Web | https://github.com/google/adk-web |

This project is licensed under the Apache 2.0 License, with the exception of `internal/httprr`.

#GoLang #AIAgents #OpenSource #CloudNative

---

*Source: [google/adk-go](https://github.com/google/adk-go)*
