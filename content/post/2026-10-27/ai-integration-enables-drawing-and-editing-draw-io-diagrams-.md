---
title: "AI Integration Enables Drawing and Editing draw.io Diagrams via Chat"
slug: "ai-integration-enables-drawing-and-editing-draw-io-diagrams-via-chat"
description: "Users can now draw and edit draw.io diagrams by chatting with an AI across web, desktop, and Model Context Protocol (MCP) server environments."
date: 2026-10-27T22:02:24+05:30
tags: [drawio, Diagramming, MCPServer, ClaudeCode, AITools]
categories: ["AI", "Developer Tools", "Artificial Intelligence", "Software Engineering"]
image: "https://avatars.githubusercontent.com/u/34411969?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AI Integration Enables Drawing and Editing draw.io Diagrams via Chat

Users can now draw and edit draw.io diagrams by chatting with an AI across web, desktop, and Model Context Protocol (MCP) server environments.

## 🔍 Overview

By describing a diagram in a single sentence, the AI generates it directly on a real draw.io canvas. Users can subsequently edit the canvas by hand or select specific shapes and instruct the AI on what changes to make.

## ⚙️ Key Features

- **Diagram Generation**: Create architecture diagrams, flowcharts, sequence diagrams, and other visuals from a single sentence. Built-in icon libraries include AWS, Azure, GCP, and Kubernetes.
- **File & Image Inputs**: Upload screenshots or hand sketches for the AI to redraw. Upload PDF, Markdown, code, or other text files to generate diagrams based on their contents.
- **Real-Time Streaming & Highlighting**: When editing via chat, changes stream directly onto the canvas, and newly modified shapes are highlighted.
- **Targeted Selection Editing**: Select specific shapes on the canvas and instruct the AI to modify only the chosen elements.
- **Version Control & Undo**: Every AI edit creates a version card featuring a thumbnail. Users can compare versions with the current canvas, restore previous states, or undo changes. Pressing Ctrl+Z on the canvas also reverses an AI edit in a single step.
- **Standard Canvas Controls**: Diagrams function as standard draw.io files, supporting manual dragging, restyling, double-clicking to rename, multi-page structures, and animated connectors carrying flowing animations.
- **Export Formats**: Files export at any time as `.drawio`, `.png`, `.svg`, or `.drawio.svg`.

## 🧩 Supported Diagram Examples

Prompts tested with Claude Opus 5.5 in Claude Code via the MCP server demonstrate a range of diagram generation capabilities:

- **AWS Architecture**: Generates a highly available web app across two Availability Zones using AWS icons (Route 53, CloudFront with AWS WAF, Application Load Balancer, ECS Fargate services in private subnets, Aurora PostgreSQL with writer/reader, ElastiCache for Redis, S3, NAT gateways, and CloudWatch).
- **Kubernetes Deployment**: Generates a web shop deployment diagram containing an ingress, web and API deployments with services and pods, a Redis StatefulSet with a persistent volume, a ConfigMap, a Secret, and an API autoscaler.
- **Entity-Relationship (ER) Diagrams**: Renders ER diagrams for an online shop detailing entities (customers, addresses, orders, order items, products, categories, payments), primary and foreign keys, and relationship cardinalities.
- **BPMN Process Workflows**: Renders process flows, such as an expense claim process tracking employee submission, manager approval/rejection, finance receipt checks and payment, and return steps for missing receipts.
- **Customer Journey Maps**: Maps customer journeys across five stages (discover, sign up, first payment, everyday use, get help) with actions, touchpoints, feelings, pain points, and opportunities.
- **Animated Connectors**: Produces diagrams featuring flowing connector animations, such as transformer architecture diagrams.

## 🚀 Availability & Specifications

- **Platforms**: Accessible as a web app, a desktop application for Windows, macOS, and Linux, and as an MCP server for AI agents including Claude Code, Cursor, Codex, and VS Code.
- **Model Provider Support**: Supports 25 model providers alongside an OpenAI-compatible preset for custom URLs. User API keys entered in the browser remain locally on the machine. Models that reason display their thinking process.
- **Interface & Languages**: Includes dark mode support and offers an interface available in English, Simplified Chinese, Traditional Chinese, and Japanese.

#drawio #Diagramming #MCPServer #ClaudeCode #AITools

---

*Source: [DayuanJiang/next-ai-draw-io](https://github.com/DayuanJiang/next-ai-draw-io)*
