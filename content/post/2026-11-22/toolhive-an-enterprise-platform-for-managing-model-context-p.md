---
title: "ToolHive: An enterprise platform for managing Model Context Protocol servers"
slug: "toolhive-an-enterprise-platform-for-managing-model-context-protocol-servers"
description: "ToolHive is an enterprise-grade platform designed for running and managing Model Context Protocol (MCP) servers. It allows organizations to run any MCP server securely, instantly, and anywhere,..."
date: 2026-11-22T22:08:30+05:30
tags: [ToolHive, MCP, Kubernetes, EnterpriseAI, DevSecOps]
categories: ["AI", "AI Infrastructure", "Developer Tools", "Security", "Cloud Computing"]
image: "https://avatars.githubusercontent.com/u/110237746?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# ToolHive: An enterprise platform for managing Model Context Protocol servers

ToolHive is an enterprise-grade platform designed for running and managing Model Context Protocol (MCP) servers. It allows organizations to run any MCP server securely, instantly, and anywhere, addressing the need for secure and observable MCP infrastructure in production environments.

## 🔍 Overview
ToolHive addresses the challenges of managing MCP servers by providing a modular architecture that streamlines secure server management and integration. Unlike most MCP solutions that are SaaS-based, ToolHive allows companies to self-host their MCP registry and gateway, which is particularly useful when compliance requirements prohibit sensitive information from being processed by SaaS providers. The platform includes a Kubernetes operator, enabling teams to declare policies and integrate with identity and observability stacks using familiar tools and patterns.

## 🧩 How it works
At its core, ToolHive wraps every MCP server in an isolated container with a minimal permission file that does not include local credentials. This isolation helps enforce security standards. The platform uses semantic tool search to reduce token usage by up to 85%. When configured with an authentication source, ToolHive enforces identity and access policy per request, giving platform teams the observability required for production environments. It also provides audit logs and configurable identity enforcement to address security concerns regarding shadow MCP use by developers.

## ⚙️ Key details
The platform offers a range of features for managing MCP infrastructure, including:
- Defining dedicated endpoints for secure and efficient team access to tools
- Orchestrating multiple tools into a virtual MCP using a deterministic workflow engine
- Centralizing control of security policy, authentication, authorization, and auditing
- Integrating with Identity Providers (IdP) for Single Sign-On (SSO) via OIDC/OAuth compatibility
- Customizing and filtering tools and descriptions to improve performance and reduce token usage
- Connecting with local clients such as Claude Desktop, Cursor, VS Code, and VS Code Server
- Curating a catalog of trusted servers for quick discovery and deployment
- Integrating with the official MCP registry and adding custom MCP servers
- Grouping servers based on role or use case
- Managing the registry via an API-driven interface or embedding it in existing workflows
- Verifying provenance and signing servers with built-in security controls
- Providing preset configurations and permissions for a frictionless user experience

## 🚀 Availability
ToolHive supports flexible deployment options to suit different organizational needs. Users can deploy MCP servers in the cloud via Kubernetes for enterprise scalability, or run them locally via Docker or Podman. Additionally, the platform can proxy remote MCP servers securely for unified management. Organizations can pilot the entire platform and, when ready to scale, leverage Stacklok’s added capabilities and expert team support.

#ToolHive #MCP #Kubernetes #EnterpriseAI #DevSecOps

---

*Source: [stacklok/toolhive](https://github.com/stacklok/toolhive)*
