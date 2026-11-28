---
title: "Misata Introduces Declarative Synthetic Data Generation with Verification"
slug: "misata-introduces-declarative-synthetic-data-generation-with-verification"
description: "Misata is a new declarative synthetic data generator for Python. It allows developers to write down the facts a dataset must satisfy, and the engine builds multi-table data that satisfies all of them..."
date: 2026-11-28T22:07:57+05:30
tags: [SyntheticData, Python, DataEngineering, Testing, DuckDB]
categories: ["AI", "Data Engineering", "Software Testing", "Python Libraries"]
image: "https://avatars.githubusercontent.com/u/112371697?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Misata Introduces Declarative Synthetic Data Generation with Verification

Misata is a new declarative synthetic data generator for Python. It allows developers to write down the facts a dataset must satisfy, and the engine builds multi-table data that satisfies all of them simultaneously.

## 🧩 How it works
Users define invariants in a `misata.yaml` file, such as monthly revenue curves, balanced ledgers, or foreign key constraints. The system generates rows derived from these specifications.

- **Specification as Ground Truth:** The specification is the ground truth, and the rows are derived from it. For example, if the specification states "January revenue is 180,000," this is true before a single row exists.
- **DuckDB Integration:** Once data is generated, DuckDB checks the files on disk and writes a certificate that anyone can re-run.
- **Independent Verification:** The `verify.py` script uses only the standard library and `duckdb`. It shares no code with the generator.

## ⚙️ Key details
The tool addresses the "oracle problem" in testing, where verifying data pipelines requires both input data and an independently known answer. Traditional methods have limitations:

- **Copying Production:** Provides data without a known answer.
- **Hand-written Fixtures:** Provide an answer that rots.
- **Random Generators:** Provide data whose answer must be computed by the code under test.

In a documented example, Misata generated data satisfying 69 invariants, including:
- Twelve monthly revenue totals (e.g., 180,000.00 in January, 240,000.00 in June).
- Channel splits inside each month.
- Planned row counts per month.
- Zero orphaned `customer_id`s and unique keys.

The verification process can detect specific failures, such as a mismatched SHA256 hash or a precision error where an observed value of 180000.01 does not match the expected 180000.00.

## 🚀 Availability
Misata is available for Python. It can be installed and used as follows:

```bash
# Installation
pip install "misata[duckdb]"

# Data Generation
misata generate -c misata.yaml -o data --attest

# Verification
python data/verify.py
```

A successful verification outputs a certificate indicating that files match their attested SHA256 hashes and all invariants hold.

#SyntheticData #Python #DataEngineering #Testing #DuckDB

---

*Source: [rasinmuhammed/misata](https://github.com/rasinmuhammed/misata)*
