---
title: "Projected Abliteration: Refining Language Model Safety Removal"
description: "A refined technique for removing refusal behaviors from language models by
targeting only mechanistically relevant components of the refusal direction, improving upon
conventional abliteration methods."
date: 2025-10-28T00:53:51.996401+05:30
tags: ["Machine Learning", "Language Models", "Abliteration", "AI Safety", "PyTorch", "Gemma", "Model Alignment", "Refusal Direction", "Neural Network Intervention", "Model Safety"]
categories: ["Artificial Intelligence", "Machine Learning", "AI Safety"]
image: "NA"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🧩 Projected Abliteration: Refining Language Model Safety Removal

Abliteration is a technique for removing refusal behaviors from language models by identifying
and intervening on "refusal directions" in activation space, notionally represented via a single
 mean refusal direction. We present a refinement called "projected abliteration" that improves
upon the conventional approach by removing only the mechanistically relevant components of the refusal direction.

Below we propose a refinement to conventional abliteration.

## ⚙️ Refusal Direction

In conventional abliteration, the refusal direction is often calculated as:

**r⃗ = μ⃗_H - μ⃗_

Where μ_H is the mean of harmful-refusal activations/directions, and μ_A is the mean of
harmless-acceptance activations/directions.

We observe that the refusal direction can be decomposed into two projections based on our choice
 of either of the two mean directions.

## 🔍 Decomposition Relative to μ⃗_A (Harmless Mean

**r⃗ = r⃗_∥μ_A + r⃗_⊥μ_

Can be expressed as:

**(r⃗ · μ⃗_A)/(∥μ⃗_A∥²) μ⃗_A + r⃗_⊥

Where r⃗_∥μ_A is the component parallel to harmless direction, and r⃗_⊥μ_A is the componen
orthogonal to harmless direction.

Furthermore, if μ_A is (normalized to) a unit vector, the parallel contribution simplifies to:

**r⃗_∥μ_A = (r⃗ · μ⃗_A) μ⃗

### 🤔 Understanding the Components

**The meaning of the parallel component r⃗_∥μ_A is unclear:*

- It represents the extent to which the refusal direction aligns with the model's general
"helpful/harmless assistance" representation
- This could mean:
  1. **Confounded interpretation**: An unimportant difference in how "helpfulness" is represented between contexts
  2. **Necessary coupling**: Refusal may require modulating helpfulness representations
  3. **Artifact**: Statistical noise from finite sampling of activation space

**The meaning of the orthogonal component r⃗_⊥μ_A is relatively straightforward:*

- It captures what distinguishes refusal *beyond* general helpfulness patterns
- Is more likely to represent refusal-specific mechanism
- But we can't be certain *a priori* it's the "complete" refusal direction without the parallel
part

However, in an empirical measurement of directions over the layers of Gemma 3 12B Instruct, we
found that the cosine similarity between the refusal direction and the harmful direction was
positive (as expected and predicted), while the cosine similarity between the refusal direction
and the harmless direction was *negative*.

We propose that the conventional interpretation of refusal being characterized by a single
direction (Arditi et al, 2024) is inaccurate, that it is instead of composed of a direction
which pushes toward refusal and another direction which pushes away from compliance.

However, for the purposes of abliteration, where the refusal direction is to be ablated to allow
 a model to comply with a harmful prompt, removing a push away from compliance is ungrounded as
compliance is the goal. Removing the component which comprises a push away from correct
compliance, however, has no theoretical justification. As released Instruct models are intended
to be correctly trained and fine-tuned, it is likely that unprincipled intervention away from
compliance would degrade model performance. (Performance drop was noted by Labonne, 2024.)
Therefore, we argue that this component should be removed from the refusal direction prior to
ablation. To this end, we propose a modification to abliteration that we term *projected abliteration*.

## 🚀 Projected Abliteration

For projected abliteration, we decompose r⃗ and remove only the theoretically principled component as follows:

**r⃗_proj = r⃗_⊥μ_A = r⃗ - (r⃗ · μ⃗_A)

Where μ⃗_A is normalized to a unit vector here to simplify the computation, avoiding potential
introduction of precision errors.

**Rationale:** The component r⃗_∥μ_A represents variation in the magnitude of general helpfulnes
 representations between contexts—a confound. The orthogonal component r⃗_⊥μ_A captures the
mechanistically specific refusal behavior.

This projection approach is conceptually related to other orthogonalization-based refusal
modulation techniques, though it differs in removing specific directional components rather than
 scaling intervention strength (Wang et al., 2024).

The additional computation required for this modification is trivial, and all required
information is on hand when computing the conventional refusal direction.

## 🔧 Methodology and Implementation Details

In our empirical measurements using Gemma 3 12B Instruct, we encountered several numerical challenges:

- **High magnitude outliers**: Activation measurements contained high-magnitude outlier values
that complicated discrimination between harmful and harmless directions, resulting in
artificially high cosine alignment between the two mean directions. These outliers are
symptomatic of the GeGLU activation function employed in Gemma 3.

- **Precision requirements**: We found it necessary to perform intermediate calculations in full
 32-bit floating point precision, rather than the bfloat16 precision that the model weights
shipped with, to avoid numerical instability.

- **Winsorization**: To separate the directions effectively, we applied magnitude clipping via
Winsorization at a strength of 0.995 (clipping values beyond the 99.5th percentile) to each
activation measurement prior to feeding into Welford accumulation (an online algorithm for
numerically stable mean calculation) for each of the harmful and harmless mean calculations.
Without this preprocessing step, conventional abliteration resulted in incoherent models
(outputs were no longer grammatical). Winsorization strength was determined empirically via
trial and error, though not optimized.

- **Quantized measurement feasibility**: We measured activations from prompts on a 4-bit
bitsandbytes quantized version of the model, computed refusal directions from these
measurements, then applied these directions as interventions on the full bfloat16-precision
model, achieving model coherence in subsequent inference. This result is interesting despite the
 introduction of quantization error. We posit that mean accumulation across many samples
moderates quantization error, and that this cross-precision transfer reflects the fundamental
robustness of refusal and compliance encodings in the model's representation space.

- **Cross-model quantization validity**: To validate this approach, we separately measured
activations on both 4-bit quantized and full-weight versions of Nemo Instruct 2407 12B, finding
that cosine similarities of the refusal directions across layers also tracked closely between
precision levels, with only mild divergence reflecting quantization error. Notably, the Nemo
model required no Winsorization preprocessing, suggesting the outlier challenges were specific
to Gemma 3's architecture.

- **Batched inference**: We performed inference and activation measurement with batch size 32
for efficiency. This partially replicates the activation shifts present in production batched
inference environments, improving ecological validity of our measurements.

- **Layer-wise intervention strategy**: Gemma 3 comprises repeating blocks of 5 local attention
layers followed by 1 global attention layer (48 layers total, numbered 0-47). We measured
refusal directions at two global attention layers (23 and 29), reasoning that global attention
captures semantically coherent refusal awareness, particularly in middle to late-middle layers
as previously observed in abliteration efforts. We then applied these measured directions across
 spans of both local and global layers: the direction from layer 23 was applied to layers 11-23,
 and the direction from layer 29 to layers 24-41. This strategy assumes that local attention
layers propagate refusal signal between global layers despite their more limited attention
scope. The need for such extensive multi-layer intervention indicates that refusal mechanisms
are robustly distributed across the model's depth rather than localized to specific layers.
Safety refusal persisted when early layers were not modified; extending interventions to later
layers improved the quality and consistency of refusal removal. This demonstrates that effective
 abliteration may require spatially consistent intervention to counter a robustly distributed
encoding of safety refusal. This is a departure from naive abliteration which intervenes only on a single layer.

## 💻 Python/PyTorch Implementation

Winsorization is easily defined as a function in PyTorch:

```python
def magnitude_clip(vector: torch.Tensor, percentile: float = 0.995) -> torch.Tensor:
    """ Perform symmetric magnitude Winsorization.
    Clip components to [-threshold, threshold] where threshold is at the percentile.

    Args:
        vector: Input tensor
        percentile: Percentile of absolute values to clip at (0.0 to 1.0)

    Returns:
        Clipped vector """
    original_dtype = vector.dtype vector_float = vector.float()
    abs_vector = torch.abs(vector_float) threshold = torch.quantile(abs_vector, percentile)
    clipped = torch.clamp(vector_float, min=-threshold, max=threshold) return clipped.to(original_dtype)
```

The projection can be implemented concisely in PyTorch:

```python
# Calculate refusal direction
refusal_dir = harmful_mean - harmless_mean

# Normalize harmless_mean to avoid numerical issues
harmless_normalized = torch.nn.functional.normalize(harmless_mean.float(), dim=0)

# Project and subtract contribution along harmless direction
projection_scalar = refusal_dir @ harmless_normalized
refined_refusal_dir = refusal_dir - projection_scalar * harmless_normalized
```

## ✅ Result

We abliterated Gemma 3 12B Instruct with the revised formula, and were able to bypass refusal
with harmful test prompts. Additionally, we confirmed the finding (Zhao et al, 2025) that
harmfulness and refusal were encoded separately, as the resulting model demonstrated awareness
of harms (e.g., couching for safety, providing disclaimers) despite compliance.

## 📚 References

- Arditi et al, "Refusal in LLMs is mediated by a single direction", lesswrong.com, 2024.
- Labonne, "Uncensor any LLM with abliteration", huggingface.co, 2024.
- Wang et al, "Surgical, Cheap, and Flexible: Mitigating False Refusal in Language Models via
Single Vector Ablation", arXiv preprint, 2024.
- Zhao et al, "LLMs Encode Harmfulness and Refusal Separately", arXiv preprint, 2025.

---

## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/grimjim/projected-abliteration*

## 🏁 Conclusion

Projected abliteration represents a significant refinement to conventional abliteration
techniques by addressing the theoretical and practical limitations of simple directional
interventions. By decomposing the refusal direction and removing only the mechanistically
relevant orthogonal component, this approach provides a more principled method for modifying
language model behavior while preserving model coherence and performance.

The empirical findings demonstrate that modern language models like Gemma 3 require more
sophisticated intervention strategies due to their distributed refusal mechanisms and numerical
sensitivities. The successful cross-precision transfer and robust implementation details provide
 practical guidance for researchers working on model alignment and safety removal techniques.

This work contributes to our understanding of how safety mechanisms are encoded in large
language models and offers a more targeted approach to intervention that minimizes unintended
side effects while achieving the desired behavioral modifications.

---

*#MACHINELEARNING #LANGUAGEMODELS #ABLITERATION #SAFETY #PYTORCH #GEMMA #AI*

