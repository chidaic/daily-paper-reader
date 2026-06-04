---
title: Learning to Cooperate with Humans using Generative Agents
title_zh: 使用生成式Agent学习与人类协作
authors: "Yancheng Liang, Daphne Chen, Abhishek Gupta, Simon Shaolei Du, Natasha Jaques"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=v4dXL3LsGX"
tags: ["query:player-ai"]
score: 8.0
evidence: 学习人类伙伴的生成模型以提升协作
tldr: 针对AI Agent与人类零样本协作的难题，本文提出学习人类伙伴的生成模型。该方法通过潜在变量表示捕捉人类多样化策略，训练出能与真人高效协同的Cooperator agent。实验证明该模型显著优于传统行为克隆或种群训练方法，为人类-AI协作提供了新范式。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1339, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1021, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1405, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1410, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1415, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 528, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 712, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 687, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 685, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 688, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1330, \"height\": 558, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1395, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 658, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-v4dxl3lsgx/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 961, \"height\": 356, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-v4dxl3lsgx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1388, \"height\": 614, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-v4dxl3lsgx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 742, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-v4dxl3lsgx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1266, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-v4dxl3lsgx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1514, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-v4dxl3lsgx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1512, \"height\": 400, \"label\": \"Table\"}]"
motivation: 现有方法模拟的人类伙伴无法覆盖真实人类多样化策略，导致协作困难。
method: 学习人类伙伴的生成式模型，结合潜在变量表示捕捉多样化行为。
result: 训练的Cooperator agent能与真人实现零样本高效协作。
conclusion: 生成式伙伴建模有效提升人机协作效果。
---

## Abstract
Training agents that can coordinate zero-shot with humans is a key mission in multi-agent reinforcement learning (MARL). Current algorithms focus on training simulated human partner policies which are then used to train a Cooperator agent. The simulated human is produced either through behavior cloning over a dataset of human cooperation behavior, or by using MARL to create a population of simulated agents. However, these approaches often struggle to produce a Cooperator that can coordinate well with real humans, since the simulated humans fail to cover the diverse strategies and styles employed by people in the real world.  We show \emph{learning a generative model of human partners} can effectively address this issue. Our model learns a latent variable representation of the human that can be regarded as encoding the human's unique strategy, intention, experience, or style. This generative model can be flexibly trained from any (human or neural policy) agent interaction data. By sampling from the latent space, we can use the generative model to produce different partners to train Cooperator agents. We evaluate our method---Generative Agent Modeling for Multi-agent Adaptation (GAMMA)---on Overcooked, a challenging cooperative cooking game that has become a standard benchmark for zero-shot coordination. We conduct an evaluation with real human teammates, and the results show that GAMMA consistently improves performance, whether the generative model is trained on simulated populations or human datasets. Further, we propose a method for posterior sampling from the generative model that is biased towards the human data, enabling us to efficiently improve performance with only a small amount of expensive human interaction data.

---

## 论文详细总结（自动生成）

# GAMMA: 使用生成式Agent学习与人类协作——论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：在多人强化学习（MARL）中，训练能够与陌生人（人类）进行零样本协作（zero-shot coordination）的AI Agent是一项关键挑战。现有方法通常通过行为克隆（Behavior Cloning, BC）利用人类协作数据，或使用MARL创建模拟Agent种群（population）来训练协作Agent（Cooperator）。然而，这些方法生成的模拟伙伴无法覆盖真实人类策略的多样性（不同风格、意图、技能等），导致与真实人类协作时因分布偏移而表现不佳。
- **整体意义**：本文旨在通过**学习人类伙伴的生成模型**来解决分布偏移问题，从而训练出能与真实人类高效协作的AI Agent。这项工作对实现人机协作（如辅助机器人、软件助手）具有重要价值。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用变分自编码器（VAE）从人类或模拟协作轨迹中学习一个生成模型，该模型通过一个**潜在变量 `z`** 编码伙伴的独特策略、意图、经验或风格。通过从潜在空间采样，可以生成多样化的伙伴策略，用于训练鲁棒的Cooperator Agent。进一步，提出**人类自适应（Human-Adaptive）采样**方法，利用少量真实人类数据将采样偏向人类策略区域，实现数据高效的目标。

- **关键技术细节**：
  - **学习生成模型**：采用VAE架构。编码器 `q(z|τ; φ)` 从完整轨迹 `τ` 推断潜在变量 `z`；解码器 `p(a_t | z, τ_{0:t-1}; θ)` 基于 `z` 和历史观测预测伙伴的动作。训练损失为证据下界（ELBO）：
    \[
    \mathcal{L}(\theta,\phi) = \mathbb{E}_{\tau\sim\mathcal{D}}\left[\mathbb{E}_{z\sim q(\cdot|\tau,\phi)}\left[\sum_{t=1}^T \log p(a_t|z,\tau_{0:t-1};\theta)\right] + \beta\,\text{KL}(q(z|\tau,\phi)\| \mathcal{N}(0,I))\right]
    \]
  - **训练Cooperator**：将生成模型作为伙伴生成器，每集从先验 `z∼p(z)` 采样，用解码器模拟伙伴行为。Cooperator（使用PPO优化）与这些生成伙伴交互，最大化期望累积奖励：
    \[
    J(\pi_C) = \mathbb{E}_{z\sim\mathcal{D}_z}[V_z(\pi)] = \mathbb{E}_{z\sim p(z)}[V(\pi,\mu_z)]
    \]
  - **人类自适应采样**：若有一小部分人类数据 `\mathcal{D}_h`，计算其编码后潜在向量的均值：
    \[
    \bar{z} = \mathbb{E}_{\tau_h\in\mathcal{D}_h}\left[\mathbb{E}_{z\in q(\cdot|\tau_h)}[z]\right]
    \]
    用 `\mathcal{N}(\bar{z}, I)` 作为新的采样分布 `p_h(z)`，替代标准正态先验，使采样更集中于人类策略区域。同时可对VAE进行微调（解码器仅微调DFT或全微调FFT）。

- **算法流程（文字说明）**：
  1. 准备数据集（模拟种群生成的轨迹或人类真实协作轨迹）。
  2. 训练VAE生成模型（编码器+解码器）。
  3. 如果存在人类数据，计算人类自适应分布 `p_h(z)` 并对VAE进行微调。
  4. Cooperator训练循环：每批从 `p(z)` 或 `p_h(z)` 采样一批潜在变量 `z_i`，通过解码器生成对应的伙伴策略 `μ_{z_i}`；Cooperator（PPO）与这些伙伴在环境中交互，更新策略。
  5. 评估：在真实人类或人类代理（BC）上进行零样本协作测试。

## 3. 实验设计：数据集/场景、基准、对比方法

- **环境与场景**：使用**Overcooked**合作烹饪游戏，包含6个布局（layout）：
  - 原有5个：Cramped Room, Asymmetric Advantages, Coordination Ring, Forced Coordination, Counter Circuit。
  - 新增1个：**Multi-strategy Counter**（需要选择洋葱或番茄汤，增加策略复杂度）。
- **基准方法与对比**：
  - **模拟种群方法**：Fictitious Co-Play (FCP), Maximum Entropy Population (MEP), Cross-play Optimized, Mixed-play Enforced Diversity (CoMeDi)。这些方法各自生成模拟Agent种群。
  - **人类数据方法**：PPO+BC（用人类数据行为克隆作为伙伴训练Cooperator）。
  - **本文方法GAMMA变体**：
    - 在模拟种群基础上训练GAMMA：FCP+GAMMA, CoMeDi+GAMMA, MEP+GAMMA。
    - 在人类数据基础上训练GAMMA：PPO+BC+GAMMA。
    - 人类自适应采样GAMMA HA（结合模拟种群和人类数据，分别进行解码器微调DFT或全微调FFT）。
- **评估方式**：
  - **模拟评估**：使用held-out人类数据训练的BC模型作为人类代理，测试Cooperator与其协作的奖励。
  - **真实人类评估**：通过Prolific招募80名用户，每人与9种不同Agent（5种子策略随机抽样）在Counter Circuit和Multi-strategy Counter上各进行60秒游戏，收集合作得分、Likert量表评分（协调能力、适应性、类人性、挫败感等）和定性反馈。使用Holm-Bonferroni校正进行统计显著性检验。

## 4. 资源与算力

- 论文明确报告了计算资源：
  - **硬件**：集群使用AMD EPYC 64-Core Processor CPU和NVIDIA A40/L40 GPU。
  - **训练时间**：训练一个Cooperator约需1天。
  - **总计算量**：主实验约消耗3600 GPU小时。

## 5. 实验数量与充分性

- **实验数量**：
  - 模拟评估：6个布局 × 6种方法（FCP, FCP+GAMMA, CoMeDi, CoMeDi+GAMMA, MEP, MEP+GAMMA），以及人类数据方法（PPO+BC, PPO+BC+GAMMA, GAMMA HA DFT/FFT）在2个布局上的学习曲线。
  - 真实人类评估：2个布局 × 9种Agent策略（FCP, FCP+GAMMA, CoMeDi, CoMeDi+GAMMA, MEP, MEP+GAMMA, PPO+BC, PPO+BC+GAMMA, GAMMA HA DFT），每策略至少5个随机种子，80名用户每人8轮（顺序随机）。
  - 消融实验：比较DFT与FFT微调效果，以及z条件Cooperator的初步实验（附录）。
- **充分性评价**：
  - **优势**：覆盖多种主流基线，在多个布局上验证，包括新增复杂布局；进行了真实人类主观和客观评估，并报告统计显著性；消融实验探究了关键设计选择（微调方式、自适应采样）。
  - **不足**：真实人类评估仅集中在两个最复杂布局上，未在简单布局上进行；参与者来源于Prolific，可能引入样本偏差；人类数据量有限（35-38条轨迹），虽符合常见情况但代表性可能不足。总体而言，实验设计较为充分且公平，但外部有效性仍有提升空间。

## 6. 主要结论与发现

- **核心结果**：无论使用模拟种群数据还是人类数据，GAMMA均一致提升了Cooperator与真实人类的协作性能。**GAMMA HA（人类自适应采样+解码器微调）在所有方法中达到最佳**：
  - 在Counter Circuit上比最强基线MEP提升约60%（81.10 vs 91.11）；在Multi-strategy Counter上比PPO+BC提升约43%（85.26 vs 93.09）。
  - 进一步统计检验表明多数改进显著（p<0.05）。
- **主观评分**：GAMMA方法在协调能力、适应性、类人性、低挫败感等维度均获得更积极的评价。用户反馈表明GAMMA Agent更“有目的”、“逻辑一致”，而基线Agent常被描述为“不一致”、“阻碍”或“随机行为”。
- **模拟评估**：GAMMA在多个布局上均优于未使用生成模型的种群方法，且改进幅度随布局复杂度增加而增大。
- **人类数据利用**：GAMMA HA在少量人类数据下即能显著提升性能，而PPO+BC在真实人类评估中仅能在较简单布局上表现良好，在复杂布局上弱于GAMMA HA。

## 7. 优点

- **方法创新性强**：首次将生成模型（VAE）引入人类伙伴策略建模，利用潜在空间的插值能力生成无限多样且连续的伙伴策略，克服了离散种群覆盖不足的问题。
- **数据融合灵活**：能有效结合大规模模拟数据和小规模人类数据，通过人类自适应采样实现数据高效的目标协作。
- **实验设计全面且严谨**：同时进行模拟评估和真实人类评估，收集客观得分和主观评分，并进行统计显著性检验，结论可信度高。
- **定性分析深入**：通过用户反馈揭示了GAMMA Agent在适应性和一致性方面的优势，为性能提升提供了解释。
- **提供了新的基准**：新增的Multi-strategy Counter布局增加了策略复杂度，更适合评估高级协作方法。

## 8. 不足与局限

- **对数据质量敏感**：“垃圾进，垃圾出”。当基础种群数据质量低时（如CoMeDi在Multi-strategy Counter上无法学习番茄汤策略），GAMMA也受到限制，性能提升有限。
- **人类数据代表性有限**：真实人类评估参与者来自Prolific，可能主要是年轻、熟悉游戏的群体，且人类数据集仅35-38条轨迹，可能无法覆盖所有真实人类行为模式。
- **可扩展性挑战**：当前方法仅针对两人场景。扩展到更多Agent将导致数据集大小和训练复杂度指数增长，需要更高效的采样技术。
- **z条件Cooperator不稳定**：附录中尝试直接基于z条件训练Cooperator，但性能不稳定，容易过拟合，未作为主要方法。
- **未在简单布局上进行真实人类评估**：虽然模拟评估覆盖6个布局，但真实人类评估仅集中在两个复杂布局上，简单布局中的泛化能力未验证。
- **计算开销**：训练VAE和Cooperator需要约3600 GPU小时，对于资源有限的研究者可能门槛较高。

（完）
