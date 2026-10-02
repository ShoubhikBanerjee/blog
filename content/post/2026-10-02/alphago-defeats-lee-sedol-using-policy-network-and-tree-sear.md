---
title: "AlphaGo defeats Lee Sedol using policy network and tree search"
slug: "alphago-defeats-lee-sedol-using-policy-network-and-tree-search"
description: "On an afternoon in Seoul in March 2016, a program I helped build put a stone on the fifth line of a Go board in what looked like a gift to its human opponent.  AlphaGo won the game, ultimately..."
date: 2026-10-02T18:04:26+05:30
tags: [AlphaGo, Go, AI, MachineLearning, DeepLearning]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Game AI"]
image: "https://wp.technologyreview.com/wp-content/uploads/2026/10/2llm-go.jpg?resize=1200,600"
author: "Shoubhik Banerjee"
draft: false
---

# AlphaGo defeats Lee Sedol using policy network and tree search

On an afternoon in Seoul in March 2016, a program I helped build put a stone on the fifth line of a Go board in what looked like a gift to its human opponent.  AlphaGo won the game, ultimately triumphing 4-1 over Lee Sedol, one of the greatest professional Go players of all time.

## 🔍 Overview
- Move 37 in game two of the five‑game match looked so absurd that some commentators thought it was a programming glitch.
- The move had a roughly one in 10,000 chance of being made by an expert human player.
- AlphaGo’s choice was driven by its search machinery, not by the “intuitive” policy network alone.

## 🧩 How AlphaGo works
- **AlphaGo is made up of two systems.**
- The first, its *policy network*, was trained to guess what move a strong human would play.
- The search component *explicitly constructed and searched a game tree with thousands of branches*, each representing a different possible future.
- As its reasoning progresses, AlphaGo *maintains a record of what it knows about a given position: the game tree*, updating it and eventually synthesizing the information to decide which move to make.

## ♟️ Comparison to Deep Blue
- When Deep Blue defeated then‑reigning world chess champion Garry Kasparov in 1997, it did so by looking six to eight moves ahead per player and evaluating **200 million chess positions per second**, using rules hard‑coded by humans.
- **Go is a vastly more complex game.** A stone’s worth depends on how distant groups and territory unfold over dozens of moves. Computing even a fraction of the possible outcomes would take a supercomputer billions of years.

## 🧠 Cognitive analogy
- A well‑known theory in the behavioral sciences, popularized by Daniel Kahneman, distinguishes between two modes of human thought: *System 1* (fast, gut‑level) and *System 2* (slow, deliberative).
- AlphaGo offered a striking machine analogue of that split: its networks supplied the hunches—*this move looks promising, this position looks won*—and its search supplied the deliberation, testing those hunches against the moves and countermoves that would follow.

## 🤖 Contrast with large language models
- A large language model picks the next token, over and over.
- Researchers have added *chain‑of‑thought* prompting so models can generate intermediate steps that decompose a problem, carry forward partial results, and influence subsequent reasoning.
- The intermediate reasoning is still produced by the same next‑token prediction process, iterated for longer before the model commits to an answer.
- However, these models **typically maintain no explicit, persistent, and inspectable epistemic state**; there is no open ledger of hypotheses, confidence, or evidence.
- Knowledge and reasoning are **inextricably interwoven in the weights of the neural network**—there is no independent, explicitly represented set of beliefs.
- Research has shown that bots often **concoct chain‑of‑thought explanations after the fact**, reaching an answer by one route but reporting another.
- By contrast, AlphaGo’s *game tree* provides an explicit, inspectable record of the variations it considered.

## 📊 Key facts
- AlphaGo won **4‑1** against Lee Sedol.
- Move 37 had a **≈1/10,000** chance of being chosen by a human expert.
- Deep Blue evaluated **200 million** positions per second.
- Go’s outcome space is so large that exhaustive computation would take **billions of years** on a supercomputer.
- AlphaGo’s architecture combines a *policy network* with *tree search* and a *game‑tree data structure*.


![figure](https://wp.technologyreview.com/wp-content/uploads/2026/10/2llm-go.jpg)

#AlphaGo #Go #AI #MachineLearning #DeepLearning

---

*Source: [Don’t be fooled—LLMs don’t reason](https://www.technologyreview.com/2026/10/02/1145639/dont-be-fooled-llms-dont-reason/)*
