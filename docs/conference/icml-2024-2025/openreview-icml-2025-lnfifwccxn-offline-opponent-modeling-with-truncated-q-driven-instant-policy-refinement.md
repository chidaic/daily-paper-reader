---
title: Offline Opponent Modeling with Truncated Q-driven Instant Policy Refinement
title_zh: 基于截断Q驱动即时策略精炼的离线对手建模
authors: "Yuheng Jing, Kai Li, Bingyun Liu, Ziwen Zhang, Haobo Fu, QIANG FU, Junliang Xing, Jian Cheng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=LNfiFWccxn"
tags: ["query:player-ai"]
score: 8.0
evidence: 离线对手建模用于玩家行为模拟
tldr: 针对离线对手建模中数据集次优导致算法失效的问题，提出截断Q驱动即时策略精炼（TIPR）框架，通过学习地平线截断的上下文动作价值函数，提升对次优数据的鲁棒性，实验表明TIPR有效恢复离线对手建模性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lnfifwccxn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 839, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnfifwccxn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1783, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnfifwccxn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1761, \"height\": 1075, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnfifwccxn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1762, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnfifwccxn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1749, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnfifwccxn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1761, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnfifwccxn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1094, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnfifwccxn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1740, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnfifwccxn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1695, \"height\": 1518, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lnfifwccxn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 891, \"height\": 566, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lnfifwccxn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1268, \"height\": 1474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lnfifwccxn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1512, \"height\": 1318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lnfifwccxn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1623, \"height\": 1021, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lnfifwccxn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1619, \"height\": 891, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lnfifwccxn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1551, \"height\": 508, \"label\": \"Table\"}]"
motivation: 离线对手建模假设数据集最优，实际中难以满足，导致性能下降。
method: 提出TIPR框架，包含截断动作价值函数学习和即时策略更新。
result: 在多个多智能体游戏环境中，TIPR显著提升了次优数据下的对手建模效果。
conclusion: TIPR为离线对手建模提供通用改进，推动实际应用中的自适应智能体。
---

## Abstract
Offline Opponent Modeling (OOM) aims to learn an adaptive autonomous agent policy that dynamically adapts to opponents using an offline dataset from multi-agent games. Previous work assumes that the dataset is optimal. However, this assumption is difficult to satisfy in the real world. When the dataset is suboptimal, existing approaches struggle to work. To tackle this issue, we propose a simple and general algorithmic improvement framework, Truncated Q-driven Instant Policy Refinement (TIPR), to handle the suboptimality of OOM algorithms induced by datasets. The TIPR framework is plug-and-play in nature. Compared to original OOM algorithms, it requires only two extra steps: (1) Learn a horizon-truncated in-context action-value function, namely Truncated Q, using the offline dataset. The Truncated Q estimates the expected return within a fixed, truncated horizon and is conditioned on opponent information. (2) Use the learned Truncated Q to instantly decide whether to perform policy refinement and to generate policy after refinement during testing. Theoretically, we analyze the rationale of Truncated Q from the perspective of No Maximization Bias probability. Empirically, we conduct extensive comparison and ablation experiments in four representative competitive environments. TIPR effectively improves various OOM algorithms pretrained with suboptimal datasets.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：离线对手建模（Offline Opponent Modeling, OOM）旨在利用多智能体游戏的离线数据集，学习一个能动态适应未知对手的自适应智能体策略。然而，现有OOM方法均假设离线数据集是“最优的”——即数据集中每个对手策略对应的自我智能体策略是其最佳响应（Best Response）。在实际场景中，这一假设难以满足，数据集往往是“次优的”（suboptimal），即自我智能体策略可能任意差，导致OOM算法性能急剧下降。
- **整体含义**：本文旨在解决OOM在次优数据集下的性能退化问题，提出一种通用、即插即用的改进框架，使OOM算法能在实际不完美的数据条件下仍能有效工作，从而推动OOM在真实多智能体系统（如体育分析、策略博弈）中的部署。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
- 在离线数据集上额外学习一个**地平线截断的上下文动作价值函数**（Truncated Q），用于在测试阶段**即时判断是否需要对原始OOM策略进行精炼**（Instant Policy Refinement, IPR），从而在不过度依赖离线数据分布的前提下提升策略质量。
- 该方法与离线保守学习（Offline Conservative Learning, OCL）不同：OCL在训练时通过保守约束改进策略，而TIPR在测试时根据当前对手的上下文动态决策，避免分布偏移带来的负面影响。

### 关键技术细节

#### (1) Truncated Q 训练
- **动机**：原始Q函数（Original Q）需要估计全地平线期望回报，在多智能体环境中由于对手的存在和维度爆炸，拟合误差极大（如图1所示）。截断地平线（H步）可大幅降低学习难度。
- **定义**：Truncated Q 包含两个预测头：置信度头 $`\tilde{Q}^h_C`$ 和 价值头 $`\tilde{Q}^h_V`$，分别预测未来第h步获得非零奖励的概率（置信度）和奖励值（价值）。
- **损失函数**：
  - 置信度损失 $`\mathcal{L}_{QC}`$：使用二分类交叉熵，标签为未来H步内每一步奖励是否非零。
  - 价值损失 $`\mathcal{L}_{QV}`$：使用均方误差，预测未来H步的奖励值。
  - 总体目标：$`\min_\omega \mathbb{E}[\alpha \mathcal{L}_{QC} + \beta \mathcal{L}_{QV}]`$。
- **网络架构**：基于因果Transformer（GPT-2）的编码器-解码器结构。编码器将对手的上下文数据（$`D`$，包含最近C条轨迹的 $`(o^{-1}, a^{-1})`$ 元组）编码为潜在表征；解码器以自智能体观测、对手动作、自智能体动作为输入，通过交叉注意力与编码器交互，自回归输出每个时间步的置信度和价值预测。
- **附加模块**：学习一个对手模仿器（$`\pi^{OI}`$），用于在测试时估计对手动作。

#### (2) 即时策略精炼（IPR）
- **测试阶段流程（算法1）**：
  1. 在每个时间步t，从最近C条对手轨迹中采样上下文数据 $`D_t`$。
  2. 用对手模仿器估计对手动作 $`a^{-1}_t$。
  3. 计算**精炼条件（Refinement Condition, RC）**：$`f_{RC}(o^1_t, a^{-1}_t, D_t) = \sum_{\hat{a}^1 \in A^1} \mathbf{1}\{ \tilde{Q}^\Sigma_C(o^1_t, \hat{a}^1, a^{-1}_t, D_t) > 0 \}`$，即统计有多少个自智能体动作对应的截断累积置信度大于0。
  4. **如果 $`f_{RC} > 0`$（RC满足）**：根据价值头输出生成精炼策略 $`\tilde{\pi}`$：$`\tilde{\pi}(o^1_t, a^{-1}_t, D_t) = \arg\max_{\hat{a}^1} \tilde{Q}^\Sigma_V(o^1_t, \hat{a}^1, a^{-1}_t, D_t)`$。
  5. **否则**：使用原始OOM策略 $`\bar{\pi}`$ 生成动作。
- **核心思想**：仅当Truncated Q对价值估计有足够信心（即置信度累积为正的动作存在）时才进行贪心精炼，否则保持原策略，实现“自信时进取，不确定时保守”的折中。

### 理论分析
- 论文证明了**无最大化偏差概率（No Maximization Bias Probability）** $`y(h) = P(\arg\max_{a^1} \tilde{Q}^h = \arg\max_{a^1} \mathbb{E}[G_T])`$ 的下界为 $`f(h)g(h)`$，其中 $`f(h)`$ 是经验风险无偏概率（随截断地平线h增加而下降），$`g(h)`$ 是天然无偏概率（随h增加而上升）。因此存在最优截断地平线 $`h^*`$ 最大化该下界，且 $`h^*`$ 通常不等于全地平线T，证明了截断Q的合理性。

## 3. 实验设计：使用数据集/场景、benchmark、对比方法

### 环境与场景
- **四个稀疏奖励的竞争性多智能体环境**：
  - `Markov Soccer (MS)`：双人零和，离散状态，网格足球。
  - `Level-Based Foraging (LBF)`：双人混合动机，离散状态，需合作觅食。
  - `Physical Deception (PD)`：三人（一个自智能体+两个对手），连续状态，自智能体需识别目标地标。
  - `Predator Prey (PP)`：四人（一个猎物自智能体+三个捕食者对手），连续状态，猎物需躲避围捕。
- **对手策略**：使用多样性驱动的种群训练算法（MEP）训练策略种群，从中选取12个作为训练集（Seen），8个作为测试集的未见策略（Unseen），以及两者混合（Mixed）。定量验证了对手策略的多样性（KL散度>1的比例超过80%）。

### 数据集构建（次优度控制）
- 定义**最优比率 $`\rho`$** = 数据集中自智能体策略表现 / 最佳响应策略表现。通过使用PPO训练不同步数获得不同次优度的自智能体策略，构建 $`\rho = 0.2, 0.4, 0.6, 0.8`$ 的四个子数据集。$`\rho`$ 越小越次优。

### 对比方法
- **OOM基线**（来自Jing et al., 2024a）：
  - `DRON-concat`、`DRON-MoE`（基于对手特征编码）
  - `LIAM`（变分自编码器对手建模）
  - `Prompt-DT`（基于决策Transformer的提示学习）
  - `TAO`（表现最优的OOM算法，基于表征学习和上下文学习）
- **自身消融变体**：
  - 不同Q函数（Original Q vs Truncated Q）
  - 不同使用方法（IPR vs OCL）
  - Truncated Q的消融：去掉置信度头（$`\tilde{Q}^h_C`$）、去掉上下文数据D
  - 不同截断地平线H（1,3,5,10）

### 测试协议
- 每20个 episode 对手从测试集（Seen/Unseen/Mixed）中随机切换一次策略（非平稳对手）。
- 每个条件使用5个随机种子，报告均值和标准差。

## 4. 资源与算力

- **文中未明确说明使用的GPU型号、数量、训练时长等具体算力信息**。仅提到训练OOM基线（3000步）和Truncated Q（10000步）的batch size、学习率等超参数（附录F）。可合理推测实验基于常见深度学习硬件（如单卡或少量GPU），但具体资源细节缺失。

## 5. 实验数量与充分性

### 实验数量
- **主实验**（图3）：5个OOM基线 × 4个环境 × 4种次优度（ρ）× 3种测试模式（Seen/Unseen/Mixed）= 240组条件，每组5个种子，共约1200个子实验。
- **消融研究**：
  - IPR vs OCL + Q变体（图4）：5种方法 × 4环境 × 4ρ = 80组。
  - 不同H（图5）：4种H × 4环境 × 4ρ = 64组。
  - 训练阶段改进（图6）：4种ρ × 4环境 × 3000步 = 大量点。
- **定量指标**（表1）：MSE和准确率在4环境 × 4ρ下报告。
- **附录**：还提供了多样性分析、超参数表等。

### 充分性评价
- **充分**：实验覆盖了不同环境（离散/连续、不同对手数量）、不同次优度、多种测试集（Seen/Unseen/Mixed）、多种基线，并进行了深入的消融分析（Q变体、截断地平线、训练阶段改进等）。统计显著性（标准差）报告充分。
- **客观公平**：所有方法使用相同的数据集和训练流程，超参数公开。但需注意：
  - 所有对比基线均来自同一作者前作（Jing et al., 2024a），可能存在设计偏向。
  - 测试对手策略来源相同（MEP种群），未包含完全异质的对手（如基于不同算法的策略）。
- **整体评价**：实验设计较为全面，但泛化性（如扩展到合作场景、更大规模环境）未验证。

## 6. 论文的主要结论与发现

1. **次优数据集导致OOM算法严重退化**：随着最优比率ρ降低，所有OOM基线性能急剧下降，尤其在高对手数量环境（PD、PP）中几乎失效。
2. **TIPR框架能有效恢复OOM性能**：无论数据集次优程度如何，TIPR在Seen、Unseen和Mixed测试模式下均一致性地提升所有OOM基线的平均回报（图3），提升幅度稳定。
3. **IPR优于离线保守学习（OCL）**：在测试阶段进行即时精炼比在训练阶段通过保守约束改进更有效，因为OCL难以应对测试时的分布偏移（图4）。
4. **Truncated Q远优于Original Q**：Original Q在多对手环境中拟合误差极大，导致策略改进失败甚至恶化；Truncated Q在MSE和置信度准确率上均有数量级提升（表1），且能有效指导精炼。
5. **截断地平线H是关键超参数**：最优H取决于环境，过大（如H=10）或过小（H=1）可能导致性能下降，存在非单调关系（图5）。H=T时退化为Original Q。
6. **置信度头和上下文数据对性能贡献积极**：消融实验（图4）表明，去掉置信度头（始终贪心）或去掉上下文数据D（无对手条件）均降低TIPR效果，验证了设计必要性。
7. **TIPR可提升OOM训练效率**：在OOM预训练过程中使用TIPR，能显著降低达到目标性能所需的训练步数（图6），且提升效果稳定。

## 7. 优点：方法或实验设计上的亮点

1. **问题导向明确**：聚焦于OOM中普遍但被忽视的次优数据集问题，具有实际价值。
2. **框架简洁通用**：TIPR是即插即用的，只需额外两步（训练Truncated Q、测试时采用IPR），不改变原OOM算法结构，易于集成到现有系统中。
3. **理论支撑扎实**：从无最大化偏差概率角度推导了截断Q的合理性，证明了存在最优截断地平线，为截断操作提供了理论依据。
4. **实验设计细致**：通过最优比率ρ量化次优度，并在多个环境、多种测试模式（Seen/Unseen/Mixed）下验证，消融研究覆盖关键组件，结论可信。
5. **方法新颖**：将截断思想与上下文学习结合，并引入测试时的即时策略精炼（IPR），区别于传统OCL；置信度驱动的精炼条件实现了敏捷的贪心-保守折中。
6. **对OOM社区贡献大**：首次提出处理OOM次优数据集问题的通用方案，可能成为未来OOM工作的标准改进组件。

## 8. 不足与局限

1. **测试对手策略集有限**：所有对手来自同一种群（MEP），虽然多样化但未覆盖不同训练范式（如IL、RL）产生的对手，泛化性有待验证。
2. **应对持续更新对手的能力**：论文限制对手从固定策略集中切换，未考虑对手策略持续在线更新的场景（如对手在交互中学习进步），作者也将其列为未来工作。
3. **最优截断地平线H的自动选择未解决**：H需手工调整，论文未提供自动选取H的方法（如基于验证集或理论估计），可能影响实际部署便利性。
4. **扩展到合作或混合场景**：实验全为竞争环境，OOM在中性/合作场景下的表现未知，TIPR是否适用尚待验证。
5. **计算开销**：在测试时增加Truncated Q推理和IPR判定，带来额外计算开销（包括对手动作估计、多动作评估），在实时性要求高的场景可能受限。但作者未报告具体延迟数据。
6. **对手模仿器依赖**：IPR需要估计对手动作（通过π_OI），若对手模仿器在测试中出现分布外误差，会影响精炼决策的可靠性。论文未量化此误差影响。
7. **基线选择范围**：对比的OOM基线均来自同一团队前作（Jing et al., 2024a），缺乏其他独立OOM方法的比较（如基于Bayesian或递归推理的方法），可能引入偏差。
8. **资源信息缺失**：未报告GPU型号、数量、训练时长等，不利于复现和评估算力需求。
9. **理论复杂度分析**：定理3.1中的VC维等参数在实际中难以计算，理论分析更多是定性指导，定量预测能力有限。

（完）
