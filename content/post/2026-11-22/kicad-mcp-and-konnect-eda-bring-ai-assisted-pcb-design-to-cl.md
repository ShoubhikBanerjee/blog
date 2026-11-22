---
title: "KiCAD MCP and Konnect-EDA Bring AI-Assisted PCB Design to Claude"
slug: "kicad-mcp-and-konnect-eda-bring-ai-assisted-pcb-design-to-claude"
description: "KiCAD MCP and Konnect-EDA introduce Model Context Protocol implementations that enable Large Language Models like Claude to directly interact with KiCAD for printed circuit board design automation."
date: 2026-11-22T12:09:58+05:30
tags: [KiCAD, EDA, Claude, ModelContextProtocol, PCBDesign]
categories: ["AI", "Hardware Design", "AI Agents", "Open Source", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/11727006?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# KiCAD MCP and Konnect-EDA Bring AI-Assisted PCB Design to Claude

KiCAD MCP and Konnect-EDA introduce Model Context Protocol implementations that enable Large Language Models like Claude to directly interact with KiCAD for printed circuit board design automation.

## 🔍 Overview

KiCAD MCP is an open-source (MIT) and actively maintained Model Context Protocol implementation for KiCAD. Meanwhile, Konnect is now Konnect-EDA at Orchis.ai, growing out of the earlier mixelpixx/Konnect repository which is now archived and replaced by Konnect-EDA. Built on the MCP 2025-06-18 specification, these tools allow users to describe what they want to build and let AI handle the EDA work.

## 🧩 How it works

- Runs locally on your machine and sends nothing to Orchis.ai
- Native KiCad 10 plugin utilizing a single Rust binary working through KiCad's official IPC API and kicad-cli, with no SWIG
- Compatible with claude.ai, Claude Desktop, Claude Code, VS Code, and any MCP client
- Integrates with Nimrod, a web-research MCP server providing quality-scored Google search, clean webpage extraction, and deep multi-source research

## ⚙️ Key details

- Konnect-EDA features 228 tools in 21 on-demand toolsets covering schematic capture, PCB layout and routing, ERC and DRC, design-review audits, and JLCPCB parts and fab outputs
- KiCAD MCP Server provides comprehensive tool schemas and real-time project state access
- Bundled skills for Claude and Codex
- Nimrod pricing: 1 credit per search, extraction always free, with a free 50-credit trial and no card required

| Capability | Description |
| --- | --- |
| Project Setup | Initializing and setting up projects |
| Schematic & Layout | Schematic editing, component placement, custom symbol and footprint generation, and routing |
| Verification & Export | DRC/ERC checks, design-review audits, and production file exports |
| Integrations | JLCPCB parts catalog with pricing/stock data and Freerouting via Java/Docker |
| Traceability | Visual feedback via snapshots and session logs |

## 🚀 Availability

- Cross-platform support for Windows, Linux, and macOS
- Free for students, hobbyists, and individual developers now and after version 1.0 with a free license key; only businesses need a commercial license
- Everyone can use it free during the beta
- Installation guides and downloads are available on GitHub and at konnect-eda.orchis.ai, with the Nimrod registry at ai.orchis/nimrod

#KiCAD #EDA #Claude #ModelContextProtocol #PCBDesign

---

*Source: [mixelpixx/KiCAD-MCP-Server](https://github.com/mixelpixx/KiCAD-MCP-Server)*
