---
title: "LLM Chess Benchmark Evaluates AI Reasoning Through Multi-Turn Games"
slug: "llm-chess-benchmark-evaluates-ai-reasoning-through-multi-turn-games"
description: "LLM Chess is a new benchmark that evaluates Large Language Models (LLMs) on their reasoning and instruction-following abilities in an agentic setting. The benchmark engages LLMs in multi-turn dialogs..."
date: 2026-11-27T12:07:17+05:30
tags: [LLMBenchmark, ChessAI, LargeLanguageModels, AIReasoning, MultiTurnDialog]
categories: ["AI", "Artificial Intelligence", "Machine Learning Benchmark", "AI Agents", "Game AI"]
image: "https://avatars.githubusercontent.com/u/7947027?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LLM Chess Benchmark Evaluates AI Reasoning Through Multi-Turn Games

LLM Chess is a new benchmark that evaluates Large Language Models (LLMs) on their reasoning and instruction-following abilities in an agentic setting. The benchmark engages LLMs in multi-turn dialogs to play chess against opponents like a Random Player or the Komodo Dragon chess engine.

## 📊 Evaluation Landscape

### Early Challenges (2024)

- Early models struggled with basic instruction following
- Common issues included hallucinating illegal moves
- Dialog failures were frequent during gameplay

### 2025 Advancements

- Advanced reasoning models (o1, o3, o4-mini) saturated random-based evaluations
- Dragon opponent added for Elo anchoring with stronger challenge

## ⚙️ Key Metrics

- **Chess Skill**: Win/Loss outcomes and Elo ratings
- **Durability**: Game duration reveals capability trade-offs

## 🚀 Availability and Setup

### Repository Access

- Clone the repository: `git clone https://github.com/maxim-saplin/llm_chess.git`
- Create a virtual environment (recommended): `uv sync`

### Configuration Steps

- Configure LLMs: Copy `.env.sample` to `.env` and add your API keys
- Supports multiple providers: Azure OpenAI, OpenAI, Anthropic, Google, Groq, and local models via Autogen
- For local models, ensure Ollama or LM Studio is running

### Chess Engine Setup

| Component | Installation | Configuration |
|-----------|--------------|---------------|
| Dragon | Download binaries from https://komodochess.com/installation.htm | Place in `dragon/` directory, set `llm_chess.dragon_path` |
| Stockfish | Install via `brew install stockfish` (macOS) or equivalent | Set `llm_chess.stockfish_path` (default: `/opt/homebrew/bin/stockfish`) |

### Running Simulations

- Run a single simulation: `uv run llm-chess`
- Default: Random Player (white) vs. LLM (black)
- Logs saved to `_logs/` with JSON details
- Run multiple simulations: `uv run python run_multiple_games.py` (default: 42 games)

### Game Rules and Outcomes

- Max 200 moves (100 per player)
- Max 10 turns per LLM move
- Max 3 mistakes per dialog (exceeding → LLM loss)

### Results Interpretation

- **Win/Loss**: Checkmate or opponent errors/timeouts
- **Draw**: Max moves reached, stalemate, insufficient material, repetition, or 75-move rule
- Moves use UCI notation with Unicode board visualization

### Provider Configuration

- Provider choice from `MODEL_KIND_W` / `MODEL_KIND_B` in `.env`
- Use `azure` for classic Azure chat-completions deployments
- Use `azure_responses` for Azure deployments requiring the Responses API

### Dragon Difficulty Levels

| Level | Elo Rating |
|-------|------------|
| 1 | 250 |
| 2 | 375 |
| 3 | 500 |
| 4 | 625 |
| 5 | 750 |
| 6 | 875 |
| 7 | 1000 |

#LLMBenchmark #ChessAI #LargeLanguageModels #AIReasoning #MultiTurnDialog

---

*Source: [maxim-saplin/llm_chess](https://github.com/maxim-saplin/llm_chess)*
