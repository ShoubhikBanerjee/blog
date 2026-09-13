---
title: "Agentic Awesome Skills Releases AAS Core V17.1.0"
slug: "agentic-awesome-skills-releases-aas-core-v17-1-0"
description: "Agentic Awesome Skills has released V17.1.0, featuring AAS Core, a local, agent-first control plane for catalog discovery, stack validation, and planning backed by over 2,115 agentic skills."
date: 2026-09-13T18:02:33+05:30
tags: [AASCore, AIagents, MCP, OpenSource]
categories: ["AI", "AI Agents", "Software Development", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/184072420?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Agentic Awesome Skills Releases AAS Core V17.1.0

Agentic Awesome Skills has released V17.1.0, featuring AAS Core, a local, agent-first control plane for catalog discovery, stack validation, and planning backed by over 2,115 agentic skills.

## 🔍 Overview

AAS Core provides a local control plane for complete catalog search, agent-owned selection, manifest validation, planning, and diagnosis. It is an independent community project and is not affiliated with, sponsored by, endorsed by, or authorized by Google.

## 🧩 How it works

Agents such as Claude or Codex inspect a project and choose exact skills from the local AAS catalog. The process follows these parameters:

* **Selection:** Core does not rank, recommend, exclude, or hide skills.
* **Validation:** The read-only `compose_stack` tool validates the agent-owned selection in memory.
* **Persistence:** A client or the `aas` CLI can persist the selection as `aas-stack.json` to produce an immutable plan before any target change.
* **Agent Requirements:** MCP session instructions require agents to evaluate the full project surface—including architecture, domain behavior, data, integrations, testing, security, UX, deployment, and maintenance—to compare candidates and cover capabilities with non-redundant skills.
* **Limitations:** Core records and validates selections but does not certify semantic completeness. Apply and recovery features remain experimental and are outside the supported preview path.

## ⚙️ Key details

### Components and Tooling

| Component | Description |
| :--- | :--- |
| AAS Core | Local control plane for discovery, selection, validation, and planning |
| Local MCP | Offers tools for skill searching, reading, and stack composition/inspection |
| CLI | Tool used to persist selections as `aas-stack.json` |
| Workbench | Browser-local companion discovery and review surface |
| Catalog | Hosted companion discovery surface |

### Local MCP Toolset

* `search_skills`
* `get_skill`
* `list_skill_files`
* `read_skill_file`
* `compose_stack`
* `inspect_stack`
* `diff_stack`
* `export_selection_evidence` (read-only)
* `inspect_selection_evidence` (read-only)

## 🚀 Availability

* **Current Release:** V17.1.0
* **Canonical Source:** GitHub repository
* **Security Support:** Snyk
* **Pending Updates:** Changes under [Unreleased], such as complete bundle inspection and Workbench evidence import, require a subsequent release.

#AASCore #AIagents #MCP #OpenSource

---

*Source: [sickn33/agentic-awesome-skills](https://github.com/sickn33/agentic-awesome-skills)*
