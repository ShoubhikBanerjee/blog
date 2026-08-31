---
title: "NVIDIA BioNeMo Agent Toolkit integrates with Claude Science for scientific workflows"
description: "NVIDIA and Anthropic have integrated the NVIDIA BioNeMo Agent Toolkit into Claude Science, enabling AI agents to discover, launch, and call BioNeMo NIM microservices for complex scientific workflows..."
date: 2026-08-31T22:56:10+05:30
tags: [AIagents, BioNeMo, ClaudeScience, NVIDIA, scientificAI, proteinfolding]
categories: [AI]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/AdobeStock_842772489-e1787092703768-660x370.webp"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA BioNeMo Agent Toolkit integrates with Claude Science for scientific workflows

NVIDIA and Anthropic have integrated the NVIDIA BioNeMo Agent Toolkit into Claude Science, enabling AI agents to discover, launch, and call BioNeMo NIM microservices for complex scientific workflows in biology, chemistry, genomics, and drug discovery.

## 🔍 Overview
The NVIDIA BioNeMo Agent Toolkit packages over a decade of NVIDIA BioNeMo life sciences models, libraries, and workflows into agent-callable skills. Built to run with any agent framework, it enables complex scientific workflows using specialized domain expertise. On internal benchmarks, BioNeMo skills raise task correctness from 60% to 100% and roughly double token efficiency.

## 🧩 How it works
- The toolkit provides agent-callable skills for biology, chemistry, genomics, and drug discovery.
- It integrates with Claude Science, Anthropic’s AI workbench for scientific research, to run protein structure prediction workflows.
- Agents can discover, launch, and call BioNeMo NIM microservices directly within Claude Science.
- Workflows can include multiple-sequence alignment (MSA) and protein folding models like OpenFold3 and Boltz-2.

## ⚙️ Key details
Claude Science runs in various configurations based on GPU location and security requirements. This tutorial focuses on running the platform on a machine with a GPU, requiring:
- Access to a workstation or cloud machine with an NVIDIA L40S GPU or NVIDIA H100 GPU.
- Claude Science installed.
- Approximately 700 GB of storage (UniRef30 database: ~490 GB; Boltz-2 and OpenFold3 containers: 30–40 GB total).

To set up:
1. In Claude Science, select **Customize > Compute > NVIDIA BioNeMo NIM > Connect**.
2. Import the BioNeMo Agent Toolkit skills from GitHub.
3. Add an NVIDIA API key and connect to local endpoints (Docker containers using the host GPU).
4. Download and launch local BioNeMo NIM containers for msa-search, OpenFold3, and Boltz-2 microservices.
5. Run a smoke test on each microservice to confirm they are healthy.

## 🧪 Example workflow
The tutorial examines the Seh1 protein and a predicted Mio-family partner from *Paracoccidioides lutzii*, a fungus that causes paracoccidioidomycosis. The workflow:
- Retrieves protein sequences from UniProt.
- Generates MSAs for single-chain and species-paired sequences using the GPU-accelerated MSA Search NIM.
- Predicts structures for a single chain and a two-chain complex using OpenFold3 and Boltz-2 NIMs.
- Compares results across models to evaluate structural differences.

The agent creates unpaired and paired alignments, recording source sequences and checksums for verification. In this run, the search returned 202 sequences for each protein.

## 💡 Why it matters
- AI agents can now orchestrate domain-specific tools for scientific problems, such as protein folding or molecular characterization.
- The toolkit simplifies the use of specialized models and workflows, reducing the complexity of managing different environment requirements or APIs.
- Integration with Claude Science enables end-to-end scientific research workflows, from hypothesis generation to experiment execution.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/image-16.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/image-17.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/image-18.webp)

#AIagents #BioNeMo #ClaudeScience #NVIDIA #scientificAI #proteinfolding

---

*Source: [Run NVIDIA BioNeMo NIM Microservices for Protein Structure Prediction in Claude Science | NVIDIA Technical Blog](https://developer.nvidia.com/blog/run-nvidia-bionemo-nim-microservices-for-protein-structure-prediction-in-claude-science/)*
