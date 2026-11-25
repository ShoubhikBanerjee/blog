---
title: "Automated AI paper writing skill pack for coding agents released"
slug: "automated-ai-paper-writing-skill-pack-for-coding-agents-released"
description: "A new open-source skill pack has been released that enables standard coding agents to execute the multi-agent pipeline defined in the PaperOrchestra framework, turning unstructured research materials..."
date: 2026-11-25T18:07:47+05:30
tags: [PaperOrchestra, AIAgents, AutomatedResearch, CodingAgents, LaTeX]
categories: ["AI", "AI Agents", "Research Automation", "Developer Tools", "Academic Writing"]
image: "https://avatars.githubusercontent.com/u/29639685?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Automated AI paper writing skill pack for coding agents released

A new open-source skill pack has been released that enables standard coding agents to execute the multi-agent pipeline defined in the PaperOrchestra framework, turning unstructured research materials into submission-ready LaTeX papers. The tool operates without requiring API keys or LLM SDK dependencies, delegating all language model reasoning and web search capabilities to the host agent's native tools.

## 🔍 Overview
The project transforms the specific prompts, schemas, halt rules, and verification pipelines from the PaperOrchestra paper into host-agent-executable skills. It supports a wide range of coding agents, including Claude Code, Cursor, Antigravity, Cline, Aider, OpenCode, and OpenClaw. The underlying PaperOrchestra framework, defined by Song, Y., Song, Y., Pfister, T., and Yoon, J., utilizes a five-agent pipeline that outperforms single-agent and tree-search baselines on the `PaperWritingBench` benchmark, showing absolute win margins of 50–68% on literature review quality and 14–38% on overall quality.

## 🧩 How it works
The system consists of a top-level driver skill and several specialized sub-skills that coordinate the paper writing process. The pipeline allows Steps 2 and 3 to run in parallel.

*   **`paper-orchestra`**: The top-level driver that coordinates the other six skills.
*   **`outline-agent`**: Step 1. Converts idea, log, template, and guidelines into a structured outline JSON containing plotting, literature review, and section plans.
*   **`plotting-agent`**: Step 2. Executes the plotting plan, renders plots and conceptual diagrams, and captions them.
*   **`literature-review-agent`**: Step 3. Conducts web searches, verifies candidates via Semantic Scholar, and drafts the Introduction and Related Work sections with high citation integration.
*   **`section-writing-agent`**: Step 4. Drafts remaining sections in a single multimodal call, builds tables from experimental logs, and splices figures.
*   **`content-refinement-agent`**: Step 5. Runs simulated peer review and applies strict halt rules to accept or revert changes.
*   **`paper-writing-bench`**: Reverse-engineers raw materials from existing papers to build benchmark cases.
*   **`paper-autoraters`**: Executes the paper's own automated raters for citation F1, literature review quality, and side-by-side paper quality.
*   **`claim-evidence-audit`**: An optional post-pipeline skill that maps claims to log numbers, figures, or verified citations and enforces coverage thresholds.

## ⚙️ Key details
Each skill is composed of three distinct components that ensure deterministic behavior where possible:

*   `SKILL.md`: A dense instruction document the host agent reads and follows.
*   `references/`: Contains verbatim paper prompts, JSON schemas, rubrics, halt rules, and example outputs.
*   `scripts/`: Purely deterministic local helpers for JSON schema validation, Levenshtein fuzzy matching, BibTeX formatting, deduplication, LaTeX sanity checks, and coverage gates.

There are no network calls, LLM calls, or API keys embedded within the skill scripts. An optional pre-pipeline skill aggregates scattered coding-agent history into the structured `idea.md` and `experimental_log.md` inputs required by PaperOrchestra. If these inputs already exist, this aggregation step is skipped, and the main pipeline proceeds directly. Users can trigger this by pointing their agent at a directory containing research notes.

## 🚀 Availability
The skill pack is designed for developers and researchers using coding agents who need to automate the transition from experimental logs to formal academic papers. It requires no special environment setup beyond the host coding agent's capabilities, as it relies on the agent's native tools for LLM reasoning and web search.

#PaperOrchestra #AIAgents #AutomatedResearch #CodingAgents #LaTeX

---

*Source: [Ar9av/PaperOrchestra](https://github.com/Ar9av/PaperOrchestra)*
