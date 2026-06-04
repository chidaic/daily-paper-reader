---
title: Cross-environment Cooperation Enables Zero-shot Multi-agent Coordination
title_zh: 跨环境协作实现零样本多智能体协调
authors: "Kunal Jha, Wilka Carvalho, Yancheng Liang, Simon Shaolei Du, Max Kleiman-Weiner, Natasha Jaques"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zBBYsVGKuB"
tags: ["query:player-ai"]
score: 8.0
evidence: 在类游戏环境中零样本多智能体协调
tldr: 该论文针对多智能体零样本协调在任务间泛化困难的问题，提出跨环境协作(CEC)范式，通过两个基于JAX的程序化生成器创建数十亿可解协调挑战，使智能体在单一伙伴训练后能泛化到新伙伴和新问题。在多个基准上超越现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 813, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 528, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 180, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 726, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 842, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 863, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 776, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 849, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1505, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 888, \"height\": 1209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 863, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1782, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 854, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 850, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 847, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 848, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 816, \"height\": 845, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1772, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 814, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 474, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 473, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1765, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 449, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1724, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1730, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 851, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 853, \"height\": 323, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1709, \"height\": 1404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1578, \"height\": 778, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1246, \"height\": 911, \"label\": \"Table\"}]"
motivation: 现有零样本协调方法仅针对单一任务训练，无法泛化到新任务。
method: 提出CEC范式，在分布式的环境中与单一伙伴进行强化学习，学习通用协作技能。
result: 在程序化生成的协调挑战上超越基线，实现与新伙伴和新问题的零样本泛化。
conclusion: 跨环境训练是解锁零样本多智能体协调泛化能力的关键。
---

## Abstract
Zero-shot coordination (ZSC), the ability to adapt to a new partner in a cooperative task, is a critical component of human-compatible AI. While prior work has focused on training agents to cooperate on a single task, these specialized models do not generalize to new tasks, even if they are highly similar. Here, we study how reinforcement learning on a **distribution of environments with a single partner** enables learning general cooperative skills that support ZSC with **many new partners on many new problems**. We introduce *two* Jax-based, procedural generators that create billions of solvable coordination challenges. We develop a new paradigm called **Cross-Environment Cooperation (CEC)**, and show that it outperforms competitive baselines quantitatively and qualitatively when collaborating with real people. Our findings suggest that learning to collaborate across many unique scenarios encourages agents to develop general norms, which prove effective for collaboration with different partners. Together, our results suggest a new route toward designing generalist cooperative agents capable of interacting with humans without requiring human data.

---

## 论文详细总结（自动生成）

# 论文总结：Cross-environment Cooperation Enables Zero-shot Multi-agent Coordination

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：零样本协调（Zero-shot Coordination, ZSC）要求智能体在未见过的合作任务中与陌生伙伴有效协作。现有方法（如基于种群训练 PBT）仅在单一任务上训练，导致当任务稍有变化时（如厨房布局微调）完全失效，无法泛化到新环境。
- **整体含义**：本文提出**跨环境协作（CEC）** 范式，通过让智能体在大量程序化生成的多样化环境上使用自对弈训练，学习通用的协作规范（general norms），从而在与新伙伴面临新问题时仍能成功协调。这为构建与人类自然交互的通用协作AI提供了新路线，有望应用于家庭机器人、自动驾驶等场景。

## 2. 方法论

- **核心思想**：用**环境多样性**替代传统的**伙伴多样性**。训练时只使用单个固定伙伴（self-play），但不断采样不同的任务环境 m ~ M，迫使智能体学习超越单一布局的、更抽象的合作策略。
- **优化目标**：
  ```
  J(πC) = E_{mi ~ M} [ S(πC, πC, mi) ]
  ```
  其中 S 为合作奖励（联合得分），πC 为策略，mi 为任务环境。
- **关键技术细节**：
  - 使用 **IPPO**（独立PPO）作为基础多智能体强化学习算法。
  - 构建两个基于 **Jax** 的程序化环境生成器：
    - **双目标游戏（Dual Destination Game）**：简单gridworld，随机化智能体和目标位置。
    - **Overcooked 程序化生成器**：基于五种经典布局随机放置锅、洋葱、盘子、目标点等，可生成约 1.16×10¹⁷ 个可解厨房配置，旋转增强，确保物体可达。
  - 网络结构：观察编码器（卷积 + 全连接）→ LSTM循环核心 → actor-critic头（带正交初始化）。
  - 训练过程：**自对弈**，不维护伙伴池，只训练单个策略。

## 3. 实验设计

- **环境/场景**：
  - 双目标游戏（Toy环境，5×5网格）
  - Overcooked（2人合作烹饪游戏，复杂协作任务）
- **Benchmark**：
  - **5个原始布局**（Asymmetric Advantages, Coordination Ring, Counter Circuit, Cramped Room, Forced Coordination）
  - **100个程序化生成的新布局**（从未在训练中出现）
- **对比方法**：
  - **IPPO**（标准自对弈）
  - **FCP**（Fictitious Co-Play，基于种群训练，PBT代表）
  - **E3T**（Efficient End-to-End Training，单任务ZSC SOTA）
  - **CEC-FT**（CEC后在单个布局上微调100M步）
  - **CEC-E3T**（CEC与E3T结合，探索伙伴与环境多样性联合）
- **评价指标**：
  - **AI-AI交叉游戏（XP）奖励**（与不同种子伙伴合作）
  - **跨算法交叉游戏**（IPPO/FCP/E3T/CEC互玩）
  - **人类实验**（80名参与者，2个布局，每轮后Likert量表评分：适应性、一致性、类人性、是否碍事、挫败感、享受度、协调能力）
  - **碰撞次数、实证博弈分析（复制子动态）**
- **消融实验**：
  - 部分可观测（3×3视野）
  - 多任务环境（双目标有多个解）
  - 是否使用LSTM（无LSTM无法收敛）

## 4. 资源与算力

- 所有模型训练 **30亿步（3 billion steps）**，以标准化比较。
- 使用 **Jax** 实现，在 **单个 GPU 上** 可达 **1000万步/分钟**（10 million steps per minute）。
- 未明确说明GPU型号和数量（推测为一张高端GPU如A100或V100）。
- 人类实验通过 **NiceWebRL** 框架部署，可在普通笔记本上同时服务全球多用户。

## 5. 实验数量与充分性

- **实验组数**：
  - 双目标游戏：全观测、部分观测、多任务三种变体，各训练6个种子。
  - Overcooked：6个种子训练IPPO、FCP、E3T、CEC、CEC-FT、CEC-E3T。
  - 跨算法交叉游戏：构建5×5和5×2的收益矩阵。
  - 人类实验：2个布局，各40人，每人玩多轮（含所有算法），共约160轮次。
- **充分性评估**：
  - ✓ 控制了总训练步数（3B steps）进行公平比较。
  - ✓ 使用标准误差与t检验验证显著性。
  - ✓ 消融实验覆盖关键变量（观测性、多任务、循环结构、伙伴+环境联合）。
  - ✓ 既评估AI-AI，也评估Human-AI，且包含主观评分。
  - ⚠ 人类样本限于英语使用者（WEIRD偏差）。
  - ⚠ CEC训练3B steps后尚未收敛，可能未达到上限。

## 6. 主要结论与发现

1. **环境多样性比伙伴多样性更有效**：CEC在交叉游戏（XP）性能上显著超越PBT（FCP）和自对弈（IPPO），且能泛化到从未见过的新布局。
2. **单任务方法无法泛化到新环境**：FCP和E3T在100个程序化新布局上获得零奖励，而CEC成功获得约0.56的归一化奖励。
3. **CEC可微调适应特定任务**：CEC-FT在原始5个布局上提升XP（超越FCP），但牺牲了泛化能力（在新布局上下降）。
4. **人类实验主观评分CEC最优**：尽管奖励低于E3T，但CEC和CEC-FT在适应性、低碰撞、低挫败感等7项指标上均获最高评分，且CEC-FT显著优于E3T（p<0.01）。
5. **CEC学习到更通用的协作规范**：例如避免碰撞、均匀覆盖状态空间，而非僵化的固定路径。
6. **伙伴与环境多样性联合效果不佳**：CEC-E3T在标准布局上表现差，表明简单叠加噪声可能增加训练难度。

## 7. 优点

- **方法简洁高效**：仅用自对弈 + 程序化环境生成，无需维护复杂伙伴池，计算成本低。
- **基础设施贡献大**：开源Jax程序化生成器，支持10^17种布局，训练速度快（10M steps/min）。
- **实验设计全面**：覆盖简单玩具到复杂游戏、模拟到真人、客观奖励到主观评分，结论稳健。
- **挑战传统观点**：证明自对弈在多样化环境下也能实现ZSC，破除了“合作游戏自对弈必然脆弱”的认知。
- **人类实验设计优良**：使用NiceWebRL实现低延迟、多用户并行，问卷信度高（Cronbach's α ≈ 0.874）。

## 8. 不足与局限

- **训练未收敛**：3B步后CEC的XP性能仍在上升，未达到上限，可能进一步训练能提升奖励。
- **人类样本偏差**：仅招募英语流利者（WEIRD群体），可能影响泛化性；文化差异可能影响游戏行为与评分。
- **奖励与主观体验分离**：CEC奖励低于E3T但主观评分更高，需进一步理解人类偏好的权衡。
- **伙伴与环境多样性结合不成功**：CEC-E3T表现差，需要更深入的理论与实践探索。
- **环境生成随机性**：物体放置虽确保可解，但难度分布不均衡，可能影响学习稳定性。
- **未在更复杂现实场景验证**：结论基于gridworld和Overcooked，未来需在机器人、自动驾驶等更具挑战性的领域测试。

（完）
