---
title: "Amazon Bedrock Adds Web Search API for AI Agents"
slug: "amazon-bedrock-adds-web-search-api-for-ai-agents"
description: "AI agents increasingly handle work that depends on what changed today, such as security advisories, product releases, prices, and regulations. A model’s training data can’t answer those questions, so..."
date: 2026-11-11T18:02:06+05:30
tags: [B, e, d, r, o, c, k, W, e, b, S, e, a, r, c, h, A, I, A, g, e, n, t, s, L, a, n, g, C, h, a, i, n, A, W, S, S, e, c, u, r, i, t, y]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "A", "I", "A", "g", "e", "n", "t", "s", ",", "C", "l", "o", "u", "d", "C", "o", "m", "p", "u", "t", "i", "n", "g", ",", "S", "o", "f", "t", "w", "a", "r", "e", "D", "e", "v", "e", "l", "o", "p", "m", "e", "n", "t"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-22037-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Adds Web Search API for AI Agents

AI agents increasingly handle work that depends on what changed today, such as security advisories, product releases, prices, and regulations. A model’s training data can’t answer those questions, so agents need web search. For production use, teams also need results they can cite, and control over which sources count.

## 🌐 Overview
The Web Search API in Amazon Bedrock AgentCore is now available. It gives agents and applications current web results through a single API call, signed with the AWS credentials they already use.

## ⚙️ Key Details
*   AWS serves every query from a web index that Amazon operates, and doesn’t send it to a third‑party search engine.
*   Each result includes the page’s title, URL, publication date, and an extract relevant to the query.
*   Requests can include or exclude domains, and limit results to a publication date range.
*   There’s no search API key to store or rotate.
*   Web Search on Amazon Bedrock AgentCore is also available through AgentCore Gateway.
*   For LangChain developers, the AgentCore web search tool in LangChain’s AWS integration now calls the Web Search API.
*   The tool can also hold rules that the model can’t change, such as a date window, a source blocklist, and a search budget.
*   It works with LangChain agents, with LangGraph, the orchestration framework that runs them, and with Deep Agents, which adds subagents, a virtual filesystem, and context compression.
*   The Web Search API needs one IAM action on one resource that AWS owns, so the statement is the same in every account.
*   Web Search and model calls are billed per use.
*   One run of the watch makes at most 12 searches.

## 🧩 Use Case: The Watch
Every morning, the watch checks whether anything new affects the open source packages and container base images the team ships. It researches three package ecosystems in parallel, while your code keeps the date window, the blocklist, and the search budget out of the model’s control.

In our test, the three branches finished in 36 seconds, against 99 seconds one after another. A run starts the graph with the watchlist and the watch window. Inside each branch, the agent calls an Anthropic Claude model in Amazon Bedrock. The model decides what to search for and, at the end, produces structured findings.

The branch’s search tool adds the date window and the blocklist to each query. It calls the Web Search API with a request signed with AWS Signature Version 4 (SigV4). Each branch keeps only findings that its sources support and that fall inside the window. The examples use the US East (N. Virginia) Region (us-east-1).

The watch can’t let the model choose the date window, the trusted sources, or the number of searches. Every search carries the blocklist and the date floor, and a model’s own arguments could only narrow them.

## 🚀 Availability
On AWS Lambda, Amazon Elastic Container Service (Amazon ECS), or Amazon Bedrock AgentCore runtime, your agent calls the API with its execution role. One function call gives an agent current, cited search results.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-22037-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-22037-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-22037-3.png)

#B #e #d #r #o #c #k #, # #W #e #b #S #e #a #r #c #h #, # #A #I #A #g #e #n #t #s #, # #L #a #n #g #C #h #a #i #n #, # #A #W #S #, # #S #e #c #u #r #i #t #y

---

*Source: [Build a daily dependency watcher with LangGraph and Amazon Bedrock AgentCore web search | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-a-daily-dependency-watcher-with-langgraph-and-amazon-bedrock-agentcore-web-search/)*
