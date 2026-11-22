---
title: "Metaswarm: AI Agent Orchestration Framework for Production Code"
slug: "metaswarm-ai-agent-orchestration-framework-for-production-code"
description: "Metaswarm is a self-improving multi-agent orchestration framework for Claude Code, Gemini CLI, and Codex CLI, designed to coordinate 23 AI agents and 14 orchestration skills through a complete..."
date: 2026-11-22T12:09:58+05:30
tags: [AIagents, SoftwareDevelopment, TDD, QualityGates, Metaswarm]
categories: ["AI", "AI Agents", "Software Development", "Machine Learning", "Computer Science"]
image: "https://avatars.githubusercontent.com/u/244816?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Metaswarm: AI Agent Orchestration Framework for Production Code

Metaswarm is a self-improving multi-agent orchestration framework for Claude Code, Gemini CLI, and Codex CLI, designed to coordinate 23 AI agents and 14 orchestration skills through a complete software development lifecycle. It has been proven in the field, writing production-level code with 100% test coverage, mandatory TDD, multi-reviewed spec-driven development, and SDLC best practices across hundreds of PRs.

## 🔍 Overview
- A structured 9-phase workflow: Research → Plan (with its Plan Review Gate) → Design Review Gate → Work Unit Decomposition → Orchestrated Execution → Final Review → PR Creation → PR Shepherd → Closure & Learning
- Each work unit runs through IMPLEMENT → VALIDATE → ADVERSARIAL REVIEW → COMMIT
- The orchestrator validates independently (never trusts subagent self-reports), and adversarial reviewers check DoD compliance with file:line evidence

## 🧩 How it works
- 23 agents: phase agents and specialized personas (Researcher, Architect, Coder, Security Auditor, PR Shepherd, etc.)
- Parallel Design Review Gate: 6 specialist agents (PM, Architect, Designer, Security, UX Reviewer, CTO) review in parallel; severity-gated iteration (only `blocker: yes` findings re-run the gate, cap 10 rounds) before human escalation
- Recursive orchestration: Swarm Coordinators spawn Issue Orchestrators, which spawn sub-orchestrators for complex epics (swarm of swarms)
- Uses [BEADS](https://github.com/steveyegge/beads) (`bd` CLI) for issue/task management and dependencies; metaswarm's own `/prime` command handles knowledge priming
- JSONL-based fact store for patterns, gotchas, decisions, and anti-patterns — agents prime from this before every task
- Quality rubrics: Standardized review criteria for code, architecture, security, testing, planning, UX, release engineering, and adversarial spec compliance
- Optionally delegate implementation and review tasks to OpenAI Codex CLI and Google Gemini CLI for cost savings and cross-model adversarial review
- Playwright-based screenshot capture for reviewing web UIs, presentations, and rendered pages
- Autonomous CI monitoring, review comment handling, and thread resolution
- Mandatory quality gate intercepts at every handoff point — agents cannot skip design review, plan review, or knowledge capture
- Approved plans and execution state persist to disk via BEADS, surviving context compaction and session interruption

## ⚙️ Key details
- 18 agents, 13 skills, 15 commands, TDD enforcement, quality gates, spec-driven development
- Coordinate 23 AI agents and 14 orchestration skills through a complete software development lifecycle, from issue to merged PR
- Metaswarm is an extraction of a production-tested agentic orchestration system

## 💡 Why it matters
- Metaswarm demonstrates the potential of AI agent orchestration in production environments, with a proven track record of writing high-quality, tested code
- The framework's structured workflow and quality gates ensure robust, reliable software development
- The use of multiple AI models and adversarial review processes enhances the overall quality and reliability of the code produced

#AIagents #SoftwareDevelopment #TDD #QualityGates #Metaswarm

---

*Source: [dsifry/metaswarm](https://github.com/dsifry/metaswarm)*
