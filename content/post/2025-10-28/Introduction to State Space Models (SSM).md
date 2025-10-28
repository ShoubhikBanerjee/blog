---
title: "Introduction to State Space Models (SSM): A Complete Guide"
description: "A comprehensive guide to State Space Models in deep learning, covering continuous,
 recursive, and convolutional views with practical applications across audio, vision, and text
domains."
date: 2025-10-28T06:46:49.304626+05:30
tags: ["State Space Models", "SSM", "Deep Learning", "S4", "Sequence Modeling", "Neural Networks", "HiPPO", "Long Range Dependencies", "Machine Learning", "AI"]
categories: ["Machine Learning", "Deep Learning", "AI"]
image: "https://cdn-uploads.huggingface.co/production/uploads/613b0a62a14099d5afed7830/G7icfkYoxIqHZcJGHM7UD.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 Introduction to State Space Models (SSM): A Complete Guide

![State Space Model Diagram](https://cdn-uploads.huggingface.co/production/uploads/613b0a62a14099d5afed7830/G7icfkYoxIqHZcJGHM7UD.png)
*Figure 1: View of a continuous, time-invariant SSM*

*A French version is available on my
[blog](https://huggingface.co/blog/lbourdois/get-on-the-ssm-train).*

## 📋 Table of Contents

- **Foreword**
- **Introduction**
- **Definition of an SSM in deep learning**
- **Discretization**
- **Recursive view of an SSM**
- **Convolutive view of an SSM**
- **Advantages and limitations of each of the three views**
- **Learning matrices**
- **Experimental results**
- **Conclusion**
- **To dig deeper**
- **References**

---

## 🙏 Foreword

I'd like to extend my warmest thanks to Boris ALBAR, Pierre BEDU and Nicolas PREVOT for agreeing
 to set up a working group on the subject of SSMs and thus accompanying me in my discovery of
this type of model. A special thanks to the former for taking the time to proofread this blog
post.

---

## 🎯 **Introduction**

The **State Space Models** are traditionally used in control theory to model a dynamic system via state variables.

Aaron R. VOELKER and Chris ELIASMITH addressed the question of how the brain effectively
represents temporal information. They discovered in 2018 in "[Improving Spiking Dynamical
Networks: Accurate Delays, Higher-Order Synapses, and Time
Cells](https://papers.nips.cc/paper/2018/hash/5f2e1a1e6966b54f6b6c3d2b5d6b9f1e-Paper.html)" that
 an SSM is an excellent model for describing the "[time
cells](https://en.wikipedia.org/wiki/Time_cell)" present in the brain (hippocampus and cortex in particular).

From neuroscience, they applied their work to the field of deep learning and were thus (to our
knowledge) the first to use SSMs in deep learning. For more details on this work, please refer
to the "[SSM history](#ssm-history)" section at the end of this blog post.

In this article, we will define the basics of a deep learning SSM. To do this, we will base on
the S4 model introduced in "[*Efficiently Modeling Long Sequences with Structured State
Spaces*](https://arxiv.org/abs/2111.00396)" by Albert GU et al. in 2021. This is not a model
that is used as is in practice (other SSMs with better performance or easier to implement are
now available). We use it here for educational purposes. Released a week earlier than S4,
[LSSL](https://arxiv.org/abs/2110.13985), by the same authors, is also an important source of
information on the subject. We'll take a look at the various developments arising from S4 in a
future [blog post](https://huggingface.co/blog/lbourdois/ssm-2022).

--- 
## ⚙️ **Definition of an SSM in deep learning**

![SSM Structure](https://github.com/lbourdois/blog/assets/58078086/12bbe1cf-3911-4bad-9a3b-3f427bc6bc82)
*Figure 2: Image from blog post "Structured State Spaces: Combining Continuous-Time, Recurrent,
and Convolutional Models" by Albert GU et al. (2022)*

An SSM is based on three variables that depend on time `t`:

- `x(t) ∈ ℂⁿ` represents the `n` state variables
- `u(t) ∈ ℂᵐ` represents the `m` state inputs
- `y(t) ∈ ℂᵖ` represents the `p` outputs

It's made up of four learnable matrices: **A**, **B**, **C** and **D**:

- `A ∈ ℂⁿˣⁿ` is the state matrix (controlling the latent state `x`)
- `B ∈ ℂⁿˣᵐ` is the control matrix
- `C ∈ ℂᵖˣⁿ` is the output matrix
- `D ∈ ℂᵖˣᵐ` is the command matrix

This can be reduced to the following system of equations:

```
x'(t) = Ax(t) + Bu(t) y(t) = Cx(t) + Du(t)
```

In deep learning SSMs, `Du = 0` is seen as an easily computable *skip connection*, simplifying to:

```
x'(t) = Ax(t) + Bu(t) y(t) = Cx(t)
```

This system is continuous and must be discretized before being supplied to a computer.

--- 
## 🔄 **Discretization**

Discretization is one of, if not the most important point in SSM. All the efficiency of this
architecture lies in this step, since it enables us to pass from the continuous view of the SSM
to its two other views: the **recursive view** and the **convolutive view**.

*If there's one thing to remember from this article, it's this.*

We'll see in later [articles](https://huggingface.co/blog/lbourdois/ssm-2022) that there are
several possible discretizations. This is one of the main differences between the various existing SSM architectures.

--- 
## 🔁 **Recursive view of an SSM**

To discretize the continuous case, let's use the [trapezoid
method](https://en.wikipedia.org/wiki/Trapezoidal_rule) where the principle is to assimilate the
 region under the representative curve of a function `f` defined on a segment `[tₙ, tₙ₊₁]` to a trapezoid.

Through mathematical derivation using the trapezoid method, we obtain our discretized SSM:

```
Ā = (I - Δ/2 A)⁻¹(I + Δ/2 A) B̄ = (I - Δ/2 A)⁻¹Δ
C̄ =
```

We then have:

```
xₖ = Āxₖ₋₁ + B̄u yₖ = C̄x
```

The notation of matrices with a bar was introduced in S4 to designate matrices in the discrete
case and has since become a convention in the field of SSM applied to deep learning.

--- 
## 🌊 **Convolutive view of an SSM**

This recurrence can be written as a convolution. By iterating the equations of the system:

- Step 0: `x₀ = B̄u₀
- Step 1: `x₁ = ĀB̄u₀ + B̄u
- Step 2: `x₂ = Ā²B̄u₀ + ĀB̄u₁ + B̄

We can observe the convolution kernel:

```
K̄ₖ = (C̄B̄, C̄ĀB̄, ...,
```

This convolution kernel is calculated by [Fast Fourier
Transform](https://en.wikipedia.org/wiki/Fast_Fourier_transform) (FFT) and will be explained in future articles.

--- 
## ⚖️ **Advantages and limitations of each of the three views**

![Three Views Comparison](https://github.com/lbourdois/blog/assets/58078086/cb2dca34-9a3e-481a-8773-2360a1ceaa1c)
*Figure 3: Image from the paper "Combining Recurrent, Convolutional, and Continuous-time Models
with Linear State-Space Layers" by Albert GU et al.*

### **Continuous View**
✅ **Advantages:**
- Automatically handles continuous data (audio signals, time series)
- Mathematically feasible analysis

❌ **Disadvantages:**
- Extremely slow for both training and inference

### **Recursive View**
✅ **Advantages:**
- Natural inductive bias for sequential data
- Efficient inference (constant-time state updates)

❌ **Disadvantages:**
- Slow learning (lack of parallelism)
- Gradient disappearance or explosion with long sequences

### **Convolutional View**
✅ **Advantages:**
- Local, interpretable features
- Efficient (parallelizable) training

❌ **Disadvantages:**
- Slow in online or autoregressive contexts
- Fixed context size

**Key Insight:** We can switch between views depending on the stage (training vs inference) and
data type to maximize model efficiency.

--- 
## 🧠 **Learning matrices**

In the convolution kernel, `C̄` (row vector) and `B̄` (column vector) are learnable. For `Ā`, w
need it to be efficiently computable as powers. The best option is to have it diagonal:

```
A = [λ₁  0   ⋯  0 ]    ⟹    Aᵏ = [λ₁ᵏ  0   ⋯  0 ] [0   λ₂  ⋯  0 ]           [0    λ₂ᵏ ⋯  0 ]
    [⋮   ⋮   ⋱  ⋮ ]           [⋮    ⋮   ⋱  ⋮ ] [0   0   ⋯  λₙ]           [0    0   ⋯  λₙᵏ]
```

### **HiPPO Matrix**

Empirically, an SSM initialized with a random `A` matrix leads to poor results, whereas
initialization based on the **HiPPO** matrix (*High-Order Polynomial Projection Operator*) gives
 excellent results (from 60% to 98% on the MNIST sequential benchmark).

The **HiPPO-LegT** matrix formula is:

```
Aₙₖ = { (-1)ⁿ⁻ᵏ(2k+1)  if n > k
  k+1             if n = k 0               if n < k
}
```

This matrix is not normal, but can be decomposed as a normal matrix plus a matrix of lower rank
(NPLR for *Normal Plus Low Rank*). The authors prove this can be computed efficiently via:
- Truncated generating series
- Cauchy kernels
- Woodbury identity

--- 
## 📊 **Experimental results**

Let's analyze S4's performance across various benchmarks:

### **Audio: Speech Commands**

| Model | Parameters | Accuracy | 16K→8K Transfer |
|-------|------------|----------|-----------------|
| ConvNet | 85M | 95.4% | Poor |
| S4 | 1M | 98.3% | 95% retained |

**Key Insights:**
- S4 achieves +13% better performance with 85× fewer parameters
- Excellent transfer learning due to continuous view (simply halve Δ)

### **Time Series Performance**

S4 outperformed the Informer transformer on 40 of 50 configurations in univariate time series forecasting.

### **Vision: sCIFAR-10**

S4 established state-of-the-art on sCIFAR-10 with just 100,000 parameters.

### **Text: Long Range Arena**

| Task | S4 Performance | Notes |
|------|----------------|-------|
| Path-X (16K) | First to succeed | Demonstrates long-sequence capability |
| Overall LRA | Strong performance | 6 task benchmark |

**Notable Achievement:** S4 was the first model to solve Path-X with 16K tokens. It took over 2
years before transformers could match this, and they still cannot handle PathX-256 (65K tokens).

**Limitation:** Higher perplexity than transformers on WikiText-103, likely due to text's
non-continuous nature.

--- 
## 🏁 **Conclusion**

SSMs are versatile models with three complementary views:
- **Continuous view** for mathematical analysis and irregular sampling
- **Recursive view** for efficient inference
- **Convolutional view** for parallel training

### **Key Strengths:**
- 🚀 Handle very long sequences efficiently
- 💡 Lower parameter count than alternatives
- 🔄 Versatile across modalities (text, vision, audio, time-series)
- ⚡ Fast training and inference

### **Future Directions:**
The main differences between SSM architectures lie in:
- Discretization methods
- Definition of the **A** matrix

As we'll see in future articles, these fundamental concepts have evolved significantly, leading
to even more powerful architectures.

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/lbourdois/get-on-the-ssm-train*

--- 
## ✅ Final Thoughts

State Space Models represent a fundamental shift in sequence modeling, offering a mathematically
 principled approach that bridges continuous dynamical systems with discrete deep learning.
Their ability to switch between different computational views makes them uniquely suited for
modern AI applications requiring both efficiency and long-range dependencies.

The journey from neuroscience observations to practical deep learning architectures demonstrates
 the power of interdisciplinary research in advancing AI capabilities.

--- 
*#STATESPACENODELS #DEEPLEARNING #SEQUENCEMODELING #S4 #LONGRANGEDEPENDENCIES #NEURALNETWORKS
#AI #MACHINELEARNING*

--- 
**MCP Server used:** No MCP servers were utilized for this content conversion task, as it
involved text processing and markdown formatting rather than tool-specific operations.

