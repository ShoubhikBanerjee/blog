---
title: "NVIDIA Introduces BioNeMo Inference Runtime for Biomolecular Structure Prediction"
slug: "nvidia-introduces-bionemo-inference-runtime-for-biomolecular-structure-prediction"
description: "NVIDIA has introduced the BioNeMo Inference Runtime (BioIR), designed to accelerate supported biomolecular structure-prediction models on NVIDIA GPUs while maintaining a PyTorch workflow."
date: 2026-09-10T22:04:27+05:30
tags: [NVIDIA, BioNeMo, BioIR, Proteomics, PyTorch]
categories: ["AI", "Machine Learning", "Biotechnology", "GPU Computing"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image4-1.webp"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Introduces BioNeMo Inference Runtime for Biomolecular Structure Prediction

NVIDIA has introduced the BioNeMo Inference Runtime (BioIR), designed to accelerate supported biomolecular structure-prediction models on NVIDIA GPUs while maintaining a PyTorch workflow.

## 🔍 Overview
BioIR speeds up model execution using optimized kernels and, where applicable, CUDA Graphs. It supports an end-to-end processor that moves an InputRequest through the following stages:
* Parsing
* Tokenization
* Feature generation
* GPU inference
* PDB or mmCIF writing

## 🧩 How it works
BioIR offers two executor backends for the end-to-end processor workflow:

| Backend | Functionality |
| :--- | :--- |
| Serial | Runs each stage in sequence for one input, completing the full workflow before moving to the next input. |
| Ray | Runs a complete model replica on each GPU in a single node to increase overall throughput for large batches of independent inputs. |

Direct PyTorch integration allows users to construct a supported model (`torch.nn.Module`) or reuse selected modules in custom code.

## ⚙️ Key details
**System Requirements:**
* Python 3.12 or later
* A compatible NVIDIA GPU and driver
* A BioIR wheel or supported development environment
* A staged model checkpoint (such as Boltz-2) and required chemical metadata

**Technical Specifications:**
* **Input Requirements:** Each protein chain requires an A3M MSA. For inputs with multiple non-identical protein chains, paired or unpaired MSAs are accepted.
* **Deployment:** The wheel contains precompiled CUBINs, removing the need for nvcc, CUDA source, CMake, or the CUDA toolkit during runtime use.
* **Capabilities:** The end-to-end processor supports ligand structure prediction, though it does not support ligand-affinity prediction. Because BioIR does not run HHsearch or HMMsearch, users can optionally supply their own templates.
* **Measurement:** `model_inference_time` is the CUDA-synchronized folding-model forward measurement, which excludes parsing, tokenization, feature generation, postprocessing, and writing.

## 💡 Why it matters
BioIR has been utilized in real proteome-scale work, including the expansion of the AlphaFold Database (AFDB). This accelerated the generation of protein-complex structures across 4,777 proteomes, totaling about 31 million candidate complexes, with 1.81 million released as high-confidence predictions.

#NVIDIA #BioNeMo #BioIR #Proteomics #PyTorch

---

*Source: [High-Throughput Structure Prediction with BioNeMo Inference Runtime | NVIDIA Technical Blog](https://developer.nvidia.com/blog/high-throughput-structure-prediction-with-bionemo-inference-runtime/)*
