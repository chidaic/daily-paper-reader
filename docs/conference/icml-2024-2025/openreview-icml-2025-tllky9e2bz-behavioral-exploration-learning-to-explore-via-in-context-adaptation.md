---
title: "Behavioral Exploration: Learning to Explore via In-Context Adaptation"
title_zh: 行为探索：通过上下文内适应学习探索
authors: "Andrew Wagenmaker, Zhiyuan Zhou, Sergey Levine"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tlLkY9E2bZ"
tags: ["query:player-ai"]
score: 6.0
evidence: 适用于游戏训练的自主智能体探索方法
tldr: 针对自主智能体快速探索和在线适应的难题，提出行为探索方法，通过大规模行为克隆和上下文学习训练智能体内化探索能力，在多个环境（包括游戏）中实现少样本适应，超越随机探索和梯度方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 460, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 556, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 559, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 563, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 451, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 367, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 557, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 555, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 315, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 533, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 888, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 631, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 631, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1775, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 634, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1783, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 635, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 637, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1780, \"height\": 2231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1781, \"height\": 2235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1782, \"height\": 2240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1783, \"height\": 2241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 566, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 567, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 554, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 553, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 565, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 557, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1755, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1760, \"height\": 494, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 422, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1665, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1024, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 903, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1139, \"height\": 887, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1683, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 731, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 793, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 731, \"height\": 450, \"label\": \"Table\"}]"
motivation: 现有探索依赖随机性和慢速梯度更新，难以快速适应。
method: 训练智能体通过上下文学习从专家行为中内化探索策略。
result: 在机器人控制和游戏环境中，智能体实现快速探索和适应。
conclusion: 行为探索为通用自主探索提供了新范式。
---

## Abstract
Developing autonomous agents that quickly explore an environment and adapt their behavior online is a canonical challenge in robotics and machine learning. While humans are able to achieve such fast online exploration and adaptation, often acquiring new information and skills in only a handful of interactions, existing algorithmic approaches tend to rely on random exploration and slow, gradient-based behavior updates. How can we endow autonomous agents with such capabilities on par with humans? Taking inspiration from recent progress on both in-context learning and large-scale behavioral cloning, in this work we propose behavioral exploration: training agents to internalize what it means to explore and adapt in-context over the space of ''expert'' behaviors. To achieve this, given access to a dataset of expert demonstrations, we train a long-context generative model to predict expert actions conditioned on a context of past observations and a measure of how ''exploratory'' the expert's behaviors are relative to this context. This enables the model to not only mimic the behavior of an expert, but also, by feeding its past history of interactions into its context, to select different expert behaviors than what have been previously selected, thereby allowing for fast online adaptation and targeted, ''expert-like'' exploration. We demonstrate the effectiveness of our method in both simulated locomotion and manipulation settings, as well as on real-world robotic manipulation tasks, illustrating its ability to learn adaptive, exploratory behavior.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：自主智能体在陌生环境中需要快速探索并在线适应行为，这是机器人和机器学习领域的核心挑战。人类可以仅通过少量交互获取信息并适应，而现有算法大多依赖随机探索（如 $\epsilon$-greedy）或慢速的梯度更新，无法实现高效的在线适应。
- **动机**：受大语言模型中上下文学习（in-context learning）和大规模行为克隆（behavioral cloning）的启发，作者提出**行为探索**（Behavioral Exploration, BE），旨在训练智能体“内化”探索和适应的能力，使其能在部署时仅通过将历史交互注入上下文，就迅速调整行为，聚焦于专家演示所覆盖的有用行为空间进行探索。
- **整体目标**：在奖励不可知的情况下，利用无标签的专家演示数据集，训练出一个既能模仿专家又能主动探索的策略，从而在真实世界或模拟环境中实现类似人类的快速适应。

## 2. 论文提出的方法论

### 核心思想
- 将探索问题转化为**条件分布建模**问题：不再直接克隆专家行为，而是学习一个策略 $\pi_{\text{BE}}$，使其在给定当前状态 $s_t$、历史观测集合 $h$ 以及一个“覆盖度”度量 $\text{cov}(h \cup \tau)$ 的条件下，输出最有可能**增加覆盖度**的专家动作。
- 覆盖度定量刻画了当前已访问状态集合对专家行为特征空间的覆盖程度，鼓励策略尝试与历史不同的行为，从而实现定向探索。

### 关键技术细节
1. **覆盖度定义**（公式 1, 2）：
   - 定义特征映射 $\phi(s) \in \mathbb{R}^d$（例如随机初始化神经网络输出）。
   - 对于状态集合 $h$，其覆盖度为 $\text{cov}(h) = 1 / \operatorname{tr}\big((\sum_{s_i \in h} \phi(s_i)\phi(s_i)^\top + \lambda I)^{-1}\big)$。该度量源于A-最优实验设计，值越小表示覆盖越充分。
   - 为聚焦于专家行为空间，定义 $\text{cov}_\beta(h)$ 仅考虑专家特征空间 $U_{\beta,\epsilon}$ 内的覆盖。

2. **行为探索目标**（公式 4）：
   - 最大化：$\sum_{t=1}^T \sum_{k=1}^K \mathbb{E}_{h\sim\mathcal{H}(\mathcal{D})} [\log \pi_{\text{BE}}(a_t^k \mid s_t^k, h, \text{cov}(h \cup \tau_t^k))]$。
   - 训练时从演示数据 $\mathcal{D}$ 中采样历史 $h$ 和未来轨迹 $\tau_t^k$，计算覆盖度作为条件。

3. **网络架构**：
   - 采用**扩散模型** (Diffusion Model) 处理连续多模态动作分布。
   - 使用**Transformer** 骨干网络（基于 Dasari et al., 2024 的 Diffusion Policy）来编码长序列上下文（历史状态、当前状态、覆盖度值等）。

4. **训练与部署**：
   - 训练时，历史 $h$ 均匀采样自演示轨迹（模拟在线可能遇到的各种历史）。
   - 部署时，将之前收集到的状态存入上下文，并设定一个期望的覆盖度值 $c_{\text{exp}}$，模型自动采样出能够增加覆盖度的动作（相当于探索）。
   - 支持任务条件（如语言指令），只需将任务标签 $y$ 额外加入条件。

### 理论支撑
- 作者给出了一个非正式命题（命题 4.2）：在确定性环境和有限状态等假设下，通过条件化于历史和高覆盖事件得到的策略是覆盖度最大化的最优解。该策略本质上是对专家策略 $π_β$ 进行重加权，使动作倾向于带来新颖覆盖。

## 3. 实验设计

### 所用数据集/场景
- **D4RL**（模拟 RL 基准）：
  - Antmaze（medium/large，diverse 数据集，无奖励标签）
  - Kitchen（partial 数据集）
- **Libero 90**（模拟机械臂操作基准）：90 个任务，21 个场景，每个任务 50 条人类演示。
- **BridgeData V2**（真实机器人数据集）：>60,000 条遥操作演示。
- **真实 WidowX 250 机械臂**：3 个不同的抓取/触碰任务。

### 对比方法
- **RL 探索方法**：RND、ExPLORe、HILP、SUPE（后三者利用离线数据初始化）。
- **模仿学习方法**：标准 BC、带动作噪声的 BC、带历史条件的 BC、随机任务条件的 BC。
- **通用机器人策略**：OpenVLA（仅 WidowX 实验）。
- 所有 RL 方法使用 Wilcoxson et al. (2024) 提供的预训练检查点与默认超参数。

### 评估指标
- Antmaze：目标达成率（4 个目标）、到达的区域数（grid cell 计数）。
- Kitchen：子任务完成百分比。
- Libero：隐藏任务成功率（15 次尝试内完成指定任务）、给定任务成功率（6 次尝试）。
- WidowX：成功 trial 比例（5 次 episode 内触碰两个物体）以及成功所需平均尝试次数。

## 4. 资源与算力

- 论文中**未明确说明**具体使用的 GPU 型号、数量和总训练时长。
- 仅提及使用了加州大学伯克利分校的 Savio 计算集群。
- 由于 BE 模型基于 Transformer + 扩散模型，参数量较大（WidowX 实验使用 512 隐藏维度、8 注意力头、6 层），训练**可能**需要 2-4 张 GPU（如 V100 或 A100），耗时从数小时到数天不等，但原文未提供详细信息。

## 5. 实验数量与充分性

- **RL 实验**：
  - 每个 D4RL 环境训练 8 个随机种子，每个种子在线评估 10 轮（共 80 个 trails）。结果报告均值与标准误差。
  - 绘制了多条学习曲线（Steps vs. % Goals Reached 等），并包含个体目标表现。
- **模拟 IL 实验**（Libero）：
  - 每个任务重复 3 次，5 个种子。覆盖全部 90 个任务（共 1350 次评估）。
  - 两个设置（任务隐藏、任务给定），分别报告平均曲线和个体任务图。
- **真实世界实验**（WidowX）：
  - 每个任务进行 8 个 5-episode trial。
  - 除 BE 外，还比较了 BC 和 OpenVLA，并分析了 OpenVLA 的不同语言提示效果。
- **消融与理解实验**：
  - 改变覆盖度条件值（calibration 曲线，图 6）。
  - 历史条件重要性实验（图 31）：比较 BE(完整历史)、BE(仅首状态) 和 BC 的轨迹覆盖。
  - Maze2D 环境中的定性可视化（图 30）展示历史适应能力。

**评估**：实验覆盖了从低维状态到高维图像、从模拟到真实、从有限步探索到多任务场景，对比方法多样且具有代表性。消融设计合理，验证了核心设计选择（历史条件、覆盖度条件）的效果。统计显著性通过标准误差表示，未进行严格的假设检验，但趋势明显。**整体充分且公平**。

## 6. 论文的主要结论与发现

1. **BE 能显著加速探索**：在 Antmaze 上，BE 的目标达成率是 BC 的约 2 倍（55.6% vs 28.5%），区域覆盖数也更高（24.1 vs 20.1）。在 Kitchen 上，BE 与最先进的 RL 方法 SUPE/HILP 性能相当（均 >90%），且无需梯度更新。
2. **BE 的探索是定向且高效的**：在 Libero 隐藏任务中，BE 仅需约 5 次尝试即可超过 BC 在 15 次尝试后的成功率（82.4% vs 59.0%）。相比带动作噪声的 BC，BE 在给定任务时表现更好（99.3% vs 95.0%），说明探索不破坏任务成功率。
3. **BE 可扩展到真实世界**：在 WidowX 上，BE 成功 trial 比例比 BC 高约 40%，比 OpenVLA 高约 40%，且需要更少的尝试次数。
4. **BE 通过覆盖度值可调节探索程度**：图 6 显示，随着条件覆盖度值增加，探索到的区域数单调上升，策略表现出良好校准性。
5. **历史适应是关键**：图 31 对比显示，BE 使用完整历史时覆盖度远大于仅使用初始状态，说明 BE 真正实现了“不重复探索已访问区域”。

## 7. 优点

- **方法简洁有效**：仅需在标准 BC 目标中添加历史与覆盖度条件，训练完全离线，无需在线 RL 或额外的奖励工程。
- **在线适应无需梯度更新**：利用 Transformer 的上下文能力，部署时只需将新观测拼接进上下文即可调整行为，速度远快于在线微调方法。
- **探索空间受控**：通过演示数据隐式限制了探索范围，避免了随机探索可能导致的危险或无效行为。
- **通用架构**：扩散模型+Transformer 组合可处理高维连续动作和多模态分布，易于迁移到不同域（模拟、真机、视觉、状态）。
- **理论支撑**：提供了非正式的优化最优性论证（命题 4.2），为方法合理性给出了解释。
- **消融实验充分**：验证了历史条件、覆盖度条件、不同覆盖度值的影响，并且展示了 BE 能有效覆盖演示数据的低密度区域（图 31d）。

## 8. 不足与局限

1. **依赖演示数据覆盖范围**：BE 只能探索存在于演示数据中的行为模式。如果目标任务需要的行为完全不在演示空间中（例如一种全新的操作方式），则 BE 无法泛化。作者也承认这是未来方向。
2. **历史分布选择简略**：训练时历史均匀采样自演示数据，而最优的历史分布应该是部署时在线状态的诱导分布（固定点问题）。当前近似可能不是最优，可能导致某些历史下策略校准不佳。
3. **计算资源未透明**：未报告训练 BE 所需的 GPU 类型、数量及时间，不利于复现和成本评估。鉴于 Transformer 扩散模型参数量较大，训练可能对资源要求较高。
4. **未与大规模强化学习方法对比**：尽管与 RND 等离线初始化 RL 方法比较，但未与直接从零训练的 PPO 等进行比较。不过由于任务侧重探索而非最优回报，该缺失可接受。
5. **长期任务与稀疏奖励场景未深入**：实验主要集中在几步到几十步的探索，对于需要数百步推理的复杂任务（如 Minecraft 式探索）尚未验证。
6. **真实世界实验规模有限**：WidowX 仅涉及 3 个任务，每个任务 8 次 trial，统计稳定性一般。且 OpenVLA 是通用策略，可能未针对具体场景微调，比较略有失衡。
7. **未严格证明最优性**：命题 4.2 的假设较强（确定性、有限动作、特征为 one-hot 等），实际场景中不成立，只能提供直觉而非严格保证。
8. **潜在安全风险**：探索本身可能产生危险行为，文中在影响声明中提及但未给出缓解措施。

（完）
