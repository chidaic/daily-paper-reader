---
title: "Preference-CFR: Beyond Nash Equilibrium for Better Game Strategies"
title_zh: Preference-CFR：超越纳什均衡的更优游戏策略
authors: "Qi Ju, Thomas Tellier, Meng Sun, Zhemei Fang, YunFeng Luo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=beBNOZP5Tk"
tags: ["query:player-ai"]
score: 9.0
evidence: 通过Preference-CFR在游戏策略中建模用户偏好
tldr: 现有游戏AI主要追求最大收益，忽略了策略多样性和用户偏好。本文提出Preference-CFR，引入偏好度和脆弱度参数，使AI能在可接受性能损失内调整策略分布，生成符合不同用户口味的多种玩法。在不完全信息博弈中实验表明，该方法平衡了性能和偏好，提升了AI的适应性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bebnozp5tk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1321, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bebnozp5tk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1318, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bebnozp5tk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1322, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bebnozp5tk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1320, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bebnozp5tk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1750, \"height\": 1014, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bebnozp5tk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 865, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bebnozp5tk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 985, \"height\": 607, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bebnozp5tk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 865, \"height\": 102, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bebnozp5tk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 863, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bebnozp5tk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 169, \"label\": \"Table\"}]"
motivation: 游戏AI缺乏策略多样性和对用户偏好的适应性，限制了应用。
method: 扩展CFR算法，加入偏好度和脆弱度参数，调整策略分布。
result: 在不完全信息博弈中生成多样策略，满足不同用户偏好且性能损失小。
conclusion: Preference-CFR使游戏AI能同时考虑收益和偏好，更具实用性。
---

## Abstract
Artificial intelligence (AI) has surpassed top human players in a variety of games. In imperfect information games, these achievements have primarily been driven by Counterfactual Regret Minimization (CFR) and its variants for computing Nash equilibrium. However, most existing research has focused on maximizing payoff, while largely neglecting the importance of strategic diversity and the need for varied play styles, thereby limiting AI’s adaptability to different user preferences.

To address this gap, we propose Preference-CFR (Pref-CFR), a novel method that incorporates two key parameters: preference degree and vulnerability degree. These parameters enable the AI to adjust its strategic distribution within an acceptable performance loss threshold, thereby enhancing its adaptability to a wider range of strategic demands. In our experiments with Texas Hold’em, Pref-CFR successfully trained Aggressive and Loose Passive styles that not only match original CFR-based strategies in performance but also display clearly distinct behavioral patterns. Notably, for certain hand scenarios, Pref-CFR produces strategies that diverge significantly from both conventional expert heuristics and original CFR outputs, potentially offering novel insights for professional players.

---

## 论文详细总结（自动生成）

# 论文总结：Preference-CFR: Beyond Nash Equilibrium for Better Game Strategies

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：现有不完全信息博弈AI（如基于CFR的算法）主要追求纳什均衡（NE），以最大化期望收益为目标，忽视了策略多样性和玩家风格偏好。这导致AI策略过于理性、单一，难以适应不同用户（如娱乐型玩家）的需求，并限制了AI在多人博弈中的实用性。
- **核心问题**：如何在可接受的性能损失范围内，使AI能生成多种风格（如激进型、松被动型）且性能可比的策略，从而提升AI的适应性和娱乐性。
- **整体含义**：本文认为“更好”的策略不应仅停留在NE，而应兼顾用户偏好和多样性，通过引入偏好度和脆弱度参数，扩展了CFR框架，实现了从“唯一最优”到“多样化可接受”的转变。

## 2. 方法论：核心思想、关键技术细节与算法流程
- **核心思想**：在CFR迭代过程中，引入两个可调参数：
  - **偏好度** δ(I,a)：表示玩家在信息集 I 中对动作 a 的倾向程度。
  - **脆弱度** β：表示愿意容忍的最大可剥削性（即允许策略偏离NE的上限）。
- **关键技术细节**：
  1. **Preference-CFR (Pref-CFR)**：修改CFR的遗憾匹配策略，在更新策略时乘以 δ 权重。对于RM型策略：  
     σ^{T+1}(I,a) ∝ δ(I,a) × max(0, 平均遗憾)，当所有遗憾非正则使用 δ 的归一化分布。  
     对于BR型策略：  
     σ^{T+1}(I) = argmax_{a} δ(I,a) × 遗憾(I,a)。
  2. **Vulnerability-CFR**：将遗憾值减去 β，使策略收敛到 ϵ-NE（ϵ ≤ β）。  
     B^T(I,a) = 平均遗憾(I,a) - β，然后基于B^T进行策略选择。
  3. **结合使用**：同时设定 δ 和 β，既可引导策略接近偏好风格，又能容忍一定性能损失，从而扩大可接受的策略空间。
- **理论保证**：论文证明Pref-CFR满足Blackwell可接近性，在两人零和博弈中收敛到NE（当β=0），当β>0时收敛到β-NE。收敛速度与δ最大值成反比，但在合理范围内（δ≤5）速度可接受。

## 3. 实验设计
- **使用的游戏/场景**：
  - **Kuhn扑克**（3张牌）：用于验证Pref-CFR能收敛到不同NE（存在多个NE）。
  - **Leduc扑克**（12张牌，6对）：用于测试只有唯一NE时，需引入β>0才能产生风格差异。
  - **德州扑克（Texas Hold'em）**：包括2人（Heads-Up）和3人两种设置，分别训练激进型和松被动型AI。
- **Benchmark**：对比原始CFR（或ES-MCCFR）策略，以及不同参数设置下的Pref-CFR变体。
- **对比方法**：
  - 原始CFR / ES-MCCFR（无偏好）
  - Pref-CFR(RM) 和 Pref-CFR(BR)
  - 不同 δ 值（如5、10）、不同 β 值（如0、0.05等）
- **评估指标**：
  - 对局收益（mBB/h，千分之一个大盲注每手）
  - 策略分布差异（下注、跟注、弃牌等频率）
  - exploitability（可剥削性）

## 4. 资源与算力
- **计算资源**：论文明确提到“Solutions were computed in under 10 minutes with a 24-core CPU；subgames included 35k states and the full game used for leaf estimates had 25M states.”  
  - 未使用GPU，纯CPU计算。
  - 每次实验运行时间不超过10分钟（针对德州扑克子游戏解算）。
- **算力规模**：未提供具体GPU型号或集群信息，属于中等规模单机实验。

## 5. 实验数量与充分性
- **实验数量**：
  - Kuhn扑克：多组 δ 和 β 设置，对比收敛曲线和α值变化（Figure 1-2）。
  - Leduc扑克：多组 δ 和 β 设置，对比策略概率变化（Figure 3-4）。
  - 2人德州扑克：训练三种AI（正常、激进、松被动），进行头对头对战（Table 2），并展示策略热图（Figure 5a-c）。
  - 3人德州扑克：类似地训练三种AI并对比（Table 3, Figure 5d-f）。
  - 共至少10组以上对比实验，包括不同游戏、不同风格、不同参数。
- **充分性评估**：
  - **客观性**：采用标准评估方法（exploitability、head-to-head收益），结果统计置信区间（90%），重复30次实验。
  - **公平性**：所有算法在相同环境下运行，初始策略随机，对比显著有效。
  - **局限**：未进行大规模多玩家、多策略空间（如更复杂游戏如StarCraft）的测试；未与人类玩家行为模式进行系统比较。

## 6. 主要结论与发现
- **Pref-CFR能收敛到不同风格的策略**：在Kuhn扑克（多NE）中，仅用δ（β=0）即可收敛到不同NE；在Leduc扑克（唯一NE）中，需结合β>0才能产生显著风格差异。
- **性能损失可控**：在2人德州扑克中，不同风格AI之间的收益差<10 mBB/h（通常低于人类显著优势阈值）；在3人游戏中，风格变化更明显，但收益差仍在10 mBB/h以内。
- **产生新颖策略**：激进型AI对弱牌（如82o）也会加注，松被动型AI几乎从不弃牌；这些策略与GTO计算和人类专家直觉不同，可以为专业玩家提供新视角。
- **风格调节有效**：通过调整δ和β，可定量控制策略的激进程度或松紧度，且对收敛速度影响有限（δ≤5时）。

## 7. 优点
- **理论创新**：将偏好和脆弱性引入CFR，并证明收敛性，填补了非NE策略计算的空白。
- **实用性强**：直接生成具有明确风格且性能可比的AI，适用于娱乐、教学、社交通信等场景。
- **实验充分**：覆盖简单到复杂游戏，多维度评估（收益、策略分布、对抗结果），并展示显著性差异。
- **效率可接受**：计算开销与原始CFR相当（仅增加δ和β的额外计算），且可在CPU上快速解算。
- **可解释性**：策略热图直观展示风格差异，便于人类理解和分析。

## 8. 不足与局限
- **手动参数调优**：δ和β需要专家根据宏观风格（如“激进”）手动设定到每个信息集，缺乏自动映射机制，限制了易用性。
- **泛化性不足**：仅测试了扑克类不完全信息博弈，未涉及其他类型游戏（如完全信息、多人一般和博弈），也未在高维连续动作空间验证。
- **实验规模有限**：德州扑克子游戏约35k状态，完整游戏约25M状态，但未与超大规模AI系统（如Pluribus、Supremus）进行直接性能对比。
- **缺乏人类玩家验证**：虽声称能为专业玩家提供新见解，但未进行真人实验或行为学评估，策略的实际可学习性和对抗效果未知。
- **收敛速度分析**：理论表明收敛速度与δ最大值成反比，但实验仅测试δ≤10，更高δ的行为未探索。
- **偏差风险**：偏好参数可能引入主观偏差，若设定不当（如过度激进），AI容易被智能对手利用；论文未讨论如何平衡风险与多样性。

（完）
