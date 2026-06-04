---
title: "Boosting Virtual Agent Learning and Reasoning: A Step-Wise, Multi-Dimensional, and Generalist Reward Model with Benchmark"
title_zh: 提升虚拟智能体学习与推理：逐步骤多维通用奖励模型与基准
authors: "Bingchen Miao, Yang Wu, Minghe Gao, Qifan Yu, Wendong Bu, Wenqiao Zhang, Yunfei Li, Siliang Tang, Tat-Seng Chua, Juncheng Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=OKWlVPHeW1"
tags: ["query:player-ai"]
score: 7.0
evidence: 针对虚拟智能体的逐步骤多维通用奖励模型
tldr: 本文提出Similar，一个逐步骤多维通用奖励模型，用于提升虚拟智能体（GVA）的学习与推理。该模型系统定义五个评估维度，并设计MCTS-P算法自动收集和标注逐步骤数据，提供细粒度训练信号。在多个基准上，Similar显著提高了GVA的任务完成率和泛化能力。该方法可迁移至游戏AI的智能体训练与评估。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 804, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1729, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 627, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 889, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1603, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 179, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 179, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 178, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 186, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 577, \"height\": 343, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 889, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 884, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 898, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 886, \"height\": 759, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 793, \"height\": 753, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 840, \"height\": 377, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1312, \"height\": 1517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1598, \"height\": 2176, \"label\": \"Table\"}]"
motivation: 当前虚拟智能体训练依赖结果监督和人工标注，效率低。
method: 提出Similar，定义五个维度并通过MCTS-P自动标注逐步骤数据。
result: 在多个基准上提升虚拟智能体任务完成率和泛化能力。
conclusion: Similar提供了高效虚拟智能体训练信号。
---

## Abstract
The development of Generalist Virtual Agents (GVAs) has shown significant promise in autonomous task execution. However, current training paradigms face critical limitations, including reliance on outcome supervision and labor-intensive human annotations. To address these challenges, we propose **Similar**, a **s**tep-w**i**se **m**ult**i**-dimensiona**l** gener**a**list **r**eward model, which offers fine-grained signals for agent training and can choose better actions for inference-time scaling. Specifically, we begin by systematically defining five dimensions for evaluating agent actions. Building on this framework, we design an MCTS-P algorithm to automatically collect and annotate step-wise, five-dimensional agent execution data. Using this data, we train **Similar** with our crafted Triple-M strategy. Furthermore, we introduce the first benchmark in the virtual agent domain for step-wise, multi-dimensional reward model training and evaluation, named ***SRM***. This benchmark consists of two components: ***SRMTrain***, which serves as the training set for **Similar**, and ***SRMEval***, a manually selected test set for evaluating the reward model. Experimental results demonstrate that **Similar**, through its step-wise, multi-dimensional assessment and synergistic gain, provides GVAs with effective intermediate signals during both training and inference-time scaling. The code is available at [https://github.com/antgroup/Similar](https://github.com/antgroup/Similar).

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：当前通用虚拟智能体（Generalist Virtual Agents, GVAs）的训练主要依赖结果监督（outcome-based rewards）和大量人工标注的轨迹数据。这种范式存在三大局限：
  1. **缺乏细粒度的过程监督**：只关注最终任务是否成功，无法识别中间步骤的错误，导致学习效率低下。
  2. **依赖人工标注**：逐步骤的细粒度奖励信号需要领域专家手动标注，成本高、可扩展性差。
  3. **推理时难以扩展**：基于结果的训练无法有效支持通过搜索选择最佳动作的推理时缩放（inference-time scaling）。
- **本文目标**：提出一种**逐步骤、多维度的通用奖励模型**，能够自动提供细粒度的过程监督信号，同时支持训练与推理时的智能体优化，并建立首个针对虚拟智能体奖励模型的评估基准。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 整体框架
- 提出 **Similar**（step-wise multi-dimensional generalist reward model），包括三大组件：
  1. **五维过程监督框架**：系统定义了五个关键维度来评估智能体每一步动作的质量。
  2. **MCTS-P算法**：自动收集并标注跨平台的逐步骤数据。
  3. **Triple-M训练策略**：整合多步、多目标、多模态数据训练奖励模型，并实现五维协同增益。

### 关键维度定义（图3示例）
| 维度 | 含义 | 计算方式 |
|------|------|----------|
| Helpfulness (H) | 动作对任务完成的贡献（正或负） | 基于轨迹长度和模拟结果，使用递归公式 \(H_i = 1 - \frac{AC_{i-1}}{M-i+1}(2r_i - 1)\) |
| Odds of Success (OS) | 该步骤导致成功完成的概率 | 模拟N条后续轨迹，计算成功路径比例 \(OS_i = \frac{\sum I(a_{i,j}=a^*)}{N}\) |
| Efficiency (E) | 步骤的效率提升，即减少剩余步数的程度 | \(E_i = \frac{Len_{i-1} - Len_i}{len_0}\) |
| Task Relevance (TR) | 动作是否与任务指令相关（0/1） | 使用MLLM（GPT-4o）评估 |
| Coherence (C) | 动作与前一步的逻辑连贯性（0/1） | 使用MLLM评估 |

### MCTS-P自动数据收集算法
- 基于传统MCTS改进，使用五维得分的加权和作为节点选择与反向传播的值函数。
- 在Web、Android、Linux、Windows四个平台的基准环境（WebArena、VisualWebArena、AndroidWorld、OSWorld）中执行任务，生成轨迹树。
- 每个节点存储动作、访问次数、值，通过模拟N条路径计算五维分数，并利用MLLM评估TR和C。
- 最终保留完整分支，剔除未到达最终答案的路径，构建110k个偏好对数据集（SRMTrain 78k, SRMEval 32k）。

### Triple-M训练策略（图2）
- **第一阶段**：基于预训练decoder-only MLLM（如Llama-3.2-11B-Vision或Qwen2-VL-7B），添加线性回归层（\(W \in \mathbb{R}^{d \times 5}\)）预测五维分数，优化回归损失 \(L_{RG} = \|W^\top h - r\|_2^2\)。
- **第二阶段**：冻结backbone和回归层，训练一个浅层MLP门控网络\(g_\phi\)，根据输入prompt动态调整五维权重的非负系数，并使用Bradley-Terry损失\(L_{BT}\)训练。最终综合得分 \(R = g_\phi(f_\theta(x))^\top r\)。

## 3. 实验设计

### 使用的数据集/场景与基准
- **SRMEval**：首个虚拟智能体领域逐步骤多维奖励模型评估基准，包含32k手工标注的测试数据，涵盖五个单维度、总维度（Tot）和轨迹级维度（Traj），评估指标为**动作选择的准确率**。
- 训练数据：**SRMTrain**（78k自动标注数据）。
- 模拟环境：WebArena、VisualWebArena、AndroidWorld、OSWorld四个跨平台环境。
- 在训练阶段（DPO）和推理阶段（MCTS）评估智能体的任务成功率（SR）。

### 对比方法
- **基线MLLM直接作为奖励模型**：GPT-4-Turbo、GPT-4o、InternVL-2.5-8B、Qwen2-VL-7B-Instruct、Llama-3.2-11B-Vision-Instruct，通过prompt直接打分。
- **Similar-RL变体**：使用Qwen或Llama backbone，通过强化学习在SRMTrain上训练，输出五维分数（不包含门控）。
- **Similar-TM变体**：使用Triple-M策略完整训练，含门控网络。
- 训练阶段智能体：UGround、OS-Atlas（开源），以及GPT-4o、GPT-4-Turbo（闭源）；推理阶段智能体：OS-Atlas、GPT-4o、GPT-4-Turbo。
- 所有评估使用各基准预留的30%数据，确保无数据泄露。

## 4. 资源与算力

- 论文中**未明确说明**训练Similar所使用的GPU型号、数量或训练时长。
- 提及使用GPT-4o-1120进行数据标注和MLLM评估，但未给出具体的API调用成本或算力消耗。
- 实验在多个基准上重复，但未报告单次实验的硬件需求。

## 5. 实验数量与充分性

- **实验数量**：论文共包含8个正式表格和多个图示，主要实验组包括：
  1. **SRMEval偏好对齐测试**（表1）：6个MLLM基线 + 2个Similar-RL + 2个Similar-TM，共10组。
  2. **训练阶段DPO提升**（表2）：在AndroidWorld和WebArena上，对比UGround/OS-Atlas使用不同奖励模型，共约20组。
  3. **推理阶段MCTS提升**（表3）：在AndroidWorld和OSWorld上，对比GPT-4-Turbo/GPT-4o/OS-Atlas使用不同奖励模型，共约30组。
  4. **消融实验**（表4）：在AndroidWorld和WebArena上，移除单个或组合维度，共约25组。
  5. **推理时间缩放实验**（图6a）：改变MCTS子节点数N，对比多个设置。
  6. **相关性分析**（图6b）：五维间的Pearson相关系数。
  7. **人类评估**（附录表5）：随机抽样各维度样本，验证标注质量。
  8. **附录消融扩展**（表6）：更多维度组合，共约30组。
- **充分性**：实验覆盖了训练、推理、不同智能体、不同平台、维度消融、时间缩放等，较为全面。但推理时缩放仅测试N≤8，未探索更大规模（如N=16, 32）；仅在一个种子下运行，未报告多次重复的标准差。

## 6. 论文的主要结论与发现

1. **自动收集的逐步骤多维数据有效**：使用SRMTrain训练的Similar-RL-Llama在SRMEval上平均准确率53.9%，比基线Llama-3.2-11B-Vision（47.6%）提升13.2%，甚至超越GPT-4o（51.4%），证明自动标注数据提供细粒度评估能力。
2. **Triple-M策略带来协同增益**：Similar-TM-Llama平均准确率61.2%，比Similar-RL-Llama（53.9%）再提升13.5%，在所有维度上均有显著改善（如H维度从48.2提升至63.8，涨幅32.3%）。
3. **有效指导训练**：在DPO训练中，使用Similar-TM-Llama作为奖励模型的OS-Atlas，在AndroidWorld上成功率从30.4%提升至34.9%，在WebArena上从20.2%提升至35.6%（+76%）。
4. **有效指导推理时缩放**：在MCTS推理中，使用Similar-TM-Llama的GPT-4o在AndroidWorld上成功率从25.4%提升至34.6%，在OSWorld上从10.8%提升至16.5%。
5. **维度重要性排序**：消融实验显示，Helpfulness维度影响最大，其次为Odds of Success、Efficiency、Task Relevance、Coherence，且五维间相关性较低（Pearson系数均<0.47），表明维度独立。

## 7. 优点：方法或实验设计上的亮点

- **自动化数据标注**：通过MCTS-P算法自动生成五维分数，极大减少人工标注成本，可扩展至多种平台。
- **多维细粒度评估**：首次在虚拟智能体领域定义五个互补且独立的维度，提供全面的过程监督。
- **统一的跨平台基准**：SRMEval涵盖Web、Android、Linux、Windows，支持公平比较不同奖励模型。
- **训练与推理双阶段有效**：Similar既能作为DPO训练的奖励信号，也能集成MCTS用于推理时决策。
- **协同增益设计**：Triple-M策略的门控网络能根据任务动态调整维度权重，优于简单平均。
- **消融研究全面**：系统性地分析了单个维度及组合的影响，验证了五维设计的必要性。

## 8. 不足与局限

- **自动标注的潜在偏差**：MCTS-P依赖MLLM（GPT-4o）评估TR和C，可能引入语言模型自身的偏见；五维分数基于模拟路径，复杂任务中模拟可能不准确。
- **环境覆盖有限**：仅测试了四个平台，未涉及更动态的接口（如滚动内容、弹窗、手势交互）或移动端真实设备。
- **推理时缩放探索不深**：仅在N≤8范围内实验，未测试更高分支数（如N=16, 32），且未报告多次运行的标准差，可能不够稳健。
- **计算资源未报告**：缺乏训练和推理的GPU型号、时长、能耗等详细信息，影响可复现性。
- **门控网络可能过拟合**：仅使用30k SRMEval测试集，未在更大规模或分布外任务上验证泛化性。
- **人类评估样本量较小**：附录表5中，各维度抽样6000/2000/1000不等，可能不足以代表整体数据分布。
- **未与更强的过程奖励模型对比**：如ReST-MCTS*、Math-Shepherd等，仅在MLLM和简单RL变体上对比。

（完）
