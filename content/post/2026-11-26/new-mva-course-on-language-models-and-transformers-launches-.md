---
title: "New MVA Course on Language Models and Transformers Launches in Fall 2026"
slug: "new-mva-course-on-language-models-and-transformers-launches-in-fall-2026"
description: "The Master Vision Apprentissage (MVA) program is introducing a new course focused on language models and transformers during the first semester of the academic year 2026–2027. Taught in English, the..."
date: 2026-11-26T22:08:01+05:30
tags: [MLCourse, Transformers, LargeLanguageModels, AIAlignment, MVA]
categories: ["AI", "Machine Learning", "AI Education", "Language Models", "Deep Learning"]
image: "https://avatars.githubusercontent.com/u/7555483?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New MVA Course on Language Models and Transformers Launches in Fall 2026

The Master Vision Apprentissage (MVA) program is introducing a new course focused on language models and transformers during the first semester of the academic year 2026–2027. Taught in English, the course is open to all students enrolled in the MVA program and is structured around eight sessions held between October and December 2026.

David Louapre and Nathanaël Fijalkow lead the first four sessions, covering foundational topics in language modeling, transformer architectures, pre-training dynamics, and post-training alignment. Each session provides educational materials including slides in PDF or HTML format, lecture notes, and interactive Jupyter notebooks. Additional sessions in November and December are scheduled, with further details on content and resources to be released.

A companion course is offered in the second semester by Marc Lelarge and Guillaume Baudart, titled Large Language Models for Code and Proof.

## 📚 Course Structure

| Session | Date | Instructor | Topic | Resources |
|--------|------|------------|-------|----------|
| 1 | October 1 | David Louapre | Language models | [Slides (PDF)](david/lecture01.pdf), [Hugging Face Space](https://huggingface.co/spaces/dlouapre/nlp-before-llms) |
| 2 | October 29 | Nathanaël Fijalkow | Transformers | [Slides (HTML)](slides/01_transformers_101.html), [Lecture notes](notes/01_transformers_101.html), [Notebook](notebooks/01_transformers_101.ipynb) |
| 3 | November 5 | David Louapre | Pre-training and scaling laws | [Slides (PDF)](david/lecture03_part1.pdf), [Slides (PDF)](david/lecture03_part2.pdf) |
| 4 | November 12 | Nathanaël Fijalkow | Post-training and alignment | [Slides (HTML)](slides/05_post_training.html), [Lecture notes](notes/05_post_training.html), [Notebook](notebooks/05_post_training.ipynb), [Recording](https://u-bordeaux-fr.zoom.us/rec/share/agRYane6iPKXA_tI-lM_APGbIR0ylmINIZIhQIYxUcrbloPv9AWdYwaLlba59Al6.2g4tdldzsOtG6h1B) (passcode: `=S3^kc2U`) |
| 5 | November 19 | David Louapre | Decoding and inference optimization | [Slides (PDF)](david/lecture05_inference.pdf) |
| 6 | November 26 | Nathanaël Fijalkow | Advanced architectures | [Slides (HTML)](slides/02_advanced_architectures.html), [Lecture notes](notes/02_advanced_architectures.html), [Notebook](notebooks/02_advanced_architectures.ipynb) |

## 🛠️ Resource Format and Tools

All lecture materials are built from source files using Quarto, a markdown-based publishing system. The course repository includes:

- Source files in `src/` folder, with each lecture defined in a `.qmd` file that generates slides, notes, and notebooks.
- Supporting assets in `figs/` and `anim/` directories.
- A `render.py` script to compile individual or multiple lectures. Run with `python3 render.py 01 06` to build lectures 1 and 6.
- Use `python3 render.py 01 --slides` to generate only the slides for lecture 1.

The notebooks are executable and designed to run the lab component of each lecture. Execution is cached and only re-runs when code cells change, which may take several minutes.

## 🗓️ Timeline

- Course runs during the first semester of the MVA academic year 2026–2027 (October–January 2027).
- Sessions are held weekly from October through December 2026.
- A second course, Large Language Models for Code and Proof, begins in the second semester of 2026–2027.

## 💬 Why It Matters

The course introduces students to core concepts in modern language modeling, including the evolution from early NLP to large language models (LLMs), the mechanics of transformers, and practical aspects of model training and deployment. Emphasis is placed on hands-on learning through notebooks and real-world tools like Hugging Face Spaces.

Students will also explore advanced topics such as agent design and alignment techniques, preparing them for current developments in AI systems.

#MLCourse #Transformers #LargeLanguageModels #AIAlignment #MVA

---

*Source: [nathanael-fijalkow/LLM-Course](https://github.com/nathanael-fijalkow/LLM-Course)*
