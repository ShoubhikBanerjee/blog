---
title: "TorchNeuron Model Support Space Shows Which Transformers Run on AWS Trainium"
slug: "torchneuron-model-support-space-shows-which-transformers-run-on-aws-trainium"
description: "A new Hugging Face Space, **torch‑neuronx‑model‑support**, lets you see whether a given Transformers model runs unmodified on AWS Trainium and provides the exact script to run it yourself."
date: 2026-10-23T22:04:00+05:30
tags: [TorchNeuron, AWS, Trainium, Transformers, ModelSupport]
categories: ["AI", "Machine Learning", "Hardware Acceleration", "Frameworks", "Cloud Computing"]
image: "https://huggingface.co/blog/assets/torch-neuronx-model-support/thumbnail.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# TorchNeuron Model Support Space Shows Which Transformers Run on AWS Trainium

## 🔍 Overview
A new Hugging Face Space, **torch‑neuronx‑model‑support**, lets you see whether a given Transformers model runs unmodified on AWS Trainium and provides the exact script to run it yourself.

## 🛠️ How it works
- Uses the `torch‑neuronx` package, the native PyTorch backend for AWS Trainium.
- Runs Transformers models on Trainium the same way they run on any other device.
- The provided `run.py` script loads the model with `from_pretrained`, shards it when needed, then generates with a static cache and `torch.compile(backend="neuron")`.

## 📊 What the Space displays
- PASS/FAIL result for each model.
- Number of Trainium cores the model is sharded over.
- Wall‑time of the run (compilation included).
- Peak device memory usage.
- The Neuron stack version, required packages, and the `run.py` script used.
- If a model is omitted, the Space explains why (e.g., not prioritized or truly incompatible).

## 📈 Testing methodology
- Tests run on a Trainium2 (`trn2`) instance, typically in the AWS Neuron Deep Learning Container.
- Each model is sharded over the smallest number of Trainium cores that can hold its weights (maximum 16 cores, i.e., four Trainium2 devices).
- Most models use tensor parallelism; Mixture‑of‑Experts models without a tensor‑parallel plan use expert parallelism only.
- The test generates 32 tokens and checks them.
  - On a single core, the tokens are compared with a CPU run of the same checkpoint.
  - When sharded, a small judge model verifies that the text is fluent English.
- A PASS only confirms correctness of the 32‑token output; it says nothing about throughput or longer generations.

## ⚙️ Configurability
- The Space opens on the **Selected** view (our own selection of top‑downloaded and trending models).
- You can switch to **Trending** or **Downloads** views and type part of a model name to look it up.
- Versions of the Neuron compiler (`neuronx‑cc`) and Transformers library can be chosen.
- When a model is left out on purpose, the Space tells you the reason.

## 📌 Current scope
- Only Transformers models are tested.
- The selection is limited to text‑generation and image‑text‑to‑text models.
- Only models that fit on four Trainium2 devices (up to 16 cores) are included.

## 🚀 Getting started
1. Open the Space (it starts on the Selected view).
2. Choose the desired `neuronx‑cc` and Transformers versions.
3. Follow the displayed `run.py` script: install the listed packages, then run on a `trn2` instance.
4. The first run compiles the model’s graphs; subsequent runs can reuse compiled graphs by copying them from the public NEFF cache bucket.

## 🔎 Where the data comes from
- All rows are sourced from the public `aws‑neuron/torch‑neuronx‑model‑support` dataset.
- The dataset contains one Parquet file per pair of `neuronx‑cc` and library versions.
- Each row stores the model’s result, any error, the stack versions, and the `run.py` script that was executed.

Next time you wonder whether a model runs on Trainium, look it up.

![figure](https://huggingface.co/spaces/aws-neuron/torch-neuronx-model-support/resolve/main/thumbnail.jpg)

![figure](https://huggingface.co/blog/assets/hf-torchneuron/thumbnail.png)

#TorchNeuron #AWS #Trainium #Transformers #ModelSupport

---

*Source: [Does Your Model Run on AWS Trainium? Look It Up](https://huggingface.co/blog/torch-neuronx-model-support)*
