---
title: "TypeSafe AI Launches Jev as a System One Decision Model"
slug: "typesafe-ai-launches-jev-as-a-system-one-decision-model"
description: "Last week, TypeSafe AI unveiled Jev, the first example of a new category of models they call “System One models.”"
date: 2026-09-22T18:02:41+05:30
tags: [TypeSafeAI, Jev, SystemOne, MachineLearning, Classification]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Software Development"]
author: "Shoubhik Banerjee"
draft: false
---

# TypeSafe AI Launches Jev as a System One Decision Model

Last week, TypeSafe AI unveiled Jev, the first example of a new category of models they call “System One models.”

## 🔍 Overview
Jev functions as a frontier-intelligence function call that takes unstructured state as input and returns typed probabilistic decisions. It is designed for classification tasks such as:
* Spam detection
* Suggesting labels
* Prioritization and ranking

## 💡 How it works
Users compose a “state” object containing a set of name-value pairs, an array of strings, or a string. While the model accepts text inputs, it returns floating point numbers instead of text. 

Jev supports three types of questions:

| Question Type | Description | Output |
| :--- | :--- | :--- |
| Noul | Yes/No questions (short for Bernoulli) | A floating point number between 0 and 1 indicating confidence the statement is true |
| Choice | Picking one from a set of provided options | A confidence score plus a probability distribution across all options |
| Score | Numeric levels with descriptions | A floating point score within the provided range |

## ⚙️ Key details
* **API Capabilities**: The API can accept a single document and as many questions as the context window allows. Questions are evaluated in parallel, meaning multiple questions take a similar amount of time as one.
* **Pricing**: Output is free, and the model charges $0.042 per million input tokens, which is cheaper than OpenAI’s GPT-5 Nano ($0.05/million).
* **Model Variants**: Kev is an example using Qwen 3.5 to produce 0.8B, 4B, and 9B models.

## 🚩 Community Applications
Since its release just under a week ago, several implementations have appeared:
* **jevchat**: Created by Kyle Pena, this turns Jev into a chat model by asking which symbol comes next at every step.
* **jev-leftpad**: Created by Fatih Kadir Akƿn, this implements left-pad using a choice query to determine how many spaces are needed to reach a target length.
* **jev-2048**: Created by Andy Gayton, this uses Jev to play the 2048 sliding puzzle game.
* **JevBench**: A benchmark that has emerged to compare “Jev-class decision models.”

#TypeSafeAI #Jev #SystemOne #MachineLearning #Classification

---

*Source: [Jev introduces a new shape of LLM—System One, aka Decision Models](https://simonwillison.net/2026/Sep/21/jev/)*
