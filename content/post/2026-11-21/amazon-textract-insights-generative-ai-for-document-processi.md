---
title: "Amazon Textract Insights: Generative AI for Document Processing"
slug: "amazon-textract-insights-generative-ai-for-document-processing"
description: "Amazon Textract Insights, a new generative AI feature of Amazon Textract, is now generally available. This feature allows users to describe the fields they want in natural language and submit..."
date: 2026-11-21T06:15:51+05:30
tags: [AmazonTextract, GenerativeAI, DocumentProcessing, AWS, AI]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Document Processing", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22308-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Textract Insights: Generative AI for Document Processing

Amazon Textract Insights, a new generative AI feature of Amazon Textract, is now generally available. This feature allows users to describe the fields they want in natural language and submit documents or mixed, multi-document packets to receive structured results with confidence scores and page-level grounding, without requiring model training.

## 🔍 Overview
- Amazon Textract Insights is a new generative AI feature of Amazon Textract.
- It allows users to describe the fields they want in natural language and submit documents or mixed, multi-document packets.
- The feature returns structured results with confidence scores and page-level grounding, without requiring model training.

## 🧩 How it works
- A blueprint is a JSON Schema in which each field carries a natural language description of what to find.
- Each field also has an inference type that determines whether the value is read verbatim from the page or inferred from the content of the document.
- You can begin with an AWS public blueprint for a common document type, such as a W-2, Form 1040, Form 1098, a passport, or a birth certificate.
- You can also author your own blueprint for the documents specific to your business.
- For a mixed packet, you add the blueprints for each document type you expect to the same project.
- You then submit a single file of up to 3,000 pages from your own Amazon Simple Storage Service (Amazon S3) bucket and enable splitting.
- Amazon Textract Insights splits the packet into logical sub-documents, matches each one to the blueprint that fits it, extracts the requested fields, and returns a confidence score and grounding for each value.

## ⚙️ Key details
- Amazon Textract Insights returns two kinds of fields: explicit fields read directly from the page and inferred fields derived from the document’s content.
- Both return with a confidence score and with grounding that identifies the page and the coordinates the value was drawn from.
- Because each value is traceable to its source, a reviewer or an auditor can confirm any result against the original document.

## 🚀 Availability
- Amazon Textract Insights is available through a new API within Amazon Textract.

## 💡 Why it matters
- Amazon Textract Insights brings reliable document processing into a single asynchronous request on Amazon Textract.
- It allows users to extend automation to documents that would previously have gone to manual review, while keeping people in the process wherever judgment is required.
- The feature improves accuracy, strengthens the handling of dense tables and handwriting, and expands language coverage to 40 languages for the DetectDocumentText and AnalyzeDocument APIs.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22308-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22308-3.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22308-4.jpg)

#AmazonTextract #GenerativeAI #DocumentProcessing #AWS #AI

---

*Source: [Announcing Amazon Textract Insights: Verifiable generative AI for documents | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/announcing-amazon-textract-insights-verifiable-generative-ai-for-documents/)*
