---
title: "Amazon Bedrock Managed Knowledge Base adds tabular search for agentic retrieval"
slug: "amazon-bedrock-managed-knowledge-base-adds-tabular-search-for-agentic-retrieval"
description: "Amazon Bedrock Managed Knowledge Base adds tabular search, enabling agentic retrieval to answer analytical questions from tables combined with related documents."
date: 2026-11-16T22:14:27+05:30
tags: [AmazonBedrock, TabularSearch, AgenticRetrieval]
categories: ["AI", "Machine Learning", "AI Agents", "Data Analytics"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-22293-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Managed Knowledge Base adds tabular search for agentic retrieval

Amazon Bedrock Managed Knowledge Base adds tabular search, enabling agentic retrieval to answer analytical questions from tables combined with related documents.

## 🔍 Overview
- Tabular search in Amazon Bedrock Managed Knowledge Base lets agents get answers from tables through agentic retrieval.
- When a question needs data from CSV, XLSX, or XLS files, tabular search looks up values and runs calculations across every relevant row in one or more tables or sheets.
- It combines results with facts from related documents to answer analytical questions that take several steps.
- Example: A finance team closing the quarter asks "Which departments must write variance commentary?" No single file has the answer; it depends on the variance policy's threshold, the quarter-close memo's budget revisions, and math over every department in the profit and loss (P&L) workbook.
- Most teams keep narratives and data in the same place; for example, a Microsoft SharePoint site holds workbooks next to policies, and an Amazon S3 bucket holds CSV exports next to PDFs.

## 🔧 How It Works
- Tabular search is part of the agentic retrieval flow; there's nothing to turn on.
- When a question needs the data in a table, the request moves through these stages:
  - Retrieve: Passages come back, including passages from a table file.
  - Plan: The agent uses the question and table structure to determine whether to run code over one or more retrieved tables.
  - Stage: Tabular search copies the original file into an isolated sandbox with no network access.
  - Compute: Model-written code runs over the whole table or sheet.
  - Return: The agent gets back only what the code prints, such as totals or matching rows.
  - Answer: The agent answers from the results and the passages, with citations.
- Tabular search starts when retrieved passages come from a CSV, XLSX, or XLS file and the question needs a calculation across rows or a lookup of specific values.
- The Retrieve API keeps returning passages and doesn't run code.
- Tables lose information when split into passages, in ways that depend on the table's shape:
  - Long tables: A table with thousands of rows spans many passages, and retrieval returns only the few that best match the question. An answer built from them uses a handful of rows, so a total, a comparison, or a threshold check can be incomplete.
  - Wide tables: In a table with hundreds of columns, one row can hold more text than a passage or a search model takes in at once. As a result, values in later columns are harder to match.
  - Long passages from wide tables can also match many unrelated questions and push more relevant passages out of the results.
- Retrieval also has to match a question to the right table; questions use business terms such as "controllable spend," but tables hold cost center codes, account names, and numbers.
- A draft and a final workbook look almost the same to search.
- The rule that gives the numbers meaning is often in a separate document, such as a policy.
- Tabular search therefore splits the work: retrieval only has to return one passage from the right table file, and code then reads the whole table.
- Because retrieval still has to find that file first, naming the file in your question helps.

## ⚙️ Key Details
- Tabular search is built for questions that need calculations or lookups over the table files it retrieves.
- Running code adds at least one more agent turn, so answers that use table data take longer than text-only answers.
- Governed metrics, recurring dashboards, warehouse-scale joins, and reporting controls still belong in business intelligence (BI) tools.
- Tabular search works on table files stored next to your documents, and you don't define a schema.
- In this solution, an Amazon Bedrock Managed Knowledge Base stores your CSV and Excel files together with related documents.
- Then an agent running Amazon Bedrock's Claude 3 reads the files and decides whether to run code over them to answer specific questions.
- The trace shows which files the code was run over.
- To see what tabular search can do, build a knowledge base from a set of sample finance files, then run a question that needs a calculation across rows and check the trace to see which file the code read.
- The knowledge base automatically converts the XLSX workbook to a CSV format for analysis.
- The example question "Which departments must write variance commentary?" needs data from three sources: the variance threshold from the policy, the list of departments and their variances from the workbook, and the list of revised budgets from the memo.
- Sending an AgenticRetrieveStream request with that prompt returns the full answer and citations to the sources.
- The trace shows which passages the search model found and which of those passages the agent used to build the answer; for tabular search, it also shows which file the code was run over.
- In the trace, look for a passage that says: "Based on the provided variance data, the following departments exceed the 5% threshold and require variance commentary: Sales (6.3%), Engineering (6.1%), and Operations (5.5%)."
- The source for that passage isn't the P&L workbook; it's a file that begins with "thought" and ends with ".csv".
- To see what that file contains, copy the "sourceUri" value, including the "s3://" prefix, into the URL bar of a browser logged into AWS, such as the AWS Management Console.
- When you open the URL, you see the result of the calculation over the P&L workbook.
- The file contains the question, the revised budgets from the memo, and the calculated variances.
- Looking back at the trace, the agent used only two passages from the original files: the list of revised budgets from the memo and the definition of the variance threshold from the policy.
- It didn't refer to the workbook at all because it used the computed results instead.

## 💡 Why It Matters
- With retrieval instructions in Amazon Bedrock Managed Knowledge Base, you can customize answers per tenant.
- The same product and policy documents often serve several audiences, such as customers in different regions or internal teams, and each audience needs its own answer.
- You set the voice, format, retrieval guidance, and answer policy that agentic retrieval applies to each request.
- Before this feature, you couldn't set the answer style, so agentic retrieval could use a different style from one request to the next.
- For a fixed voice or structured output, you had to turn off response generation, call a model yourself, and maintain the prompt in every application.
- Now you write that guidance once, as a managed, versioned Amazon Bedrock resource, and each request references it.
- When you change an instruction, you can pin a version so that each application switches to the new version when you're ready.
- AnyCompany Smart Home, a fictitious company that sells a home controller and room sensors in three sales regions, serves as an example; its customer assistant serves all three regions, and its support, field sales, and legal teams use internal assistants built on the same documents; AnyCompany defines each region and internal team as a tenant, and each needs a different answer; a customer in Sales Region Central needs Spanish with day/month/year dates, and a support agent needs a short ticket note; to keep the example compact, every tenant queries one knowledge base, however agentic retrieval can search up to five knowledge bases in a single request, and the tenant's instruction applies to all of them.
- Retrieval instructions change how the assistant answers, but they aren't an authorization or data-isolation boundary; use metadata filters or separate knowledge bases to control what each tenant can retrieve.
- Tenants that share documents still differ in language, date and money conventions, voice, and which policy values they can quote.
- A retrieval instruction has four fields for these differences: persona, who the assistant is including identity, tone, and language; answerFormat, how the answer is structured including how it cites sources; retrievalGuidance, how the agent interprets the question and what it prioritizes when it searches; answerPolicy, whether and how to answer, including questions outside scope.
- The persona, answerFormat, and answerPolicy fields apply only when generateResponse is true, which is the default, and retrievalGuidance applies either way.
- An instruction belongs to your AWS account and AWS Region, not to a knowledge base, and goes through these stages: Create (CreateRetrievalInstruction returns HTTP 202), Review (Amazon Bedrock reviews the instruction's fields asynchronously, and you poll for the result), Activate (a passing review makes the instruction ACTIVE, and DRAFT points to its current content), Version (CreateRetrievalInstructionVersion saves an immutable numbered version), Apply (a request names the instruction and, optionally, a version, which defaults to DRAFT), Report (the first Planning trace event includes appliedInstruction).
- Instructions set voice, format, conventions, and policy wording; they don't limit which documents the agent can retrieve, and they don't choose the tenant's own values, which come from naming the tenant in the request; use metadata filters or separate knowledge bases to limit what each tenant can retrieve, and each tenant gets its own instruction and metadata filter; your backend chooses both from the authenticated tenant, so one shared knowledge base can serve every tenant; a request can query a shared global knowledge base and the tenant's own knowledge base together, each with its own filter.

#AmazonBedrock #TabularSearch #AgenticRetrieval

---

*Source: [Get answers from tables with tabular search in Amazon Bedrock Managed Knowledge Base | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/get-answers-from-tables-with-tabular-search-in-amazon-bedrock-managed-knowledge-base/)*
*Source: [Customize answers per tenant in Amazon Bedrock Managed Knowledge Base | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/customize-answers-per-tenant-in-amazon-bedrock-managed-knowledge-base/)*
