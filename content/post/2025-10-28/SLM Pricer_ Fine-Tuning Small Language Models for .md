---
title: "SLM Pricer: Fine-Tuning Small Language Models for Price Prediction"
description: "Exploring the optimization of Small Language Models through LoRA and QLoRA
techniques for specialized price prediction tasks, achieving breakthrough performance with
ensemble methods."
date: 2025-10-28T00:54:05.631418+05:30
tags: ["Small Language Models", "LoRA", "QLoRA", "Fine-tuning", "Transformers", "LLM Engineering", "AI Optimization", "Ensemble Methods", "Parameter Efficient Fine-tuning", "Meta-Llama"]
categories: ["Machine Learning", "AI Engineering", "Model Optimization"]
image: "https://cdn-avatars.huggingface.co/v1/production/uploads/67bb6f5da0cb6e48cfe10c75/uRug8lhUf1wZQ1pO_Edyz.jpeg"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 SLM Pricer: Fine-Tuning Small Language Models for Price Prediction

![Author Profile](https://cdn-avatars.huggingface.co/v1/production/uploads/67bb6f5da0cb6e48cfe10c75/uRug8lhUf1wZQ1pO_Edyz.jpeg)
*Anton Winkler's exploration into optimizing Small Language Models for specialized tasks*

When GPT-3 was published in 2020 (released to a wider audience in 2021), it opened the eyes of
the broader public to the amazing potential of AI. It sounds like a dream: fed with vast amounts
 of online data—including textbooks, literature, scientific works, and forum discussions—a
machine was suddenly capable of solving PhD-level exercises in mathematics, proofreading emails,
 giving life advice, and proposing New Year's Eve dinner menus tailored to dietary constraints
and the kitchen's limitations.

The enormous amount of data processed by these Large Language Models (LLMs) and their vast
number of parameters (e.g., 671 billion for DeepSeek) comes at a literal cost. Training and
inference require massive energy consumption, and the alignment and fine-tuning phases often
involve significant human effort. There is another type of cost as well: *latency*—the time spent waiting for answers.

Recently, *The Economist* highlighted the rising importance of Small Language Models
(SLMs)—ranging from a few million to a few billion parameters—in their article "Peak LLM?" The
article suggests that the trend is shifting from monstrous, "God-like" LLMs provided by tech
companies to smaller, specialized SLMs fine-tuned in-house. They quote David Cox, head of
research on AI models at IBM: *"Your HR chatbot doesn't need to know advanced physics."* SLMs
are going to be a crucial ingredient in many agentic systems: fast, accurate, and precise when given the right task.

## 🎯 The Pricer Challenge

In his lecture on LLM Engineering, Ed Donner provides a detailed example of training an SLM.
This model is fine-tuned to predict prices based on product descriptions. His curated dataset consists of:

- **400,000** training samples
- **2,000** test samples
- Prices restricted to the range **$1–$999**

Example:

```
How much does this cost to the nearest dollar? Delphi FG0166 Fuel Pump Module Delphi brings 80
years of OE Heritage into each Delphi pump, ensuring quality and fitment for each Delphi part.
Part is validated, tested and matched to the right vehicle application Delphi brings 80 years of
 OE Heritage into each Delphi assembly, ensuring quality and fitment for each Delphi part Always
 be sure to check and clean fuel tank to avoid unnecessary returns Rigorous OE-testing ensures
the pump can withstand extreme temperatures Brand Delphi, Fit Type Vehicle Specific Fit,
Dimensions LxWxH 19.7 x 7.7 x 5.1 inches, Weight 2.2 Pounds, Auto Part Position Unknown,
Operation Mode Mechanical, Manufacturer Delphi, Model FUEL PUMP, Dimensions 19.7 Price is $227.00
```

The model is trained to predict the number following **"Price is $"**.

One might be tempted to approach this problem by extracting features from the product
description (e.g., brand, size, weight) and then applying a linear regression model. But
extracting the right features would be quite challenging, and a language model is arguably much
better suited to grasp the important parts of the text. It also has an understanding of the
ordering of numbers. In fact, Ed Donner compares its performance (before and after fine-tuning)
with other approaches. Not to give away too much of the course, I'll just say that the
performance of the fine-tuned SLM compared to frontier models and a human is excellent.

---

## ⚡ The Challenge of Scale

Even for SLMs, "bigger is better" often holds true. In the course, Ed Donner shows how base
models can be chosen with intent, and he selects **Meta-Llama-3.1-8B**, which is on the high end
 of the SLM scale.

Meta-Llama-3.1-8B has 8 billion parameters with 32-bit precision. Training this on a single
affordable GPU presents challenges:

1. Training all parameters on one server will likely not finish in a reasonable amount of
time—and we have far more parameters than we should train given the amount of training data.
2. **Memory requirements are extreme**:
   - 8B weights in 32-bit precision → **32 GB**
   - Gradients → **+32 GB**
   - Optimizer state → **+64 GB**
   - Activations → additional overhead

There are two complementary techniques to address these problems:

---

### 🧩 1. Low-Rank Adaptation (LoRA)

With LoRA, instead of training all 8 billion parameters, low-rank matrices are attached to
selected linear layers. The parameters of the base model are **frozen**. We only train the
weights of the low-rank matrices.

![LoRA Comparison](https://cdn-uploads.huggingface.co/production/uploads/67bb6f5da0cb6e48cfe10c75/dD8JNG-SaA453_EitvdvS.png)
*Visual comparison showing how LoRA reduces the number of trainable parameters*

--- 
### 💾 2. Quantization

Even if we do not train the base model's parameters, we still need to load them into memory.
Parameters for Meta-Llama-3.1-8B are stored in 32-bit precision, which would require around 32
GB of memory. It turns out that one can reduce this precision without losing much of the model's
 performance—even going down to 4 bits. Quantization is a separate technique from LoRA, but
their combination is widespread, leading to what is known as QLoRA.

![Traditional vs QLoRA](https://cdn-uploads.huggingface.co/production/uploads/67bb6f5da0cb6e48cfe10c75/GUu3w3Nar91dhMhmN0CzO.png)
*Comparison between traditional fine-tuning and QLoRA approach*

## 📊 Optimal Performance in the Overfitting Regime

In his course, Ed Donner fine-tunes the Meta-Llama-3.1-8B model. Initially, the **mean absolute
error (MAE)** was approximately **$400**, and fine-tuning reduced it to an impressive
**$46.67**. I attempted to reproduce these calculations. Unlike in the course, I used a
validation set (Ed Donner does recommend students add one).

![Training Progress](https://cdn-uploads.huggingface.co/production/uploads/67bb6f5da0cb6e48cfe10c75/fxxQpjp6UAx_TULLifdik.png)
*Training and validation metrics over the course of fine-tuning with hyperparameters from the
course targeting attention layers. Generated on wandb.ai.*

The best result I obtained while trying to reproduce the result from the course—keeping
hyperparameters unchanged—was **$48.24** from the third epoch (I also tried one, two, and four
epochs). This leads to an interesting finding: **The best results for the MAE occur in a regime of clear overfitting.**

Ed Donner's result is slightly better, with an MAE of around **$47**. I did not manage to fully
reproduce it. I contacted him to get details, particularly regarding the number of epochs he
ran. (The snapshot he uses for the results appears to be taken after around 3.4 epochs. I did
try running 4 epochs, but it did not bring any improvement. The difference may also simply be
due to noise—I analyze this below.)

--- 
## 🏆 The Donner-Winkler Model Contest: Too Close to Call

The Meta-Llama-3.1-8B model I fine-tuned is a representative of a transformer architecture,
introduced in the seminal article "Attention Is All You Need". The core of the Meta-Llama-3.1-8B
 model consists of 32 transformer layers.

![Llama Transformer Layer](https://cdn-uploads.huggingface.co/production/uploads/67bb6f5da0cb6e48cfe10c75/Dge2gcEPTkhSXHUi5SbiK.png)
*Architecture diagram of a single transformer layer in the Llama model*

The majority of parameters is contained in the Multi-Head Self-Attention and in the Feed-Forward
 Network. There are compelling arguments for why Multi-Head Self-Attention can be a powerful
approach, particularly for text processing. As "self-attention" already suggests, it allows the
model to connect distant tokens—a task which sequence models (RNNs, LSTMs, GRUs) struggle with.
It appears more difficult to find arguments for the Feed-Forward Network.

> If adding extra dense projections is so useful, why don't we also apply one or two to the
output of the attention mechanism? [...] That's roughly the thought process that I imagine
unfolded in the minds of the inventors of the transformer architecture at the time.
> > — François Chollet, *Deep Learning with Python*, Second Edition, 2021

In any case, the Feed-Forward Network has proven efficient in practice.

### 🎯 Which Layers Should We Target?

So which layers should be trained with the (Q)LoRA approach? The authors of LoRA restrict
themselves to the attention module "both for simplicity and parameter-efficiency." Ed Donner, in
 his course, mentions that targeting the attention layers was the standard choice.

The documentation of the Parameter-Efficient Fine-Tuning (PEFT) library states:

> Low-Rank Adaptation (LoRA) is a PEFT method that decomposes a large matrix into two smaller
low-rank matrices in the attention layers.

And in its conceptual guide:

> In principle, LoRA can be applied to any subset of weight matrices in a neural network to
reduce the number of trainable parameters. However, for simplicity and further parameter
efficiency, in Transformer models LoRA is typically applied to attention blocks only.

On the other hand, in the QLoRA paper, the best results were obtained when **all linear layers**
 (i.e., Attention and Feed-Forward) were targeted.

After having tried a number of different ideas without managing to beat Ed Donner's fine-tuned
model, I gave this approach a try. Here are the results for the **first 250** data points. (I
only state the hyperparameters which were changed compared to Ed Donner's fine-tuning.)

![Model Comparison](https://cdn-uploads.huggingface.co/production/uploads/67bb6f5da0cb6e48cfe10c75/8JfV69ewWmZfrgE0zcDgl.png)
*Performance comparison between different layer targeting strategies*

### 📈 Results

When targeting only attention layers, the performance of my models was slightly worse than the
"Ed Donner model." However, **targeting all linear layers, I got very close to his performance.**

What is also compelling is the fact that when targeting all linear layers, I clearly obtain
lower loss and higher accuracy than when I target only the attention layers.

![Training Comparison](https://cdn-uploads.huggingface.co/production/uploads/67bb6f5da0cb6e48cfe10c75/41oU-TJ2PMitq8pAnitr9.png)
*Training and validation metrics over the course of fine-tuning for attention-only layers vs all
 linear layers. Generated on wandb.ai.*

As the standard error bars indicate, when we only evaluate the first 250 samples, there is
considerable uncertainty. I therefore calculated the price predictions on all available test
data of size **4,588** (in the lecture, this is reduced to 2,000 samples).

![Comprehensive Results](https://cdn-uploads.huggingface.co/production/uploads/67bb6f5da0cb6e48cfe10c75/nnkSGopgR6PbJX0JmwpuJ.png)
*Full dataset evaluation showing statistical significance of improvements*

The comprehensive evaluation shows that the model targeting all linear layers consistently
performs better, with the differences becoming statistically significant over the larger sample size.

--- 
## 🤝 The Donner-Winkler Model Ensemble: MAE $44

When I studied the SLM pricer, I noticed how hard it was to get below **$47** MAE for the first
250 samples. Looking at the results of the different models I evaluated, their predictions were
clearly correlated. There seemed to be "hard" product descriptions where all of them struggled
and "simple" ones where they all were close. I wondered if we were approaching the **Bayes
error**¹, which cannot be beaten.

We now have two models which perform similarly on average, with an MAE of around $47 on the
first 250 samples. What if we combine them by averaging their predictions? It is easy to see
that the MAE of the combined model (the "ensemble") is going to be at least as good as the
average of the two MAEs. If both models consistently overestimate or underestimate the true
price, the ensemble will perform no better than the average of the two models—but otherwise,
some of the errors cancel out and the ensemble performs better.

![Ensemble Results](https://cdn-uploads.huggingface.co/production/uploads/67bb6f5da0cb6e48cfe10c75/4G5DkXUzE6a9GAiqzkZ9q.png)
*Pairwise comparison showing the power of ensemble methods*

Indeed, the ensemble of the attention-only model **(ed-donner|attention|epoch?|LoRA_R32)** and
my all-linear-layers model **(all-linear|batchsize64|2epochs|LoRA_R16)** reduced the MAE to
**$43.92**—representing the best performance achieved in this experiment. This demonstrates that
 the two models, trained on different layer configurations, capture complementary aspects of the pricing function.

--- 
## 📚 Epilogue

What a satisfying outcome: The best performance does not come from a single model competing with
 others, but from an ensemble. It is a victory for the team. :)

Nevertheless, I do have to admit that I felt a bit frustrated: In the course, only the results
of the first 250 samples are shown, where the MAE of Ed Donner's model is reported as
**$46.67**. My best model may perform better on the complete test set, but on the first 250 its
MAE is **$46.91**. And I tried out a number of different ideas too—e.g., training models
specialized for different categories, changing prompts, making random transformations to the
prompts, training Qwen models. None of them was able to beat $46.67.

I felt reminded of Phileas Fogg in Jules Verne's *Around the World in Eighty Days*, who
tragically seemed to have lost his bet, taking 80 days and 5 minutes to circle the Earth. Then I
 noticed that when I evaluated Ed Donner's model on the first 250 samples **I got an MAE of
$46.74**, not $46.67. This is because I had run this on my own computer with a different NVIDIA
GPU than was used in the course (where it was done on a T4 via Google Colab). The results we get
 are **not deterministic**—they depend on hardware variation and library versions.

I had run my best performing all-linear-layers model on a T4 via Google Colab as well, but with
the latest libraries, which had changed since autumn 2024 when Ed Donner made his run. So I gave
 the evaluation another try using **exactly** the same hardware and software libraries as were
used in the course. And here is the result:

![Final Results](https://cdn-uploads.huggingface.co/production/uploads/67bb6f5da0cb6e48cfe10c75/TnVd8q65ZffR4rLTAKRHV.png)
*The moment of truth: achieving breakthrough performance with identical conditions*

The MAE is **$46.48** a few cents better than in the course.

Similar to Phileas Fogg, who noticed that by travelling east he had gained one day just early
enough to still win his bet, I felt I had achieved my goal after all when I saw this result.

Phileas Fogg married two days after spectacularly winning his bet—and I assume lived happily
ever after. For me, the next pricer challenge is going to begin soon. Ed Donner is updating his
course at the moment. He told me he has managed to find a model that performs significantly better.

## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/antonawinkler/slm-pricer*

## 🏁 Conclusion

This exploration into Small Language Model optimization reveals several crucial insights for the
 AI engineering community:

1. **💡 Strategic Layer Targeting**: Contrary to conventional wisdom focusing solely on
attention layers, targeting all linear layers in transformer architectures can yield superior
performance for specialized tasks.

2. **🎯 Ensemble Power**: The combination of complementary models trained with different
configurations consistently outperforms individual models, achieving a breakthrough MAE of $43.92.

3. **⚖️ Overfitting as Strategy**: The optimal performance occurred in the overfitting regime,
challenging traditional machine learning paradigms and suggesting that task-specific fine-tuning
 may benefit from different optimization strategies.

4. **🔧 Hardware Determinism**: Model performance can vary significantly based on hardware and
software environments, emphasizing the importance of reproducible experimental conditions.

The shift toward specialized SLMs represents a practical evolution in AI deployment—prioritizing
 efficiency, speed, and task-specific accuracy over general-purpose capabilities. This research
demonstrates that with careful architectural choices and ensemble strategies, smaller models can
 achieve remarkable performance on specialized tasks while maintaining computational efficiency.

*#SMALLLANGUAGEMODELS #LORA #QLORA #FINETUNING #TRANSFORMERS #LLMENGINEERING #AIOPTIMIZATION
#ENSEMBLEMETHODS*

--- 
## 📝 Footnotes

**[1]** Bayes error: The theoretical minimum prediction error determined by irreducible
uncertainty in the data.

*All code from this experiment is available on GitHub, and the best pricer model is available on
 Hugging Face. Special thanks to Ed Donner for his excellent LLM Engineering course.*

