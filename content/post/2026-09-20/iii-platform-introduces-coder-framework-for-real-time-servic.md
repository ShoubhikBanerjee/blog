---
title: "iii platform introduces CODER framework for real-time service composition"
slug: "iii-platform-introduces-coder-framework-for-real-time-service-composition"
description: "iii is a new development platform designed to compose, observe, discover, extend, and react (CODER) to every service in a stack in real time. It unifies backend concerns such as queues, cron, HTTP,..."
date: 2026-09-20T22:01:28+05:30
tags: [iii, backend, microservices, agents, devops]
categories: ["AI", "Software Engineering", "Cloud Computing", "AI Agents"]
image: "https://avatars.githubusercontent.com/u/258310054?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# iii platform introduces CODER framework for real-time service composition

iii is a new development platform designed to compose, observe, discover, extend, and react (CODER) to every service in a stack in real time. It unifies backend concerns such as queues, cron, HTTP, state, observability, agents, and sandboxes into a single system surface.

## 🧩 How it works

iii functions through three core primitives:

* Workers: Processes that register with the iii engine and define triggers and functions. Examples include TypeScript API services, Python data pipelines, and Rust microservices.
* Triggers: Declarative events that cause a function to run. These include direct calls, HTTP endpoints, cron schedules, queue subscriptions, state changes, or stream events.
* Functions: Units of work with a stable identifier that receive input, perform tasks, and return output.

## ⚙️ Key details

| Primitive | Description |
| :--- | :--- |
| Worker | A registered process that contains functions and triggers |
| Trigger | A declarative event that executes a function |
| Function | A specific unit of work with a stable identifier |

When a worker joins the catalog, every other worker is notified and can call it immediately. Developers define workers in a `worker-compose.yaml` file and deploy them using the `iii compose --up` command. 

## 💡 Why it matters

This architecture extends to AI agents. When a task requires a capability not currently in the system, an agent can add a worker, discover its functions, and call them using the same interface as a developer. This allows applications and agents to extend the system at runtime.

## 🚀 Availability

Available workers can be browsed at workers.iii.dev.

#iii #backend #microservices #agents #devops

---

*Source: [iii-hq/iii](https://github.com/iii-hq/iii)*
