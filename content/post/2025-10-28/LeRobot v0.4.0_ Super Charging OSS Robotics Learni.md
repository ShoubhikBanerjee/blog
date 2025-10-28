---
title: "LeRobot v0.4.0: Super Charging OSS Robotics Learning"
description: "A comprehensive overview of LeRobot v0.4.0's major advancements including scalable
 Datasets v3.0, powerful VLA models like PI0.5 and GR00T N1.5, new simulation environments, and
revolutionary plugin system for hardware integration."
date: 2025-10-28T00:50:04.103327+05:30
tags: ["LeRobot", "Robotics", "Machine Learning", "Open Source", "VLA", "Vision Language Action", "AI", "Embodied AI", "Deep Learning", "Hardware Integration"]
categories: ["Robotics", "Machine Learning", "Open Source"]
image: "https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/lerobot-blog/release-v0.4.0/lerobot-libero-groot-v040.gif"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🤖 LeRobot v0.4.0: Super Charging OSS Robotics Learning

*Published October 24, 2025*

We're thrilled to announce a series of significant advancements across LeRobot, designed to make
 open-source robot learning more powerful, scalable, and user-friendly than ever before! From
revamped datasets to versatile editing tools, new simulation environments, and a groundbreaking
plugin system for hardware, LeRobot is continuously evolving to meet the demands of cutting-edge embodied AI.

## ⚡ TL;DR

LeRobot v0.4.0 delivers a major upgrade for open-source robotics, introducing scalable Datasets
v3.0, powerful new VLA models like PI0.5 and GR00T N1.5, and a new plugin system for easier
hardware integration. The release also adds support for LIBERO and Meta-World simulations,
simplified multi-GPU training, and a new Hugging Face Robot Learning Course.

---

## 📋 Table of Contents

- [Datasets: Ready for the Next Wave of Large-Scale Robot
Learning](#datasets-ready-for-the-next-wave-of-large-scale-robot-learning)
  - [What's New in Datasets v3.0?](#whats-new-in-datasets-v30)
  - [New Feature: Dataset Editing Tools!](#new-feature-dataset-editing-tools)
- [Simulation Environments: Expanding Your Training
Grounds](#simulation-environments-expanding-your-training-grounds)
  - [LIBERO Support](#libero-support)
  - [Meta-World Integration](#meta-world-integration)
- [Codebase: Powerful Tools For Everyone](#codebase-powerful-tools-for-everyone)
  - [The New Pipeline for Data Processing](#the-new-pipeline-for-data-processing)
  - [Multi-GPU Training Made Easy](#multi-gpu-training-made-easy)
- [Policies: Unleashing Open-World
Generalization](#policies-unleashing-open-world-generalization)
  - [PI0 and PI0.5](#pi0-and-pi05)
  - [GR00T N1.5](#gr00t-n15)
- [Robots: A New Era of Hardware Integration with the Plugin
System](#robots-a-new-era-of-hardware-integration-with-the-plugin-system)
- [The Hugging Face Robot Learning Course](#the-hugging-face-robot-learning-course)

---

## 📊 Datasets: Ready for the Next Wave of Large-Scale Robot Learning

We've completely overhauled our dataset infrastructure with **LeRobotDataset v3.0**, featuring a
 new chunked episode format and streaming capabilities. This is a game-changer for handling
massive datasets like OXE (Open X Embodiment) and Droid, bringing unparalleled efficiency and scalability.

### 🔧 What's New in Datasets v3.0?

- **Chunked Episodes for Massive Scale**: Our new format supports datasets at the OXE-level (>
400GB), enabling unprecedented scalability
- **Efficient Video Storage + Streaming**: Enjoy faster loading times and seamless streaming of
video data
- **Unified Parquet Metadata**: Say goodbye to scattered JSONs! All episode metadata is now
stored in unified, structured Parquet files for easier management and access
- **Faster Loading & Better Performance**: Experience significantly reduced dataset
initialization times and more efficient memory usage

We've also provided a conversion script to easily migrate your existing v2.1 datasets to the new
 v3.0 format, ensuring a smooth transition.

### ✏️ New Feature: Dataset Editing Tools!

Working with LeRobot datasets just got a whole lot easier! We've introduced a powerful set of
utilities for flexible dataset editing.

With our new `lerobot-edit-dataset` CLI, you can now:

- Delete specific episodes from existing datasets
- Split datasets by fractions or episode indices
- Add or remove features with ease
- Merge multiple datasets into one unified set

```bash
# Merge multiple datasets into a single dataset
lerobot-edit-dataset \ --repo_id lerobot/pusht_merged \
  --operation.type merge \ --operation.repo_ids "['lerobot/pusht_train', 'lerobot/pusht_val']"

# Delete episodes and save to a new dataset (preserves original dataset)
lerobot-edit-dataset \ --repo_id lerobot/pusht \
  --new_repo_id lerobot/pusht_after_deletion \ --operation.type delete_episodes \
  --operation.episode_indices "[0, 2, 5]"
```

These tools streamline your workflow, allowing you to curate and optimize your robot datasets like never before.

--- 
## 🎮 Simulation Environments: Expanding Your Training Grounds

We're continuously expanding LeRobot's simulation capabilities to provide richer and more
diverse training environments for your robotic policies.

![libero-demo](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/lerobot-blog/release-v0.4.0/lerobot-libero-groot-v040.gif)

*LIBERO simulation environment in action*

### 🧪 LIBERO Support

LeRobot now officially supports **LIBERO**, one of the largest open benchmarks for
Vision-Language-Action (VLA) policies, boasting over 130 tasks! This is a huge step toward
building the go-to evaluation hub for VLAs, enabling easy integration and a unified setup for
evaluating any VLA policy.

### 🌍 Meta-World Integration

We've integrated **Meta-World**, a premier benchmark for testing multi-task and generalization
abilities in robotic manipulation, featuring over 50 diverse manipulation tasks. This
integration, along with our standardized use of `gymnasium ≥ 1.0.0` and `mujoco ≥ 3.0.0`,
ensures deterministic seeding and a robust simulation foundation.

--- 
## ⚙️ Codebase: Powerful Tools For Everyone

We're making robot control more flexible and accessible, enabling new possibilities for data
collection and model training.

### 🔄 The New Pipeline for Data Processing

Getting data from a robot to a model (and back!) is tricky. Raw sensor data, joint positions,
and language instructions don't match what AI models expect. Models need normalized, batched
tensors on the right device, while your robot hardware needs specific action commands.

We're excited to introduce **Processors**: a new, modular pipeline that acts as a universal
translator for your data. Think of it as an assembly line where each `ProcessorStep` handles one
 specific job—like normalizing, tokenizing text, or moving data to the GPU.

You can chain these steps together into a powerful pipeline to perfectly manage your data flow:

- `PolicyProcessorPipeline`: Built for models. It expertly handles batched tensors for
high-performance training and inference
- `RobotProcessorPipeline`: Built for hardware. It processes individual data points for
real-time robot control

```python
# Get environment state
obs = robot.get_observation()

# Rename, Batch, Normalize, Tokenize, Move Device ...
obs_processed = preprocess(obs)

# Run inference
action = model.select_action(obs_processed)

# Unnormalize, Move Device ...
action_processed = postprocess(action)

# Execute action
robot.send_action(action_processed)
```

### 🚀 Multi-GPU Training Made Easy

Training large robot policies just got a lot faster! We've integrated **Accelerate** directly
into our training pipeline, making it incredibly simple to scale your experiments across
multiple GPUs with just **one command**:

```bash
accelerate launch \ --multi_gpu \
  --num_processes=$NUM_GPUs \ $(which lerobot-train) \
  --dataset.repo_id=${HF_USER}/my_dataset \ --policy.repo_id=${HF_USER}/my_trained_policy \
  --policy.type=$POLICY_TYPE \ # ... More training configuration flags
```

Whether you're fine-tuning a policy or running large-scale experiments, LeRobot now handles all
the complexities of distributed training for you.

--- 
## 🧠 Policies: Unleashing Open-World Generalization

![groot-demo](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/lerobot-blog/release-v0.4.0/lerobot-libero-groot2-v040.gif)

*GR00T N1.5 model in action*

### 🔥 PI0 and PI0.5

In a major milestone for open-source robotics, we've integrated **pi0** and **pi0.5** policies
by Physical Intelligence into LeRobot! These Vision-Language-Action (VLA) models represent a
significant leap towards addressing open-world generalization in robotics.

**What makes π₀.₅ revolutionary?**

- **Open-World Generalization**: Designed to adapt to entirely new environments and situations,
generalizing across physical, semantic, and environmental levels
- **Co-training on Heterogeneous Data**: Learns from a diverse mix of multimodal web data,
verbal instructions, subtask commands, and multi-environment robot data
- **Physical Intelligence Collaboration**: Huge thanks to the Physical Intelligence team for
their groundbreaking work!

### 🤖 GR00T N1.5

In another exciting development, we've integrated **NVIDIA's GR00T N1.5** into LeRobot, thanks
to a fantastic collaboration with the NVIDIA robotics team! This open foundation model is a
powerhouse for generalized robot reasoning and skills.

**What makes GR00T N1.5 a game-changer?**

- **Generalized Reasoning & Skills**: Designed as a cross-embodiment foundation model, GR00T
N1.5 excels at generalized reasoning and manipulation tasks, with improved language-following ability
- **Expansive Heterogeneous Training**: It learns from a massive dataset combining real captured
 humanoid data, synthetic data generated by NVIDIA Isaac GR00T Blueprint, and internet-scale video data
- **NVIDIA Collaboration**: We're thrilled to partner with the NVIDIA team to bring this
state-of-the-art model to the open-source LeRobot community!

The native integration of these policies in `lerobot` is a huge step forward in making robot
learning as open and reproducible as it can be.

--- 
## 🔌 Robots: A New Era of Hardware Integration with the Plugin System

Big news for hardware enthusiasts! We've launched a brand-new plugin system to revolutionize how
 you integrate third-party hardware with LeRobot. Now, connecting any robot, camera, or
teleoperator is as simple as a `pip install`, eliminating the need to modify the core library.

### 💡 Key Benefits

- **Extensibility**: Develop and integrate custom hardware in separate Python packages
- **Scalability**: Supports a growing ecosystem of devices without bloating the core library
- **Community-Friendly**: Lowers the barrier to entry for community contributions, fostering a
more collaborative environment

```bash
pip install lerobot_teleoperator_my_awesome_teleop lerobot-teleoperate --teleop.type=my_awesome_teleop
```

### 🦾 Reachy 2 Integration

Thanks to our new plugin system, we've also added **Reachy 2** from Pollen Robotics to LeRobot!
Reachy 2 is available for both real robot control and simulation, enabling you to experiment
with teleoperation and autonomous demos right away.

### 📱 Phone Integration

Thanks to our powerful new pipeline system, you can now teleoperate your follower arm **right
from your phone** (iOS/Android). The phone acts as a teleoperator device, and our
`RobotProcessor` pipeline handles all the transformations, allowing you to drive robots in
different action spaces with ease.

--- 
## 🎓 The Hugging Face Robot Learning Course

We're launching a comprehensive, self-paced, and entirely **open-source course** designed to
make robot learning accessible to everyone! If you're curious about how real-world robots learn,
 this is the perfect place to start.

**In this course, you'll learn how to:**

- Understand the fundamentals of classical robotics
- Use generative models for imitation learning (VAEs, diffusion, etc.)
- Apply Reinforcement Learning to real-world robots
- Explore the latest generalist robot policies like PI0 and SmolVLA

### 📚 Deep Dive: The Modern Robot Learning Tutorial

For those who want to go deeper, we've also published a **hands-on tutorial** on the most recent
 advancements in robotics. This guide provides self-contained explanations, re-derives modern
techniques from first principles, and includes ready-to-use code examples using LeRobot and Hugging Face.

--- 
## 💭 Final Thoughts from the Team

Beyond these major features, this release is packed with numerous bug fixes, documentation
improvements, updated dependencies, more examples and better infrastructure to make your
experience with LeRobot smoother and more reliable.

We want to extend a huge **thank you to everyone in the community** for your invaluable
contributions, feedback, and support. We're incredibly excited about the future of open-source
robotics and can't wait to work with you on what's next!

Stay tuned for more to come 🤗 Get started here! – The LeRobot team ❤️

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/lerobot-release-v040*

--- 
## 🏁 Conclusion

LeRobot v0.4.0 represents a significant milestone in open-source robotics, delivering powerful
tools that democratize robot learning research and development. The combination of scalable
datasets, advanced VLA models, streamlined hardware integration, and comprehensive educational
resources positions LeRobot as the go-to platform for the next generation of embodied AI research.

Whether you're a researcher exploring new frontiers in robot learning, a developer building
practical applications, or a student just getting started in robotics, this release provides the
 foundation and tools needed to push the boundaries of what's possible in open-source robotics.

**_#ROBOTICS #MACHINELEARNING #OPENSOURCE #AI #EMBODIEDAI #VLA #HUGGINGFACE #LEROBOT
#DEEPLEARNING #AUTOMATION_**

