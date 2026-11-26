---
title: "New LSRP*-LA Planner Solves Large-Agent MAPF with Scalable Asynchronous Coordination"
slug: "new-lsrp-la-planner-solves-large-agent-mapf-with-scalable-asynchronous-coordination"
description: "Researchers have introduced LSRP*-LA, a novel multi-agent path finding (MAPF) planner designed for large agents with asynchronous actions. Unlike prior approaches, LSRP*-LA scales to 800 agents,..."
date: 2026-11-26T12:19:42+05:30
tags: [multiagentpathfinding, roboticsplanning, asynchronousagents, pathfindingalgorithm, scalableAI]
categories: ["AI", "Artificial Intelligence", "Robotics", "Algorithms", "Computer Science"]
author: "Shoubhik Banerjee"
draft: false
---

# New LSRP*-LA Planner Solves Large-Agent MAPF with Scalable Asynchronous Coordination

Researchers have introduced LSRP*-LA, a novel multi-agent path finding (MAPF) planner designed for large agents with asynchronous actions. Unlike prior approaches, LSRP*-LA scales to 800 agents, improves solution quality over time, and delivers near-optimal results for complex scenarios involving agents that occupy multiple cells.

## 📌 Overview

Multi-Agent Path Finding (MAPF) aims to calculate collision-free paths for multiple agents moving from start to goal locations while minimizing total path costs. Traditional MAPF methods assume:

- Each agent occupies a single vertex
- All agents act synchronously

These constraints limit real-world applicability. Existing planners that relax both assumptions either struggle with scalability or fail to refine solutions effectively.

## 🧩 What's New

The newly proposed LSRP*-LA addresses these limitations by supporting:

- Large agents that occupy multiple cells
- Asynchronous actions among agents

It builds upon LSRP*, a prior scalable and anytime planner with asynchronous capabilities, extending it to handle spatially larger agents.

## ⚙️ Key Details

| Feature | Description |
|---------|-------------|
| Scalability | Handles up to 800 agents on diverse maps |
| Anytime Improvement | Continues enhancing solution quality post-initial output |
| Path Cost Efficiency | Achieves roughly half the cost of synchronous planners for large agents |
| Agent Size Support | Designed specifically for agents occupying multiple cells |

## 🚀 Availability

The paper titled *"LSRP*-LA: Scalable and Anytime Multi-Agent Path Finding for Large Agents with Asynchronous Actions"* was submitted on 25 Nov 2026. A PDF and experimental HTML version are available online.

## 💡 Why It Matters

LSRP*-LA represents a significant advancement in robotics planning by overcoming two major limitations in existing MAPF algorithms. Its ability to scale efficiently while improving paths over time makes it especially valuable for deployments involving numerous spatially complex agents.

#multi-agentpathfinding #roboticsplanning #asynchronousagents #pathfindingalgorithm #scalableAI

---

*Source: [LSRP*-LA: Scalable and Anytime Multi-Agent Path Finding for Large Agents with Asynchronous Actions](https://arxiv.org/abs/2611.33793v1)*
