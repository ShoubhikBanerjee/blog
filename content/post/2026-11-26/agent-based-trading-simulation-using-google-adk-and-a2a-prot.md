---
title: "Agent-based trading simulation using Google ADK and A2A protocol"
slug: "agent-based-trading-simulation-using-google-adk-and-a2a-protocol"
description: "This project demonstrates an agent-based trading system simulation featuring distinct agents for trading logic and risk management, communicating via the Agent-to-Agent (A2A) protocol. It includes a..."
date: 2026-11-26T06:13:08+05:30
tags: [AIAgents, GoogleADK, A2AProtocol, TradingSimulation, FastAPI]
categories: ["AI", "AI Agents", "Trading Systems", "Developer Tools", "Simulation"]
image: "https://avatars.githubusercontent.com/u/11586922?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Agent-based trading simulation using Google ADK and A2A protocol

This project demonstrates an agent-based trading system simulation featuring distinct agents for trading logic and risk management, communicating via the Agent-to-Agent (A2A) protocol. It includes a web-based simulator UI to configure, run, and visualize trading strategy performance.

## 🔍 Overview
The system consists of three main services interacting via HTTP and the A2A protocol. It leverages the open A2A protocol for standardized, interoperable communication between the agents. This allows agents built with different frameworks to discover capabilities and interact securely. The entire system is built using the Google Agent Development Kit (ADK).

## 🧩 How it works
The workflow begins with the Simulator UI taking simulation parameters from the user. It then runs the market simulation loop. For each step, the Simulator calls the AlphaBot service via A2A tasks/send, providing current market data and portfolio state. AlphaBot analyzes the data to determine a potential trade signal. If a trade is proposed, AlphaBot calls the RiskGuard service with the trade proposal and portfolio state. RiskGuard evaluates the proposal against configured rules and returns an approval or rejection. The final trade decision is returned to the Simulator, which updates the portfolio state based on executed trades.

## ⚙️ Key details
- **AlphaBot**: Implements a Simple Moving Average (SMA) crossover strategy to propose trades. It calculates SMAs to determine BUY or SELL signals and updates its internal state.
- **RiskGuard**: Evaluates trade proposals against configurable risk rules, including max position size and max portfolio concentration.
- **Simulator UI**: A FastAPI-based web application that allows users to configure parameters for market conditions (initial price, volatility, trend), trading strategy (SMA periods, trade quantity), and risk rules. It visualizes results using Plotly, displaying price action, SMA indicators, portfolio value, and trade execution markers on interactive charts.
- **Deployment**: Includes scripts for easy local execution and deployment to Google Cloud Run. Dockerfiles are provided for building container images for each service, facilitated by Google Cloud Build.

## 💡 Why it matters
The project demonstrates how distinct AI agents can collaborate in a specific domain (trading) using the A2A protocol. By separating trading logic from risk management into different agents that communicate securely and interoperably, the system showcases a modular approach to building multi-agent applications where each agent focuses on a specialized task.

#AIAgents #GoogleADK #A2AProtocol #TradingSimulation #FastAPI

---

*Source: [kweinmeister/agentic-trading](https://github.com/kweinmeister/agentic-trading)*
