---
title: "Rust‑Based docling.rs Speeds Up Document Conversion for LLM Pipelines"
slug: "rustbased-docling-rs-speeds-up-document-conversion-for-llm-pipelines"
description: "The docling.rs project released a Rust port of IBM’s docling that delivers faster, lower‑memory document conversion for LLM and RAG pipelines."
date: 2026-10-25T22:04:16+05:30
tags: [docling, Rust, documentconversion, LLM, RAG]
categories: ["AI", "Artificial Intelligence", "Natural Language Processing", "Document Processing", "Software Development"]
image: "https://avatars.githubusercontent.com/u/188446108?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Rust‑Based docling.rs Speeds Up Document Conversion for LLM Pipelines

The docling.rs project released a Rust port of IBM’s docling that delivers faster, lower‑memory document conversion for LLM and RAG pipelines.

## 🔧 Overview
- Converts PDF, Office, HTML, scanned documents, and audio into Markdown, docling JSON, and other formats that LLMs or RAG pipelines can consume.
- Produces output that is *byte‑for‑byte* identical to the original IBM docling implementation.
- Operates as a single static binary – no Python runtime and no PyTorch dependency.

## ⚙️ How it works
- **Layout analysis, table recognition, and OCR** are performed by built‑in ONNX models (layout, OCR, TableFormer, Whisper). These models are bundled (under 1 GB) and can be downloaded once via the provided scripts.
- Office, HTML, Markdown, and e‑mail formats require no ML models.
- PDF, images, and audio trigger the ONNX models for full‑fidelity extraction.

## 🚀 Performance
| Format | Speedup vs. Python docling | RAM usage |
|--------|---------------------------|-----------|
| PDF    | 4.3× faster               | under half |
| Office & HTML | 20–60× faster      | — |
- Table extraction retains structure with **cell recall 0.94**, compared to MarkItDown's 0.31 (see [numbers](#conformance-with-microsoft-markitdown)).

## 🔗 Compatibility with existing stacks
- **MarkItDown**: `pip install docling-rs` and replace the import with `from docling_rs.markitdown import MarkItDown`. All original formats, layout analysis, tables, and OCR remain functional.
- **Marker**: Swap imports to `from docling_rs.marker.converters.pdf import PdfConverter` and keep the original API (`create_model_dict`, `text_from_rendered`, JSON block tree, etc.).
- **MinerU**: Replace imports to `from docling_rs.mineru.parser import parse` and retain MinerU 4’s SDK (`ParseResult`, `markdown()`, JSON, Content Lists, `save()`).
- Each compatibility guide includes side‑by‑side measurements ([MarkItDown](#conformance-with-microsoft-markitdown), [Marker](#conformance-with-marker), [MinerU](#conformance-with-mineru)).

## 🌐 Availability
- Install with **pip**: `pip install docling-rs`.
- Install with **npm** or from source checkout.
- Download models once with:
  ```python
  import docling_rs
  docling_rs.download_models()
  ```
  or via `download_dependencies.sh` for non‑Python workflows.
- Windows support documented in [`docs/WINDOWS.md`](./docs/WINDOWS.md).
- Try the converter directly in the browser (WebAssembly, OCR included) at https://docling-project.github.io/docling.rs/ – processing stays on your device.

## 📚 Documentation
- Detailed performance and profiling notes: `./docs/PDF_CONFORMANCE.md#performance--review--profiling-notes`.
- Model download instructions: see the **Getting the ML models** section referenced in the docs.
- API migration guides for MarkItDown, Marker, and MinerU are linked in each bullet above.


#docling #Rust #documentconversion #LLM #RAG

---

*Source: [docling-project/docling.rs](https://github.com/docling-project/docling.rs)*
