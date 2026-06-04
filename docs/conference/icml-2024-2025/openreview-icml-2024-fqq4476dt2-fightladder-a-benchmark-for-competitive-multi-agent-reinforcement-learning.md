---
title: "FightLadder: A Benchmark for Competitive Multi-Agent Reinforcement Learning"
title_zh: FightLadder：竞争性多智能体强化学习基准平台
authors: "Wenzhe Li, Zihan Ding, Seth Karten, Chi Jin"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=FQQ4476dT2"
tags: ["query:player-ai"]
score: 9.0
evidence: 面向格斗游戏的MARL基准平台
tldr: 该论文针对竞争性多智能体强化学习缺乏轻量级视觉基准的问题，构建了实时格斗游戏平台FightLadder，并提供多种先进算法实现，为训练和评估游戏AI代理提供了标准化环境。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 892, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 795, \"height\": 277, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1742, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 828, \"height\": 814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1670, \"height\": 2109, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1687, \"height\": 2097, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1668, \"height\": 2135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1737, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1740, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1738, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1738, \"height\": 714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1738, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fqq4476dt2/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1780, \"height\": 472, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-fqq4476dt2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fqq4476dt2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fqq4476dt2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 669, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fqq4476dt2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1763, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fqq4476dt2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1765, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fqq4476dt2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1134, \"height\": 623, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fqq4476dt2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1542, \"height\": 365, \"label\": \"Table\"}]"
motivation: 现有MARL基准多面向合作，缺乏竞争性可视化游戏平台。
method: 构建实时格斗游戏环境FightLadder，集成多种视觉输入和算法接口。
result: 平台支持多个格斗游戏场景，复现的基线算法展现了竞争性训练效果。
conclusion: FightLadder填补了竞争MARL基准空白，促进游戏AI研究。
---

## Abstract
Recent advances in reinforcement learning (RL) heavily rely on a variety of well-designed benchmarks, which provide environmental platforms and consistent criteria to evaluate existing and novel algorithms. Specifically, in multi-agent RL (MARL), a plethora of benchmarks based on cooperative games have spurred the development of algorithms that improve the scalability of cooperative multi-agent systems. However, for the competitive setting, a lightweight and open-sourced benchmark with challenging gaming dynamics and visual inputs has not yet been established. In this work, we present FightLadder, a real-time fighting game platform, to empower competitive MARL research. Along with the platform, we provide implementations of state-of-the-art MARL algorithms for competitive games, as well as a set of evaluation metrics to characterize the performance and exploitability of agents. We demonstrate the feasibility of this platform by training a general agent that consistently defeats 12 built-in characters in single-player mode, and expose the difficulty of training a non-exploitable agent without human knowledge and demonstrations in two-player mode. FightLadder provides meticulously designed environments to address critical challenges in competitive MARL research, aiming to catalyze a new era of discovery and advancement in the field. Videos and code at https://sites.google.com/view/fightladder/home.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：当前多智能体强化学习（MARL）基准多集中在**合作任务**（如SMAC、Hanabi等），而**完全竞争**场景的轻量级、开源、具有视觉输入和挑战性动态的基准平台极度缺乏。现有竞争性环境要么状态空间低维（如棋盘游戏），要么计算资源需求高（如星际争霸II、Dota），难以平衡复杂度、效率和通用性。
- **核心问题**：如何构建一个既能提供丰富策略空间和高保真视觉输入，又保持计算高效、易扩展的竞争性MARL基准平台，以推动游戏理论算法在实际应用中的发展。
- **整体意义**：FightLadder填补了竞争性MARL基准空白，提供了多种经典格斗游戏（街霸、拳皇等）的标准化环境，集成了多种基线算法和评估指标（Elo、可剥削性测试），旨在催化非剥削性策略和自博弈算法的研究。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：基于现代游戏模拟器（Gym Retro、MAMEToolkit），将经典格斗游戏封装为符合Gym接口的MARL环境，支持像素级观察（128×100 RGB图像堆栈）和可定制动作空间（原生人类动作空间与转换后的分类动作空间，包含方向移动、攻击、特殊技能等）。
- **关键技术细节**：
  - **状态与观测**：部分可观测马尔可夫博弈（POMG），观测为渲染图像的像素帧，可叠加多帧。
  - **动作空间**：原生12维二值空间经编码转换为分类空间，包含方向移动集和攻击集，并内置硬编码特殊技能列表以降低学习难度。
  - **奖励设计**：支持**稀疏奖励**（+1/-1胜负）和**密集奖励**（基于血量变化的加权和+胜负奖励），密集奖励与胜率保持序数一致性。
  - **评估指标**：
    - **Elo评分**：基于FIDE系统，通过循环赛计算。
    - **可剥削性**（Exploitability）：定义为策略的贝叶斯响应（BR）与其自身对战时的胜率，越接近0.5表示越接近纳什均衡。
    - **对局内置AI**、**人类玩家对战**等。
- **算法流程**（以人口方法为例）：
  - 初始化策略集合和元策略分布。
  - 每轮更新一个玩家的策略，其对手从对方历史策略池中按特定分布（如均匀分布、纳什均衡分布、优先级分布）采样。
  - 重复至收敛。具体可实现为**虚构自博弈（FSP）**、**策略空间响应或acles（PSRO）**、**联赛训练（League）**。

## 3. 实验设计：数据集/场景、benchmark、对比方法
- **场景**：主要使用《街头霸王II》（Street Fighter II）作为主要测试游戏，同时支持《致命格斗》《拳皇》等。
  - **单人完整游戏场景**（sf_ryu_full_game）：代理需依次击败12个不同角色（CPU控制），难度递增，使用课程学习采样对手。
  - **双人对战场景**（sf_ryu_vs_ryu）：两个代理使用相同角色（Ryu）对战。
  - **CPU单挑场景**（sf_ryu_vs_ryu(cpu)）：用于预训练。
- **基准算法**：共5种竞争性MARL算法：
  - **独立PPO（IPPO）**：每个玩家独立训练。
  - **两时间尺度IPPO（2Timescale）**：两个玩家使用不同学习率。
  - **虚构自博弈（FSP）**：从历史策略均匀采样对手。
  - **策略空间响应或acles（PSRO）**：通过求解当前收益矩阵的纳什均衡确定对手采样分布。
  - **联赛训练（League）**：包含主代理、联赛利用者、主利用者多种角色，按特定规则采样。
- **评估指标**：Elo评分（最高1000+）、可剥削性（利用者胜率）、CPU胜率、人类玩家对战。

## 4. 资源与算力
- 论文明确提到：所有实验使用**一台服务器，配备192个CPU和8块A6000 GPU**。
- 具体训练步数：
  - IPPO/2Timescale：约50M步（每个种子）。
  - FSP：约250M步。
  - PSRO：约250M步。
  - League：约700M步（因人口更多）。
- 单人模式PPO课程学习：20个epoch，每个epoch约10M步。
- 论文未提供精确的训练时间（小时/天），但给出了步数规模。

## 5. 实验数量与充分性
- **实验数量**：
  - 单人模式：1组（PPO+课程学习），展示了胜率曲线和调度分布。
  - 双人模式：5种基线算法，每种算法3个随机种子，训练多个检查点。
  - 可剥削性测试：对每个基线中选择最高Elo的模型，训练单独的PPO利用者（固定对方策略）评估胜率，重复3个种子。
  - 人类评估：定性展示。
- **充分性评估**：
  - **优点**：覆盖了主流竞争性MARL算法，实验种子数可接受，训练步数充分（尤其League训练长达700M步），使用了统一PPO backbone和超参数，保证了公平性。
  - **不足**：仅测试了一个游戏（街霸II）的对战场景，未在其他支持游戏（拳皇、致命格斗等）上重复实验；未进行不同密集奖励权重、不同动作空间、不同CNN架构的消融；可剥削性测试中利用者算法固定为PPO，可能低估其他利用者能力；人类评估样本小，仅作定性展示。

## 6. 主要结论与发现
- **单人模式**：PPO+课程学习可稳定击败12个不同角色，完整游戏胜率超过0.6，证明现有RL算法能有效学习格斗游戏基础策略。
- **双人模式**：
  - 人口方法（League, PSRO）在Elo上显著优于独立学习方法（IPPO, 2Timescale, FSP）——League最高Elo约1682（左）/1503（右），PSRO约1262/1517，而独立方法仅约1100左右。
  - 所有训练策略可剥削性均较高（利用者胜率>0.88），其中League和PSRO的可剥削性略低于单一人预训练策略，但仍远未达到纳什均衡（50%胜率）。
  - CPU策略仍能击败大多数训练代理，表明当前算法距离超人类水平有较大差距。
- **非剥削性挑战**：即使使用复杂的人口方法，训练出的策略依然易被利用，说明竞争性格斗游戏中实现非剥削性策略是开放难题。

## 7. 优点
- **平台设计**：轻量、开源、计算高效（FPS≈1935，内存<200MB），比SMACv2快13倍且内存更少，平衡了复杂度与效率。
- **基准完整性**：提供标准化评估体系（Elo、可剥削性）、多种游戏和算法实现，降低复现门槛。
- **可扩展性**：基于通用模拟器，可轻松扩展至其他格斗游戏；支持自定义奖励、动作空间、观测等。
- **实验设计**：统一PPO backbone和超参数，确保基线公平对比；训练步数充分，尤其League训练长达700M步。
- **问题揭示**：明确指出现有算法在竞争性视觉任务中的非剥削性瓶颈，为后续研究指明方向。

## 8. 不足与局限
- **游戏多样性不足**：实验仅全面测试了《街头霸王II》一个游戏，其余游戏（拳皇、致命格斗等）未在双人模式下进行量化评估，限制了结论的普适性。
- **消融实验缺失**：未对动作空间（人类vs转换）、密集奖励权重、帧堆叠数、特殊技能编码等关键设计进行消融分析。
- **可剥削性评估局限性**：利用者固定为PPO，可能低估基于其他算法（如进化策略、搜索方法）的利用能力；利用者训练步数未明确说明。
- **人类评估样本小**：仅提供了定性演示，缺乏系统的人类对比实验（如多位玩家、不同水平）。
- **对称性问题**：左右两侧代理的Elo存在不对称（如League左侧1682 vs 右侧1503），论文未深入解释原因（可能源于优化不稳定、采样随机性等）。
- **超参数通用性**：密集奖励中攻击性系数λ在不同游戏中取值不同（SF2=3，SF3=1），提示该平台可能需要针对不同游戏调参，降低了即插即用性。

（完）
