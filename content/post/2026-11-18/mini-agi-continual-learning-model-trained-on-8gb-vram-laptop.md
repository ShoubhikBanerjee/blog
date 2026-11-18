---
title: "Mini-AGI: Continual Learning Model Trained on 8GB VRAM Laptop"
slug: "mini-agi-continual-learning-model-trained-on-8gb-vram-laptop"
description: "A new continual learning byte-level language model, mini-AGI, has been trained from scratch on a single 8GB VRAM GPU. This model, which stores its weights as ordinary files on disk, can grow new..."
date: 2026-11-18T12:19:35+05:30
tags: [AI, MachineLearning, ContinualLearning, miniAGI, LanguageModel]
categories: ["AI", "Machine Learning", "AI Agents", "Computer Vision", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/14307880?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Mini-AGI: Continual Learning Model Trained on 8GB VRAM Laptop

A new continual learning byte-level language model, mini-AGI, has been trained from scratch on a single 8GB VRAM GPU. This model, which stores its weights as ordinary files on disk, can grow new capacity while training and prune what it doesn't need. It is targeted at a PC or laptop with at least a 6GB VRAM GPU on the board.

## 🔍 Overview
- mini-AGI is a continual learning byte-level language model that assembles its own architecture.
- It trains from scratch on a single 8GB VRAM GPU and keeps learning from everything it reads.
- The model stores its weights as ordinary files on disk and pages them onto the card as it needs them.
- The parameter count is bounded by free disk space rather than by VRAM.
- It grows new capacity while training when it runs short, prunes what nothing asks for, and reads through exactly the same code path it serves on.

## ⚙️ Key details
- The model is pointed to the corpus to constantly read and learn from.
- History - here is the samples from the whole training run history so far.
- You can inspect them yourself to see how the model improved over the course of training/reading the corpus.
- The model is rather a small experiment to show that continual learning from the single stream of data without catastrophic forgetting is possible.
- Furthermore, it is possible on a modest hardware.
- The capabilities would be bounded by the actual hardware, scale, and quality of the data available and the amount of time one willing to spend on training the model.

## 🚀 Availability
- The "final" weights are not published yet.
- The run is still reading its first pass over the corpus, the weights go up once it has been through all of it, which is several weeks away at the current rate.
- If you would like to play with undertrained weights as they are right now, you can find the most recent (9 Nov 2026) snapshot here: https://huggingface.co/Volotat/mini-AGI-undertrained/tree/main

## 💡 Why it matters
- Continual single-stream learning and natural size and processing adaptation to the available resources exactly what I myself expect from an AGI to have.
- It has just a small toy-level memory footprint and hence it is “mini-AGI”.
- The name is a half-joke and not a statement of the current capabilities of the model, but rather the potential and traits it has.
- This is rather a small experiment to show, that continual learning from the single stream of data without catastrophic forgetting is possible.
- Furthermore, it is possible on a modest hardware.
- Which means that almost everyone could train their own version of the model (or simply continue training this one) exactly as they see it fit.

#AI #MachineLearning #ContinualLearning #miniAGI #LanguageModel

---

*Source: [volotat/mini-AGI](https://github.com/volotat/mini-AGI)*
