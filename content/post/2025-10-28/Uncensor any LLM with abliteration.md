---
title: "Uncensor Any LLM with Abliteration: A Complete Technical Guide"
description: "Learn how to uncensor language models using abliteration technique without retraining, including implementation details and performance recovery with DPO fine-tuning."
date: 2025-10-28T01:03:06.548836+05:30
tags: ["LLM", "Abliteration", "Machine Learning", "AI Safety", "Transformers", "PyTorch", "Llama", "DPO", "Fine-tuning", "Neural Networks"]
categories: ["Artificial Intelligence", "Machine Learning", "AI Safety"]
image: "https://i.imgur.com/KhorYYG.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🔧 Uncensor Any LLM with Abliteration: A Complete Technical Guide

![Banner Image](https://i.imgur.com/KhorYYG.png)
*Abliteration technique for uncensoring language models*

The third generation of Llama models provided fine-tuned (Instruct) versions that excel in
understanding and following instructions. However, these models are heavily censored, designed
to refuse requests seen as harmful with responses such as "As an AI assistant, I cannot help
you." While this safety feature is crucial for preventing misuse, it limits the model's flexibility and responsiveness.

In this article, we will explore a technique called **"abliteration"** that can uncensor any LLM
 without retraining. This technique effectively removes the model's built-in refusal mechanism,
allowing it to respond to all types of prompts.

---

## ✂️ What is Abliteration?

Modern LLMs are fine-tuned for safety and instruction-following, meaning they are trained to
refuse harmful requests. Research by Arditi et al. has shown that this refusal behavior is
mediated by a specific direction in the model's residual stream. If we prevent the model from
representing this direction, it **loses its ability to refuse requests**. Conversely, adding
this direction artificially can cause the model to refuse even harmless requests.

In the traditional decoder-only Llama-like architecture, there are three residual streams we can
 target: at the start of each block ("pre"), between the attention and MLP layers ("mid"), and
after the MLP ("post"). The following figure illustrates the location of each residual stream.

![Residual Stream Diagram](https://i.imgur.com/hsdR9e7.png)
*Location of residual streams in transformer architecture*

### 🔬 The Abliteration Process

To uncensor an LLM, we first need to identify the "refusal direction" within the model. This
process involves a few technical steps:

1. **Data Collection**: Run the model on a set of harmful instructions and a set of harmless
instructions, recording the residual stream activations at the last token position for each.
2. **Mean Difference**: Calculate the mean difference between the activations of harmful and
harmless instructions. This gives us a vector representing the "refusal direction" for each
layer of the model.
3. **Selection**: Normalize these vectors and evaluate them to select the single best "refusal
direction."

Once we have identified the refusal direction, we can "ablate" it, effectively removing the
model's ability to represent this feature. This can be done through an **inference-time
intervention** or permanently with **weight orthogonalization**.

Let's talk about inference-time intervention first. For every component that writes to the
residual stream (such as an attention head), we calculate the projection of its output onto the
refusal direction and subtract this projection. This subtraction is applied at every token and
every layer, ensuring that the model never represents the refusal direction.

On the other hand, weight orthogonalization involves modifying the model weights directly. By
orthogonalizing the component weights with respect to the refusal direction, it prevents the
model from writing to this direction altogether. This is achieved by adjusting the matrices that
 write to the residual stream, ensuring they do not contribute to the refusal direction.

---

## 💻 Implementation

The following implementation of abliteration is based on FailSpy's notebook, which is itself
based on the original authors' notebook. This section shows the technical details, but you can
use FailSpy's abliterator library if you're less interested in the implementation specifics.

The code relies on the excellent **TransformerLens** library (formerly known as EasyTransformer)
 to do the heavy lifting. It is designed for mechanistic interpretability and is used here to intervene on activations.

### 📦 Setup and Dependencies

First, let's install the necessary packages and import them:

```python
!pip install transformers transformers_stream_generator tiktoken transformer_lens einops jaxtyping

import torch import functools
import einops import gc
from datasets import load_dataset from tqdm import tqdm
from torch import Tensor from typing import List
from transformer_lens import HookedTransformer, utils from transformer_lens.hook_points import HookPoint
from transformers import AutoModelForCausalLM, AutoTokenizer from jaxtyping import Float, Int
from collections import defaultdict

# Turn automatic differentiation off to save GPU memory (credit: Undi95)
torch.set_grad_enabled(False)
```

### 📊 Data Preparation

We need two datasets: one containing harmless instructions, and one containing harmful
instructions. We'll use `tatsu-lab/alpaca` as well as data from `llm-attacks`. The data has been
 repackaged into two Hugging Face datasets: `mlabonne/harmless_alpaca` and
`mlabonne/harmful_behaviors`.

```python
def reformat_texts(texts):
    return [[{"role": "user", "content": text}] for text in texts]

# Get harmful and harmless datasets
def get_harmful_instructions():
    dataset = load_dataset('mlabonne/harmful_behaviors')
    return reformat_texts(dataset['train']['text']), reformat_texts(dataset['test']['text'])

def get_harmless_instructions():
    dataset = load_dataset('mlabonne/harmless_alpaca')
    return reformat_texts(dataset['train']['text']), reformat_texts(dataset['test']['text'])

harmful_inst_train, harmful_inst_test = get_harmful_instructions()
harmless_inst_train, harmless_inst_test = get_harmless_instructions()
```

### 🤖 Model Loading

Now we can load the model we want to abliterate. In this example, we'll use
`mlabonne/Daredevil-8B`, a mega-merge created with DARE TIES that has the highest MMLU score on
the Open LLM Leaderboard in the 8B category.

```python
MODEL_ID = "mlabonne/Daredevil-8B" MODEL_TYPE = "meta-llama/Meta-Llama-3-8B-Instruct"

# Download and load model
!git clone https://huggingface.co/{MODEL_ID} {MODEL_TYPE}

# Load model and tokenizer
model = HookedTransformer.from_pretrained_no_processing( MODEL_TYPE,
    local_files_only=True, dtype=torch.bfloat16,
    default_padding_side='left' )
tokenizer = AutoTokenizer.from_pretrained(MODEL_TYPE) tokenizer.padding_side = 'left'
tokenizer.pad_token = tokenizer.eos_token
```

### 🔄 Data Collection Phase

We can now tokenize our datasets and process them to collect residual stream activations:

```python
def tokenize_instructions(tokenizer, instructions):
    return tokenizer.apply_chat_template( instructions,
        padding=True, truncation=False,
        return_tensors="pt", return_dict=True,
        add_generation_prompt=True, ).input_ids

n_inst_train = min(256, len(harmful_inst_train), len(harmless_inst_train))

# Tokenize datasets
harmful_tokens = tokenize_instructions( tokenizer,
    instructions=harmful_inst_train[:n_inst_train], )
harmless_tokens = tokenize_instructions( tokenizer,
    instructions=harmless_inst_train[:n_inst_train], )

# Define batch size based on available VRAM
batch_size = 32

# Initialize defaultdicts to store activations
harmful = defaultdict(list) harmless = defaultdict(list)

# Process the training data in batches
num_batches = (n_inst_train + batch_size - 1) // batch_size for i in tqdm(range(num_batches)):
    start_idx = i * batch_size end_idx = min(n_inst_train, start_idx + batch_size)

    # Run models on harmful and harmless prompts, cache activations
    harmful_logits, harmful_cache = model.run_with_cache( harmful_tokens[start_idx:end_idx],
        names_filter=lambda hook_name: 'resid' in hook_name, device='cpu',
        reset_hooks_end=True )
    harmless_logits, harmless_cache = model.run_with_cache( harmless_tokens[start_idx:end_idx],
        names_filter=lambda hook_name: 'resid' in hook_name, device='cpu',
        reset_hooks_end=True )

    # Collect and store the activations for key in harmful_cache:
        harmful[key].append(harmful_cache[key]) harmless[key].append(harmless_cache[key])

    # Flush RAM and VRAM del harmful_logits, harmless_logits, harmful_cache, harmless_cache
    gc.collect() torch.cuda.empty_cache()

# Concatenate the cached activations
harmful = {k: torch.cat(v) for k, v in harmful.items()} harmless = {k: torch.cat(v) for k, v in harmless.items()}
```

### 🎯 Refusal Direction Computation

We can now compute the refusal direction for each layer by calculating the mean difference
between harmful and harmless activations:

```python
# Helper function to get activation index
def get_act_idx(cache_dict, act_name, layer):
    key = (act_name, layer) return cache_dict[utils.get_act_name(*key)]

# Compute difference of means between harmful and harmless activations at intermediate layers
activation_layers = ["resid_pre", "resid_mid", "resid_post"] activation_refusals = defaultdict(list)

for layer_num in range(1, model.cfg.n_layers):
    pos = -1  # Position index for layer in activation_layers:
        harmful_mean_act = get_act_idx(harmful, layer, layer_num)[:, pos, :].mean(dim=0)
        harmless_mean_act = get_act_idx(harmless, layer, layer_num)[:, pos, :].mean( dim=0
        ) refusal_dir = harmful_mean_act - harmless_mean_act
        refusal_dir = refusal_dir / refusal_dir.norm() activation_refusals[layer].append(refusal_dir)

# Get all calculated potential refusal directions, sort them in descending order based on their
mean selected_layers = ["resid_pre"]
activation_scored = sorted( [
        activation_refusals[layer][l - 1] for l in range(1, model.cfg.n_layers)
        for layer in selected_layers ],
    key=lambda x: abs(x.mean()), reverse=True,
)
```

### 🧪 Evaluation and Weight Orthogonalization

The final step consists of evaluating the refusal directions and applying weight orthogonalization:

```python
def get_orthogonalized_matrix( matrix: Float[Tensor, "... d_model"], vec: Float[Tensor, "d_model"]
) -> Float[Tensor, "... d_model"]:
    proj = ( einops.einsum(
            matrix, vec.view(-1, 1), "... d_model, d_model single -> ... single" )
        * vec )
    return matrix - proj

# Select the layer with the highest potential refusal direction
LAYER_CANDIDATE = 9 refusal_dir = activation_scored[LAYER_CANDIDATE]

# Orthogonalize the model's weights
if refusal_dir.device != model.W_E.device:
    refusal_dir = refusal_dir.to(model.W_E.device)

model.W_E.data = get_orthogonalized_matrix(model.W_E, refusal_dir)

for block in tqdm(model.blocks):
    if refusal_dir.device != block.attn.W_O.device:
        refusal_dir = refusal_dir.to(block.attn.W_O.device)
    block.attn.W_O.data = get_orthogonalized_matrix(block.attn.W_O, refusal_dir)
    block.mlp.W_out.data = get_orthogonalized_matrix(block.mlp.W_out, refusal_dir)
```

--- 
## ⚖️ DPO Fine-Tuning

After abliteration, models typically experience a performance drop across benchmarks. The
ablation process successfully uncensors the model but also degrades its quality.

![Performance Comparison](https://i.imgur.com/ECCejII.png)
*Performance comparison before and after abliteration*

To address this issue, we can use **Direct Preference Optimization (DPO)** to heal the
abliterated model. DPO is a good candidate here for its ease of use and good track record. The
training process involves:

1. Using a preference dataset like `mlabonne/orpo-dpo-mix-40k` 2. Fine-tuning with LoRA adapters to maintain efficiency
3. Training with appropriate hyperparameters to recover performance

After DPO training, we can see significant performance recovery:

![DPO Results](https://i.imgur.com/ChDwx4r.png)
*Performance after DPO fine-tuning*

The final model recovers most of the performance drop due to abliteration, resulting in an
uncensored LLM with state-of-the-art performance in the 8B category.

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/mlabonne/abliteration*

--- 
## 🏁 Conclusion

In this article, we introduced the concept of abliteration, a powerful technique that uses model
 activations on harmless and harmful prompts to calculate a refusal direction. By modifying the
model's weights to prevent representation of this direction, we can effectively uncensor any LLM without retraining.

We successfully applied abliteration to Daredevil-8B to uncensor it, then used DPO fine-tuning
to recover the performance degradation, creating NeuralDaredevil-8B - a fully uncensored and high-quality 8B LLM.

**Key takeaways:**
- Abliteration demonstrates the fragility of safety fine-tuning
- The technique can be applied to various models and use cases
- Performance recovery through DPO is essential for maintaining model quality
- This approach raises important ethical considerations about AI safety

Abliteration should be seen as a form of fine-tuning without retraining that can be creatively
applied to various goals beyond removing alignment, such as changing conversational styles or
other behavioral modifications.

--- 
*#LLMS #MACHINELEARNING #ARTIFICIALINTELLIGENCE #TRANSFORMERS #ABLITERATION #DPO #HUGGINGFACE
#LLAMA #NEURALNETWORKS #AISAFETY*

