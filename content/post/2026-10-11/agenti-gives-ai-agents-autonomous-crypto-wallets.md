---
title: "Agenti Gives AI Agents Autonomous Crypto Wallets"
slug: "agenti-gives-ai-agents-autonomous-crypto-wallets"
description: "A new development called **Agenti** lets any AI agent hold, spend, earn, and receive cryptocurrency on its own, removing the need for human‑mediated payments."
date: 2026-10-11T22:04:07+05:30
tags: [AIAgents, CryptoWallet, AutonomousAI, Blockchain]
categories: ["AI", "Artificial Intelligence", "Blockchain", "AI Agents", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/22895867?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Agenti Gives AI Agents Autonomous Crypto Wallets

A new development called **Agenti** lets any AI agent hold, spend, earn, and receive cryptocurrency on its own, removing the need for human‑mediated payments.

## 🔍 Overview
Agenti provides a crypto wallet that is owned by the AI agent rather than a human, enabling the agent to be funded by its own work, pay for resources, and earn yield when idle.

## 🧩 How it works
- A fresh wallet can be generated for both EVM and Solana chains in a single call, or an existing wallet can be loaded. 
- When an API returns a 402 response, Agenti automatically pays the fee and retries the request. 
- The `@agenti/mcp` package turns every SDK tool into an MCP tool that any LLM client can invoke without writing code. 
- Once configured, you can instruct any LLM with a prompt such as *“Pay for this API and summarize the response”* and the agent will handle the payment and the task.

## ⚙️ Key details
- **Supported LLMs** – Claude, GPT‑4, Llama, Gemini, or any custom model.
- **Supported chains** – EVM and Solana.
- **Compatible clients** – Works with Claude, LangChain, AutoGen, CrewAI, and any MCP client.
- **Payment flow** – Pay x402 APIs, receive USDC, and check balances autonomously.
- **Ownership** – The wallet is owned by the agent, not managed by a human.
- **Economic autonomy** – Agents can fund their own operations, compensate other agents, and earn yield.

| Component | Supported |
| --------- | --------- |
| LLMs      | Claude, GPT‑4, Llama, Gemini, any custom LLM |
| Chains    | EVM, Solana |
| Clients   | Claude, LangChain, AutoGen, CrewAI, any MCP client |

## 🚀 Availability
- The service is hosted at the domain **agenti.cash**.
- The project is not published on npm yet; the `@agenti` scope returns 404 errors (tracked in issue #126).
- Until the first release is tagged, developers can use the repository directly.
- The `@agenti/mcp` package enables MCP‑style tool calls without additional code.

## 💡 Why it matters
- Currently, a human must intervene whenever an AI needs to pay for an API, buy a resource, compensate another agent, or receive payment for its work, which breaks autonomy.
- By giving agents their own wallet, Agenti removes that bottleneck, allowing agents to operate financially independent of humans.
- The mission expressed in the name—**Agenti**—is to equip every AI with the ability to manage money autonomously.


#AIAgents #CryptoWallet #AutonomousAI #Blockchain

---

*Source: [nirholas/agenti](https://github.com/nirholas/agenti)*
