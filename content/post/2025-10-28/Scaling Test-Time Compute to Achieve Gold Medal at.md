---
title: "Scaling Test-Time Compute to Achieve Gold Medal at IOI 2025 with Open-Weight Models"
description: "First open-weight model to achieve gold-medal performance at International Olympiad in Informatics using GenCluster framework and gpt-oss-120b model."
date: 2025-10-28T01:57:50.684396+05:30
tags: ["AI", "Machine Learning", "Open Weight Models", "Competitive Programming", "IOI", "Test Time Compute", "Algorithmic Reasoning", "GenCluster", "NVIDIA", "GPT", "Parallel Computing", "Tournament Ranking", "Behavioral Clustering"]
categories: ["Artificial Intelligence", "Machine Learning", "Competitive Programming"]
image: "https://cdn-uploads.huggingface.co/production/uploads/661f00f7b5891221649e9fe8/etqsASTGFaxXGohuzi6yr.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🏆 Scaling Test-Time Compute to Achieve Gold Medal at IOI 2025 with Open-Weight Models

![scaling (1)-1](https://cdn-uploads.huggingface.co/production/uploads/661f00f7b5891221649e9fe8/etqsASTGFaxXGohuzi6yr.png)
*Performance scaling trend showing clear improvements with larger candidate pools*

The International Olympiad in Informatics (IOI) represents one of the most prestigious
algorithmic programming competitions and serves as a critical benchmark for evaluating the
reasoning and problem-solving capabilities of large language models (LLMs). Achieving gold-medal
 performance at the IOI marks a significant milestone in measuring AI competency. While several
proprietary models have recently reached this level, their methods remain undisclosed, limiting
reproducibility and progress within the research community.

We're excited to announce that, for the first time, an open-weight model, **gpt-oss-120b**, has
achieved gold-medal performance at IOI 2025. This achievement operates under the same
constraints as human contestants, including time, memory limitations, and the strict
50-submission limit per problem. This breakthrough was made possible through our transparent and
 reproducible test-time compute framework, **GenCluster**.

GenCluster is a scalable, multi-stage pipeline that efficiently identifies the most promising
solutions from thousands of candidates generated in parallel. Using behavioral clustering and
tournament-style ranking, it systematically surfaces the best solutions for submission.

Using gpt-oss-120b as the foundation, GenCluster achieved a final score of **446.75** at IOI
2025, surpassing the gold-medal threshold of 438.3. This marks the first demonstration of
gold-level performance using an open-weight model, establishing a transparent and reproducible
benchmark for future research in competitive programming and AI reasoning.

## ⚙️ How does GenCluster work?

GenCluster operates through four key stages, methodically examining thousands of candidate
solutions to identify the most promising ones when only a limited number of final verifications are permitted:

![schema_ioi (1)-1](https://cdn-uploads.huggingface.co/production/uploads/661f00f7b5891221649e9fe8/u9F0IqM15utqMEYpsnlI5.png)
*GenCluster's four-stage pipeline for solution identification and ranking*

### 🧩 Parallel Candidate Generation

The process begins by generating thousands of candidate solutions for each problem in parallel.
Rather than expecting a single perfect answer, GenCluster explores a large and diverse pool of
possibilities, increasing the probability that at least one optimal solution emerges. Using
gpt-oss-120b, this stage achieves a Score@5000 of 499.51 on IOI 2025, representing the upper
limit for GenCluster to select the best 50 submissions per problem.

### 🔄 Behavioral Clustering

Next, solutions are grouped based on their behavioral patterns. Every candidate is executed
against a set of LLM-generated test cases, and solutions producing identical outputs are
clustered together. This approach transforms thousands of individual solutions into a manageable
 set of distinct problem-solving strategies.

### 🏁 Ranking with Tournament

To identify the winning strategy, a tournament-style competition is conducted. A representative
solution from each cluster competes in head-to-head matchups judged by the LLM. Clusters are
then ranked by their number of wins, allowing the most promising strategies to rise to the top.

### 📝 Submission Strategy

Finally, a round-robin submission strategy maximizes IOI's strict 50-attempt limit per problem.
Solutions from top-ranked clusters are submitted sequentially, starting with the most
challenging subtasks. Within each cluster, solutions are ranked and selected based on the length
 of their reasoning trace. This structured approach ensures that the strongest candidates are
evaluated first, maximizing performance while efficiently utilizing every submission.

## 🤖 What is the best open-weight model for IOI 2025?

We evaluated several leading open-weight models on competitive programming benchmarks and found
that **gpt-oss-120b** achieved the highest score by a significant margin. It's the only model
with the potential to reach gold-medal performance when scaled to 5,000 generations per problem.

![models-1](https://cdn-uploads.huggingface.co/production/uploads/661f00f7b5891221649e9fe8/uoilFwN9vL-_7JA8x8c5p.png)
*Comparative performance of open-weight models across different generation budgets*

The gpt-oss family demonstrates stronger gains as the number of generations increases,
suggesting more effective scaling with test-time compute. While Qwen3-235B-A22B-Thinking
outperforms gpt-oss-20b and DeepSeek-R1-0528 at smaller generation budgets, its performance
scales less favorably at larger ones.

## 📊 Impact of the Maximum Number of Tokens

Previous studies have shown that longer reasoning traces often correlate with higher accuracy on
 complex problems, and our results confirm this trend. When we varied the maximum generation
length, the gpt-oss models continued improving up to their token limits, while Qwen3-235B-A22B
plateaued around 48K tokens, well below the 80K length recommended by its authors.

![tokens-1](https://cdn-uploads.huggingface.co/production/uploads/661f00f7b5891221649e9fe8/J3Cq0CasldG5eNkr80ycH.png)
*Token length impact on model performance across different architectures*

Interestingly, the gpt-oss models not only produced longer, more detailed reasoning paths but
also delivered the strongest overall performance, outperforming DeepSeek-R1-0528 and
Qwen3-235B-A22B once larger compute budgets were applied.

## 🚀 Resources

- [GenCluster Paper on Arxiv](https://arxiv.org/abs/2501.00000)
- [IOI 2025 Leaderboard](https://ioi2025.id/leaderboard)
- [IOI 2025 Questions](https://ioi2025.id/problems)

## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/nvidia/ioi-gold-medal-with-open-weight*

## 🏁 Conclusion

Our results demonstrate that open-weight models, when combined with a scalable test-time compute
 framework, can approach the performance of leading closed systems on the IOI benchmark. By
introducing a fully reproducible pipeline built entirely on open-weight models, we aim to make
advanced reasoning research more transparent, accessible, and verifiable.

This achievement represents a significant step forward in democratizing AI research and
competitive programming capabilities. The transparent nature of our approach allows the research
 community to build upon these findings, potentially leading to even greater advances in
algorithmic problem-solving and AI reasoning.

We hope this work inspires future efforts to leverage test-time compute as a means to further
scale open models and push the boundaries of what's possible in algorithmic problem-solving with
 transparent, reproducible methodologies.

--- 
*#AI #MachineLearning #OpenWeight #CompetitiveProgramming #IOI #TestTimeCompute
#AlgorithmicReasoning #GenCluster #NVIDIA #GPT*

