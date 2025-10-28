---
title: "GSMA Open-Telco LLM Benchmarks 2.0: The First Dedicated LLM Evaluation for Telecoms"
description: "Cross industry effort to build telecom LLM benchmarks revealing how advanced
language models perform on real-world telecom challenges from standards interpretation to
network troubleshooting."
date: 2025-10-28T00:59:24.402764+05:30
tags: ["GSMA", "LLM", "Benchmarks", "Telecommunications", "5G", "Network Management", "AI Evaluation", "Network Troubleshooting", "Intent-to-Configuration", "TeleYAML", "TeleLogs", "TeleMath", "3GPP", "Network Automation"]
categories: ["Telecommunications", "Artificial Intelligence", "Network Management"]
image: "https://cdn-uploads.huggingface.co/production/uploads/669f33546634993898163061/QStlXRzFuhr8RMxc7OH60.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 📡 GSMA Open-Telco LLM Benchmarks 2.0: The First Dedicated LLM Evaluation for Telecoms

*Cross industry effort to build telecom LLM benchmarks. The GSMA Open-Telco LLM Benchmarks
reveal how today's most advanced language models perform when faced with real-world telecom
challenges—from standards interpretation to network troubleshooting.*

Short on time? Jump straight to the [GSMA Open-Telco LLM
Leaderboard](https://huggingface.co/spaces/otellm/gsma-open-telco-llm-leaderboard).

## 🔄 A Recap

The first release of GSMA Open-Telco LLM Benchmarks was aimed to establish the first systematic,
 telecom-centric evaluation framework for large language models (LLMs). While general-purpose
LLMs had achieved remarkable progress on conventional NLP tasks, their performance on
telecom-specific tasks, including telecom standards, and network operations and configuration
remained poorly understood and largely unquantified.

[GSMA Open-Telco LLM Benchmarks 1.0](https://huggingface.co/blog/otellm/gsma-benchmarks-01)addressed this gap by introducing a selected group of tasks designed around the telecom industry
 and its requirements. It included datasets such as:

1. **TeleQnA** - evaluates the models' understanding of domain knowledge and standards
2. **3GPPTdocs Classification** - evaluates the ability to interpret and categorize complex technical specifications
3. **FOLIO and MATH500** - reasoning-oriented tasks that test logic consistency and numerical
reasoning under telecom-specific constraints

These tasks offered a multi-faceted view of model capabilities, from comprehension and reasoning
 to information retrieval.

The initial results showed that even the most advanced models, including state-of-the-art
commercial LLMs, showed strong performance on generic reasoning but significant limitations when
 tested with telecom-native scenarios. On tasks such as standards interpretation or technical
classification, performance often dropped well below expectations, in some cases falling below 50%.

These findings confirmed a critical gap: telecom requires more than language proficiency, it
demands deep structural understanding, standards literacy, and the ability to reason over
complex, multi-layered information.

## 🤝 Industry Momentum: Multi-Operator Collaboration

Over the past year, the GSMA Open-Telco benchmarks project has expanded far beyond its initial
proof-of-concept phase to become a shared platform for collective LLM experimentation and
validation, with contributions now coming directly from major mobile network operators (MNOs) around the world.

This collaborative phase was made possible with the active participation from across the ecosystem, including:

**Tech & Research:** GSMA, Huawei GTS, The Linux Foundation, Khalifa University, Universitat
Pompeu Fabra (UPF), University of Texas, and Queen's University.

**Telcos:** AT&T, China Telecom, Deutsche Telekom, du, KDDI, KPN, Liberty Global, Orange,
Telefónica, Turkcell, Swisscom, Vodafone.

**Industry Labs & SMEs:** NetoAI, Datumo, Adaptive-AI

Participants have contributed new task definitions, operational scenarios, and ground-truth
datasets, expanding the scope of the benchmarks beyond the original knowledge-centric focus.
This collective input has driven the evolution of evaluation tasks from isolated
question-answering and classification exercises to complex, context-rich workflows that better
approximate production-level use cases.

## 📊 Expansion of Benchmark Scope: Two Working Groups

The second phase of the GSMA Open-Telco Benchmark saw 12 mobile network operators submit 34
concrete use cases spanning eight strategic domains, ranging from RAN optimization and
forecasting to customer support and knowledge retrieval, with the majority of priorities
clustered around three core operational areas: *Network Management*, *Network Configuration*,
and *Network Troubleshooting*.

These three pillars represent critical touchpoints where AI systems and LLMs are expected to
deliver tangible impact in real-world telecom environments. They also correspond directly to the
 operational lifecycle of a network:

- **Management:** continuous, intent-driven oversight of network behavior, performance, and
policy execution
- **Configuration:** the translation of high-level intents into deployable configurations, such
as slice provisioning, parameter tuning, or service rollout
- **Troubleshooting:** rapid and accurate root-cause analysis, ticket handling, and automated
resolution in live environments

Recognizing this, the GSMA Open-Telco LLM benchmarks consortium formalized these domains into
two dedicated working groups, each co-led by MNOs, industry, and research partners charged with
building specialized datasets, tasks, and metrics that reflect their operational realities.

### ⚙️ Network Management & Configuration

The first working group, led by Khalifa University, addresses one of the most fundamental
challenges in telecom automation, which is focused on the translation of high-level operator
intents into machine-executable configurations. As networks evolve toward AI-native operation,
the ability of LLMs to correctly interpret natural language requests and convert them into
structured, standards-compliant outputs, whether YAML-based policies or slice configuration
templates, is becoming essential for closed-loop automation and zero-touch orchestration.

This working group focuses on two complementary tasks that together define the foundation of intent-driven management:

#### *Intent-to-Configuration for 5G Core Networks (TeleYAML)*

At the core of intent-based networking lies the capability to transform human-level requests
into precise, structured configurations. **TeleYAML** benchmark dataset is developed with the
aim to evaluate how effectively an LLM can generate valid, complete, and standards-aligned YAML
configuration intents from free-form operator instructions. TeleYAML (comprising 300 samples and
 is a subset of [NetBench](https://arxiv.org/abs/2407.09424)) is purpose-built for the 5G Core
domain, focusing on three key configuration categories that capture critical aspects of core network intelligence:

- **Network Function & AMF Configuration:** Provisioning, activation, and parameterization of
core network functions, including AMF, SMF, and UPF
- **Subscriber Management & UE Provisioning:** Defining subscriber profiles, authentication
policies, and service entitlements through declarative intent
- **Network Slicing & Slice Deployment:** Configuring slice descriptors, mapping service types
(eMBB, URLLC, mIoT), and deploying slice instances

The dataset is divided into two complementary tasks, namely, 200 samples focused on
intent-to-YAML generation for 5G Core automation, and 100 samples focused on slice configuration
 generation tasks, targeting specific network functions, subscriber provisioning, and slice deployment scenarios.

### 🔧 Network Troubleshooting

The second working group, co-led by AT&T and Huawei, focuses on the following critical
capability: assessing how effectively LLMs can interpret complex telemetry data, correlate
symptoms with underlying causes, and support autonomous decision-making during network
incidents. In this working group, [**TeleLogs**](https://arxiv.org/abs/2407.09424), a
purpose-built benchmark, was designed to evaluate LLM performance on root-cause analysis (RCA) tasks in 5G networks.

TeleLogs is a synthetic yet realistic dataset seeded from real network traces, designed to
measure an LLM's ability to perform structured reasoning over multi-source network data. It
reflects the complexity of production troubleshooting workflows, where faults rarely occur in
isolation and diagnosing them requires contextual understanding across multiple network layers.

Each sample of the dataset combines a symptom description with context data, such as user-plane
and signaling-plane drive test results, engineering KPIs, and configuration information, and
asks the model to infer the most likely root cause. Scenarios are designed as multiple-choice
questions (MCQs), typically offering eight potential solutions, to provide solid evaluation of
the diagnostic precision and reasoning depth. The dataset contains pre-labeled root-cause
categories, and has more than 2000 samples in the training set and 800 samples in the test set.

### 📚 Measuring Domain Depth and Standards Understanding

The [**TeleQnA**](https://arxiv.org/abs/2407.09424) benchmark evaluates an LLM's ability to
understand and reason about telecom knowledge through a diverse set of 10,000 MCQs. Covering
terminology, research trends, and technical details from standards bodies such as IEEE and 3GPP,
 it probes well beyond surface-level familiarity.

### 📋 On Telecom Standard Structuring

The **3GPP-TSG** benchmark focuses on the model's ability to interpret and classify 3GPP
technical knowledge into the correct categories based on their content, purpose, and context.
This task requires the model to recognize small distinctions between 3GPP technical information
and map them to the appropriate working group or specification area. High performance here
indicates that an LLM can effectively organize standards-related information.

### 🧮 On The Reasoning Aspect

While the primary focus of the GSMA Open-Telco Benchmarks has been on domain-specific tasks such
 as configuration generation, troubleshooting, and intent translation, another dimension is
becoming increasingly important in evaluating the readiness of LLMs for telecom deployment:
quantitative reasoning. This dimension demonstrates more than functional correctness, but also
they assess whether models can reason like telecom engineers and operate sustainably at scale.

#### *TeleMath: Benchmarking Quantitative Reasoning for Telecom*

From link-budget calculations and throughput modeling to queueing analysis and protocol
optimization, telecom operations are deeply rooted in quantitative reasoning. The
[**TeleMath**](https://arxiv.org/abs/2407.09424) benchmark directly targets this capability,
evaluating an LLM's ability to solve telecom-specific mathematical problems and output precise numerical answers.

The dataset consists of 500 expert-curated question-answer pairs covering a wide range of
engineering domains. Each item includes a clearly defined question, a strictly numerical
solution, difficulty level, and category tags. Problems range from physical-layer computations
and access-protocol analysis to resource-allocation modeling, ensuring that models are tested
not only on formula application but also on logical reasoning, unit handling, and equation correctness.

## 🔍 Evaluation Pipelines

To capture the diverse nature of telecom tasks, the GSMA Open-Telco LLM Benchmarks employ two
complementary evaluation pipelines:

### 1. Exact Evaluation for Objective Scoring at Scale

For tasks with well-defined answers, such as classification, MCQ, or numerical problem solving,
the benchmarking framework uses an automated exact-match evaluation approach. In this pipeline,
the model receives a question (and, where applicable, a set of answer options) and must output a
 single answer or choice. This prediction is then automatically compared against a ground-truth key.

- ☑️ **Datasets:** 3GPP-TSG, TeleQnA, TeleLogs, TeleMath
- ☑️ **Metric:** Exact-match accuracy

This approach provides highly objective, machine gradable and reproducible results, making it
ideal for large-scale benchmarking campaigns. It enables fast comparison of multiple models
across a variety of tasks and ensures that results are directly tied to correctness.

### 2. LLM-as-a-Judge Evaluation

Not all tasks have a single *correct* answer. Configuration generation, intent translation, and
slice provisioning often produce structured, multi-dimensional outputs where accuracy can be
measured in degrees, comprising completeness, syntax, semantic fidelity, and reasoning quality.
For such scenarios, the framework uses an **LLM-as-a-judge** evaluation pipeline.

In these LLM-as-a-Judge pipelines, a powerful evaluator model (i.e., GPT-oss-120B) is given the
original prompt, the candidate model's output, and a reference solution. Then, it scores the
output on a scale of 1–10 according to structured metrics that assess correctness, completeness,
 alignment with intent, and quality of reasoning.

- ☑️ **Dataset:** TeleYAML
- ☑️ **Metric:** Graded score (1–10)

This approach is particularly valuable for evaluating complex, open-ended tasks such as YAML
generation, slice intent translation, and natural-language-to-configuration mapping.

## 📈 Results & Key Insights

The results presented in Table 1 provide a comprehensive view of LLM performance across a
diverse range of telecom-specific tasks. By benchmarking models on five complementary
dimensions, TeleYAML (intent generation), TeleLogs (network troubleshooting), TeleMATH
(mathematical reasoning), 3GPP-TSG (standard comprehension), and TeleQnA (domain question
answering), we obtain a solid overview of their strengths, weaknesses, and suitability for
real-world telecom applications.

### *Table 1: LLM benchmarks on telecom-specific tasks*

![LLM Benchmarks Table](https://cdn-uploads.huggingface.co/production/uploads/669f33546634993898163061/QStlXRzFuhr8RMxc7OH60.png)

### 🔍 Key observations & findings:

#### 1. General-Purpose Frontier Models Lead Across Most Tasks

General-purpose frontier models such as GPT-5, Grok-4-fast, Claude-sonnet-4.5, and
Gemini-2.5-pro consistently achieve among the highest scores across most benchmarks. **GPT-5**,
in particular, dominates other frontier models in **TeleLogs (80.00)**, **TeleMATH (70.27)**,
**3GPP-TSG (67.9)**, and **TeleQnA (82.51)**, demonstrating its superior general reasoning,
contextual understanding, and adaptability to complex telecom-domain queries. **Grok-4-fast**
and **Gemini-2.5-pro** follow closely, maintaining balanced performance across reasoning,
comprehension, and structured tasks. This performance indicates that state-of-the-art foundation
 models remain a strong baseline even for highly domain-specific tasks.

#### 2. Domain-Specific Fine-Tuning Yields Targeted Advantages

While general models typically dominate overall, several domain-tuned models display competitive
 or even superior performance on specialized tasks. For example, **TSLAM-18B** performs
competitively in **TeleMATH (69.5)** and **3GPP-TSG (63.5)**, narrowing the gap with general
models. On the other hand, AT&T's fine tuned Gemma model, **Gemma-3-4B-IT**, tops all models in
**TeleLogs**. This suggests that *targeted fine-tuning* on telecom-specific tasks can challenge
larger general models on telecom-centric reasoning tasks.

Importantly, even on **TeleYAML**, where absolute scores are lower across the board, we observe
a relative narrowing: mid-scale, domain-aligned models can approach frontier results when
outputs are constrained to schemas and examples. This suggests that targeted task adaptation can
 enhance domain reasoning without requiring large-scale model expansion.

#### 3. Strength in Reasoning vs. Weakness in Domain Context

One clear trend is the gap between reasoning-oriented and context-specific tasks. For instance,
top models achieve high accuracy on **TeleMATH** and **TeleLogs**, which are primarily driven by
 general reasoning and pattern-matching capabilities. However, performance on **TeleYAML**,
which demands structured intent generation aligned with telecom configuration schemas, remains
significantly lower for most models. This suggests that current *LLMs still struggle to
integrate domain-specific knowledge with structured reasoning*, a capability critical for
automation use cases such as network orchestration or slice provisioning.

#### 4. Task Complexity Drives Performance Spread

The spread between top and bottom performers varies considerably by task. **TeleQnA** and
**TeleLogs** exhibit the widest performance gap, with frontier models achieving scores in the
70–80 range while smaller and less specialized models often fall below 30. This broad gap
underscores how complex reasoning, contextual grounding, and domain literacy differentiate model
 capabilities. In contrast, **TeleYAML** displays a much narrower distribution, with most models
 clustered between 25 and 30. This tighter range indicates that when tasks rely on rigid schema
adherence and structured configuration logic, model architecture and scale offer limited
advantages without domain-specific fine-tuning.

#### 5. Domain Curation Outperforms Scale in Some Tasks

Interestingly, model size does not always correlate with performance. The **TSLAM-G3-29B**
achieves an exceptional 82.5 on TeleQnA, outperforming several much larger models like
**Llama-3.3-70B** and **GPT-OSS-120B**. This finding reinforces the strategic importance of
domain-curated datasets, showing that smaller models with focused training on telecom literature
 and standards can outperform generalist giants in specialized question-answering and terminology comprehension.

#### 6. Structured Intent Generation Remains a Core Challenge

Across all models, performance on **TeleYAML** remains relatively low, with even GPT-5 and
Grok-4-fast scoring 27.07 and 26.67, respectively. This highlights an ongoing challenge in
translating natural-language intents into valid, standards-compliant configurations. The limited
 progress in this area indicates that current LLMs struggle with schema alignment and multi-step
 logical mapping required for automation workflows such as slice provisioning and closed-loop orchestration.

![Overall Performance Chart](https://cdn-uploads.huggingface.co/production/uploads/669f33546634993898163061/K8q8mswKP1EOWP-xgS8NL.png)

*Figure 1: Overall evaluation of LLMs in Telecom*

### 🏆 Overall Performance Highlights (Figure 1):

- **Frontier models remain typically dominant:** GPT-5 (65.55), Grok-4-fast (61.52),
Claude-Sonnet-4.5 (60.64), and Gemini-2.5-pro (58.44) lead the overall rankings, confirming that
 large-scale foundation models still provide the most balanced performance across reasoning,
comprehension, and domain understanding.

- **Domain-focused and open-source models close the gap:** Whilst not top performing across all
benchmarks, mid-scale and domain-aligned models such as TSLAM-18B (49.93), GPT-OSS-120B (49.71),
 Qwen-32B (47.46), as well as AT&T's Gemma in *TeleLogs*, deliver competitive results. Showing
that targeted telecom adaptation and open-source can raise effectiveness without frontier-scale compute.

- **Long-tail performance spread:** Beyond the top tier, scores cluster in the 40–50 band (e.g.,
 Mistral-Large-123B 44.93, GPT-OSS-20B 43.97, Llama-3.3-70B 42.40), then lower to the mid-20s
and below for compact models (e.g., LFM2-2.6B 25.79, TSLAM-2B-MINI 25.35, Phi-4-mini-instruct
22.45, Apertus-8B-instruct-2509 21.52), illustrating a significant capability gap between
frontier LLMs and lighter, domain-specific alternatives.

- **Efficiency gains highlight the path to sustainable AI:** Smaller and lightweight models such
 as Phi-4-mini-instruct and TSLAM-2B-MINI deliver respectable accuracy across multiple tasks
while maintaining far lower energy requirements. These models demonstrate that efficiency can
coexist with reasonable performance, particularly in constrained or distributed deployments. As
telecom networks increasingly adopt AI-native architectures, balancing accuracy with energy and
latency efficiency will become essential for sustainable large-scale deployment, making this new
 efficiency-oriented direction a crucial step forward for the industry.

**Strategic takeaway:** Future telecom LLM strategies should combine the broad reasoning
strength of frontier models with open-source based domain-tuned components to achieve both high
accuracy and operational relevance.

### 💡 Final Reflections: Towards Telecom-Optimized Intelligence

The benchmarking results make one point clear: there is no single *"best"* model for telecom AI.
 Frontier LLMs remain unmatched in general reasoning, comprehension, and contextual
understanding, while domain-specialized models excel in structured, schema-driven tasks that
reflect real network operations. This divergence highlights the need for a hybrid architecture
strategy, one that combines the breadth and adaptability of foundation models with the precision
 and domain-awareness of specialized components.

Looking ahead, the most effective telecom AI systems will be multi-layered by design,
integrating multiple capabilities, from intent generation and standards interpretation to KPI
analytics and closed-loop automation, into a cohesive intelligence layer. Bridging the gap
between reasoning-heavy tasks like TeleMATH and knowledge-grounded tasks like TeleYAML
represents a major research frontier. Innovations such as retrieval-augmented generation (RAG),
schema-aware decoding, and multi-agent orchestration will be key to enabling models that are not
 only intelligent but also contextually aligned with the complexities of telecom networks.

Ultimately, ***the future of telecom AI lies not in chasing single-model supremacy but in
orchestrating collaborative intelligence***, systems where diverse models complement one another
 to deliver scalable, efficient, and domain-native capabilities across the entire network lifecycle.

## 🚀 Next Steps

### 📊 Scaling beyond accuracy:

In the next phase, we aim to extend the benchmarking pipeline beyond task-level correctness to
incorporate real-world performance metrics. Our goal is to scale the LLM-as-a-judge approach
across all benchmark categories and introduce a dedicated Agent Evaluation Framework with
metrics such as time-to-first-token and end-to-end task latency, providing deeper insights into model behavior.

### 📈 Richer use cases and harder tasks

The benchmark suite will continue to expand with new operator-contributed use cases derived from
 working group efforts, ensuring coverage of emerging network functions, deployment contexts,
and operational requirements. Additional sub-groups will focus on specialized domains such as
service orchestration, RAN automation, and predictive assurance.

## 🤝 Get Involved

The GSMA Open-Telco LLM Benchmarks thrive on industry collaboration. Whether you're a telecom
operator, AI researcher, or technology provider, your contributions can help shape the future of AI in telecom.

### 📧 How to Participate?

**Submit Telco AI Use Cases & Datasets:** Have a real-world AI use case or dataset that could
improve telecom AI benchmarking? Contribute by emailing [aiusecase@gsma.com](mailto:aiusecase@gsma.com).

**Join the Open-Telco Benchmarking Community:** Be part of the discussion, access the latest
benchmarking insights, and collaborate with leading telcos, AI vendors, and researchers by
joining the [Otellm Hugging Face community](https://huggingface.co/otellm).

**Next Steps:** The Open-Telco initiative will continue expanding benchmarks, integrating new
datasets, use cases, and evaluation metrics. By participating, you help drive standardized,
transparent, and efficient AI adoption in the telecom industry.

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/otellm/gsma-benchmarks-02*

## 🏁 Conclusion

The GSMA Open-Telco LLM Benchmarks 2.0 represent a significant milestone in evaluating AI
readiness for telecommunications. Through comprehensive multi-operator collaboration and
rigorous evaluation across five critical dimensions, this initiative has revealed both the
promise and challenges of current LLMs in telecom applications.

Key insights show that while frontier models excel in general reasoning tasks, domain-specific
fine-tuning can level the playing field for specialized telecom functions. The persistent
challenge in structured intent generation highlights the need for hybrid AI architectures that
combine broad reasoning capabilities with domain-specific precision.

As the telecom industry continues its AI transformation, these benchmarks provide essential
guidance for practitioners, researchers, and operators seeking to deploy intelligent systems
that are both technically sound and operationally relevant. The collaborative framework
established by GSMA ensures that future developments will remain grounded in real-world
requirements and industry expertise.

*#TELECOM #5G #AI #LLM #GSMA #BENCHMARKS #NETWORKAUTOMATION #DEEPLEARNING*

