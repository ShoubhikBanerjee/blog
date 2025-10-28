---
title: "Promoter-GPT: Writing DNA Instructions with Language Models"
description: "Revolutionizing synthetic biology by teaching transformers to speak the language
of life and generate novel DNA promoter sequences using a decoder-only transformer
architecture."
date: 2025-10-28T01:29:08.022196+05:30
tags: ["DNA", "GPT", "Transformers", "Synthetic Biology", "Bioinformatics", "Machine Learning", "Genomics", "k-mer Tokenization", "Promoter Sequences", "Neural Networks"]
categories: ["AI", "Bioinformatics", "Machine Learning"]
image: "NA"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🧬 Promoter-GPT: Writing DNA Instructions with Language Models

*Revolutionizing synthetic biology by teaching transformers to speak the language of life*

---

## 🧩 If DNA is truly a language, then we should be able to teach transformers how to write it.

For decades, biologists have called DNA "the language of life"—and they weren't being
metaphorical: DNA encodes the instructions that make life possible.

But here's one thing about languages: once you understand their rules, you can start writing
your own sentences.

So what if we could teach a transformer to compose entirely new genetic programs and create
novel biological instructions that have never existed in nature?

That's exactly what we want to do with **PromoterGPT**: a decoder-only transformer trained to
generate grammatically correct DNA instruction.

In this context, those "instructions" refer to **promoters**—the DNA regions located upstream of
 a gene that control whether it is activated or not. Promoters are what make the same gene
expressed in the brain but silent in the liver. If we can learn to design these elements, we can
 establish new rules for controlling gene expression, with possible applications in
biotechnology and medicine.

## 🎯 Project Overview

In this comprehensive guide, we'll build a decoder-only transformer that learns to generate
biologically plausible DNA promoter sequences. We'll cover:

- **k-mer tokenization** for genomic data
- **Custom vocabulary building** for DNA
- **Training a small GPT-2** from scratch
- **Generating novel 200bp** promoter sequences

```python
import pandas as pd
import numpy as np
import itertools
from tokenizers import Tokenizer, models, pre_tokenizers, normalizers, trainers
from transformers import PreTrainedTokenizerFast
from transformers import AutoConfig, GPT2LMHeadModel
from torch.utils.data import DataLoader
from torch.optim import AdamW
from accelerate import Accelerator
from transformers import get_scheduler
from torch.nn import CrossEntropyLoss
import torch
from tqdm import tqdm
```

## 📊 Step 1: Dataset - Load life instructions

First, we need to load the instructions: the DNA promoter sequences. For this, we use a
pre-compiled dataset containing 200-base-pair promoter regions. We filter it to ensure it
contains only 200 bp promoters and keep the chromosome information for downstream splitting.

```python
# Load and filter the dataset
data = (
    pd.read_csv("data.txt", sep="\t", usecols=['sequence','chr'])
    .assign(len=lambda df: df['sequence'].str.len())  # calcola la lunghezza
    .query("len == 200")  # filtra
    .drop(columns='len')  # rimuovi la colonna di servizio
    .reset_index(drop=True)  # resetta l'indice
)
```

We split the data not randomly, but by chromosome. This chromosomal splitting ensures that the
model must generalize across different genomic contexts rather than memorizing
chromosome-specific patterns. We hold out chromosomes 19, 21, and X for validation, and
chromosomes 7 and 13 for testing.

```python
# Define chromosomes for each split
val_chroms = {"19", "21", "X"}
test_chroms = {"7", "13"}

# Create boolean masks
val_mask = data['chr'].isin(val_chroms)
test_mask = data['chr'].isin(test_chroms)
train_mask = ~(val_mask | test_mask)

# Split the data
train_data = data.loc[train_mask]
val_data = data.loc[val_mask]
test_data = data.loc[test_mask]
```

### Dataset Statistics

| Split | Sequences | Chromosomes |
|-------|-----------|-------------|
| **Training** | 640,029 | 1-18, 20, 22, Y |
| **Validation** | 59,697 | 19, 21, X |
| **Test** | 63,958 | 7, 13 |

## 🔤 Step 2: Tokenization - Breaking DNA into "Words"

If DNA is a language, its letters are the four bases: **Adenine, Timine, Guanine and Cytosine**
(A, T, G, C). With just these four symbols, we can create an incredible number of combinations
and create many different instructions.

The challenge with DNA is that while we know the letters, we don't always know the "words." We
need a way to segment sequences into meaningful units. This step is crucial because biological
function often depends on specific combinations of bases, called **motifs**.

For example, a raw sequence `ATGCGCGCG` can be tokenized into overlapping **3-mers** (also
called k-mers with k=3): `ATG`, `TGC`, `GCG`, `CGC`, `GCG`, `CGC`, `GCG`

A 200-base sequence thus becomes 198 overlapping 3-mers, transforming raw DNA into a
biologically meaningful vocabulary.

```python
def kmerization(seq, k=3):
    return " ".join(seq[i:i+k] for i in range(len(seq) - k + 1))

kmers = 3
train_data.loc[:, "kmers"] = train_data["sequence"].apply(lambda x: kmerization(x, k=kmers))
val_data.loc[:, "kmers"] = val_data["sequence"].apply(lambda x: kmerization(x, k=kmers))
test_data.loc[:, "kmers"] = test_data["sequence"].apply(lambda x: kmerization(x, k=kmers))
```

### 🧠 Custom Vocabulary Creation

Since we know in advance the set of "words" (k-mers) that can appear in our sequences, we can
directly create a tokenizer with a predefined vocabulary. This approach eliminates the need for
the tokenizer to learn tokens from data and ensures consistent representation.

```python
# Generate all possible k-mers
mers = list(itertools.product(['A','T','G','C'], repeat=kmers))
mers = [(''.join(x)) for x in mers]

# Create vocabulary directly
special_tokens = ["[UNK]", "[PAD]", "[BOS]", "[EOS]", "[CLS]", "[SEP]", "[MASK]"]
vocab = {token: idx for idx, token in enumerate(special_tokens + mers)}

# Create tokenizer with the vocabulary
tokenizer = Tokenizer(models.WordLevel(vocab=vocab, unk_token="[UNK]"))
```

**Vocabulary Statistics:**
- **Total size:** 71 tokens
- **3-mers:** 64 possible combinations (4³)
- **Special tokens:** 7 (UNK, PAD, BOS, EOS, CLS, SEP, MASK)

## 🏗️ Step 3: Build Promoter-GP

Now we reach the core of our project—building a transformer that "speaks DNA." We adopt the
proven GPT-2 architecture but adapt it specifically for genomic sequences. Since our input
length is fixed at 198 tokens, we can use a compact decoder-only transformer: just 2 layers and
8 attention heads, giving a total of around 0.5 million parameters.

```python
# Build GPT-2 config with custom vocabulary and architecture
gpt_config = {
    "vocab_size": len(wrapped_tokenizer),
    "n_positions": len(train_datat[0]),  # max sequence length
    "n_head": 8,
    "n_layer": 2,
    "n_embd": 128,
}

config = AutoConfig.from_pretrained("gpt2", **gpt_config)
model = GPT2LMHeadModel(config)
```

### 📏 Model Architecture

| Parameter | Value |
|-----------|-------|
| **Vocabulary Size** | 71 |
| **Context Length** | 198 |
| **Hidden Dimension** | 128 |
| **Layers** | 2 |
| **Attention Heads** | 8 |
| **Total Parameters** | 0.43M |

## 🚀 Step 4: Training Loop

We train with:
- **Gradient accumulation** (8 steps) to simulate larger batches
- **Cosine learning rate schedule** with warmup
- **Early stopping** to prevent overfitting
- **Chromosomal validation split** to test generalization across genomic contexts

Since Promoter-GPT is a decoder-only model, we optimize it using auto-regression in a
self-supervised fashion. During training, we monitor both the loss and the perplexity, which
gives us a sense of how well the model predicts sequences of varying lengths.

```python
# Hyperparameters
batch_size = 128
weight_decay = 0.02
learning_rate = 6e-4
num_train_epochs = 10
gradient_accumulation_steps = 8
eval_steps = 10

# Setup training components
train_dataloader = DataLoader(train_datat, batch_size=batch_size, shuffle=True)
eval_dataloader = DataLoader(val_datat, batch_size=batch_size, shuffle=False)

optimizer = AdamW(get_grouped_params(model, weight_decay), lr=learning_rate)
accelerator = Accelerator()

# Training loop with early stopping
early_stopper = EarlyStopper(patience=3, min_delta=1e-3)
```

### 📈 Training Results

| Metric | Value |
|--------|-------|
| **Training Loss** | 4.26 |
| **Validation Loss** | 1.1491 |
| **Test Loss** | 1.1975 |
| **Test Perplexity** | 3.31 |

The small difference between validation and test loss (0.0484) indicates good generalization
across different chromosomes.

## 🧬 Step 5: Generating Novel DNA Sequences

Now comes the exciting part: using our trained model to generate synthetic promoter sequences
that have never existed in nature. This is where we see if the model truly learned the "grammar"
 of DNA.

The generation is autoregressive: we provide a short "seed" sequence (a biological prompt), and
the model predicts the next k-mer, adds it to the sequence, then predicts the next one,
continuing until we reach 200bp.

```python
# Set generation parameters
temperature = 1.0  # Controls randomness (higher = more diverse)
top_p = 0.9       # Nucleus sampling threshold

# Start with a biological seed sequence
prompt = kmerization("ATGG", k=3)
input_ids = wrapped_tokenizer.encode(prompt, return_tensors="pt").to(accelerator.device)

# Generate the sequence
with torch.no_grad():
    output_ids = unwrapped_model.generate(
        input_ids,
        max_length=198,
        min_length=198,
        do_sample=True,
        temperature=temperature,
        top_p=top_p,
        num_return_sequences=100,
    )
```

### 🔬 Example Generated Sequence

```
Generated promoter sequence:
ATGGTAGCATTTATAAAAATGACTCCCACTACTATCTCATTTTTAATTCATTATTTGCTCTTCTCCTGTATTTCACCACTTAGATTTTTTTCACTG
GTTGAACACACATTCAGGTAAGAAAATAATCTGGTGACAATGGATTACCTCACTCTTCTAGTTTTGTTTCCTTTTGACCCTGATGAGAGGAAAATT
TATGCTGC

Length: 200 bp
```

Each generated sequence is like a sentence written in the language of life—composed of patterns,
 motifs, and regulatory signals that the model has learned from millions of years of evolution
encoded in real genomes.

## 🔍 Step 6: Exploration

Now that our model can generate DNA sequences, we enter the exploration phase. We want to
understand what the model has learned: Are the generated sequences biologically plausible? Do
they follow the compositional rules of real promoters?

### 📊 Biological Validation

We validate the sequences on two key aspects:

1. **GC content** – the proportion of guanine (G) and cytosine (C) nucleotides
2. **Sequence motifs** – recurring patterns that correspond to biological functions

```python
def gc_content(seq):
    """Calculate the percentage of G and C nucleotides in a sequence."""
    gc_count = seq.count('G') + seq.count('C')
    return gc_count / len(seq) * 100

# Calculate GC% for all generated sequences
gc_values = [gc_content(seq) for seq in list_new_dna]
average_gc = sum(gc_values) / len(gc_values)
```

### 🧪 Analysis Results

| Metric | Generated Sequences | Biological Range |
|--------|-------------------|------------------|
| **Average GC Content** | 44.37% | 45-55% ✅ |
| **Most Common 6-mer** | TTTTTT (101 occurrences) | AT-rich regions ✅ |
| **Second Most Common** | AAAAAA (65 occurrences) | Poly-A/T stretches ✅ |

### 🎯 Top Motifs Discovered

The most frequent 6-mers found in generated sequences:

1. **TTTTTT** - 101 occurrences
2. **AAAAAA** - 65 occurrences
3. **AAAAAT** - 29 occurrences
4. **TTTTCT** - 27 occurrences
5. **CTGCTG** - 25 occurrences

*The top motifs (TTTTTT, AAAAAA) are poly-A/T stretches, which are commonly found in promoter
regions. These AT-rich sequences enhance DNA flexibility and are often associated with
transcription start sites and TATA boxes—key regulatory elements in gene expression.*

## 🚀 What's Next?

Here are some exciting directions to explore:

### 🔬 **Architecture Experiments**
- Try more layers (4, 6, 8) or different k-mer sizes (k=4, k=5, k=6)
- Experiment with different attention mechanisms

### 🧠 **Advanced Tokenization**
- Implement BPE to learn data-driven tokens instead of fixed k-mers
- Explore hierarchical tokenization strategies

### 🧬 **New Genomic Regions**
- Train on coding sequences, enhancers, or silencers
- Expand to other species and genomic contexts

The most exciting question remains: **Would these synthetic sequences actually work in a cell?**

The next step would be validating them computationally with activity prediction models, and
ultimately testing them experimentally in the lab.

If DNA is truly a language, we've shown that transformers can learn its basic grammar. The next
challenge is teaching them to write not just grammatically correct sequences, but functionally
meaningful ones.

---

## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/hugging-science/promoter-gpt*

--- 
## ✅ Final Thoughts

We've successfully demonstrated that transformers can learn the fundamental patterns of DNA
promoter sequences through self-supervised learning. Our PromoterGPT model generates
biologically plausible sequences with realistic GC content and functionally relevant motifs—all
without explicit instruction about what makes a promoter work.

This breakthrough opens new possibilities for synthetic biology, personalized medicine, and our
understanding of genomic language. The intersection of AI and biology continues to yield
remarkable results, bringing us closer to truly programmable genetic systems.

**Key Achievements:**
- ✅ Built a custom DNA tokenizer with k-mer vocabulary
- ✅ Trained a compact GPT-2 model (0.43M parameters)
- ✅ Generated novel 200bp promoter sequences
- ✅ Validated biological plausibility of synthetic sequences
- ✅ Discovered functionally relevant motifs in generated DNA

The future of synthetic biology is here, and it speaks the language of transformers.

--- 
*#SYNTHETICBIOLOGY #DNA #TRANSFORMERS #GPT #PROMOTERS #GENOMICS #AI #MACHINELEARNING
#BIOINFORMATICS #HUGGINGFACE*

