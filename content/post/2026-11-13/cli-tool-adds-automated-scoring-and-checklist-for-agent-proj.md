---
title: "CLI tool adds automated scoring and checklist for Agent projects"
slug: "cli-tool-adds-automated-scoring-and-checklist-for-agent-projects"
description: "The agent-handbook project released a new CLI tool that can automatically score an Agent codebase against a five‑pillar checklist drawn from its 31‑chapter Chinese handbook."
date: 2026-11-13T22:02:12+05:30
tags: [AIAgents, CLI, AgentHandbook, DevTools]
categories: ["AI", "Artificial Intelligence", "Software Development", "AI Agents"]
image: "https://avatars.githubusercontent.com/u/264079252?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# CLI tool adds automated scoring and checklist for Agent projects

The agent-handbook project released a new CLI tool that can automatically score an Agent codebase against a five‑pillar checklist drawn from its 31‑chapter Chinese handbook.

## 🔍 Overview
- Provides a static scan of your Agent project and reports which of the five pillars are missing.
- Maps gaps to the exact chapter and section of the handbook that explains the concept.
- Generates a 0–10 score with concrete remediation suggestions.

## 🛠️ How it works
- The command `handbook doctor .` walks the code, checks it against the five‑pillar criteria, and produces a Markdown table of results.
- `--md` flag outputs the table so it can be pasted directly into an issue, README, or PR comment; the tool also posts the report automatically to the PR and the Job Summary.
- `handbook search <keyword>` performs full‑text search across all 31 chapters, returning chapter, line number, and snippet.
- `handbook new <name>` scaffolds a new Agent project that already satisfies all five pillars, earning a full score.
- The tool runs with zero dependencies, using only the Python standard library, and works offline because the handbook data is bundled with the package.

## ⚙️ Key details
| Command | Description |
|---|---|
| `handbook doctor .` | Five‑pillar health check, 0–10 score + remediation suggestions |
| `handbook doctor . --md` | Output Markdown table for easy inclusion in issues/README |
| `handbook search 上下文压缩` | Full‑text search of the 31‑chapter handbook, returns chapter, line, snippet |
| `handbook new my-agent` | Generate an Agent skeleton that scores full on the five pillars |

| Chapter | Title | Quick note |
|---|---|---|
| 00 | [新手快速入门](chapters/00-quickstart.md) | 10 分钟跑通第一个 Agent |
| 03 | [LangGraph 图编排](chapters/03-langgraph.md) | 复杂工作流、状态机、检查点 |
| 04 | [CrewAI 多智能体](chapters/04-crewai.md) | 角色化团队、任务分配 |
| 06 | [LlamaIndex RAG](chapters/06-llamaindex-rag.md) | 文档检索、向量数据库 |
| 07 | [Dify 低代码](chapters/07-dify.md) | 可视化拖拽构建应用 |
| 11 | [MCP 协议](chapters/11-mcp.md) | 标准化工具连接（含 2026 无状态核心） |
| 14 | [记忆系统与状态管理](chapters/14-memory-state.md) | Mem0、向量记忆、持久化 |
| 16 | [调试与可观测性](chapters/16-observability.md) | LangSmith、日志、追踪 |
| 19 | [Agent 通用工具箱](chapters/19-agent-toolkit.md) | 工具注册中心 / 审批网关 / 成本追踪等六件套 |
| 20 | [Codex CLI](chapters/20-codex-cli.md) | MCP 集成、四种审批模式、沙箱隔离 |
| 21 | [DeepSeek Harness](chapters/21-deepseek-harness.md) | 四种模式、SWE‑bench、500+ 插件 |
| 23 | [Aider 代码助手](chapters/23-aider-codestory.md) | 多模型、Git 集成、会话恢复 |
| 25 | [Harness Engineering](chapters/25-harness-engineering.md) | 五支柱：2026 年 Agent 上生产的分水岭 |
| 30 | [Agent 评测体系](chapters/30-agent-evals.md) | EDD、三层评测金字塔 |
| 99 | [中英对照术语表](chapters/99-glossary.md) | 130+ 术语通俗解释 |

## 🚀 Availability
- Install with zero‑install `uvx`: `uvx agent-handbook doctor .`
- Alternative: `pipx run agent-handbook doctor .`
- Or install via pip: `pip install agent-handbook`
- The handbook chapters are packaged together, so the tool works fully offline.

## 💡 Why it matters
- Turns the handbook’s methodology into a concrete, checkable checklist for developers.
- Provides immediate, actionable feedback directly in the code review workflow.
- Low barrier to entry: no external dependencies, works offline, and integrates with common CI/PR systems.
- Supports rapid prototyping (`handbook new`) and ongoing quality monitoring (`handbook doctor`).

#AIAgents #CLI #AgentHandbook #DevTools

---

*Source: [Xwh630/ai-agent-handbook](https://github.com/Xwh630/ai-agent-handbook)*
