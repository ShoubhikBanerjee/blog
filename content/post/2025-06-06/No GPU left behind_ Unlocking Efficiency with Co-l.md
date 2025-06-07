---
title: "🚀 No GPU Left Behind: How Co-located vLLM is Revolutionizing LLM Training Efficiency"
description: "Discover how the new co-located vLLM integration in TRL eliminates idle GPU time during GRPO training by running both training and inference on the same GPUs—delivering up to 1.73× speedup without sacrificing model quality, even on 72B parameter models."
date: 2025-06-06T20:56:54.252687+05:30
tags: [MachineLearning, LLM, GRPO, vLLM, GPUEfficiency, AITraining, HuggingFace, DistributedTraining, DeepLearning, TensorParallelism, AIOptimization]
categories: [Machine Learning, AI, Deep Learning, LLM Training, GPU Optimization]
image: "https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/vllm-colocate/gpus-design.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 No GPU Left Behind: How Co-located vLLM is Revolutionizing LLM Training Efficiency

**𝗦𝘂𝗺𝗺𝗮𝗿𝘆**: Discover how the new co-located vLLM integration in TRL eliminates idle GPU time during GRPO training by running both training and inference on the same GPUs—delivering up to 1.73× speedup without sacrificing model quality, even on 72B parameter models.

## 🔍 The Training Bottleneck Problem

Training large language models using online learning methods like GRPO (introduced in the DeepSeekMath paper) requires constant generation of model outputs during the training loop. This creates a critical efficiency challenge: traditional setups force GPUs to take turns between training and inference tasks.

Before TRL v0.18.0, vLLM was only supported in server mode, running as a separate process on dedicated GPUs—creating a wasteful "ping-pong" pattern:

1. Training GPUs run the model update step
2. Training GPUs sit idle while waiting for generation
3. vLLM server GPUs generate completions
4. vLLM GPUs sit idle while training resumes
5. Repeat...

This inefficient workflow results in:
- 💸 Wasted GPU resources on both sides
- 🔌 Increased hardware requirements 
- ⏱️ Reduced overall throughput
- 📈 Higher training costs

## 🌟 Enter Co-located vLLM: The Game-Changer

The core innovation introduced in TRL PR #3394 is elegant yet powerful: run both training and inference on the 𝘀𝗮𝗺𝗲 GPUs.

Instead of operating as a standalone server process, vLLM now runs alongside the training code within the same distributed process group. The key advantages of this colocation approach:

- **Unified GPU Utilization**: Training and inference share resources, taking turns efficiently without idle time
- **Direct Communication**: Eliminates HTTP overhead by running vLLM in-process
- **Seamless Scaling**: Works natively with torchrun for multi-node deployment
- **Full Parallelism Support**: Compatible with both Tensor and Data Parallelism
- **Simplified Deployment**: No separate server management needed

To enable this in your training pipeline, it's as simple as changing one parameter:

```python
training_args = GRPOConfig(
    ...,
    use_vllm=True,
    vllm_mode="colocate",  # This enables colocation!
)
```

## 📊 Real-World Performance Gains

The team ran extensive experiments comparing traditional server mode to the new co-located approach. The results were impressive across various model sizes and configurations:

### 🔹 For Smaller Models (1.5B parameters)
- Up to 1.43× speedup with larger batch sizes
- Better performance with less tensor parallelism

### 🔹 For Medium Models (7B parameters)
- 1.35× speedup at larger batch sizes
- Performance improves with more tensor parallelism, reaching 1.73× speedup

### 🔹 For Massive Models (Qwen2.5-Math-72B)
- Co-located setup achieves ~1.26× faster throughput even with 𝙛𝙚𝙬𝙚𝙧 GPUs
- Equal model quality on Math500 benchmark compared to traditional training

One crucial innovation that enables efficient training of massive models is the integration of vLLM's `sleep()` API into the training loop. This function temporarily frees GPU memory, allowing:

- **Level 1 Sleep**: Unloads model weights but keeps them accessible in CPU memory
- **Level 2 Sleep**: Completely unloads both weights and KV cache

For GRPO, which updates the model after every step, Level 2 sleep provides maximum memory efficiency, avoiding contention between training and generation tasks.

## 📈 Technical Implementation Details

The implementation combines several advanced techniques to maximize performance:

1. **Process Group Awareness**: Co-located vLLM respects the torch.distributed process group:

```python
if self.vllm_tensor_parallel_size > 1:
    self.tp_group, _ = torch.distributed.new_subgroups_by_enumeration(
        [
            list(range(i * self.vllm_tensor_parallel_size, 
                      (i + 1) * self.vllm_tensor_parallel_size))
            for i in range(self.accelerator.num_processes // 
                          self.vllm_tensor_parallel_size)
        ]
    )
```

2. **Memory Management**: For large models like Qwen2.5-72B, DeepSpeed ZeRO Stage 3 optimizations handle memory constraints:
   - Offloading optimizer states to CPU
   - Overlapping communication with computation
   - Using contiguous gradients to reduce memory fragmentation

3. **Accelerate Integration**: The whole system leverages HuggingFace's Accelerate library for streamlined distributed training.

## 🔮 The Future of Efficient LLM Training

Despite a few challenges like occasional segmentation faults during shutdown (reported in Issue #16993), the co-located vLLM approach represents a significant advancement in LLM training efficiency.

The most important lessons from this work:

- 🔥 Co-located inference dramatically improves GPU utilization without requiring additional hardware
- 🧠 Memory management via vLLM's sleep() is crucial for large-scale training
- ⚡ The approach maintains model quality while delivering substantial throughput gains

This innovation makes training large models faster, cheaper, and more accessible—especially important as models continue to grow in size and complexity.

## 💡 Try It Yourself

Want to experience the efficiency gains firsthand? Here's a minimal example to get started with GRPO training using co-located vLLM:

```python
from datasets import load_dataset
from trl import GRPOConfig, GRPOTrainer

dataset = load_dataset("trl-lib/tldr", split="train")

def reward_len(completions, **kwargs):
    return [-abs(20 - len(completion)) for completion in completions]

training_args = GRPOConfig(
    output_dir="Qwen2-0.5B-GRPO",
    use_vllm=True,
    vllm_mode="colocate",  # Enable colocation
    vllm_gpu_memory_utilization=0.3,
    max_steps=2,
    num_generations=4,
    per_device_train_batch_size=4,
)

trainer = GRPOTrainer(
    model="Qwen/Qwen2-0.5B-Instruct",
    reward_funcs=reward_len,
    args=training_args,
    train_dataset=dataset,
)

trainer.train()
```

As LLMs become increasingly central to AI advancement, innovations that maximize hardware efficiency will be crucial. The question is no longer just "how powerful is your model?" but also "how efficiently can you train it?"

*Credits: Originally posted here: https://huggingface.co/blog/vllm-colocate*

#MachineLearning #LLM #GRPO #vLLM #GPUEfficiency #AITraining #HuggingFace #DistributedTraining #DeepLearning #TensorParallelism #AIOptimization