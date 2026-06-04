---
title: Mastering Zero-Shot Interactions in Cooperative and Competitive Simultaneous Games
title_zh: 掌握合作与竞争同时博弈中的零样本交互
authors: "Yannik Mahlau, Frederik Schubert, Bodo Rosenhahn"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=SoqxSnEUi1"
tags: ["query:player-ai"]
score: 9.0
evidence: 同时博弈中对手行为建模以实现零样本交互
tldr: 本文提出Albatross，将AlphaZero扩展到同时博弈场景。针对同时博弈中其他智能体行为不可知的问题，该方法学习有界理性对手模型，并采用温度调节响应优化，训练出平滑最佳响应对数均衡策略。实验表明，Albatross在多种同时博弈任务中实现零样本协作与竞争。该工作直接服务于游戏AI的玩家行为建模与智能体交互。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 606, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 767, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 811, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 782, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 772, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1761, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 767, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1714, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 845, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 697, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1761, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1629, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1698, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1597, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 445, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1615, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1072, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1764, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1763, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1760, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1760, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-soqxsneui1/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1384, \"height\": 403, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-soqxsneui1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1761, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-soqxsneui1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 842, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-soqxsneui1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-soqxsneui1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1586, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-soqxsneui1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 455, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-soqxsneui1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1297, \"height\": 243, \"label\": \"Table\"}]"
motivation: 同时博弈中其他智能体的并发行动选择是限制因素。
method: 提出Albatross算法，包含有界理性对手建模和温度响应优化。
result: 在同时博弈中实现零样本有效交互。
conclusion: Albatross为同时博弈AI提供了行为建模新框架。
---

## Abstract
The combination of self-play and planning has achieved great successes in sequential games, for instance in Chess and Go. However, adapting algorithms such as AlphaZero to simultaneous games poses a new challenge. In these games, missing information about concurrent actions of other agents is a limiting factor as they may select different Nash equilibria or do not play optimally at all. Thus, it is vital to model the behavior of the other agents when interacting with them in simultaneous games. To this end, we propose Albatross: AlphaZero for Learning Bounded-rational Agents and Temperature-based Response Optimization using Simulated Self-play. Albatross learns to play the novel equilibrium concept of a Smooth Best Response Logit Equilibrium (SBRLE), which enables cooperation and competition with agents of any playing strength. We perform an extensive evaluation of Albatross on a set of cooperative and competitive simultaneous perfect-information games. In contrast to AlphaZero, Albatross is able to exploit weak agents in the competitive game of Battlesnake. Additionally, it yields an improvement of 37.6% compared to previous state of the art in the cooperative Overcooked benchmark.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：在**同时博弈**（simultaneous games）中，所有智能体同时做出动作，缺少对其他智能体并发行动的信息。传统基于自对弈和规划的算法（如AlphaZero）适用于**序贯博弈**，但在同时博弈中因无法预测其他智能体的行动而表现不佳。具体而言，其他智能体可能选择不同的纳什均衡或完全不按最优方式行动，导致零样本交互（zero-shot interaction）场景下难以适应。
- **研究动机**：为了实现与未知智能体的有效合作或竞争，必须对对手行为进行建模。现有方法多通过训练多样化策略种群来覆盖不同行为模式，但作者认为基于博弈论的显式对手建模能产生更好的协作能力。
- **整体含义**：本文提出Albatross算法，学习一种新的均衡概念——**平滑最佳响应对数均衡（SBRLE）**，使智能体能够与任何游戏强度的对手进行零样本交互，同时适用于合作与竞争场景。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将对手的理性程度参数化为一个**连续的温度参数 τ**（τ=0为完全随机，τ→∞为完全理性），通过在线最大似然估计（MLE）从单局交互中估计对手温度。然后训练一个策略网络，针对对手的不同温度采取**平滑最佳响应**。
- **关键技术细节**：
  - **均衡概念**：提出**平滑最佳响应对数均衡（SBRLE）**，其中理性智能体对其他智能体的对数均衡策略（LE）做出平滑最佳响应，而非假设对手知道理性智能体的最优策略（如Quantal Stackelberg Equilibrium中的假设）。
  - **两阶段训练**：
    1. **代理模型（Proxy Model）**：学习不同温度下的对数均衡策略，输入为状态和当前温度 τ，输出策略 π_θP 和值 v_θP。使用固定深度搜索，在叶节点构建正规形博弈（NFG）并求解对数均衡，反向传播期望效用。
    2. **响应模型（Response Model）**：学习对代理模型策略的平滑最佳响应，输入为状态和其他所有智能体的温度 τ_{-i}，输出 π_θR 和 v_θR。同样使用固定深度搜索，但利用代理模型π_θP预测其他智能体的策略，然后计算平滑最佳响应（softmax），响应温度 τ_R 为固定超参数。
  - **在线温度估计**：使用最大似然估计，基于K次观测的对手动作和代理模型的最优策略，利用梯度下降或线性搜索求解温度τ_j。似然函数被证明是凹函数，故可全局优化。
- **公式与算法流程**（文字说明）：
  - 平滑最佳响应：SBR(π_{-i}, τ) ∝ exp(τ u_i(·, π_{-i}))。
  - 对数均衡（LE）：所有智能体均以相同温度进行SBR达到不动点。
  - SBRLE定义：理性智能体以 τ_R 进行SBR，其他智能体以其各自温度 τ_j 进行LE。
  - 训练代理模型时，每个episode采样τ，使用固定深度搜索+LE求解器；训练响应模型时，采样τ_{-i}，利用代理模型策略计算SBRLE。目标为策略交叉熵和值MSE。

## 3. 实验设计：数据集/场景、benchmark、对比方法
- **合作场景**：**Overcooked**（Carroll et al. 2019）中的五个厨房布局：Cramped Room、Asymmetric Advantage、Coordination Ring、Forced Coordination、Counter Circuit。合作奖励为每份汤20分，400步。
  - 对比方法：PPO、PBT（Population-Based Training）、FCP（Fictitious Co-Play）、TrajeDi（Trajectory Diversity）、MEP（Maximum Entropy Population-Based training）、PECAN（Policy Ensemble for Context-Aware Zero-Shot Human-AI Coordination）。
  - 与**行为克隆代理**（基于人类数据训练）合作评估。
  - 与**脚本代理**（如只放置洋葱、随处放盘子等特定偏差行为）合作评估，对比HSP（Hidden-Utility Self-Play）。
- **竞争场景**：**Battlesnake**（Chung et al. 2020），包含三种模式：Tron（无食物）、随机两玩家、随机四玩家。回报为获胜+1，死亡-1。
  - 对比方法：AlphaZero（同时博弈适配版本）以及使用不同搜索预算的基线MCTS+价值启发式智能体。
  - 进行锦标赛，用TrueSkill评分比较Albatross、AlphaZero和基线智能体。
- **合作Battlesnake**：四个智能体合作生存游戏，验证多智能体合作能力。
- **消融与分析实验**：
  - 温度对代理策略熵和互信息的影响。
  - 在线MLE温度估计的收敛速度。
  - 温度误估计的鲁棒性。
  - 不同温度自对弈与Albatross配合的表现。
  - 代理与响应模型在重复矩阵游戏中的行为解释。
  - 不同树搜索变体（DUCT、EXP3、Regret Matching、SM-OOS、固定深度搜索+纳什/对数均衡）的对比。

## 4. 资源与算力
- **硬件**：Nvidia RTX 3090 GPU、Intel Xeon Gold 6258R CPU。
- **数量与时长**：
  - Overcooked：2块GPU，训练48小时。
  - Tron：3块GPU，训练24小时。
  - 随机两玩家：2块GPU，训练96小时。
  - 随机四玩家：1块GPU，训练48小时。
  - 四玩家合作Tron：1块GPU，训练24小时。
  - 每个GPU配14个CPU核。
  - 所有实验使用5个随机种子。

## 5. 实验数量与充分性
- **实验数量**：涉及三大类场景（合作Overcooked、竞争Battlesnake、合作Battlesnake），共约20余组不同设置（五个布局、三种游戏模式、多种对手强度、脚本代理）。进行了详细消融（温度分布、树搜索变体、SBRLE vs BRLE、温度误估计等）和定性分析。
- **充分性与客观性**：
  - 对比了多种SOTA方法，结果具有统计显著性（均值±标准差，5种子）。
  - 实验设计覆盖了合作与竞争、两智能体与多智能体、确定性/随机环境。
  - 弱点：在Forced Coordination布局中性能不如PECAN，作者分析了原因；在非常短的游戏（如Tron）中MLE可能无法及时收敛，属于局限性。

## 6. 主要结论与发现
- **合作Overcooked**：Albatross在所有布局（除Forced Coordination）上均优于SOTA方法PECAN，平均提升**37.6%**；与脚本代理合作时也大部分优于HSP。
- **竞争Battlesnake**：Albatross能有效利用弱对手，其TrueSkill评分高于AlphaZero；当对手非常强时两者收敛。
- **温度的作用**：代理策略熵随温度升高而降低；响应与代理策略的互信息随温度升高而增加，表明Albatross对理性伙伴更信任、对弱伙伴更自力更生。
- **在线温度估计**：MLE在20-30步内收敛至真实温度，温度误估计在合理范围内对性能影响不大，但过度高估对手理性会导致显著下降。
- **均衡稳定性**：对数均衡（LE）比纳什均衡对价值函数近似误差更鲁棒，SBRLE比BRLE训练更稳定。

## 7. 优点：方法或实验设计上的亮点
- **创新性**：提出SBRLE均衡概念，合理建模对手理性程度，避免强行假设对手知道理性智能体的策略（如QSE）。
- **可解释性**：连续温度参数直观对应理性程度，便于分析策略变化。
- **效率**：MLE仅需单局交互即可在线估计对手温度，无需预训练对手模型。
- **通用性**：同时适用于合作与竞争、两玩家与多玩家、确定性与随机环境。
- **实验充分**：与多种SOTA方法对比，在多个场景验证，并包含大量消融/分析实验，代码和模型开源。
- **对AlphaZero的适应性改进**：通过固定深度搜索+LE备份替代MCTS，更适合同时博弈。

## 8. 不足与局限
- **对短交互的限制**：MLE需要10-30步观测才能收敛，在更短的游戏（如Tron，最长24步）中可能无法及时估计。作者建议未来使用先验温度（如在线排行榜）。
- **联合动作空间爆炸**：固定深度搜索的复杂度随智能体数和动作数指数增长，限制了在大动作空间或未知动力学环境（如MeltingPot）中的应用。未来可结合MuZero学习环境模型。
- **对手模型偏差**：假设对手行为符合对数均衡，但现实对手可能具有特定偏差（如脚本代理），尽管实验显示鲁棒性，但理论保证不足。
- **Forced Coordination布局表现不佳**：由于稀疏奖励和训练困难，性能低于PECAN。
- **计算开销**：两阶段训练（代理+响应）需要更多计算资源，尽管与AlphaZero总时间相当。
- **社会伦理考虑**：理性建模是复杂概念，在真实应用中需考虑公平、隐私、安全与伦理。

（完）
