---
title: "New tool converts moderation policies into traceable preference data"
slug: "new-tool-converts-moderation-policies-into-traceable-preference-data"
description: "A new development called Preference Lab has been released, providing a workflow to turn content moderation policies into traceable preference data for machine learning and data teams. The tool allows..."
date: 2026-11-23T12:15:20+05:30
tags: [DataEngineering, ContentModeration, MachineLearning, OpenSourceAI, PreferenceData]
categories: ["AI", "Machine Learning", "Data Engineering", "AI Ethics"]
image: "https://avatars.githubusercontent.com/u/265749943?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New tool converts moderation policies into traceable preference data

A new development called Preference Lab has been released, providing a workflow to turn content moderation policies into traceable preference data for machine learning and data teams. The tool allows users to define rules, generate boundary cases, and export candidate preference pairs that include original text, rule evidence, and decision history.

## 🧩 How It Works
The system operates by converting declarative policies into executable sequences. A PolicyPack declares language, labels, evidence requirements, scores, exceptions, and an ordered decision table using a fixed declarative vocabulary that cannot execute code. Every stage of the process uses the same compiled PolicyPack to ensure consistency.

Several components make up the release:

| Component | Status & Function |
| :--- | :--- |
| **B Alpha** | Released; provides the synthesis kernel and run dashboard. |
| **C Workbench** | Integrated into main but not yet released; adds human decisions and curated dataset versions. |
| **PolicyPack** | Declarative file defining labels, evidence, and decision logic. |

For teams building datasets, the tool checks structure, evidence references, and policy consistency via a passed gate. However, this gate does not turn machine decisions into human ground truth. The recorded workflow example provided with the release makes no external model calls and requires no API key.

## ⚙️ Technical Details
The tool is designed for Python 3.11 or 3.12 on macOS and Linux. The recorded demo operates locally and does not connect to external services. 

- **Demo Output**: Running the demo on five fixtures produces 1 completed case, 1 preference pair, and 4 abstentions.
- **Error Handling**: The demo status is `partial_failed` with exit code 3 because four cases require external material not supplied by the demo. Diagnostics are saved rather than generating definitive answers for these cases.
- **Storage**: Runs are stored under `data/demo/runs/` and exports under `data/datasets/demo/`. Users can inspect `pairs.jsonl` for accepted pairs and `manifest.json` for policy and file hashes.
- **Data Preservation**: Exports preserve original content, evidence, and policy identity to allow later inspection. SQLite checkpoints retain complete responses and stage results.

For live runs that send prompts to configured model providers, the tool enforces a budget cap and model price snapshot. Retries, usage estimates, and unsettled reservations remain visible. Unknown remote requests pause for an explicit decision instead of automatically repeating potentially charged calls.

## 🧪 Compatibility Checks
The system performs compatibility checks using actual loaders, templates, tokenization, and collators in separate pinned environments for:
- TRL standard and conversational formats.
- LLaMA-Factory ShareGPT.

Users can begin with the built-in Chinese handbook or the English contact-policy example.

## 🚀 Availability and Limitations
The project is not currently published to PyPI. For packaged installation, users should use the wheel and checksums available in the GitHub Releases. The affected `0.3.0a1` release has been withdrawn; users must use the corrected source or a later release.

The language and label schemas are open, but model quality across languages and specific training gains have not yet been established. Resuming a run requires the original rule, model, prompt, and code identities.

#DataEngineering #ContentModeration #MachineLearning #OpenSourceAI #PreferenceData

---

*Source: [dengxianghua888-ops/preference-lab](https://github.com/dengxianghua888-ops/preference-lab)*
