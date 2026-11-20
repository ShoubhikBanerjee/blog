---
title: "Kong Gateway introduces AI traffic capabilities and MCP governance"
slug: "kong-gateway-introduces-ai-traffic-capabilities-and-mcp-governance"
description: "Kong or Kong Gateway is a cloud-native, platform-agnostic, scalable API, LLM, and MCP Gateway distinguished for its high performance and extensibility via plugins. It provides advanced AI traffic..."
date: 2026-11-20T14:26:01+05:30
tags: [Kong, APIGateway, MCP, LLM, Kubernetes, DevOps]
categories: ["AI", "API Management", "AI Infrastructure", "DevOps", "Cloud Computing"]
image: "https://avatars.githubusercontent.com/u/962416?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Kong Gateway introduces AI traffic capabilities and MCP governance

Kong or Kong Gateway is a cloud-native, platform-agnostic, scalable API, LLM, and MCP Gateway distinguished for its high performance and extensibility via plugins. It provides advanced AI traffic capabilities with multi-LLM support, semantic security, MCP traffic security and analytics, and more.

## 🔍 Overview

Kong serves as the central layer for orchestrating microservices or conventional API traffic - and agentic LLM and MCP as well - with ease. By providing functionality for proxying, routing, load balancing, health checking, and authentication, it manages traffic across various architectures.

## ⚙️ Key details

- **Universal LLM API**: Routes traffic across multiple providers including OpenAI, Anthropic, GCP Gemini, AWS Bedrock, Azure AI, Databricks, Mistral, and Huggingface.
- **MCP Capabilities**: Includes MCP traffic governance, security, observability, and autogeneration from any RESTful API.
- **AI Features**: Offers over 60 features such as AI observability, semantic security, caching, and semantic routing.
- **Security and Routing**: Supports authentication and authorization via JWT, basic auth, OAuth, and ACLs.
- **Traffic Management**: Handles proxying, SSL/TLS termination, and connectivity support for L4 or L7 traffic.
- **Plugins**: Includes 60+ plugins for traffic controls, rate limiting, request/response transformations, logging, and monitoring.

| Feature | Description |
| :--- | :--- |
| Advanced Routing | Load balancing and health checking configurable via RESTful admin API or declarative configuration |
| Deployment Models | Supports Declarative Databaseless Deployment and Hybrid Deployment with control plane/data plane separation |
| Kubernetes Support | Runs natively on Kubernetes thanks to its official Kubernetes Ingress Controller |
| Plugin Hub | Showcases Kong Inc. and community-developed plugins like AWS Lambda, Correlation ID, and Response Transformer |

## 🚀 Availability

Kong is available in various distributions depending on the deployment environment. Users can run it in the cloud, on bare metal, or using containers.

- **Cloud**: Sign up for a free trial of Kong Konnect to get started with a cloud-hosted solution.
- **Docker**: The docker-compose distribution is suggested for easy setup. A docker installation procedure is also available for running the Kong Gateway in DB-less mode.
- **Installation**: To start with the Docker distribution, clone the Docker repository and navigate to the compose folder. Use the command `$ KONG_DATABASE=postgres docker-compose --profile database up` to start the Gateway stack.

Once started, the Gateway is available on localhost with the following ports:

- **8000**: Send traffic to your service via Kong.
- **8001**: Configure Kong using Admin API or via decK.
- **8002**: Access Kong's management Web UI (Kong Manager).

#Kong #APIGateway #MCP #LLM #Kubernetes #DevOps

---

*Source: [Kong/kong](https://github.com/Kong/kong)*
