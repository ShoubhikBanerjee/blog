---
title: "Garbage In, Garbage Out: The Case For Better Robot Data Understanding"
description: "A comprehensive analysis of robot dataset quality assessment using visual and
motion scoring techniques, demonstrating how low-quality data significantly impacts robot
learning performance."
date: 2025-10-28T00:56:28.542333+05:30
tags: ["robotics", "machine-learning", "data-quality", "teleoperation", "open-x-embodiment", "ACT", "franka", "UR5", "DROID", "computer-vision"]
categories: ["Robotics", "Machine Learning", "Data Science"]
image: "https://cdn-uploads.huggingface.co/production/uploads/68eae3f4b462cbf3243155c8/paxnE6FD5Lf-LWfAArml3.png"
math: true
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🤖 Garbage In, Garbage Out: The Case For Better Robot Data Understanding

![Alt Text](https://cdn-uploads.huggingface.co/production/uploads/68eae3f4b462cbf3243155c8/paxnE6FD5Lf-LWfAArml3.png)

*RobotData's comprehensive toolkit for analyzing robot dataset quality*

---

> ### 💡 Key Insight
> **Low quality robot data → Poor robot performance.**

Robot data collection is expensive, requiring hundreds of human expert teleoperation hours. At
the same time, collecting **high quality** robot data is difficult - even for a highly skilled
teleoperator. For example, idle trajectories may occur when the teleoperator pauses or poor
lighting might affect visual clarity.

While the **precise** definition of what constitutes a high quality training example is a
complicated question (e.g. does a dark video increase policy resilience or reduce performance?),
 a few quality indicators can provide an insightful snapshot into your dataset. Data
understanding is the first step to data improvement.

In this article, we introduce a lightweight Open Source toolkit to find low quality examples in
the Open X-Embodiment datasets and show that training on **20%** of low quality examples hurts
policy training loss by **30%**.

### 🎯 Want to know how good *your* dataset is?

![score_lerobot_episodes](https://cdn-uploads.huggingface.co/production/uploads/68eae3f4b462cbf3
243155c8/RocyD8bhLoorNfqo21rcL.png)

### ⚡ Try out the tool here: https://github.com/RoboticsData/score_lerobot_episodes

---

## 🔍 Robot Data Defined

We ran experiments on the Open X-Embodiment datasets - a large collection of over 60 robot
manipulation datasets gathered through teleoperation on robots such as **Franka**, **UR5**, and
**DROID**.

| ![Open X-Embodiment Overview](https://cdn-uploads.huggingface.co/production/uploads/68eae3f4b462cbf3243155c8/IVdQ5ODRVh3hmac0k2Z5j.png) |
|---|
| **Overview of the Open X-Embodiment dataset** |

A dataset is represented as a collection of N episodes (or trajectories):
**D = {E₁, …, Eₙ}**

Each episode consists of timestamped frames:
**Eᵢ = {(oᵢ,ₜ, sᵢ,ₜ, aᵢ,ₜ)}ᵀⁱₜ₌₁**

where **oᵢ,ₜ** is the **observation**, **sᵢ,ₜ** is the **robot state**, and **aᵢ,ₜ** is the
**action** at time **t**.

### 👁️ Observation spac

Each observation **oᵢ,ₜ** includes two synchronized **RGB camera streams**:

1. An over-the-shoulder view showing the full scene and robot
2. A wrist-mounted camera providing a close-up view of the robot's end-effector

### ⚙️ State space

**sᵢ,ₜ = [qᵢ,ₜ, gᵢ,ₜ] ∈ ℝᴶ⁺¹**

where **qᵢ,ₜ ∈ ℝᴶ** represents the robot's **joint angles** at time **t**, and **gᵢ,ₜ ∈ ℝ**
represents the **gripper position** (e.g., open or closed).

### 🎮 Action space

**aᵢ,ₜ = [q'ᵢ,ₜ, g'ᵢ,ₜ] ∈ ℝᶜ⁺¹**

where **q'ᵢ,ₜ** are the **motor commands** and **g'ᵢ,ₜ** is the **gripper command** applied by the teleoperator.

--- 
## 📸 Visual Scoring

We evaluate each episode for visual clarity indicators such as **lighting** and **blur**. This
allows us to ensure that only high-quality visual data is retained for training.

Our process involves:

1. **Uniformly sampling 10 frames per episode** - This strategy provides a representative
snapshot of the visual quality throughout the episode without the computational expense of analyzing every frame
2. **Compute per-episode aggregate visual score** - For each frame **I**, we compute a penalty
based on blur and brightness where frames which are too dark or too blurry are penalized. This
penalty is then averaged across the episode and used to compute an aggregate visual score
3. **Remove episodes that score below a threshold** - This final filtering step discards any
episode whose aggregate visual score falls below a pre-defined quality threshold, ensuring only
visually high-quality data is retained for training

### 🌀 Blur

We estimate blur using the **variance of the Laplacian**. This metric is used because **it
measures the magnitude of high-frequency content in an image, which is drastically reduced by
blur.** The high-frequency components correspond to sharp edges and details; a sharper image
will have a higher variance of the Laplacian.

The **Laplace operator**, **Δ**, for a 2D image **I(x, y)** is defined as the sum of its second partial derivatives:

**ΔI = ∂²I/∂x² + ∂²I/∂y²**

In discrete form, it is often approximated using a convolution kernel e.g., a **3 × 3** kernel such as:

```
⎛ 0  1  0 ⎞ ⎜ 1 -4  1 ⎟
⎝ 0  1  0 ⎠
```

where **ΔI** is the discrete convolution of the kernel **Δ** with the frame **I**.

The metric used for blur is the **variance of the Laplacian** **Var(ΔI)**, which is calculated
across all pixels in the frame:

**Var(ΔI) = (1/HW) Σₓ₌₁ᵂ Σᵧ₌₁ᴴ (ΔI(x,y) - μΔI)²**

where **W × H** is the frame size, and **μΔI** is the mean of the Laplacian values over the frame.

We then scale this variance into a blur penalty score and apply a threshold. In practice we use
a default value of 100 for the variance threshold.

### 💡 Lighting

We use mean-brightness as a proxy for good lighting. If the mean intensity **μ** of the
grayscale image is below 50 (on a scale of 0 to 255), we assign a linearly proportional penalty:

**Penalty = max(0.0, (50.0 - μ)/50.0)**

Note we only penalize images that are too dark; overexposure is not penalized since it is not a
failure mode that occurs frequently and we observe that penalizing it can result in an excessive
 rate of false positives.

In many cases, the wrist camera suffers from a noticeable drop in visual quality compared to the
 overhead view due to occlusions, shadows and focus issues.

--- 
## 🏃‍♂️ Motion Scor

In addition to visual observations, each episode contains motion data representing the robot's
internal state and control commands over time. This includes joint positions, velocities, and
actions, which specify the robot's kinematic behavior.

We introduce scoring functions that classify the quality of motion of a given episode. We
describe how we score for categories such as collision, path efficiency, and idle-time.

### 💥 Collision

We aim to detect potential physical collisions by analyzing spikes in the robot's joint-space
acceleration. The idea is that when a robot physically impacts an object, it experiences abrupt
changes in joint motion—typically seen as sudden decelerations upon contact, and rapid accelerations as it moves away.

Our collision scoring function estimates an acceleration threshold for each joint, based on the
median absolute acceleration over time. A spike is detected when any joint's acceleration at a
given timestamp exceeds its respective threshold.

- **Joint acceleration proxy:**
  **aₜ = (qₜ₊₁ - 2qₜ + qₜ₋₁)/(tₜ₊₁ - tₜ)²**

- **Per-joint robust threshold:**
  **spike_ratio = θ > 15 × median(|a|)**

- **Collision score (goodness):**
  **1 - spike_ratio**

The function returns a score between 0 and 1 where a low-score indicates high likelihood of collision.

### 📏 Path Efficiency

We also score path efficiency by calculating how close the motion of the robot is to a straight
line. This is motivated by the fact that expert trajectories are often the most direct path
between two points. A path with excessive meandering or corrections suggests poor human control
or indecision, which introduces noise and complexity that hampers policy training and results in
 inefficient robot behavior.

**Path length:**
**L = Σₜ ‖qₜ₊₁ - qₜ‖₂**

**Straight-line distance:**
**D = ‖qₑₙd - qₛₜₐᵣₜ‖₂**

**Path Efficiency Score:**
```
path_eff = { clip(D/L, 0, 1),  if L ≥ 10⁻⁶
  0,                otherwise }
```

The final score is the ratio of the straight-line distance in joint space to the actual path length traveled.

There may be situations where the direct path between two points isn't the ideal trajectory. For
 example, manipulating an object or maneuvering past obstacles in the scene might result in high
 amounts of nonlinear local perturbations or the robot's joint configuration may not permit a
direct path. In these cases, path efficiency may not be a useful metric and can be excluded from the scoring criteria.

### ⚡ Actuator Saturation

When the expected action **aₜ** doesn't result in the next state **qₜ₊₁** we use this as a proxy
 for actuator saturation. Too much actuator saturation can indicate that the robot is lifting
heavier loads than it is equipped for or is running into resistance within the scene or has
faulty motors. In order to reduce robot wear and tear over time, we want to prevent this
behavior inheriting this behavior from training data.

Specifically, we check how often **|aₜ - qₜ₊₁| > threshold_deg** for any joint (threshold default: 7).

To downweight minor transient divergence caused by slippage or inertia, we impose a
non-linearity on the saturation ratio:

**sₛₐₜ = exp(-4 · saturation_ratio)**

### ⏸️ Idle Time

We score the robot's motion based on how idle it is throughout the task. This is bad because
periods of near-zero velocity are often the result of distraction, indecision, or taking a break
 rather than intentional action to complete the task. These stationary periods slow down
learning and result in undesirable robot behavior.

Specifically, we calculate the proportion of time the robot's velocity lies below a certain
threshold during its motion. We first calculate the joint-space velocity magnitude **‖vₜ‖** for each time step **t**:

**‖vₜ‖ = √(Σⱼ₌₁ᴶ (Δqⱼ/Δt)²)**

The raw score is **1.0** minus the proportion of steps where **‖vₜ‖** is below a threshold default of **0.1**.

We also note that filtering idle intervals improves performance in openpi.

Idle time may sometimes be useful to attenuate inertia or allow the dynamics of the environment
to settle to rest before the next action. In these cases, idle time is repeated and predictable rather than incidental.

We are currently in the process of launching a tool that accounts for these cases so if your use
 case exhibits such behavior, reach out to us!

--- 
## 🧪 Corruption Experiment

We evaluate the effect of noisy examples on robot learning by artificially corrupting the robot
using the sources of noise we aim to identify using our tool. Specifically, for 20% of episodes,
 we introduce the following realistic corruptions:

- **Visual Noise**: We artificially darken frames and apply an unsharp mask or motion blur to a
random subset of frames in the episode
- **Motion Noise**: We introduce short, random idle periods (setting joint velocities to zero
for 0.5-1.0 seconds) and insert single-step acceleration spikes (random, large joint command
outliers) to simulate teleoperator jerks or minor collisions

### 📊 Note on evaluations

In a typical machine learning experiment, the most direct approach would be to compare the
held-out validation loss on a model train on the filtered and unfiltered versions of a real-world dataset.

However, in the context of robotics, validation loss isn't representative of real-world
performance and the training loss is not directly comparable since the filtered set has fewer examples.

For simplicity's sake, we opt to motivate the importance of data understanding by using an
artificial corruption experiment to illustrate the impact of low quality data on robot learning.

We invite the community to share real world or simulation evaluation results and plan to share
more of our own results in a future post.

### 🎯 Retrieval Precision-Recall

Just for illustrative purposes, we can design the following recall/precision experiment where we
 use our scoring algorithm to detect corrupted episodes within a dataset that has been
corrupted. Essentially, we have the following binary classification problem where we set a
threshold where episodes whose score fell below this result where classified as corrupt.

For example, we have the following results for the detecting corrupted videos using the visual
scoring function in the following Stanford HYDRA dataset. This is a robotic manipulation dataset
 containing 570 episodes of Franka robot demonstrations across 3 tasks, with synchronized wrist
and external camera views and 7-DOF action sequences.

For this experiment, we corrupted 50% of these episodes and obtained the following precision and
 recall results for various thresholds.

| ![Precision-Recall Results](https://cdn-uploads.huggingface.co/production/uploads/68eae3f4b462cbf3243155c8/4Wuofxeh280NEk9BprGkU.png) |
|---|
| *Precision, Recall and F-1 curves on the Stanford HYDRA dataset (50% corrupted).* |

--- 
## 📈 Effects on Training

We also compared the training losses between the original datasets and the corrupted datasets
where we used ACT as our policy.

The figure below compares policy training on a corrupted dataset—where 20% of the episodes were
intentionally degraded—with training on the original, clean dataset.

We see that models trained on corrupted data require significantly more optimization steps to
reach the same loss threshold as those trained on clean data, highlighting the sensitivity of
policy learning to data quality.

| ![Stanford Hydra Training Loss](https://cdn-uploads.huggingface.co/production/uploads/68eae3f4b462cbf3243155c8/EwfFO4KzyWsnSu-EVOXoz.png) |
|---|
| *Standard Hydra training loss curve.* |

| ![Berkeley Autolab UR5 Training Loss](https://cdn-uploads.huggingface.co/production/uploads/68eae3f4b462cbf3243155c8/caAXsXIH5c9oQO8OeheVf.png) |
|---|
| *Berkeley Autolab UR5 training loss curve.* |

In conclusion, these results quantify the large impact of incorporating low quality data into an
 otherwise useful dataset, resulting in poor performance and wasted GPU hours.

--- 
### 💬 We'd love to hear from you - do send us any comments or feedback you have!

### 🔗 https://github.com/RoboticsData/score_lerobot_episodes

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/robotdata/gigo*

--- 
## 🏁 Conclusion

This comprehensive analysis demonstrates the critical importance of data quality in robot
learning systems. The research clearly shows that even a modest 20% contamination of low-quality
 data can significantly degrade training performance by 30%, leading to wasted computational
resources and suboptimal robot behavior.

The open-source toolkit presented here provides practitioners with concrete metrics for
evaluating both visual and motion quality in robot datasets. By implementing systematic scoring
for blur, lighting, collisions, path efficiency, actuator saturation, and idle time, teams can
make informed decisions about data curation and improve their robot learning outcomes.

The "garbage in, garbage out" principle is particularly relevant in robotics, where data
collection is expensive and time-consuming. Investing in proper data quality assessment upfront
can save significant resources in training and deployment phases while ensuring more reliable
robot performance in real-world scenarios.

--- 
_#ROBOTICS #MACHINELEARNING #DATAQUALIT Y #ROBOTDATA #TELEOPERATION #OPENXEMBODIMENT #ACT
#FRANKA #UR5 #DROID_

