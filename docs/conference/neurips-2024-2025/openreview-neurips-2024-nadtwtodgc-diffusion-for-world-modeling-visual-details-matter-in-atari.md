---
title: "Diffusion for World Modeling: Visual Details Matter in Atari"
title_zh: 扩散世界模型：视觉细节在雅达利游戏中的重要性
authors: "Eloi Alonso, Adam Jelley, Vincent Micheli, Anssi Kanervisto, Amos Storkey, Tim Pearce, François Fleuret"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=NadTwTODgC"
tags: ["query:player-ai"]
score: 9.0
evidence: 基于扩散的世界模型用于雅达利游戏；直接用于训练游戏中的RL智能体
tldr: 本文指出现有世界模型因离散压缩丢失视觉细节，引入DIAMOND，利用扩散模型作为环境模型，保留丰富视觉信息。在雅达利游戏上训练RL智能体，展示了扩散世界模型在样本效率与最终性能上的优势，为游戏智能体训练提供了新范式。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 716, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 725, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 941, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1017, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1000, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1254, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1419, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1154, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1306, \"height\": 849, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nadtwtodgc/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1432, \"height\": 710, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-nadtwtodgc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 1002, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nadtwtodgc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1123, \"height\": 901, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nadtwtodgc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 992, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nadtwtodgc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 829, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nadtwtodgc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 1051, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nadtwtodgc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1153, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nadtwtodgc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1443, \"height\": 281, \"label\": \"Table\"}]"
motivation: 现有世界模型使用离散隐变量，压缩过程忽略了对RL重要的视觉细节。
method: 采用扩散模型作为世界模型，直接建模环境动态，保留视觉细节。
result: 在雅达利游戏基准上取得了优秀的性能。
conclusion: 证明了扩散模型作为世界模型在游戏RL中的有效性，推动了高保真世界模型发展。
---

## Abstract
World models constitute a promising approach for training reinforcement learning agents in a safe and sample-efficient manner. Recent world models predominantly operate on sequences of discrete latent variables to model environment dynamics. However, this compression into a compact discrete representation may ignore visual details that are important for reinforcement learning. Concurrently, diffusion models have become a dominant approach for image generation, challenging well-established methods modeling discrete latents. Motivated by this paradigm shift, we introduce DIAMOND (DIffusion As a Model Of eNvironment Dreams), a reinforcement learning agent trained in a diffusion world model. We analyze the key design choices that are required to make diffusion suitable for world modeling, and demonstrate how improved visual details can lead to improved agent performance. DIAMOND achieves a mean human normalized score of 1.46 on the competitive Atari 100k benchmark; a new best for agents trained entirely within a world model. We further demonstrate that DIAMOND's diffusion world model can stand alone as an interactive neural game engine by training on static *Counter-Strike: Global Offensive* gameplay. To foster future research on diffusion for world modeling, we release our code, agents, videos and playable world models at https://diamond-wm.github.io.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）

- **动机**：现有世界模型（如DreamerV3、IRIS）通常将环境动态建模为离散隐变量序列，这种有损压缩会丢失对强化学习（RL）至关重要的视觉细节（如远处敌人、小奖励物）。同时，扩散模型在图像生成领域已取代离散token方法，能够生成高质量、易条件化的图像。
- **核心目标**：将扩散模型引入世界模型，使其直接在像素空间建模环境动态，保留视觉细节，从而提升RL智能体在想象训练中的性能。作者提出DIAMOND（DIffusion As a Model Of eNvironment Dreams），并在Atari 100k基准上验证。

### 2. 方法论：核心思想、关键技术细节

- **核心思想**：使用条件扩散模型直接生成下一帧观测 `p(xt+1 | x≤t, a≤t)`，替代离散隐变量序列建模。RL智能体完全在此扩散世界模型的“想象”环境中训练。
- **关键技术细节**：
  - 采用EDM（Karras et al. 2022）而非DDPM，理由：EDM通过自适应信号/噪声混合的训练目标，在低去噪步数下更稳定，避免复合误差。
  - 网络结构：U-Net 2D，通过帧堆叠（最近L帧）进行观测条件化，通过自适应组归一化（Adaptive Group Normalization）注入动作和扩散时间。
  - 训练目标：`L(θ) = E[||Fθ(c_in * x_τ + ...) - target||^2]`，其中target在噪声水平高时接近干净帧，噪声低时接近添加的噪声。
  - 采样：欧拉方法，默认3步去噪（平衡质量与速度）。
  - 奖励/终止预测：独立CNN+LSTM模型。
  - RL算法：REINFORCE + 价值基线，λ-returns，在想象中训练actor-critic网络。
- **训练流程**：循环（数据收集 → 世界模型训练 → 想象中RL训练），与Kaiser et al. (2019) 类似。

### 3. 实验设计

- **主要基准**：Atari 100k benchmark（26个游戏，每个游戏仅允许10万步环境交互，约2小时游戏时间）。
- **对比方法**：世界模型类方法（SimPLe, TWM, IRIS, DreamerV3, STORM）；另在附录中与搜索/免模型方法（EfficientZero, BBF）比较。
- **附加实验**：
  - 消融：DDPM vs EDM（在Breakout上对比复合误差）；去噪步数（1步 vs 3步）对性能影响。
  - 视觉质量对比：在CS:GO和Motorway Driving数据集上计算FVD、FID、LPIPS，对比IRIS和DreamerV3。
  - CS:GO神经游戏引擎：训练381M参数扩散模型（含上采样器），在静态5M帧数据上训练，演示交互式和可玩性。
- **评估指标**：人类归一化得分（HNS）的均值、四分位均值（IQM），并给出置信区间和性能曲线。

### 4. 资源与算力

- **Atari 100k实验**：每游戏5个随机种子，每运行约12GB VRAM，单张NVIDIA RTX 4090约2.9天，总计约1.03 GPU年（130 runs × 2.9天 ≈ 377天 ≈ 1.03年）。
- **CS:GO实验**：381M参数模型（含上采样器）在RTX 4090上训练12天。
- **视觉质量对比实验**：在最多4×A6000 GPU上训练1-2天。
- 算力描述明确，可复现。

### 5. 实验数量与充分性

- **充分性**：Atari 100k全部26个游戏，每游戏5个种子，共130次独立运行，统计严谨（遵循Agarwal et al. 2021建议：提供置信区间、IQM、性能曲线）。
- **消融实验**：DDPM vs EDM（定性+定量像素漂移）；1步 vs 3步去噪（10个高表现游戏单种子比较）；视觉质量比较（在CS:GO和驾驶场景下用FVD等指标，对比IRIS、DreamerV3）。
- **客观公平**：对比方法均使用公开发布的实现或作者提供的基线，超参数公开。作者也指出DIAMOND比IRIS参数更少、训练更快，并非靠更大计算量取胜。
- 实验设计全面，结论可靠。

### 6. 主要结论与发现

- DIAMOND在Atari 100k上取得世界模型中最佳平均HNS 1.46，超越人类11个游戏，且IQM与STORM持平。
- 相比IRIS等离散token方法，DIAMOND生成的想象轨迹视觉一致性更好（无物体ID混淆、奖励/敌人交换错误），这种细节提升直接带来性能提升（如Asterix, Breakout, RoadRunner）。
- EDM比DDPM更适合世界模型：在低去噪步数下更稳定，单步生成即可避免复合误差。
- 扩散世界模型可扩展至3D环境（CS:GO），作为可交互的神经游戏引擎，但受限于记忆和罕见行为。

### 7. 优点

- **方法论创新**：首次将扩散模型成功用于在线想象训练RL智能体，并系统分析了设计选择（EDM vs DDPM, 去噪步数、条件化机制）。
- **效率优势**：仅需3 NFE每帧，比IRIS（16 NFE）更快，参数更少（13M vs 30M），训练时间更短。
- **视觉质量高**：直接像素空间建模避免了离散化的信息损失，生成帧一致性更好，有利于RL学习。
- **可玩性与扩展性**：在CS:GO上展示了可作为独立交互式游戏引擎，支持用户键盘鼠标操作。
- **开源与可复现**：提供完整代码、模型权重、视频和可玩世界模型。

### 8. 不足与局限

- **环境范围有限**：主要验证于离散控制环境（Atari），连续控制域未探索。
- **记忆机制简单**：使用帧堆叠（L=4）作为记忆，无法捕获长程依赖；作者指出可集成Transformer（如DiT）改进。
- **奖励/终止模型独立**：未整合到扩散模型中，增加计算复杂度和训练难度。
- **采样速度限制**：尽管比IRIS快，但比DreamerV3慢（266.7 Hz vs 7.4 Hz），可能影响更大规模训练。
- **CS:GO实验局限**：仅静态数据训练，无在线交互学习；模型对罕见区域和动作（如连跳）出现幻觉和漂移，缺乏定量评估（如FVD等）。
- **特定游戏表现不佳**：在BankHeist、Hero等游戏中性能低于STORM和DreamerV3，可能由于扩散模型多模态建模困难或奖励预测不准确。

（完）
