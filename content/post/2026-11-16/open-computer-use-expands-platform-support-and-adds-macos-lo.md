---
title: "open-computer-use expands platform support and adds macOS Locked Use"
slug: "open-computer-use-expands-platform-support-and-adds-macos-locked-use"
description: "open-computer-use, an open‑source Computer Use service wrapped as MCP, has expanded its platform support and added a macOS locked‑use feature."
date: 2026-11-16T22:14:27+05:30
tags: [OpenAI, ComputerUse, AIAgents, macOS, Accessibility]
categories: ["AI", "Machine Learning", "AI Agents", "Operating Systems", "Software Development"]
image: "https://avatars.githubusercontent.com/u/16201837?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# open-computer-use expands platform support and adds macOS Locked Use

open-computer-use, an open‑source Computer Use service wrapped as MCP, has expanded its platform support and added a macOS locked‑use feature.

## 🔍 Overview
- open-computer-use is an open‑source Computer Use service wrapped as MCP.
- Inspired by OpenAI’s Codex Computer Use.
- Built on Accessibility to create non‑intrusive CUA.

## 🧩 How It Works
- Any AI agent or MCP client can run Computer Use on macOS, Linux, and Windows.
- Gemini CLI connects through MCP to run full Computer Use actions.
- In Codex App and Codex CLI, it matches official experience.

## ⚙️ Key Details
### Installation
- Install the skill directly.
- Install for Codex.
- Install for Claude Code.
- Update an existing global install, including Codex install created above.
- Manually download and install the open‑computer‑use skill.

### Usage
- Call a single Computer Use tool and print the MCP‑style JSON result.
- Run a sequence in one process to reuse element_index state.
- Sequence sleeps 1s between successful operations by default.

### Permissions
- On macOS, run once and grant Accessibility and Screen Recording.
- Windows and Linux do not require this step.
- Check permissions; onboarding opens only when missing.
- macOS: query permission JSON without opening onboarding.

### Configuration
- ocu supports global configuration starting with version 1.0.0.
- Default configuration file: `~/.config/ocu/config.json`.

### Locked Use (macOS)
- Locked Use is now supported on macOS.
- OCU temporarily unlocks the Mac after it has been locked so the agent can continue working.
- Protective services such as a full‑screen shield are in place during use.
- See the Locked Use guide for setup, installed components, and permissions.

### Runtime Requirements (macOS)
| Requirement | Detail |
|-------------|--------|
| macOS version | 14.0 or later |
| Permissions | Accessibility & Screen Recording |
| Steps | Run once to grant permissions |

## 🚀 Availability
- Running on Linux.
- macOS runtime requires macOS 14.0+.
- Windows and Linux require no special permissions.

## 💡 Why it Matters
- Has become one of the most useful workflows for nearly 100 % AI‑generated projects.
- Built on open source, enabling quick setup with the harness template.
- Offers a non‑intrusive, accessibility‑based solution for Computer Use across major OSes.

For more on the methodology behind this project, see the post at https://www.ifuryst.com/blog/2026/speedrunning-the-ai-era/

#OpenAI #ComputerUse #AIAgents #macOS #Accessibility

---

*Source: [iFurySt/open-computer-use](https://github.com/iFurySt/open-computer-use)*
