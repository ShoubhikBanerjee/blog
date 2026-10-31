---
title: "Amazon Bedrock AgentCore adds Session Endpoints for secure in‑session app access"
slug: "amazon-bedrock-agentcore-adds-session-endpoints-for-secure-insession-app-access"
description: "Amazon Bedrock AgentCore now offers **Session Endpoints**, a way to open an application that runs inside an isolated agent session directly from a browser."
date: 2026-10-31T18:02:12+05:30
tags: [AmazonBedrock, AIAgents, SessionEndpoints]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "AI Agents", "Developer Tools"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/28/ML-22062-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore adds Session Endpoints for secure in‑session app access

Amazon Bedrock AgentCore now offers **Session Endpoints**, a way to open an application that runs inside an isolated agent session directly from a browser.

## 🔍 Overview
- AgentCore is a platform to build, connect, and optimize agents at scale, supporting any agent framework and foundation model.
- Each agent session runs in its own isolated microVM.
- A Session Endpoint provides an authenticated URL that forwards HTTP methods, paths, query strings, bodies, and WebSocket connections to ports you allow inside the session.

## 🧩 How it works
- When you call **CreateAgentRuntime**, you specify `allowedPorts` (1–5 entries, each a single port or a range within 8000‑12000, excluding reserved platform ports).
- The runtime starts the session; the **InvokeAgentRuntime** response includes the Session Endpoint URL in the `X-Amzn-Bedrock-AgentCore-Runtime-Session-Endpoint-Url` header (exposed by SDKs as `sessionEndpointUrl`).
- Your client always connects to port 443; a hostname prefix selects the target port inside the session.
- All request types—HTTP/1.1, HTTP/2 (including server‑sent events and gRPC), and WebSocket—pass through the Session Endpoint.

## ⚙️ Key details
- **Port binding:** Allowing a port does not start a server; your application must listen on the port bound to `0.0.0.0`.
- **Session lifetime:** The URL is short‑lived and requires valid credentials on every request.
- **Differentiation:** A Session Endpoint is separate from the runtime endpoint (e.g., `DEFAULT`) that controls which agent version callers reach.
- **Sample structure:** The provided sample (in the `14-remote-access` folder of the `agentcore-samples` GitHub repo) has four parts:
  1. A coding agent running on port 8080 that edits website files via list, read, write, and edit tools.
  2. A Vite development server started on port 8090 that serves the site and pushes hot‑reload changes over a WebSocket.
  3. `PreviewApp` on the developer machine opens `http://localhost:8088`, adds credentials to each request/WebSocket handshake, and forwards traffic to the session.
  4. A local preview page showing a chat pane on the left and the live website on the right.

### Port usage table
| Port | Purpose |
|------|---------|
| 8080 | Agent runtime that edits files |
| 8090 | Vite development server with hot‑reload |

## 🔐 Security & access control
- **IAM runtimes:** Each HTTP request, HTTP/2 stream, and WebSocket handshake carries an AWS Signature Version 4 (SigV4) signature. Callers need the `bedrock-agentcore:InvokeAgentRuntimeProxy` permission on both the runtime and its endpoint.
- **JWT runtimes:** Requests carry a bearer token instead of SigV4.
- Knowing the Session Endpoint URL alone does **not** grant access; valid credentials are required for every request.
- The Session Endpoint forwards only traffic to ports you have explicitly allowed.

## 🚀 Development workflow
- Use the Session Endpoint URL to build, test, and review agent output while the session is active.
- The walkthrough demonstrates HTTP 1.1 and WebSocket communication.
- To serve the finished application to end‑users, deploy it to a hosting service such as **AWS Amplify Hosting**.

## 📦 Deploying to production
- Continue to use the runtime endpoint (e.g., `DEFAULT`) for versioned agent access.
- `InvokeAgentRuntime` resolves through the runtime endpoint, allowing separate development and production versions and enabling promotion or rollback without changing callers.
- For full guidance, refer to the "Connect to runtime sessions through a session endpoint" documentation.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/28/ML-22062-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/28/ML-22062-2.gif)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/28/ML-22062-3.jpg)

#AmazonBedrock #AIAgents #SessionEndpoints

---

*Source: [Preview web apps live as your coding agent builds them with Amazon Bedrock AgentCore runtime | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/preview-web-apps-live-as-your-coding-agent-builds-them-with-amazon-bedrock-agentcore-runtime/)*
