---
title: "NVIDIA releases RFD4-Proteina, an open BioNeMo model for joint protein sequence and structure design"
slug: "nvidia-releases-rfd4-proteina-an-open-bionemo-model-for-joint-protein-sequence-and-structure-design"
description: "NVIDIA released RFD4-Proteina, an open BioNeMo model co-developed with the University of Washington’s Institute for Protein Design, that jointly designs protein sequences and all-atom structures..."
date: 2026-10-21T22:03:49+05:30
tags: [ProteinDesign, BioNeMo, NVIDIA, DrugDiscovery]
categories: ["AI", "Machine Learning", "Computational Biology", "Bioinformatics", "AI Models"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image4-2-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA releases RFD4-Proteina, an open BioNeMo model for joint protein sequence and structure design

NVIDIA released RFD4-Proteina, an open BioNeMo model co-developed with the University of Washington’s Institute for Protein Design, that jointly designs protein sequences and all-atom structures using reward-guided inference-time search.

## 🔍 Overview
- Co-developed with Institute for Protein Design at UW School of Medicine.
- Uses patterns learned from nature to navigate protein design space.
- Co-designs sequences and all-atom structures.
- Employs reward-guided inference-time search to focus compute on promising candidates.

## 🧩 How it works
- Combines explicit backbone coordinates with latent representation, learned sequence and atomistic variables.
- Autoencoder decoder outputs sequence and all-atom structure together, removing need for separate inverse-folding step (e.g., ProteinMPNN).
- During inference-time reasoning search, model denoises generation trajectories, scores designs, retains/branches promising partial states, continues until criteria met.
- Rewards can measure geometry, interactions, or independent prediction confidence.
- Uses residue-level latent representation (vs atom-level) to avoid memory blow-up.
- Diffusion process engineered to cut sampling steps from ~400 (Proteina-Complexa) to ~60, focusing compute where reasoning matters.
- Inference-time search accelerated via CUDA-accelerated oracles (OF3, physics methods like tmol).
- Model and kernels co-designed with cuEquivariance and BioNeMo Inference Runtime (BIR) teams for speed/scalability.
- AtomWorks provides molecular data layer for structure preparation and design annotations.

## ⚙️ Key details
- Supports Linux GPU host, Python 3.12; follow repo setup guide, need supported NVIDIA GPU.
- Self-host requirements: x86_64 or arm64 Linux meeting NIM prerequisites, Docker, NVIDIA Driver, NVIDIA Container Toolkit, NGC API key.
- NIM API endpoint (not for production): HTTP via build.nvidia.com, Shell/Python scripts, no local GPU/model install.
- Accepts annotated CIFs or condition specification plus source structure.
- Uses repository’s cropped PD-L1 structure from PDB 5O45 as target; fix sequence/backbone, allow side-chain repack, direct binder generation to hotspot atoms Tyr56, Met115, Tyr123.
- Generated binder length 100–150 residues, free sequence and coordinates.
- Install repo environment with current uv release (validated 0.12.24); update uv if present to recognize CUDA 13.2.
- Setup caches Hugging Face model bundle including paired autoencoder.

## 🚀 Availability
- Available as open model for training, inference, method development, direct control over sampling code.
- Also available as NIM microservice for rapid inference deployment with HTTP interface.

## 💡 Why it matters
- Faster and uses less memory than prior RFD3 due to residue-level latent representation, reduced diffusion steps, CUDA-accelerated oracles, and co-designed kernels.
- Enables efficient protein binder design with integrated sequence-structure generation.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image4-2-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image2-6.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/03/Proteina-Complexa-Binder-1920x1080-1-660x370.png)

#ProteinDesign #BioNeMo #NVIDIA #DrugDiscovery

---

*Source: [Design Proteins with RFD4-Proteina Using Reward-Guided Inference-Time Search | NVIDIA Technical Blog](https://developer.nvidia.com/blog/design-proteins-with-rfd4-proteina-using-reward-guided-inference-time-search/)*
