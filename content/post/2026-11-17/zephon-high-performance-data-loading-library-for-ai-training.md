---
title: "Zephon: High-Performance Data Loading Library for AI Training"
slug: "zephon-high-performance-data-loading-library-for-ai-training"
description: "Zephon is a high-performance data loading library that separates what you train on from how data is loaded and transformed."
date: 2026-11-17T12:12:52+05:30
tags: [M, a, c, h, i, n, e, L, e, a, r, n, i, n, g, D, a, t, a, L, o, a, d, i, n, g, P, y, t, h, o, n, P, y, T, o, r, c, h, Z, e, p, h, o, n]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "D", "a", "t", "a", "E", "n", "g", "i", "n", "e", "e", "r", "i", "n", "g", ",", "P", "y", "t", "h", "o", "n", "L", "i", "b", "r", "a", "r", "i", "e", "s", ",", "A", "I", "I", "n", "f", "r", "a", "s", "t", "r", "u", "c", "t", "u", "r", "e"]
image: "https://avatars.githubusercontent.com/u/146795414?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Zephon: High-Performance Data Loading Library for AI Training

Zephon is a high-performance data loading library that separates what you train on from how data is loaded and transformed.

## 🧩 Overview

*   Supports online processing (tokenization, sequence packing, filtering, dynamic mixtures) rather than requiring expensive offline preprocessing.
*   Guarantees deterministic, reproducible output regardless of parallelism or hardware topology.

### Supported Data Formats

| Feature | Description |
| :--- | :--- |
| `zephon[cloud]` | Reading from S3, GCS, and Azure (`s3://`, `gs://`, `az://` paths) |
| `zephon[hf]` | Hugging Face datasets (`hf://` paths), plus Parquet |
| `zephon[parquet]` | Parquet shards |
| `zephon[streaming]` | MosaicML Streaming / MDS shards (Python 3.11+) |
| `zephon[litdata]` | LitData shards |
| `zephon[vortex]` | Vortex shards (Python 3.11+) |
| `zephon[array_record]` | ArrayRecord shards |
| `zephon[lance]` | Lance datasets, one shard per fragment |
| `zephon[ray]` | The experimental Ray runner |

## 🔄 How it works

A Zephon pipeline has three parts: a `Dataset` that describes your data, a `WorkSource` that decides what to train on and in what order, and a `Pipeline` of operators that turns samples into training batches.

1.  **Describe the data:** A directory of JSONL, Parquet, MDS, LitData, Vortex, ArrayRecord, or Lance shards.
2.  **Decide what to train on, and in what order.**
3.  **Turn samples into training batches.**

Mixing datasets is a matter of adding them to the `WorkSource` with the proportions you want.

For example, to train on Parquet data in S3:

```bash
uv pip install "zephon[cloud,parquet]"
```

Note that running a pipeline with a cloud storage backend requires enabling the [shard cache](https://docs.zephon.io/datasets/storage_backends_and_shard_cache.html).

## ⚙️ Key Details

*   **Requirements:** Requires Python 3.10 or newer. Python 3.11+ is required for `zephon[streaming]` and `zephon[vortex]`.
*   **Tokenization:** Tokenization uses Hugging Face tokenizers, so you will also want `uv pip install transformers` if following examples.
*   **Integration:** A `Pipeline` is a plain Python iterable, so it works with whatever training loop you have. It will also run inside a PyTorch `DataLoader` or torchdata `StatefulDataLoader` if your framework insists on one, although direct iteration is recommended.
*   **State Management:** You can save and restore a pipeline's position alongside your model checkpoint:

```python
state = pipeline.checkpoint()  # store this with the model and optimizer state
pipeline.restore(state)  # on resume, before iter
```

#M #a #c #h #i #n #e # #L #e #a #r #n #i #n #g #, # #D #a #t #a # #L #o #a #d #i #n #g #, # #P #y #t #h #o #n #, # #P #y #T #o #r #c #h #, # #Z #e #p #h #o #n

---

*Source: [datologyai/zephon](https://github.com/datologyai/zephon)*
