# Awesome Physical AI

A curated, research-oriented survey guide to **Physical AI**, **World Models**, **Embodied AI**, and **Robot Foundation Models** (updated for **2026**).

This markdown is designed for researchers who want to:
- quickly map the field from first principles to current frontier systems,
- understand the connection between **perception → representation → world model → planning → control → action**,
- find **core papers**, **survey papers**, **official code**, **datasets**, and **simulation stacks**,
- track the 2025–2026 shift toward **foundation models for robotics and autonomous systems**.

> Scope: world models, generative simulation, embodied AI, robot learning, VLA/VLM/VLM-action models, planning, sim2real, robotics foundation models, and AV-oriented physical AI.

---

## Table of Contents
- [How to Read This List](#how-to-read-this-list)
- [Reading Roadmap](#reading-roadmap)
- [Field Map](#field-map)
- [World Models](#world-models)
  - [Surveys and Overviews](#surveys-and-overviews)
  - [Classic Foundations](#classic-foundations)
  - [Latent Dynamics and Model-Based RL](#latent-dynamics-and-model-based-rl)
  - [Planning-Centric World Models](#planning-centric-world-models)
  - [Video / Generative World Models](#video--generative-world-models)
  - [Multimodal and Interactive World Models](#multimodal-and-interactive-world-models)
- [Physical AI / Embodied AI](#physical-ai--embodied-ai)
  - [Surveys and Overviews-1](#surveys-and-overviews-1)
  - [Robot Learning and Imitation Learning](#robot-learning-and-imitation-learning)
  - [Policy Learning for Manipulation](#policy-learning-for-manipulation)
  - [Vision-Language-Action Models](#vision-language-action-models)
  - [Generalist Robot Foundation Models](#generalist-robot-foundation-models)
  - [Humanoid Robotics](#humanoid-robotics)
  - [Autonomous Driving as Physical AI](#autonomous-driving-as-physical-ai)
- [Planning and Decision Making](#planning-and-decision-making)
  - [Offline RL and Sequence Modeling](#offline-rl-and-sequence-modeling)
  - [Diffusion and Generative Planning](#diffusion-and-generative-planning)
- [Simulation, Physics, and Sim2Real](#simulation-physics-and-sim2real)
- [Datasets and Benchmarks](#datasets-and-benchmarks)
  - [Robot Manipulation and Embodied Data](#robot-manipulation-and-embodied-data)
  - [World Model / Video / Interactive Environment Benchmarks](#world-model--video--interactive-environment-benchmarks)
  - [Autonomous Vehicle Physical AI Data](#autonomous-vehicle-physical-ai-data)
- [Frameworks and Tools](#frameworks-and-tools)
- [GTC / 2026 Frontier Topics](#gtc--2026-frontier-topics)
  - [NVIDIA Cosmos](#nvidia-cosmos)
  - [Isaac GR00T](#isaac-gr00t)
  - [AlpaDreams](#alpadreams)
  - [Alpamayo](#alpamayo)
  - [Newton / Isaac Lab / Omniverse Stack](#newton--isaac-lab--omniverse-stack)
- [Research Directions](#research-directions)
- [Notes for Maintainers](#notes-for-maintainers)

---

## How to Read This List

This is a **curated survey list**, not an exhaustive bibliography.

Recommended reading rule:
1. Start with **survey / overview**
2. Read **classic foundation papers**
3. Compare with **current strong baselines**
4. Study **official code / toolchains**
5. Reproduce on **benchmark datasets / simulators**

Recommended tags:
- **[Must Read]** foundational or field-defining
- **[Baseline]** strong reference point
- **[Recent]** active frontier direction
- **[Practical]** useful for reproduction
- **[Infra]** important tooling / systems layer

---

## Reading Roadmap

### Path A — World Models First
1. **World Models**
2. **PlaNet**
3. **Dreamer**
4. **MuZero**
5. **Genie**
6. modern video / interactive world modeling

### Path B — Embodied / Robot AI First
1. imitation learning + behavior cloning
2. **RT-1**
3. **PaLM-E**
4. **RT-2**
5. **Diffusion Policy**
6. **Open X-Embodiment**
7. **GR00T / Cosmos / Isaac stack**

### Path C — Physical AI Systems View
1. world model papers
2. policy learning papers
3. simulator + digital twin stack
4. dataset flywheel and synthetic data generation
5. deployment stacks for humanoids / AV / industrial robots

---

## Field Map

A useful mental model:

- **World model**: a predictive / generative model of environment dynamics
- **Embodied / Physical AI**: AI that perceives and acts in the world through a body or agent
- **Robot foundation model**: a large pretrained model for robot reasoning, skill transfer, or action generation
- **Physical AI stack**:
  - Perception
  - State / scene representation
  - Dynamics / world model
  - Goal conditioning / language grounding
  - Planning / policy
  - Control / execution
  - Simulation / safety / verification

---

# World Models

## Surveys and Overviews
- **[Must Read] World Models: A Survey**  
  [[Paper](https://arxiv.org/abs/2410.18082)]  
  Broad overview of the modern world-model landscape.

- **[Must Read] Foundation Models for Decision Making: Problems, Methods, and Opportunities**  
  [[Paper](https://arxiv.org/abs/2303.04129)]  
  Useful for connecting world models, sequence models, and control.

- **[Must Read] A Survey of Embodied AI: From Simulators to Research Tasks**  
  [[Paper](https://arxiv.org/abs/2403.06849)]  
  Helpful bridge from world models to embodied systems.

## Classic Foundations
- **[Must Read] World Models**  
  David Ha, Jürgen Schmidhuber  
  [[Paper](https://arxiv.org/abs/1803.10122)] [[Project](https://worldmodels.github.io/)]  
  The canonical starting point for latent generative models used in control.

- **[Must Read] PlaNet: Learning Latent Dynamics for Planning from Pixels**  
  Danijar Hafner et al.  
  [[Paper](https://arxiv.org/abs/1811.04551)] [[Code](https://github.com/google-research/planet)]  
  Landmark latent dynamics model for planning from image observations.

- **[Must Read] Dream to Control: Learning Behaviors by Latent Imagination**  
  Danijar Hafner et al.  
  [[Paper](https://arxiv.org/abs/1912.01603)] [[Code](https://github.com/danijar/dreamer)]  
  A defining paper in imagination-based policy learning.

- **DreamerV2: Mastering Atari with Discrete World Models**  
  [[Paper](https://arxiv.org/abs/2010.02193)] [[Code](https://github.com/danijar/dreamerv2)]

- **DreamerV3: Mastering Diverse Domains through World Models**  
  [[Paper](https://arxiv.org/abs/2301.04104)] [[Code](https://github.com/danijar/dreamerv3)]  
  Strong general-purpose world-model RL baseline.

## Latent Dynamics and Model-Based RL
- **Learning Latent Dynamics for Planning from Pixels**  
  See PlaNet / Dreamer family above.

- **[Baseline] MuZero: Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model**  
  [[Paper](https://arxiv.org/abs/1911.08265)]  
  Not a generative world model in the video sense, but central to planning with learned dynamics.

- **EfficientZero: Mastering Atari with Limited Data**  
  [[Paper](https://arxiv.org/abs/2111.00210)] [[Code](https://github.com/YeWR/EfficientZero)]  
  Important data-efficient planning baseline.

- **IRIS: Efficient World Models Through Learning and Imagination**  
  [[Paper](https://arxiv.org/abs/2306.00966)] [[Code](https://github.com/eloialonso/iris)]  
  Useful recent model in visual world modeling for control.

## Planning-Centric World Models
- **Predictron: End-To-End Learning and Planning**  
  [[Paper](https://arxiv.org/abs/1612.08810)]  
  Early connection between prediction and planning.

- **Value Iteration Networks**  
  [[Paper](https://arxiv.org/abs/1602.02867)]  
  Planning inductive bias inside neural architectures.

- **TD-MPC / TD-MPC2**  
  [[Paper](https://arxiv.org/abs/2203.04955)] [[Code](https://github.com/nicklashansen/tdmpc)]  
  Strong practical planning-focused latent model-based RL direction.

## Video / Generative World Models
- **[Must Read] Video Diffusion Models**  
  [[Paper](https://arxiv.org/abs/2204.03458)]  
  Important stepping stone for modern generative world modeling.

- **Phenaki: Variable Length Video Generation from Open Domain Textual Descriptions**  
  [[Paper](https://arxiv.org/abs/2210.02399)]

- **Make-A-Video: Text-to-Video Generation without Text-Video Data**  
  [[Paper](https://arxiv.org/abs/2209.14792)]

- **Genie: Generative Interactive Environments**  
  [[Paper](https://arxiv.org/abs/2402.15391)]  
  **[Must Read]** A major step toward playable / controllable generative worlds from video.

- **Genie 2**  
  [[Project / DeepMind](https://deepmind.google/discover/blog/genie-2-a-large-scale-foundation-world-model/)]  
  Useful for tracking interactive world-model scaling.

- **Sora**  
  [[OpenAI page](https://openai.com/sora)]  
  Important frontier reference for simulation-grade video generation, even though it is not a robotics paper.

- **VideoPoet: A Large Language Model for Zero-Shot Video Generation**  
  [[Paper](https://arxiv.org/abs/2312.14125)]

## Multimodal and Interactive World Models
- **[Must Read] Gato: A Generalist Agent**  
  [[Paper](https://arxiv.org/abs/2205.06175)]  
  One of the earliest generalist-agent framing papers.

- **PaLM-E: An Embodied Multimodal Language Model**  
  [[Paper](https://arxiv.org/abs/2303.03378)]  
  Important link between language models and embodied reasoning.

- **RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control**  
  [[Paper](https://arxiv.org/abs/2307.15818)]  
  One of the most influential VLA papers.

- **VoxPoser: Composable 3D Value Maps for Robotic Manipulation with Language Models**  
  [[Paper](https://arxiv.org/abs/2307.05973)] [[Code](https://github.com/huangwl18/VoxPoser)]  
  Useful example of grounded language-to-action planning.

---

# Physical AI / Embodied AI

## Surveys and Overviews-1
- **[Must Read] Embodied AI: A Survey**  
  [[Paper](https://arxiv.org/abs/2403.06849)]  
  Broad research survey spanning tasks, training signals, and environments.

- **Robot Learning from Human Demonstrations: A Survey**  
  [[Paper](https://arxiv.org/abs/2011.13347)]  
  Important background for imitation-driven physical AI.

## Robot Learning and Imitation Learning
- **[Must Read] Behavioral Cloning from Observation**  
  [[Paper](https://arxiv.org/abs/1805.01954)]  
  Core idea for learning from trajectories without explicit action labels.

- **DAPG: Learning Complex Dexterous Manipulation with Deep Reinforcement Learning and Demonstrations**  
  [[Paper](https://arxiv.org/abs/1709.10087)] [[Code](https://github.com/aravindr93/hand_dapg)]  
  Early and important dexterous manipulation milestone.

- **BC-Z: Zero-Shot Task Generalization with Robotic Imitation Learning**  
  [[Paper](https://arxiv.org/abs/2202.02005)]  
  Important precursor to large-scale robot policy transfer.

- **Open X-Embodiment: Robotic Learning Datasets and RT-X**  
  [[Project](https://robotics-transformer-x.github.io/)]  
  Key open-data initiative for large-scale robot learning.

## Policy Learning for Manipulation
- **[Must Read] RT-1: Robotics Transformer for Real-World Control at Scale**  
  [[Paper](https://arxiv.org/abs/2212.06817)]  
  Strong bridge from internet-scale model thinking to real robot control.

- **[Must Read] Diffusion Policy: Visuomotor Policy Learning via Action Diffusion**  
  [[Paper](https://arxiv.org/abs/2303.04137)] [[Code](https://github.com/real-stanford/diffusion_policy)]  
  One of the most important practical policy-learning papers in modern manipulation.

- **Behavior Transformer: Predicting Human-Like Actions from Robot Demonstrations**  
  [[Paper](https://arxiv.org/abs/2206.11251)]  
  Useful sequence-modeling baseline.

- **ACT: Action Chunking with Transformers**  
  [[Project / Code](https://github.com/tonyzhaozh/act)]  
  Widely used in practical manipulation pipelines.

- **Octo: An Open-Source Generalist Robot Policy**  
  [[Project](https://octo-models.github.io/)] [[Code](https://github.com/octo-models/octo)]  
  Important open generalist policy effort.

## Vision-Language-Action Models
- **[Must Read] PaLM-E: An Embodied Multimodal Language Model**  
  [[Paper](https://arxiv.org/abs/2303.03378)]

- **[Must Read] RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control**  
  [[Paper](https://arxiv.org/abs/2307.15818)]

- **SayCan: Do As I Can, Not As I Say — Grounding Language in Robotic Affordances**  
  [[Paper](https://arxiv.org/abs/2204.01691)]  
  Classic language grounding paper for robot planning.

- **Code as Policies**  
  [[Paper](https://arxiv.org/abs/2209.07753)] [[Code](https://github.com/google-research/google-research/tree/master/code_as_policies)]  
  Important tool-use / program synthesis perspective.

- **OpenVLA**  
  [[Project](https://openvla.github.io/)] [[Code](https://github.com/openvla/openvla)]  
  Strong open-source VLA reference point.

## Generalist Robot Foundation Models
- **[Must Read] Gato: A Generalist Agent**  
  [[Paper](https://arxiv.org/abs/2205.06175)]

- **[Must Read] Open X-Embodiment / RT-X**  
  [[Project](https://robotics-transformer-x.github.io/)]  
  Large-scale cross-robot generalization direction.

- **Octo**  
  [[Project](https://octo-models.github.io/)] [[Code](https://github.com/octo-models/octo)]

- **RoboMimic**  
  [[Project](https://robomimic.github.io/)] [[Code](https://github.com/ARISE-Initiative/robomimic)]  
  Important reproducibility and policy-learning toolkit.

## Humanoid Robotics
- **[Recent] NVIDIA Isaac GR00T N1**  
  [[News / Overview](https://nvidianews.nvidia.com/news/nvidia-isaac-gr00t-n1-open-humanoid-robot-foundation-model-simulation-frameworks)]  
  2025 milestone in open humanoid robot foundation modeling.

- **Figure / 1X / Agility / Boston Dynamics / NEURA Robotics**  
  Track these builders as system integrators of humanoid stacks, often combining foundation models, simulation, and edge deployment.

- **GR00T research ecosystem**  
  [[Developer page](https://developer.nvidia.com/isaac/gr00t)]  
  Use this as an anchor for current NVIDIA humanoid tooling when the page is live.

## Autonomous Driving as Physical AI
- **[Recent] NVIDIA Alpamayo**  
  [[Developer page](https://developer.nvidia.com/drive/alpamayo)]  
  Strong example of AV being reframed as physical AI with reasoning VLA models, open simulation, and open datasets.

- **End-to-end autonomous driving with reasoning / planning traces**  
  This is a fast-moving frontier; prefer official model and dataset pages over third-party summaries.

---

# Planning and Decision Making

## Offline RL and Sequence Modeling
- **[Must Read] Decision Transformer: Reinforcement Learning via Sequence Modeling**  
  [[Paper](https://arxiv.org/abs/2106.01345)] [[Code](https://github.com/kzl/decision-transformer)]

- **Trajectory Transformer**  
  [[Paper](https://arxiv.org/abs/2106.02039)] [[Code](https://github.com/jannerm/trajectory-transformer)]

- **Implicit Q-Learning (IQL)**  
  [[Paper](https://arxiv.org/abs/2110.06169)] [[Code](https://github.com/ikostrikov/implicit_q_learning)]  
  Important practical offline RL baseline.

- **Conservative Q-Learning (CQL)**  
  [[Paper](https://arxiv.org/abs/2006.04779)] [[Code](https://github.com/aviralkumar2907/CQL)]

## Diffusion and Generative Planning
- **[Must Read] Diffuser: Planning with Diffusion for Flexible Behavior Synthesis**  
  [[Paper](https://arxiv.org/abs/2205.09991)] [[Code](https://github.com/jannerm/diffuser)]

- **Decision Diffuser**  
  [[Paper](https://arxiv.org/abs/2211.15657)]  
  Good continuation of diffusion-based planning ideas.

- **Diffusion Policy**  
  [[Paper](https://arxiv.org/abs/2303.04137)] [[Code](https://github.com/real-stanford/diffusion_policy)]  
  Relevant to both manipulation and planning.

---

# Simulation, Physics, and Sim2Real

- **[Must Read] Domain Randomization for Transferring Deep Neural Networks from Simulation to the Real World**  
  [[Paper](https://arxiv.org/abs/1703.06907)]

- **RMA: Rapid Motor Adaptation for Legged Robots**  
  [[Paper](https://arxiv.org/abs/2107.04034)]  
  Important sim2real lesson for robust control.

- **Isaac Gym**  
  [[Project](https://developer.nvidia.com/isaac-gym)]

- **Isaac Sim**  
  [[Docs](https://developer.nvidia.com/isaac/sim)]

- **Isaac Lab**  
  [[Docs](https://developer.nvidia.com/isaac/lab)]  
  Increasingly central for large-scale robot learning workflows.

- **MuJoCo**  
  [[Website](https://mujoco.org/)] [[Docs](https://mujoco.readthedocs.io/)]

- **PyBullet**  
  [[Project](https://pybullet.org/wordpress/)]

- **Omniverse**  
  [[Overview](https://www.nvidia.com/en-us/omniverse/)]  
  Important for digital twins, simulation, and synthetic data.

---

# Datasets and Benchmarks

## Robot Manipulation and Embodied Data
- **Open X-Embodiment**  
  [[Project](https://robotics-transformer-x.github.io/)]

- **BridgeData V2**  
  [[Project](https://rail-berkeley.github.io/bridgedata/)]

- **RoboNet**  
  [[Project](https://robonet.wiki/)]  
  Early large-scale multi-robot manipulation dataset.

- **Ego4D**  
  [[Website](https://ego4d-data.org/)]  
  Useful for egocentric perception and embodied understanding.

## World Model / Video / Interactive Environment Benchmarks
- **DMLab / Atari / Procgen / Minecraft-like interactive settings**  
  Classic evaluation families for generalization, planning, and model-based RL.

- **D4RL**  
  [[Paper](https://arxiv.org/abs/2004.07219)] [[Code](https://github.com/rail-berkeley/d4rl)]  
  Standard offline RL benchmark.

- **MineDojo**  
  [[Project](https://minedojo.org/)]  
  Useful for generalist embodied agent research.

## Autonomous Vehicle Physical AI Data
- **[Recent] NVIDIA Physical AI Open Datasets**  
  [[Dataset page](https://developer.nvidia.com/drive/alpamayo)]  
  Refer to the Alpamayo ecosystem for the open AV dataset entry point.

- **nuScenes / nuPlan / Waymo Open Dataset / Argoverse 2**  
  Use alongside AV reasoning / planning research if your focus is physical AI for autonomy.

---

# Frameworks and Tools

- **[Practical] RLlib**  
  [[Docs](https://docs.ray.io/en/latest/rllib/)]

- **[Practical] Stable-Baselines3**  
  [[GitHub](https://github.com/DLR-RM/stable-baselines3)]

- **[Practical] CleanRL**  
  [[GitHub](https://github.com/vwxyzjn/cleanrl)]

- **[Practical] RoboMimic**  
  [[GitHub](https://github.com/ARISE-Initiative/robomimic)]

- **[Practical] LeRobot**  
  [[GitHub](https://github.com/huggingface/lerobot)]  
  A very useful modern open robotics stack for reproduction.

- **[Practical] ManiSkill**  
  [[Project](https://maniskill.ai/)] [[Code](https://github.com/haosulab/ManiSkill)]  
  Strong benchmark and simulator ecosystem for manipulation.

---

# GTC / 2026 Frontier Topics

## NVIDIA Cosmos
- **Cosmos platform / world foundation model direction**  
  [[Overview](https://blogs.nvidia.com/blog/nvidia-cosmos-world-foundation-model-platform-physical-ai/)]  
  Track as the core NVIDIA world-foundation direction for synthetic data generation, reasoning, and simulation.

## Isaac GR00T
- **Isaac GR00T N1**  
  [[News](https://nvidianews.nvidia.com/news/nvidia-isaac-gr00t-n1-open-humanoid-robot-foundation-model-simulation-frameworks)]  
  2025 release framing humanoid robotics around an open robot foundation model.

- **Isaac GR00T developer stack**  
  [[Developer page](https://developer.nvidia.com/isaac/gr00t)]  
  Watch for current model versions, post-training recipes, and deployment guidance.

## AlpaDreams
- **[Recent] AlpaDreams — NVIDIA SIL**  
  [[Project](https://research.nvidia.com/labs/sil/projects/alpadreams/)]  
  An AV-oriented generative world model project focused on physically realistic scene dynamics and traffic-relevant semantics.

## Alpamayo
- **[Recent] Alpamayo for Autonomous Vehicle Development**  
  [[Developer page](https://developer.nvidia.com/drive/alpamayo)]  
  Open VLA models + simulator + datasets for autonomous driving.

- **Alpamayo 1 / 1.5 research pages**  
  [[Research page](https://research.nvidia.com/publication/2025-10_alpamayo-r1)]  
  Good entry point for the reasoning + trajectory prediction framing.

## Newton / Isaac Lab / Omniverse Stack
- **Newton physics engine**  
  [[News](https://nvidianews.nvidia.com/news/nvidia-isaac-gr00t-n1-open-humanoid-robot-foundation-model-simulation-frameworks)]  
  Open-source robotics-focused physics effort associated with NVIDIA, Google DeepMind, and Disney Research.

- **Isaac Lab**  
  [[Docs](https://developer.nvidia.com/isaac/lab)]

- **Isaac Sim**  
  [[Docs](https://developer.nvidia.com/isaac/sim)]

- **Omniverse**  
  [[Overview](https://www.nvidia.com/en-us/omniverse/)]

---

# Research Directions

## 1. General world models
How can we move from video prediction to models that preserve:
- geometry,
- causality,
- contact dynamics,
- affordances,
- action-conditioned semantics?

## 2. Synthetic data flywheel
A major 2025–2026 trend:
- collect real trajectories,
- train world model / simulator,
- generate synthetic edge cases,
- train policy,
- validate in closed loop,
- distill for deployment.

## 3. VLA + world model fusion
Important open question:
- should action policies call a world model explicitly,
- or should world-model-like behavior emerge implicitly inside VLA architectures?

## 4. Humanoid scaling
Key challenge areas:
- dexterity,
- long-horizon household skills,
- robust locomotion,
- safe failure recovery,
- post-training on small real data.

## 5. Autonomous driving as reasoning-based physical AI
AV is increasingly being reframed from:
- modular perception / planning stacks
to
- end-to-end or hybrid reasoning systems
with:
- simulation,
- synthetic long-tail generation,
- interpretable reasoning traces,
- safety validation.

## 6. Evaluation
The field still lacks universally accepted evaluation for:
- grounded reasoning,
- physical consistency,
- action reliability,
- closed-loop long-horizon robustness,
- sim2real transfer.

---

## Notes for Maintainers

Suggested curation rules:
1. Prefer **official paper links**, **official project pages**, and **official code**.
2. Keep **full paper titles**.
3. Tag entries as **survey / baseline / recent / practical / infra**.
4. Avoid listing too many derivative reimplementations.
5. Keep the repo useful for both:
   - first-pass survey,
   - deep-dive literature review.

Suggested future sections:
- tactile foundation models
- multimodal robot memory
- causal world models
- embodied safety / alignment
- industrial physical AI
- physical AI for science and labs
