# Awesome Physical AI

A curated research-oriented survey guide to **Physical AI** and **World Models** (updated for **2026**).

This document is designed for researchers who want to:
- understand the structure of modern embodied AI,
- quickly identify key papers and paradigms,
- connect perception → world modeling → planning → control,
- access official implementations when possible.

---

## Table of Contents
- [Overview](#overview)
- [Reading Roadmap](#reading-roadmap)
- [World Models](#world-models)
  - [Classic Foundations](#classic-foundations)
  - [Latent World Models](#latent-world-models)
  - [Video / Generative World Models](#video--generative-world-models)
  - [Multimodal World Models](#multimodal-world-models)
- [Embodied / Physical AI](#embodied--physical-ai)
  - [Robot Learning and Manipulation](#robot-learning-and-manipulation)
  - [Vision-Language-Action Models](#vision-language-action-models)
  - [Simulation and Sim2Real](#simulation-and-sim2real)
- [Planning and Decision Making](#planning-and-decision-making)
- [Datasets and Benchmarks](#datasets-and-benchmarks)
- [Frameworks and Tools](#frameworks-and-tools)
- [Research Directions](#research-directions)

---

## Overview

Physical AI refers to AI systems that **interact with the real world** through perception, reasoning, and action.

Core pipeline:
- Perception → Representation → World Model → Planning → Control → Action

Modern trend (2023–2026):
- shift from modular pipelines → **foundation models + world models**
- shift from supervised learning → **self-supervised + simulation**
- shift from task-specific → **generalist agents**

---

## Reading Roadmap

### Step 1: Understand World Models
- Ha & Schmidhuber (2018)
- Dreamer / PlaNet / MuZero

### Step 2: Learn Modern Generative Models
- Video diffusion / latent dynamics
- Sora-style models

### Step 3: Study Embodied AI
- RT-1 / RT-2
- PaLM-E

### Step 4: Connect to Planning
- MuZero / Decision Transformer / diffusion policy

---

# World Models

## Classic Foundations

- **World Models**  
  Ha & Schmidhuber  
  [[Paper](https://arxiv.org/abs/1803.10122)]  
  Introduced latent world models for control.

- **PlaNet: Learning Latent Dynamics for Planning from Pixels**  
  Hafner et al.  
  [[Paper](https://arxiv.org/abs/1811.04551)] [[Code](https://github.com/google-research/planet)]

- **Dreamer: Reinforcement Learning with Latent World Models**  
  Hafner et al.  
  [[Paper](https://arxiv.org/abs/1912.01603)] [[Code](https://github.com/danijar/dreamer)]

- **DreamerV2 / DreamerV3**  
  Hafner et al.  
  [[Paper](https://arxiv.org/abs/2010.02193)]  
  Strong model-based RL baselines.

- **MuZero: Mastering Atari, Go, Chess without Rules**  
  Schrittwieser et al.  
  [[Paper](https://arxiv.org/abs/1911.08265)]

---

## Latent World Models

- **Learning Latent Dynamics for Planning**  
  PlaNet / Dreamer family (see above)

- **IRIS: Efficient World Models via Latent Imagination**  
  [[Paper](https://arxiv.org/abs/2306.00966)] [[Code](https://github.com/eloialonso/iris)]

- **Genie: Generative Interactive Environments**  
  Google DeepMind  
  [[Paper](https://arxiv.org/abs/2402.15391)]

---

## Video / Generative World Models

- **Video Diffusion Models**  
  Ho et al.  
  [[Paper](https://arxiv.org/abs/2204.03458)]

- **Make-A-Video: Text-to-Video Generation without Text-Video Data**  
  Meta AI  
  [[Paper](https://arxiv.org/abs/2209.14792)]

- **Sora: OpenAI Text-to-Video Model**  
  [[Blog](https://openai.com/sora)]

- **VideoPoet: A Large Language Model for Zero-Shot Video Generation**  
  Google  
  [[Paper](https://arxiv.org/abs/2312.14125)]

---

## Multimodal World Models

- **PaLM-E: Embodied Multimodal Language Model**  
  Google  
  [[Paper](https://arxiv.org/abs/2303.03378)]

- **RT-2: Vision-Language-Action Models**  
  Google  
  [[Paper](https://arxiv.org/abs/2307.15818)]

- **Gato: A Generalist Agent**  
  DeepMind  
  [[Paper](https://arxiv.org/abs/2205.06175)]

---

# Embodied / Physical AI

## Robot Learning and Manipulation

- **RT-1: Robotics Transformer for Real-World Control**  
  [[Paper](https://arxiv.org/abs/2212.06817)]

- **Diffusion Policy: Visuomotor Policy Learning via Diffusion**  
  [[Paper](https://arxiv.org/abs/2303.04137)] [[Code](https://github.com/real-stanford/diffusion_policy)]

- **Behavior Transformer (BeT)**  
  [[Paper](https://arxiv.org/abs/2206.11251)]

---

## Vision-Language-Action Models

- **RT-2-X / RT-H (recent extensions)**  
  (See RT-2 ecosystem)

- **SayCan: Grounding Language in Robotic Affordances**  
  [[Paper](https://arxiv.org/abs/2204.01691)]

---

## Simulation and Sim2Real

- **Domain Randomization for Sim2Real Transfer**  
  [[Paper](https://arxiv.org/abs/1703.06907)]

- **Isaac Gym / Isaac Sim**  
  [[Docs](https://developer.nvidia.com/isaac)]

- **MuJoCo Physics Engine**  
  [[Website](https://mujoco.org/)]

---

# Planning and Decision Making

- **Decision Transformer: Reinforcement Learning via Sequence Modeling**  
  [[Paper](https://arxiv.org/abs/2106.01345)] [[Code](https://github.com/kzl/decision-transformer)]

- **Trajectory Transformer**  
  [[Paper](https://arxiv.org/abs/2106.02039)]

- **Diffuser: Planning with Diffusion Models**  
  [[Paper](https://arxiv.org/abs/2205.09991)]

---

# Datasets and Benchmarks

- **D4RL: Offline Reinforcement Learning Benchmark**  
  [[Paper](https://arxiv.org/abs/2004.07219)] [[Code](https://github.com/rail-berkeley/d4rl)]

- **Open X-Embodiment Dataset**  
  [[Website](https://robotics-transformer-x.github.io/)]

- **Ego4D Dataset**  
  [[Website](https://ego4d-data.org/)]

---

# Frameworks and Tools

- **RLlib (Ray)**  
  [[Docs](https://docs.ray.io/en/latest/rllib/)]

- **Stable-Baselines3**  
  [[GitHub](https://github.com/DLR-RM/stable-baselines3)]

- **CleanRL**  
  [[GitHub](https://github.com/vwxyzjn/cleanrl)]

---

# Research Directions

- General world models (physical + semantic + causal)
- Scaling laws for embodied intelligence
- Long-horizon planning with LLMs
- Simulation-to-real generalization
- Multimodal reasoning + action integration
