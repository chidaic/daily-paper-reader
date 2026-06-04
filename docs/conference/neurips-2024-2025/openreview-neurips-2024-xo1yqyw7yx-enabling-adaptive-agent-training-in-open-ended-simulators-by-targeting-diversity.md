---
title: Enabling Adaptive Agent Training in Open-Ended Simulators by Targeting Diversity
title_zh: 面向多样性的自适应Agent训练：在开放式模拟器中的探索
authors: "Robby Costales, Stefanos Nikolaidis"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=Xo1Yqyw7Yx"
tags: ["query:player-ai"]
score: 6.0
evidence: 通过多样性目标在开放式模拟器中训练自适应Agent
tldr: 针对元强化学习中训练任务设计成本高的问题，本文提出通过多样性自动生成训练任务的框架，使Agent能在开放式模拟器中快速适应新环境。方法在多个复杂领域验证了有效性和泛化能力，为游戏或其他模拟环境中Agent的高效训练提供了新思路。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1378, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 283, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 563, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1421, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1432, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1398, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1424, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 552, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 565, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1218, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1103, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1435, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1089, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1080, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1116, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1087, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xo1yqyw7yx/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1415, \"height\": 427, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-xo1yqyw7yx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1062, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xo1yqyw7yx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 856, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xo1yqyw7yx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1319, \"height\": 601, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xo1yqyw7yx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1473, \"height\": 937, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xo1yqyw7yx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1375, \"height\": 1908, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xo1yqyw7yx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1164, \"height\": 519, \"label\": \"Table\"}]"
motivation: 手工设计多样化训练任务成本过高，限制了元强化学习的应用。
method: 通过多样性驱动自动生成训练任务，结合元学习实现快速适应。
result: 在多个复杂模拟环境中Agent适应能力显著提升。
conclusion: 为大规模Agent训练提供了自动化任务生成方案。
---

## Abstract
The wider application of end-to-end learning methods to embodied decision-making domains remains bottlenecked by their reliance on a superabundance of training data representative of the target domain.
Meta-reinforcement learning (meta-RL) approaches abandon the aim of zero-shot *generalization*—the goal of standard reinforcement learning (RL)—in favor of few-shot *adaptation*, and thus hold promise for bridging larger generalization gaps.
While learning this meta-level adaptive behavior still requires substantial data, efficient environment simulators approaching real-world complexity are growing in prevalence.
Even so, hand-designing sufficiently diverse and numerous simulated training tasks for these complex domains is prohibitively labor-intensive.
Domain randomization (DR) and procedural generation (PG), offered as solutions to this problem, require simulators to possess carefully-defined parameters which directly translate to meaningful task diversity—a similarly prohibitive assumption.
In this work, we present **DIVA**, an evolutionary approach for generating diverse training tasks in such complex, open-ended simulators.
Like unsupervised environment design (UED) methods, DIVA can be applied to arbitrary parameterizations, but can additionally incorporate realistically-available domain knowledge—thus inheriting the *flexibility* and *generality* of UED, and the supervised *structure* embedded in well-designed simulators exploited by DR and PG.
Our empirical results showcase DIVA's unique ability to overcome complex parameterizations and successfully train adaptive agent behavior, far outperforming competitive baselines from prior literature.
These findings highlight the potential of such *semi-supervised environment design* (SSED) approaches, of which DIVA is the first humble constituent, to enable training in realistic simulated domains, and produce more robust and capable adaptive agents.
Our code is available at [https://github.com/robbycostales/diva](https://github.com/robbycostales/diva).

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：元强化学习（meta-RL）旨在训练能够快速适应新任务的智能体，但训练过程需要大量代表目标分布的任务数据。在复杂、开放式的模拟器中，手工设计足够多样且数量充足的训练任务成本极高、不可行。
- **现有方法局限**：
  - 域随机化（DR）和程序化生成（PG）假设模拟器具有定义良好的参数，能直接产生有意义的任务多样性，这在实际复杂模拟器中难以满足。
  - 无监督环境设计（UED）方法（如PLR、ACCEL）虽不依赖良好定义的参数，但需要环境生成器在随机采样下能高效产生有意义的多样性，且当参数空间复杂时探索效率低。
- **研究意义**：提出一种能够自动发现并生成多样化训练任务的方法，从而在开放式模拟器中高效训练自适应Agent，降低人工成本并提升泛化能力。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想
- **DIVA（Diversity via Quality Diversity）**：利用质量多样性（Quality Diversity, QD）优化在环境参数空间中高效搜索，生成覆盖目标特征空间的多样化训练任务。它结合了UED的灵活性和DR/PG的结构化监督，属于“半监督环境设计”（SSED）的首个工作。

### 2.2 关键技术细节
- **输入假设**：
  - 访问一个非结构化的环境参数化函数 \(E_U(\theta)\)，可随机生成有效任务。
  - 访问少量下游目标分布的特征样本（如房屋尺寸、赛道曲率等），但不需对应模拟器参数。
- **特征密度估计**：基于特征样本，用核密度估计（KDE）或参数化分布（正态/均匀）拟合每个特征的分布，并用统计检验选择最佳分布。
- **两阶段QD更新**：
  - **第一阶段**：初始化档案（archive）边界覆盖初始随机样本和目标区域。通过交替执行QD更新和样本掩码更新，逐步将采样区域引导向目标区域，加速发现目标区域内的解。
  - **第二阶段**：重置档案边界为目标区域，继续执行QD更新以丰富目标区域内的多样性。
- **元训练**：根据目标特征分布对档案中每个细胞进行采样，生成训练环境，使用VariBAD作为元学习算法训练自适应策略。
- **算法流程**（简化）：
  - 初始化档案，包含随机样本和目标特征样本。
  - 进行 \(N_{S1}\) 次第一阶段QD更新（含样本掩码更新）。
  - 重新定义档案边界为目标区域，进行 \(N_{S2}\) 次第二阶段QD更新。
  - 基于档案分布采样，进行标准VariBAD元训练。

### 2.3 关键创新点
- 将QD优化引入环境任务生成，直接控制多样性轴。
- 两阶段搜索策略解决目标区域稀疏问题。
- 可整合UED（如PLR⊥）到DIVA框架中构成DIVA+，进一步提升性能。

## 3. 实验设计：场景、基准与方法对比

### 3.1 实验场景
- **GridNav（网格导航）**：修改版，目标位置多样性被人为限制（由参数复杂度k控制）。特征：目标x和y坐标。目标分布：均匀覆盖网格。
- **Alchemy（炼金术）**：人工化学环境，潜态空间为三维立方体。特征：潜态多样性（LSD）和曼哈顿距离到最优（MTO）。目标分布：最大化石头潜态多样性。
- **Racing（赛车）**：基于Bezier曲线的赛道生成。特征：总角度变化（TAC）和质心x（CX）。目标分布：真实赛道多样性（ES），以及零样本迁移至F1赛道（EF1）。

### 3.2 对比方法（Baselines）
- **ODS**：Oracle，在目标分布上直接训练（理论上限）。
- **DR**：域随机化，直接对 \(E_U(\theta)\) 随机采样训练。
- **PLR⊥**：基于优先级的水平回放，使用代理指标评分并重采样。
- **ACCEL**：结合PLR⊥评分与进化变异，属于UED先进方法。
- **DIVA+**：DIVA生成档案 + PLR⊥赋予采样权重（用于消融分析）。

### 3.3 公平性措施
- 为补偿DIVA进行QD更新所消耗的环境交互，UED方法（PLR⊥、ACCEL）被给予**额外2.4~4倍**的环境交互步数。
- 所有方法使用相同的VariBAD超参数（基于ODS调优）。

## 4. 资源与算力

- **GPU**：少量Titan X或Titan Xp GPU。
- **CPU**：环境并行化运行于多个CPU核。
- **训练时间**：
  - DIVA和DR实验通常不到一天完成。
  - PLR⊥和ACCEL由于需要更多环境步，耗时超过一天。
- **未明确说明**：具体GPU数量、显存大小、并行进程数等未详细披露，但代码已开源可复现。

## 5. 实验数量与充分性

### 5.1 实验组数
- **主要实验**：在三个场景（GridNav、Alchemy、Racing）上各进行5次独立种子实验，报告均值与95%置信区间。
- **消融实验**：
  - Alchemy上：突变率（0.005~0.08）、QD更新次数（10k~120k）、下游样本数（5~500）的影响。
  - Alchemy上：样本掩码（mask）有无对比。
  - Racing上：DIVA+与DIVA在好/坏档案上的对比。
  - GridNav：基因复杂度k对多样性覆盖率的影响。

### 5.2 充分性与公平性
- **全面性**：覆盖了不同复杂度（GridNav参数k）、不同环境类型（离散、连续、高维潜态）。
- **公平性**：UED方法获得更多环境步；所有方法共享相同元学习架构和超参数空间。
- **统计严谨**：多重种子和置信区间报告，消融实验覆盖关键超参数。
- **潜在不足**：QD档案设计（特征选择、网格分辨率）依赖手工调优，未自动化；各场景参数设置细节在附录中，但未跨场景系统评估通用设置。

## 6. 主要结论与发现

- **DIVA显著优于所有基线**：在三个复杂参数化场景下，DIVA的最终回合回报和成功率均大幅领先DR、PLR⊥和ACCEL，尽管后者获得更多环境步。
- **DIVA能有效克服“不良”参数化**：当随机采样难以产生有意义的多样性时（如GridNav高k、Alchemy高基因数），DIVA仍能覆盖目标区域。
- **DIVA+潜力**：当QD档案设计略微偏差时，结合PLR⊥可修复并达到原DIVA性能；优质档案下提升不明显。
- **零样本迁移突出**：在Racing中，DIVA训练的Agent在F1赛道上成功率超过ODS，表明其学习到的多样性可能更广泛。
- **样本效率**：仅需少量下游特征样本（实验显示仅5个样本即可显著超越基线）即可有效引导搜索。

## 7. 优点

- **高度灵活**：可应用于任意环境参数化，不要求参数空间“良性”。
- **融合知识**：通过少量特征样本整合领域知识，避免完全无监督的盲目搜索。
- **效率高**：QD优化直接探索多样性空间，无需在每个生成任务上评估Agent（对比UED），节省计算。
- **两阶段策略**：解决目标区域稀疏问题，提升搜索效率。
- **可扩展性**：初步证明可与UED方法结合（DIVA+），未来可进一步集成。
- **开源代码**：提供完整可复现代码，文档详尽。

## 8. 不足与局限

- **需要指定多样性轴**：必须预定义特征（如LSD、TAC等），以及每个特征的分布假设。自动化特征选择未解决。
- **手工调优QD档案**：网格分辨率、特征组合、目标函数选择依赖领域知识和试错，缺乏自动化指导。
- **下游样本需求**：虽然少量即可，但仍需获取目标分布的特征样本，在某些场景可能不易获得。
- **未验证大规模复杂场景**：当前实验在相对受限的模拟器（GridNav、Alchemy、Racing）上，未在如XLand等真正开放、高维场景中测试。
- **QD计算开销**：第一阶段搜索可能耗费大量QD迭代（如Alchemy需8万次），若环境生成本身很慢，则可能成为瓶颈。
- **未考虑非平稳性**：当前假设目标分布静态，未探索Agent学习过程中分布动态变化的情况。
- **跨领域通用性证据有限**：虽然三个场景有差异，但均属于离散/连续控制，未涉及视觉或高维感知任务。

（完）
