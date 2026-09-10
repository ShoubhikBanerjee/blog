---
title: "OpenHands Launches Public Extensions Registry for Agent Skills and Plugins"
slug: "openhands-launches-public-extensions-registry-for-agent-skills-and-plugins"
description: "OpenHands has introduced a public extensions registry containing reusable skills and plugins designed to customize agent behavior."
date: 2026-09-10T22:04:27+05:30
tags: [OpenHands, AIagents, SoftwareDevelopment, OpenSource]
categories: ["AI", "AI Agents", "Software Engineering", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/225919603?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# OpenHands Launches Public Extensions Registry for Agent Skills and Plugins

OpenHands has introduced a public extensions registry containing reusable skills and plugins designed to customize agent behavior.

## 🔍 Overview
The `OpenHands/extensions` repository serves as the public registry for integrations, plugins, automations, and reusable skills. The registry currently contains 2 marketplaces with 68 extensions, consisting of 58 skills and 10 plugins.

## 🧩 How it works
Extensions are divided into two primary types:
* **Skills**: Markdown-based guidelines providing instructions and domain-specific knowledge, located in the `skills/` directory.
* **Plugins**: Extensions featuring executable code components such as scripts and hooks, located in the `plugins/` directory.

## ⚙️ Key details
* **Single Source of Truth**: Integration data is managed through hand-authored JSON files located in `integrations/catalog/<id>.json`.
* **Cross-Language Support**: Catalog data is published as both a JS package (`@openhands/extensions`) and a Python package (`openhands-extensions`).
* **Technical Requirements**: The JS package requires Node.js 18.20.0 or newer due to the use of import attributes for JSON modules.
* **Architecture**: 
    * `OpenHands/software-agent-sdk`: Manages canonical API and Agent Server execution.
    * `OpenHands/typescript-client`: Provides typed browser access to the API.
    * `OpenHands/OpenHands`: Manages the Agent Canvas UI.
    * `OpenHands/automation`: Handles sandbox lifecycle orchestration, dispatch, run history, webhooks, and scheduling.

## 🚀 Availability
Specific extensions available in the registry include:

| Extension Name | Type | Description |
| :--- | :--- | :--- |
| add-javadoc | skill | Add comprehensive JavaDoc documentation to Java classes and methods. |
| cobol-modernization | plugin | End-to-end COBOL to Java migration workflow. |
| large-codebase | skill/plugin | 4 extensions (2 skills, 2 plugins) for interacting, improving, and refactoring large codebases. |

#OpenHands #AIagents #SoftwareDevelopment #OpenSource

---

*Source: [OpenHands/extensions](https://github.com/OpenHands/extensions)*
