---
title: "From GRPO to DAPO and GSPO: Advancing Reinforcement Learning for Large Language Models"
description: "A comprehensive analysis of the evolution from PPO to GRPO, DAPO, and GSPO in
reinforcement learning for LLMs, exploring how these methods address value model dependencies,
token-level optimization challenges, and MoE architecture instabilities."
date: 2025-10-28T01:03:19.638182+05:30
tags: ["Reinforcement Learning", "Large Language Models", "GRPO", "DAPO", "GSPO", "PPO", "MoE", "Mixture of Experts", "AI Training", "Machine Learning"]
categories: ["Machine Learning", "AI", "Natural Language Processing"]
image: "NA"
math: true
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 From GRPO to DAPO and GSPO: Advancing Reinforcement Learning for Large Language Models

In the reinforcement learning stage of large language models, PPO was once the mainstream
approach. However, its reliance on the value model reveals limitations when handling long text
outputs and complex tasks. GRPO removes the dependency on the value model, significantly
improving scalability, but still leaves room for optimization in efficiency and stability. This
motivated DAPO, which refines details such as sampling, clipping, and gradient calculation. Yet,
 in MoE architectures with dynamically activated experts, token-level optimization under the
GRPO framework still struggles to converge stably. GSPO takes this a step further by shifting
the optimization granularity to the sequence level, fundamentally reducing high variance and structural noise.

In this comprehensive analysis, you'll discover:

1. Why GRPO breaks free from PPO's dependency on the value model, yet can still "collapse" in certain scenarios
2. How Clip-Higher fixes the hidden problem of good tokens being capped too early
3. How Dynamic Sampling prevents massive computation waste from ineffective samples
4. How Token-Level Gradient Loss ensures long responses no longer dilute valuable gradient signals
5. Why GRPO's per-token importance sampling creates huge variance in MoE architectures
6. How GSPO replaces token-level optimization with sequence-level optimization to fundamentally
improve stability and efficiency

## 📊 A Recap on GRPO

The training objective of GRPO is:

```math
J_GRPO(θ) = E_{q ~ P(Q), {o_i}_{i=1}^G ~ π_{θ_old}(O|q)} [ 1/G ∑_{i=1}^G 1/|o_i| ∑_{t=1}^{|o_i|} (
    min(r_{i,t}(θ)A_i, clip(r_{i,t}(θ), 1-ε, 1+ε)A_i) - β D_KL(π_θ || π_ref) )
]
```

where:

```math
r_{i,t}(θ) = π_θ(o_{i,t}|q,o_{i,<t}) / π_{θ_old}(o_{i,t}|q,o_{i,<t})
```

```math
A_i = (r_i - mean({r_1, r_2, ..., r_G})) / std({r_1, r_2, ..., r_G})
```

### ⚙️ What role does the Importance Ratio play?

The essence of importance sampling is that we want to compute expectations under a new
distribution, but our data is drawn from an old distribution. We therefore use the probability
ratio of the same action under the new and old policies as a correction weight:

```math
E_{p_new}[f(x)] = E_{p_old}[p_new(x)/p_old(x) f(x)]
```

This allows us to evaluate the expected value under the new policy using offline data from the
old policy, avoiding the need to resample after each update (thus lowering cost). However, if
the gap between the new and old policies is too large, the variance of the weights can become
very high, leading to unstable training.

### 🔄 How do the signs of A_t and r_t affect training?

Let's analyze the scenarios. Suppose A_t > 0 (the action is better than expected); we want to
increase the probability of this action. If we set ε = 0.2 in clipping, then when r_t > 1.2, the
 `min` and `clip` operations will cap it at 1.2. When r_t < 0.8, no clipping occurs due to the
`min` operation, so positive advantages have their upward change limited.

Conversely, when A_t < 0 (the action is worse than expected), we should reduce the probability
of this action. If r_t < 0.8, the `min` operation limits it further, capping at 0.8A_t; but when
 r_t > 1.2, the `min` operation imposes no restriction.

### 📉 Impact of clipping on gradients and token efficiency

For A_t > 0, when r_t > 1 + ε, i.e., the increase hits the cap, we apply clipping, and the
gradient becomes zero. This effectively nullifies the token's contribution to training.
Similarly, for A_t < 0, if r_t < 1 - ε, i.e., the decrease exceeds the cap, the clipping also
sets the gradient to zero.

---

## 🎯 From GRPO to DAPO

DAPO starts from a straightforward motivation: in practical training, GRPO often wastes a large
amount of learning signal due to issues such as an unreasonable clip range, redundant sampling,
and gradient dilution in long sequences. DAPO addresses these problems with four targeted
improvements.

```math
J_DAPO(θ) = E_{(q,a) ~ P(Q), {o_i}_{i=1}^G ~ π_{θ_old}(O|q)} [
  1/∑_{i=1}^G |o_i| ∑_{i=1}^G ∑_{t=1}^{|o_i|} min(
    r_{i,t}(θ)A_i, clip(r_{i,t}(θ), 1-ε_low, 1+ε_high)A_i
  )
]
```

subject to: `0 < |{o_i | is_equivalent(a, o_i)}| < G`

### 📈 Why does DAPO raise the upper bound 1+ε_high while keeping 1-ε_low fixed?

The authors observed that choosing a small ε as the clip upper bound can lead to the following
problem: if the old policy assigns a very low probability to a sampled token, yet its advantage
is positive (meaning the old model sampled something very good), the current policy is given
little room to increase its probability, even though increasing it is exactly what we want.

For example, if the old policy's probability is 0.9 and ε=0.2, the upper bound is 0.9 × 1.2 =
1.08, which already exceeds the maximum probability of 1.0, so it will never be clipped. But if
the old policy's probability is 0.2, the upper bound becomes 0.24. In this case, even if the
current policy raises the probability to 0.4 (a good improvement), the overly small ε causes it
to be clipped, effectively discarding that token.

This is essentially what we call the **"Matthew Effect"**: *the rich get richer, the poor
struggle to improve*. If the old policy barely manages to sample a crucial token with very low
probability, but the current model significantly increases that probability, it can still be
clipped away, depriving the model of its chance to "turn the tables."

### 🎲 DAPO - Dynamic Sampling

The second innovation in DAPO is **Dynamic Sampling**. The motivation is as follows: suppose for
 a given query we sample 10 responses, and all 10 are either very good or very bad, consistently
 receiving max reward or zero reward. Due to GRPO's computation method, all 10 samples will have
 an advantage of zero, and thus contribute zero gradient.

To counter this, DAPO enforces an additional sampling rule: for each query, the set of sampled
responses must not all have rewards of 0 or 1. If all samples are 0 or all are 1, additional
samples are drawn until this condition is violated.

### 🔗 DAPO - Token-Level Gradient Loss

The third innovation in DAPO fixes the problem that, in GRPO, the gradient weight for each token
 decreases as the sampled response length increases.

Why does this happen? Suppose we sample twice: one response has 200 tokens, the other has 10
tokens. In GRPO's formula, we first average the gradients within each sample, then average
across the batch. This gives each token in the first response a weight of (1/200) × (1/2), while
 each token in the second response gets (1/10) × (1/2). The shorter response's tokens therefore
have a much larger impact.

DAPO's solution: average over the total number of tokens generated across all samples when
computing gradients. In our example, both the long and short responses give each token a weight
of 1/(200+10).

This corresponds to changing the loss aggregation from GRPO's:

```math
1/G ∑_{i=1}^G 1/|o_i| ∑_{t=1}^{|o_i|}
```

to DAPO's:

```math
1/∑_{i=1}^G |o_i| ∑_{i=1}^G ∑_{t=1}^{|o_i|}
```

### 📏 DAPO - Overlong Reward Shaping

DAPO's fourth improvement adjusts rewards for overly long responses using a **soft punishment**
mechanism. Specifically, it penalizes tokens once the generated sequence exceeds a predefined
first length threshold, with the penalty increasing linearly as length grows.

---

## 🏗️ GSPO: Addressing GRPO Instability in MoE Trainin

If DAPO can be seen as a "fine-tuning and refinement" within the GRPO framework, GSPO takes a
more fundamental step: it changes the optimization granularity from token-level to sequence-level.

> **TL;DR:** Traditional algorithms such as PPO and GRPO typically optimize each token in the
model's output individually, giving some tokens higher weights and others lower. While this aims
 for fine-grained optimization, in long-text, large-model scenarios it can instead introduce
noise and reward bias, causing the model to lose direction, or even collapse suddenly. GSPO
aligns the reward and the optimization target by switching from per-token scoring to sequence-level optimization.

### 🎯 What role does the importance ratio play, and why is it problematic in GRPO?

Importance sampling allows us to estimate expectations under a target distribution when we only
have samples from a behavior distribution. However, this correction assumes multiple samples -
if there is only one sample, it cannot effectively adjust for the distribution shift.

The problem in large-model training is that importance sampling is performed **per-token**, and
a single token's ratio cannot meaningfully perform distribution correction. Instead, it
introduces high-variance noise, especially in the unstable MoE setting.

### 🧩 Why does GRPO struggle to converge in MoE architectures?

**Expert activation volatility:** New and old policies may activate different experts,
introducing structural bias and noise. When π_{θ_old} is updated, the router may also change, so
 the two policies could activate completely different sets of experts, even if only one training
 step has passed. This causes large fluctuations in output probabilities, triggering clipping abnormally often.

### 🔄 Routing Replay before GSPO

Routing Replay records the expert activations during sampling from π_{θ_old} and forces π_θ to
use the same routing path during training. The downside: high engineering and infrastructure
cost, and inefficiency - π_θ might have found a better routing path but is forced to follow the old one.

### 🎯 GSPO loss design

```math
J_GSPO(θ) = E_{q ~ P(Q), {o_i}_{i=1}^G ~ π_{θ_old}(O|q)} [ 1/G ∑_{i=1}^G 1/|o_i| ∑_{t=1}^{|o_i|} (
    min(s_i(θ)A_i, clip(s_i(θ), 1-ε, 1+ε)A_i) )
]
```

where:

```math
s_i(θ) = (π_θ(o_i|q) / π_{θ_old}(o_i|q))^{1/|o_i|} =
exp(1/|o_i| ∑_{t=1}^{|o_i|} log(π_θ(o_{i,t}|q,o_{i,<t}) / π_{θ_old}(o_{i,t}|q,o_{i,<t})))
```

> **Key Insight:** If the reward is sequence-level, the importance ratio should also be sequence-level.

GSPO replaces GRPO's per-token ratio r_{i,t}(θ) with a sequence-level ratio s_i(θ), which is no
longer tied to the step index t. Sequence-level ratios are **length-normalized** to reduce
variance and keep values on a consistent scale.

### 📊 Theoretical gradient analysis: GSPO vs. GRPO

**GSPO's gradient:**
```math
∇_θ J_GSPO(θ) = E[1/G ∑_{i=1}^G s_i(θ) A_i · 1/|o_i| ∑_{t=1}^{|o_i|} ∇_θ log π_θ(o_{i,t}|q,o_{i,<t})]
```

**GRPO's gradient:**
```math
∇_θ J_GRPO(θ) = E[1/G ∑_{i=1}^G Â_i/|o_i| ∑_{t=1}^{|o_i|} r_{i,t}(θ) ∇_θ log π_θ(o_{i,t}|q,o_{i,<t})]
```

In GSPO, all tokens in a response share the same weight s_i(θ)A_i/|o_i|, ensuring intra-sequence
 gradient consistency. In GRPO, weights r_{i,t}(θ)A_i/|o_i| vary by token position and context,
leading to higher variance.

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/NormalUhr/grpo-to-dapo-and-gspo*

## ✅ Final Thoughts

GSPO achieves consistent intra-sequence gradient weights, reduces variance between tokens, and
is especially suited for stable training in long-sequence and MoE scenarios. Its introduction
marks a shift from PPO → GRPO → GSPO, moving away from token-level optimization reliant on the
value model toward sequence-level optimization aligned with the nature of the task.

The evolution from GRPO to DAPO and GSPO demonstrates how RL optimization objectives for LLMs
should align closely with the nature of the task, while keeping the training logic simple,
scalable, and deployable. Progress is often driven not by complex tricks, but by insights into the core problem.

_#REINFORCEMENTLEARNING #LLM #GRPO #DAPO #GSPO #MOE #MACHINELEARNING #AI_

