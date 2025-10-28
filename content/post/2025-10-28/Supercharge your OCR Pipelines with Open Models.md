---
title: "Supercharge your OCR Pipelines with Open Models"
description: "A comprehensive guide to choosing and implementing open-weight OCR models for document AI, covering capabilities, model comparison, and practical deployment strategies."
date: 2025-10-28T01:14:56.196566+05:30
tags: ["OCR", "Document AI", "Vision Language Models", "Machine Learning", "Open Source", "Hugging Face", "Computer Vision", "VLM", "Text Recognition", "AI"]
categories: ["Artificial Intelligence", "Computer Vision", "Machine Learning"]
image: "https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/ocr/IE.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 Supercharge your OCR Pipelines with Open Models

*The rise of powerful vision-language models has transformed document AI. Each model comes with
unique strengths, making it tricky to choose the right one. Open-weight models offer better cost
 efficiency and privacy. To help you get started with them, we've put together this guide.*

## 📋 What You'll Learn

In this comprehensive guide, you'll discover:

- The landscape of current models and their capabilities
- When to fine-tune models vs. use models out-of-the-box
- Key factors to consider when selecting a model for your use case
- How to move beyond OCR with multimodal retrieval and document QA

By the end, you'll know how to choose the right OCR model, start building with it, and gain
deeper insights into document AI. Let's go! 🎯

---

## 🔍 Brief Introduction to Modern OCR

Optical Character Recognition (OCR) is one of the earliest and longest running challenges in
computer vision. Many of AI's first practical applications focused on turning printed text into
digital form.

With the surge of [vision-language
models](https://huggingface.co/blog/vision_language_pretraining) (VLMs), OCR has advanced
significantly. Recently, many OCR models have been developed by fine-tuning existing VLMs. But
today's capabilities extend far beyond OCR: you can retrieve documents by query or answer
questions about them directly. Thanks to stronger vision features, these models can also handle
low-quality scans, interpret complex elements like tables, charts, and images, and fuse text
with visuals to answer open-ended questions across documents.

### ⚙️ Model Capabilities

#### 📝 Transcription

Recent models transcribe texts into a machine-readable format. The input can include:

- Handwritten text
- Various scripts like Latin, Arabic, and Japanese characters
- Mathematical expressions
- Chemical formulas
- Image/Layout/Page number tags

OCR models convert them into machine-readable text that comes in many different formats like
HTML, Markdown and more.

#### 🧩 Handling Complex Components in Documents

On top of text, some models can also recognize:

- Images
- Charts
- Tables

Some models know where images are inside the document, extract their coordinates, and insert
them appropriately between texts. Other models generate captions for images and insert them
where they appear. This is especially useful if you are feeding the machine-readable output into
 an LLM.

![Chart Rendering](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main
/blog/ocr/chart-rendering.png)

*Example of chart conversion to machine-readable format*

![Table Rendering](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main
/blog/ocr/table-rendering.png)

*Example of table conversion while preserving structure*

#### 📄 Output Formats

Different OCR models have different output formats. Here are the common output formats used by
modern models:

**DocTag:** DocTag is an XML-like format for documents that expresses location, text format,
component-level information, and more. This format is employed by the open Docling models.

![DocTags](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/oc
r/doctags_v2.png)

*DocTag format example showing structured document representation*

- **HTML:** HTML is one of the most popular output formats used for document parsing as it
properly encodes structure and hierarchical information.
- **Markdown:** Markdown is the most human-readable format. It's simpler than HTML but not as
expressive. For example, it can't represent split-column tables.
- **JSON:** JSON is not a format that models use for the entire output, but it can be used to
represent information in tables or charts.

The right model depends on how you plan to use its outputs:

- **Digital reconstruction**: To reconstruct documents digitally, choose a model with a
layout-preserving format (e.g., DocTags or HTML).
- **LLM input or Q&A**: If the use case involves passing outputs to LLM, pick a model that
outputs Markdown and image captions, since they're closer to natural language.
- **Programmatic use**: If you want to pass your outputs to a program (like data analysis), opt
for a model that generates structured outputs like JSON.

#### 🎯 Locality Awareness in OCR

Documents can have complex structures, like multi-column text blocks and floating figures. Older
 OCR models handled these documents by detecting words and then the layout of pages manually in
post-processing to have the text rendered in reading order, which is brittle. Modern OCR models,
 on the other hand, incorporate layout metadata to help preserve reading order and accuracy.
This metadata is called "anchor", it can come in bounding boxes. This process is also called as
"grounding/anchoring" because it helps with reducing hallucination.

#### 💡 Model Prompting

OCR models can either take in images and an optional text prompt, this depends on the model
architecture and the pre-training setup.

Some OCR models support prompt-based task switching, e.g.
[granite-docling](https://huggingface.co/ibm-granite/granite-docling-258M) can parse an entire
page with the prompt "Convert this page to Docling" while it can also take prompts like "Convert
 this formula to LaTeX" along with a page full of formulas.

Other models, however, are trained only for parsing entire pages, and they are conditioned to do
 this through a system prompt.

---

## 🏆 Cutting-edge Open OCR Models

We've seen an incredible wave of new models this past year. Because so much work is happening in
 the open, these players build on and benefit from each other's work. A great example is
AllenAI's release of OlmOCR, which not only released a model but also the dataset used to train
it. With these, others can build upon them in new directions. The field is incredibly active,
but it's not always obvious which model to use.

### 📊 Comparing Latest Models

To make things a bit easier, we're putting together a non-exhaustive comparison of some of our
current favorite models. All of the models below are layout-aware and can parse tables, charts,
and math equations. The full list of languages each model supports are detailed in their model
cards, so make sure to check them if you're interested.

| Model Name | Output formats | Features | Model Size | Multilingual? | Average Score on OlmOCR
Benchmark |
| --- | --- | --- | --- | --- | --- |
| [Nanonets-OCR2-3B](https://huggingface.co/nanonets/Nanonets-OCR2-3B) | structured Markdown
with semantic tagging (plus HTML tables, etc.) | Captions images in the documents<br/>Signature
& watermark extraction<br/>Handles checkboxes, flowcharts, and handwriting | 4B | ✅Supports
English, Chinese, French, Arabic and more. | N/A |
| [PaddleOCR-VL](https://huggingface.co/PaddlePaddle/PaddleOCR-VL) | Markdown, JSON, HTML tables
 and charts | Handles handwriting, old documents<br/>Allows prompting<br/>Converts tables &
charts to HTML<br/>Extracts and inserts images directly | 0.9B | ✅Supports 109 languages | N/A
|
| [dots.ocr](https://huggingface.co/ucaslcl/GOT-OCR2_0) | Markdown, JSON |
Grounding<br/>Extracts and inserts images<br/>Handles handwriting | 3B | ✅Multilingual with
language info not available | 79.1 ± 1.0 |
| [OlmOCR-2](https://huggingface.co/allenai/OlmOCR-2) | Markdown, HTML, LaTeX |
Grounding<br/>Optimized for large-scale batch processing | 8B | ❎English-only | 82.3 ± 1.1 |
| [Granite-Docling-258M](https://huggingface.co/ibm-granite/granite-docling-258M) | DocTags |
Prompt-based task switching<br/>Ability to prompt element locations with location
tokens<br/>Rich output | 258M | ✅Supports English, Japanese, Arabic and Chinese. | N/A |
| [DeepSeek-OCR](https://huggingface.co/deepseek-ai/deepseek-vl2-tiny) | Markdown, HTML |
Supports general visual understanding<br/>Can parse and re-render all charts, tables, and more
into HTML<br/>Handles handwriting<br/>Memory-efficient, solves text through image | 3B |
✅Supports nearly 100 languages | 75.4 ± 1.0 |
| [Chandra](https://huggingface.co/chandrasg/chandra-27B) | Markdown, HTML, JSON |
Grounding<br/>Extracts and inserts images as is | 9B | ✅Supports 40+ languages | 83.1 ± 0.9 |
| [Qwen3-VL](https://huggingface.co/Qwen/Qwen2-VL-7B-Instruct) | Vision Language Model can
output in all formats | Can recognize ancient text<br/>Handles handwriting<br/>Extracts and
inserts images as is | 9B | ✅Supports 32 languages | N/A |

While Qwen3-VL itself is a powerful and versatile vision-language model post-trained for
document understanding and other tasks, it isn't optimized for a single, universal OCR prompt.
In contrast, the other models were fine-tuned using one or a few fixed prompts specifically
designed for OCR tasks. So to use Qwen3-VL, we recommend experimenting with prompts.

### 📈 Evaluating Models

#### 🔍 Benchmarks

There's no single best model, as every problem has different needs. Should tables be rendered in
 Markdown or HTML? Which elements should we extract? How should we quantify text accuracy and error rates? 👀

While there are many evaluation datasets and tools, many don't answer these questions. So we
suggest using the following benchmarks:

1. **[OmniDocBenchmark](https://huggingface.co/datasets/opendatalab/OmniDocBench)**: This widely
 used benchmark stands out for its diverse document types: books, magazines, and textbooks. Its
evaluation criteria are well designed, accepting tables in both HTML and Markdown formats. A
novel matching algorithm evaluates the reading order, and formulas are normalized before
evaluation. Most metrics rely on edit distance or tree edit distance (tables). Notably, the
annotations used for evaluation are not solely human-generated but are acquired through SoTA
VLMs or conventional OCR methods.

2. **[OlmOCR-Bench](https://allenai.org/project/olm-ocr/home)**: OlmOCR-Bench takes a different
approach: they treat the evaluation as a set of unit tests. For example, table evaluation is
done by checking the relation between selected cells of a given table. They use PDFs from public
 sources, and annotations are done using a wide range of closed-source VLMs. This benchmark is
quite successful to evaluate on the English language.

3. **[CC-OCR (Multilingual)](https://github.com/google-research-datasets/crosslingual-cv)**:Compared to the previous benchmarks, CC-OCR is less preferred when picking models, due to lower
document quality and diversity. However, it's the only benchmark that contains evaluation beyond
 English and Chinese! While the evaluation is far from perfect (images are photos with few
words), it's still the best you can do for multilingual evaluation.

#### 💰 Cost-efficiency

Most OCR models are small, having between 3B and 7B parameters; you can even find models with
fewer than 1B parameters, like PaddleOCR-VL. However, the cost also depends on the availability
of optimized implementations for specialized inference frameworks. For example, OlmOCR-2 comes
with vLLM and SGLang implementations, and the cost per million pages is 178 dollars (assuming on
 H100 for $2.69/hour). DeepSeek-OCR can process 200k+ pages per day on a single A100 with 40GB VRAM.

#### 📚 Open OCR Datasets

While the past year has seen a surge in open OCR models, this hasn't been matched by as many
open training and evaluation datasets. An exception is AllenAI's
[olmOCR-mix-0225](https://huggingface.co/datasets/allenai/olmOCR-mix-0225), which has been used
to train at least [72 models on the Hub](https://huggingface.co/models?search=olmocr) – likely
more, since not all models document their training data.

Sharing more datasets could unlock even greater advances in open OCR models. There are several
promising approaches for creating these datasets:

- **Synthetic data generation** (e.g.,
[isl_synthetic_ocr](https://huggingface.co/datasets/indonesian-nlp/isl_synthetic_ocr))
- **VLM-generated transcriptions** filtered manually or through heuristics
- **Using existing OCR models** to generate training data for new, potentially more efficient
models in specific domains
- **Leveraging existing corrected datasets** like the [Medical History of British India
Dataset](https://github.com/Living-with-machines/alto2txt2fixture), which contains extensively
human-corrected OCR for historic documents

--- 
## 🛠️ Tools to Run Model

We have received many questions about getting started with OCR models, so here are a few ways
you can use local inference tools and host remotely with Hugging Face.

### 💻 Locally

Most cutting-edge models come with vLLM support and transformers implementation. You can get
more info about how to serve each from the models' own cards. For convenience, we show how to
infer locally using vLLM here.

```bash
vllm serve nanonets/Nanonets-OCR2-3B
```

And then you can query as follows using e.g. OpenAI client.

```python
from openai import OpenAI import base64

client = OpenAI(base_url="http://localhost:8000/v1")model = "nanonets/Nanonets-OCR2-3B"

def encode_image(image_path):
    with open(image_path, "rb") as image_file:
        return base64.b64encode(image_file.read()).decode("utf-8")

def infer(img_base64):
    response = client.chat.completions.create( model=model,
        messages=[ {
                "role": "user", "content": [
                    { "type": "image_url",
                        "image_url": {"url": f"data:image/png;base64,{img_base64}"}, },
                    { "type": "text",
                        "text": "Extract the text from the above document as if you were reading it naturally.",
                    }, ],
            } ],
        temperature=0.0, max_tokens=15000
    ) return response.choices[0].message.content

img_base64 = encode_image(your_img_path) print(infer(img_base64))
```

**Transformers Implementation:**

```python
# make sure to install flash-attn and transformers
from transformers import AutoProcessor, AutoModelForImageTextToText

model = AutoModelForImageTextToText.from_pretrained( "nanonets/Nanonets-OCR2-3B",
    torch_dtype="auto", device_map="auto",
    attn_implementation="flash_attention_2" )
model.eval() processor = AutoProcessor.from_pretrained("nanonets/Nanonets-OCR2-3B")

def infer(image_url, model, processor, max_new_tokens=4096):
    prompt = """Extract the text from the above document as if you were reading it naturally.
Return the tables in html format. Return the equations in LaTeX representation. If there is an
image in the document and image caption is not present, add a small description of the image
inside the <img></img> tag; otherwise, add the image caption inside <img></img>. Watermarks
should be wrapped in brackets. Ex: <watermark>OFFICIAL COPY</watermark>. Page numbers should be
wrapped in brackets. Ex: <page_number>14</page_number> or <page_number>9/22</page_number>.
Prefer using ☐ and ☑ for check boxes."""

    image = Image.open(image_path) messages = [
        {"role": "system", "content": "You are a helpful assistant."}, {"role": "user", "content": [
            {"type": "image", "image": image_url}, {"type": "text", "text": prompt},
        ]}, ]

    text = processor.apply_chat_template(messages, tokenize=False, add_generation_prompt=True)
    inputs = processor(text=[text], images=[image], padding=True, return_tensors="pt").to(model.device)
    output_ids = model.generate(**inputs, max_new_tokens=max_new_tokens, do_sample=False)
    generated_ids = [output_ids[len(input_ids):] for input_ids, output_ids in zip(inputs.input_ids, output_ids)]
    output_text = processor.batch_decode(generated_ids, skip_special_tokens=True, clean_up_tokenization_spaces=True)
    return output_text[0]

result = infer(image_path, model, processor, max_new_tokens=15000) print(result)
```

**MLX Support:**

MLX is an open-source machine learning framework for Apple Silicon.
[MLX-VLM](https://github.com/Blaizzy/mlx-vlm) is built on top of MLX to serve vision language models easily.

```bash
pip install -U mlx-vlm

wget https://huggingface.co/datasets/merve/vlm_test_images/resolve/main/throughput_smolvlm.pngpython -m mlx_vlm.generate --model ibm-granite/granite-docling-258M-mlx --max-tokens 4096
--temperature 0.0 --prompt "Convert this chart to JSON." --image throughput_smolvlm.png
```

### ☁️ Remotely

**Inference Endpoints for Managed Deployment:**

You can deploy OCR models compatible with vLLM or SGLang on Hugging Face Inference Endpoints,
either from a model repository "Deploy" option or directly through [Inference Endpoints
interface](https://huggingface.co/inference-endpoints).

![Inference Endpoints](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/ocr/IE.png)

*Deployment interface for Hugging Face Inference Endpoints*

**Hugging Face Jobs for Batch Inference:**

For many OCR applications, you want to do efficient batch inference, i.e., running a model
across thousands of images as cheaply and efficiently as possible. A good approach is to use
vLLM's offline inference mode.

To make this even easier, we've created
[uv-scripts/ocr](https://huggingface.co/datasets/uv-scripts/ocr), a collection of ready-to-run
OCR scripts that work with Hugging Face Jobs. These scripts let you run OCR on any dataset
without needing your own GPU.

```bash
hf jobs uv run --flavor l4x1 \ https://huggingface.co/datasets/uv-scripts/ocr/raw/main/nanonets-ocr.py \
  your-input-dataset your-output-dataset \ --max-samples 100
```

--- 
## 🚀 Going Beyond OCR

If you are interested in document AI, not just OCR, here are some of our recommendations.

### 🔍 Visual Document Retrievers

Visual document retrieval is to retrieve the most relevant top-k documents when given a text
query. If you have previously worked with retriever models, the difference is that you search
directly on a stack of PDFs. Aside from using them standalone, you can also build multimodal RAG
 pipelines by combining them with a vision language model.

There are two types of visual document retrievers, single-vector and multi-vector models.
Single-vector models are more memory efficient and less performant; meanwhile, multi-vector
models are more memory hungry and more performant. Most of these models often come with vLLM and
 transformers integrations, so you can index documents using them and then do a search easily using a vector DB.

### ❓ Using Vision Language Models for Document Question Answering

If you have a task at hand that only requires answering questions based on documents, you can
use some of the vision language models that had document tasks in their training tasks. We've
observed users trying to convert documents into text and passing the output to LLMs, but if your
 document has a complex layout, and your converted document outputs charts and so on in HTML, or
 images are captioned incorrectly, the LLM will miss out. Instead, feed your document and query
to one of the advanced vision language models like
[Qwen3-VL](https://huggingface.co/Qwen/Qwen2-VL-7B-Instruct) not to miss out on any context.

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/ocr-open-models*

--- 
## 🏁 Conclusion

In this comprehensive guide, we've explored the rapidly evolving landscape of open OCR models
and their capabilities. The surge in vision-language models has transformed document AI from
simple text extraction to sophisticated multimodal understanding systems.

Key takeaways include:

- **Model Selection**: Choose based on your specific output format needs (DocTags for
reconstruction, Markdown for LLM input, JSON for programmatic use)
- **Cost Efficiency**: Open-source models offer significant cost advantages over closed-source
alternatives, especially at scale
- **Beyond OCR**: Modern capabilities extend to document retrieval, question answering, and
complex layout understanding
- **Implementation**: Multiple deployment options exist, from local inference with vLLM to
managed cloud solutions

The field continues to advance rapidly, with new models, datasets, and evaluation benchmarks
emerging regularly. By understanding these fundamentals and leveraging the right tools, you can
build powerful document AI pipelines that meet your specific requirements while maintaining cost
 efficiency and privacy control.

Whether you're processing invoices, research papers, or complex technical documents, the open
OCR ecosystem now provides robust solutions that rival proprietary offerings while giving you
full control over your data and infrastructure.

--- 
_#OCR #DOCUMENTAI #VLM #MACHINELEARNING #OPENSOURCE #HUGGINGFACE #AI #COMPUTERVISION_

