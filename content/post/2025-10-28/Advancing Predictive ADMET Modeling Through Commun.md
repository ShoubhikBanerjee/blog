---
title: "Advancing Predictive ADMET Modeling Through Community-Driven Science: The ExpansionRx-OpenADMET Blind Challenge"
description: "A comprehensive overview of the ExpansionRx-OpenADMET Blind Challenge on Hugging
Face, featuring high-quality ADMET datasets for drug discovery and community-driven predictive
modeling benchmarking."
date: 2025-10-28T00:51:14.346455+05:30
tags: ["ADMET", "Drug Discovery", "Machine Learning", "Hugging Face", "Open Science", "Pharmaceuticals", "Bioinformatics", "Cheminformatics", "Predictive Modeling", "Community Challenge"]
categories: ["Life Sciences", "Machine Learning", "Open Science"]
image: "NA"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🧪 Advancing Predictive ADMET Modeling Through Community-Driven Science: The
ExpansionRx-OpenADMET Blind Challenge

*Published October 27, 2025*

We're excited to announce that **the ExpansionRx-OpenADMET Blind Challenge is now live on Hugging Face!** 🚀

This community challenge aims to advance benchmarking of predictive models for Absorption,
Distribution, Metabolism, Excretion, and Toxicology (**ADMET**) properties by providing a
high-quality experimental dataset that participants can use to train and evaluate their models.

## 🎯 The Challenge

Small molecules continue to be the foundation of modern drug discovery, representing nearly 75%
of FDA drug approvals in the last decade. Their ease of synthesis and tunable properties make
them highly versatile therapeutic agents. However, predicting how these molecules behave in the
body (including how long they persist, where they go, and whether they interact with other
targets), is extremely challenging.

Collectively, these **ADMET** properties sit at the heart of the assay cascade and can make or
break preclinical candidate molecules.

**OpenADMET** is an open-science initiative that aims to tackle these challenges by integrating
structural biology, high-throughput experimentation, and computational modeling to improve ADMET
 prediction. A key part of these efforts is organizing blind challenges to benchmark the current
 state of predictive modeling on real, high-quality datasets.

**In partnership with ExpansionRx**, this challenge invites participants to solve realistic
ADMET prediction problems that ExpansionRx encountered during lead optimization, by predicting
the properties of late-stage molecules based on earlier-stage data from the same campaigns, across nine endpoints.

## 📊 A High-Quality Dataset of ADMET Endpoints

Expansion Therapeutics recently prosecuted several drug discovery programs targeting
RNA-mediated diseases, including Myotonic Dystrophy (DM1), Amyotrophic Lateral Sclerosis (ALS),
and Dementia. During optimization, they generated a wealth of high-quality ADMET data
off-targets and properties of interest.

Now, they've made the bold and generous decision to open-source their high-quality ADMET dataset
 for public use and benefit. 💡

The dataset includes over 7,000 small molecules measured across multiple ADMET assays, and was divided into:

- A **training set**, which will be available to all participants during the challenge
- A **blinded test set**, which will be used to score final predictions after submission

Participants will train models on the training data, submit predictions for the molecules in the
 blinded test set, and have their models evaluated on the unseen datapoints.

### 🔬 ADMET Endpoints to Predict

There are a total of **nine ADMET endpoints** that participants are tasked with predicting:

| Endpoint | Description | Units |
| --- | --- | --- |
| **LogD** | Measures compound's lipophilicity at a specific pH, which helps understand the
balance of aqueous solubility with membrane permeability | - |
| **Kinetic Solubility KSOL** | Quantifies how much a compound can be dissolved under
non-equilibrium conditions | µM |
| **Human Liver Microsomal (HLM) CLint** | Helps predict in vivo liver metabolism and clearance
| mL/min/kg |
| **Mouse Liver Microsomal (MLM) stability** | Analogous to HLM, studying MLM can provide a more
 comprehensive understanding of a compound's metabolic profile | mL/min/kg |
| **Caco-2 Papp A>B** | Measures the rate of flux of a compound across polarized Caco-2 cell
monolayers from the apical to basolateral side | 10^-6 cm/s |
| **Caco-2 Efflux Ratio** | Models intestinal absorption by measuring flux across polarized
Caco-2 cell monolayers | - |
| **Mouse Plasma Protein Binding (MPPB)** | Determines the concentration of free drug in plasma
| % Unbound |
| **Mouse Brain Protein Binding (MBPB)** | Measures the fraction of drug not bound to proteins
within brain tissue | % Unbound |
| **Mouse Gastrocnemius Muscle Binding (MGMB)** | Reflects the amount of drug free to act within
 skeletal muscle tissue | % Unbound |

## 🚀 How to Get Started

The challenge is run from a Hugging Face Space. Feel free to ask any questions on the community
Discord where the organizers and other participants will be able to assist you.

### 📚 Run Through the Tutorial

We have a set of tutorials available for you to get acquainted with the challenge. We recommend
that all participants run through the tutorial to fully understand the endpoints and submission process.

### 💾 Access the Training Set

You can easily download the clean version of the training dataset using the Hugging Face Datasets library:

```python
from datasets import load_dataset

ds = load_dataset("openadmet/openadmet-expansionrx-challenge-train-data") df = ds["train"].to_pandas()
```

And to download the raw version of the training dataset that contains out of bounds measurements:

```python
from datasets import load_dataset

ds = load_dataset("openadmet/openadmet-expansionrx-challenge-train-data", name="raw") df = ds["train"].to_pandas()
```

### 🔒 Access the Blinded Test Set

The test set contains only the SMILES strings for you to perform inference on before submitting to the challenge space.

Similarly to the training set you can access the blinded test data using the dataset library:

```python
from datasets import load_dataset

ds = load_dataset("openadmet/openadmet-expansionrx-challenge-test-data-blinded") df = ds["test"].to_pandas()
```

By taking part in this blind challenge, you'll contribute to open, reproducible ADMET modeling
and help benchmark the next generation of predictive models for drug discovery! ⚙️

## 💬 Questions or Ideas?

OpenADMET would love to hear from you whether you're:

- Interested in participating
- Have ideas for future challenges
- Want to contribute data

Join the OpenADMET Discord or email openadmet@omsf.io.

--- 
## 🙌 Credits

*Originally posted at:
https://huggingface.co/blog/hugging-science/the-expansionrx-openadmet-blind-challenge*

## ✅ Final Thoughts

The ExpansionRx-OpenADMET Blind Challenge represents a significant step forward in
community-driven drug discovery science. By open-sourcing high-quality ADMET datasets and
creating standardized benchmarks, this initiative promises to accelerate the development of more
 accurate predictive models for pharmaceutical research.

The collaboration between ExpansionRx and OpenADMET demonstrates the power of open science in
tackling complex challenges in drug development, potentially benefiting researchers worldwide
and ultimately improving patient outcomes through better drug discovery processes.

_#DRUGDISCOVERY #ADMET #MACHINELEARNING #HUGGINGFACE #OPENSCIENCE #PHARMACEUTICALS
#BIOINFORMATICS #CHEMINFORMATICS_

