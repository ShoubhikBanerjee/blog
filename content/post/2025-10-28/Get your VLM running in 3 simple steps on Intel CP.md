---
title: "Get Your VLM Running in 3 Simple Steps on Intel CPUs"
description: "Learn how to deploy Vision Language Models efficiently on Intel CPUs using Optimum Intel and OpenVINO with up to 65x performance improvements through quantization techniques."
date: 2025-10-28T00:47:56.980330+05:30
tags: ["Intel", "OpenVINO", "VLM", "Vision Language Models", "Quantization", "CPU Optimization", "SmolVLM", "Optimum Intel", "Machine Learning", "AI Inference"]
categories: ["AI", "Machine Learning", "Computer Vision"]
image: "https://huggingface.co/datasets/OpenVINO/documentation/resolve/main/blog/openvino_vlm/quantization.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 Get Your VLM Running in 3 Simple Steps on Intel CPUs

![Quantization](https://huggingface.co/datasets/OpenVINO/documentation/resolve/main/blog/openvino_vlm/quantization.png)
*Visual representation of the quantization process that optimizes model performance*

With the growing capability of large language models (LLMs), a new class of models has emerged:
**Vision Language Models (VLMs)**. These models can analyze images and videos to describe
scenes, create captions, and answer questions about visual content.

While running AI models on your own device can be difficult as these models are often
computationally demanding, it also offers significant benefits: including improved privacy since
 your data stays on your machine, and enhanced speed and reliability because you're not
dependent on an internet connection or external servers. This is where tools like **Optimum
Intel** and **OpenVINO** come in, along with a small, efficient model like **SmolVLM**. In this
blog post, we'll walk you through three easy steps to get a VLM running locally, with no
expensive hardware or GPUs required (though you can run all the code samples from this blog post on Intel GPUs).

## 🛠️ Deploy Your Model with Optimu

Small models like SmolVLM are built for low-resource consumption, but they can be further
optimized. In this blog post we will see how to optimize your model, to lower memory usage and
speedup inference, making it more efficient for deployment on devices with limited resources.

To follow this tutorial, you need to install `optimum` and `openvino`, which you can do with:

```bash
pip install optimum-intel[openvino] transformers==4.52.*
```

## 📝 Step 1: Convert Your Model

First, you will need to convert your model to the **OpenVINO IR**. There are multiple options to do it:

### Option 1: Using the Optimum CLI

```bash
optimum-cli export openvino -m HuggingFaceTB/SmolVLM2-256M-Video-Instruct smolvlm_ov/
```

### Option 2: Convert On-the-Fly

Or you can convert it **on the fly** when loading your model:

```python
from optimum.intel import OVModelForVisualCausalLM

model_id = "HuggingFaceTB/SmolVLM2-256M-Video-Instruct" model = OVModelForVisualCausalLM.from_pretrained(model_id)
model.save_pretrained("smolvlm_ov")
```

## ⚡ Step 2: Quantization

Now it's time to optimize your model. **Quantization** reduces the precision of the model
weights and/or activations, leading to smaller, faster models. Essentially, it's a way to map
values from a high-precision data type, such as 32-bit floating-point numbers (FP32), to a
lower-precision format, typically 8-bit integers (INT8). While this process offers several key
benefits, it can also impact in a potential loss of accuracy.

Optimum supports two main post-training quantization methods:

- **Weight Only Quantization (WOQ)**
- **Static Quantization**

Let's explore each of them.

### 🎯 Option 1: Weight Only Quantization

Weight-only quantization means that only the weights are quantized but activations remain in
their original precisions. As a result, the model becomes smaller and more memory-efficient,
improving loading times. But since activations are not quantized, inference speed gains are
limited. Weight-only quantization is a simple first step since it usually doesn't result in
significant accuracy degradation.

> 💡 Since OpenVINO 2024.3, if the model's weight have been quantized, the corresponding
activations will also be quantized at runtime, leading to additional speedup depending on the device.

In order to run it, you will need to create a quantization configuration
`OVWeightQuantizationConfig` as follows:

```python
from optimum.intel import OVModelForVisualCausalLM, OVWeightQuantizationConfig

q_config = OVWeightQuantizationConfig(bits=8)
q_model = OVModelForVisualCausalLM.from_pretrained(model_id, quantization_config=q_config)
q_model.save_pretrained("smolvlm_int8")
```

Or equivalently using the CLI:

```bash
optimum-cli export openvino -m HuggingFaceTB/SmolVLM2-256M-Video-Instruct --weight-format int8 smolvlm_int8/
```

## 🔧 Option 2: Static Quantization

With Static Quantization, both weights and activations are quantized before inference. To
achieve the best estimate for the activation quantization parameters, we perform a calibration
step. During this step, a small representative dataset is fed through the model. In our case, we
 will use 50 samples of the **contextual dataset** and will apply static quantization on the
vision encoder while weight-only quantization will be applied on the rest of the model.
Experiments show that applying static quantization on the vision encoder provides a noticeable
performance improvement without significant accuracy degradation.

```python
from optimum.intel import OVModelForVisualCausalLM, OVPipelineQuantizationConfig,
OVQuantizationConfig, OVWeightQuantizationConfig

q_config = OVPipelineQuantizationConfig( quantization_configs={
        "lm_model": OVWeightQuantizationConfig(bits=8), "text_embeddings_model": OVWeightQuantizationConfig(bits=8),
        "vision_embeddings_model": OVQuantizationConfig(bits=8), },
    dataset=dataset, num_samples=num_samples,
)

q_model = OVModelForVisualCausalLM.from_pretrained(model_id, quantization_config=q_config)
q_model.save_pretrained("smolvlm_static_int8")
```

Quantizing activations adds small errors that can build up and affect accuracy, so careful
testing afterward is important. More information and examples can be found in **our documentation**.

### 🚀 Step 3: Run Inference

You can now run inference with your quantized model:

```python
generated_ids = q_model.generate(**inputs, max_new_tokens=100)
generated_texts = processor.batch_decode(generated_ids, skip_special_tokens=True) print(generated_texts[0])
```

If you have a recent Intel laptop, Intel AI PC, or Intel discrete GPU, you can load the model on
 GPU by adding `device="gpu"` when loading your model:

```python
model = OVModelForVisualCausalLM.from_pretrained(model_id, device="gpu")
```

We also **created a space** so you can play with the **original model** and its quantized
variants obtained by respectively applying **weight-only quantization** and **mixed
quantization**. This demo runs on 4th Generation Intel Xeon (Sapphire Rapids) processors.

![HF Space](https://huggingface.co/datasets/OpenVINO/documentation/resolve/main/blog/openvino_vlm/chat1.png)
*Interactive demo space showing the VLM in action*

To reproduce our results, check out our **notebook**.

## 📊 Evaluation and Conclusion

We ran a benchmark to compare the performance of the **PyTorch**, **OpenVINO**, and **OpenVINO
8-bit WOQ** versions of the original model. The goal was to evaluate the impact of weight-only
quantization on latency and throughput on Intel CPU hardware. For this test, we used **a single image** as input.

We measured the following metrics to evaluate the model's performance:

- **Time To First Token (TTFT)**: Time it takes to generate the first output token
- **Time Per Output Token (TPOT)**: Time it takes to generate each subsequent output tokens
- **End-to-End Latency**: Total time it takes to generate the output all output tokens
- **Decoding Throughput**: Number of tokens per second the model generates during the decoding
phase

Here are the results on Intel CPU:

| Configuration | Time To First Token (TTFT) | Time Per Output Token (TPOT) | End-to-End Latency
 | Decoding Throughput |
| --- | --- | --- | --- | --- |
| pytorch | 5.150 | 1.385 | 25.927 | 0.722 |
| openvino | 0.420 | 0.021 | 0.738 | 47.237 |
| openvino-8bit-woq | 0.247 | 0.016 | 0.482 | 63.928 |

This benchmark demonstrates how small, optimized multimodal models, like **SmolVLM2-256M**,
perform on Intel CPUs across different configurations. According to the tests, the PyTorch
version shows high latency, with a time to first token (TTFT) of over 5s with a decoding
throughput of 0.7 tokens/s. Simply converting the model with Optimum and running it on OpenVINO
drastically reduces the time to first token (TTFT) to 0.42s (**x12** speedup) and raises
throughput to 47 tokens/s (**x65**). Applying 8-bit weight-only quantization further reduces
TTFT (**x1.7**) and increases throughput (**x1.4**), while also reducing model size and improving efficiency.

> **Platform configuration** Platform Configuration for performance claims above:
> > **System Board:** MSI B860M GAMING PLUS WIFI (MS-7E42)
> **CPU:** Intel® Core™ Ultra 7 265K > **Sockets/Physical Cores:** 1/20 (20 threads)
> **HyperThreading/Turbo Settings:** Disabled > **Memory:** 64 GB DDR5 @ 6400 MHz
> **TDP:** 665W > **BIOS:** American Megatrends International, LLC. 2.A10
> **BIOS Release Date:** 28.11.2024 > **OS:** Ubuntu 24.10
> **Kernel:** 6.11.0–25-generic > **OpenVINO Version:** 2025.2.0
> **torch:** 2.8.0 > **torchvision:** 0.23.0+cpu
> **optimum-intel:** 1.25.2 > **transformers:** 4.53.3
> **Benchmark Date:** 15.05.2025
> **Benchmarked by:** Intel Corporation Performance may vary by use, configuration, and other
factors. See the platform configuration below.

## 🔗 Useful Links & Resources

- **Notebook**
- **Try our Space**
- **Watch the webinar recording**
- **Optimum Intel Documentation**

---

## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/openvino-vlm*

## 🏁 Conclusion

This tutorial demonstrates how to deploy Vision Language Models efficiently on Intel CPUs using
just three simple steps. By leveraging Optimum Intel and OpenVINO, developers can achieve
significant performance improvements - up to **65x throughput increase** and **12x faster
time-to-first-token** compared to vanilla PyTorch implementations. The quantization techniques,
particularly weight-only quantization, provide an excellent balance between performance gains
and model accuracy preservation.

The results showcase that advanced AI capabilities are no longer limited to expensive GPU
setups. With proper optimization, Intel CPUs can deliver impressive performance for VLM
inference, making AI more accessible while maintaining privacy and reducing dependencies on
external services.

Whether you're building applications for edge deployment, developing privacy-focused solutions,
or simply want to run VLMs locally without expensive hardware, this approach provides a
practical path forward with proven performance benefits.

---

*#INTEL #OPENVINO #VLM #QUANTIZATION #OPTIMIZATION #CPU #AI #MACHINELEARNING #COMPUTERVISION*

