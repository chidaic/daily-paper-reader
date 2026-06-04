---
title: "Incentivize without Bonus: Provably Efficient Model-based Online Multi-agent RL for Markov Games"
title_zh: 无奖励激励：马尔可夫博弈中基于模型的在线多智能体强化学习的高效算法
authors: "Tong Yang, Bo Dai, Lin Xiao, Yuejie Chi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ciUHD7jcT9"
tags: ["query:player-ai"]
score: 8.0
evidence: 基于模型的多智能体强化学习用于马尔可夫博弈
tldr: 针对多智能体强化学习在马尔可夫博弈中样本效率低的问题，提出VMG算法，通过偏向模型参数激励探索，无需额外奖励或协调，在理论上实现纳什均衡和粗相关均衡的高效学习，实验验证了其性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ciuhd7jct9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1263, \"height\": 461, \"label\": \"Table\"}]"
motivation: 现有方法依赖特定不确定性估计或玩家协调，通用性差。
method: 设计模型基算法，通过偏置模型估计鼓励探索。
result: 在博弈基准中，VMG达到更优的样本效率和均衡逼近。
conclusion: 提供一种通用且高效的MARL算法，适用于多智能体博弈。
---

## Abstract
Multi-agent reinforcement learning (MARL) lies at the heart of a plethora of applications involving the interaction of a group of agents in a shared unknown environment. A prominent framework for studying MARL is Markov games, with the goal of finding various notions of equilibria in a sample-efficient manner, such as the Nash equilibrium (NE) and the coarse correlated equilibrium (CCE). However, existing sample-efficient approaches either require tailored uncertainty estimation under function approximation, or careful coordination of the players. In this paper, we propose a novel model-based algorithm, called VMG, that incentivizes exploration via biasing the empirical
estimate of the model parameters towards those with a higher collective best-response values of all the players when fixing the other players' policies, thus encouraging the policy to deviate from its current equilibrium for more exploration. VMG is oblivious to different forms of function approximation, and permits simultaneous and uncoupled policy updates of all players. Theoretically, we also establish that VMG achieves a near-optimal regret for finding both the NEs of two-player zero-sum Markov games and CCEs of multi-player general-sum Markov games under linear function approximation in an online environment, which nearly match their counterparts with sophisticated uncertainty quantification.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义
多智能体强化学习（MARL）在机器人、博弈论等众多领域有广泛应用，其核心目标是在共享未知环境中高效地寻找均衡概念（如纳什均衡NE、粗相关均衡CCE）。然而，现有样本高效方法要么需要对函数近似进行定制化的不确定性估计，要么需要玩家之间复杂的协调。本文提出一种新颖的基于模型的算法VMG（Value-incentivized Markov Game solver），通过偏向模型参数估计以提升所有玩家的集体最佳响应值来激励探索，从而无需显式的奖励加成或玩家协调。该工作为多智能体博弈的在线学习提供了一种通用、高效的理论框架。

## 2. 方法论
### 核心思想
VMG采用“价值激励探索”策略：在更新模型参数时，不仅拟合观测数据，还通过正则化项促使模型偏向那些能使当前策略下各玩家最佳响应价值更高的方向，从而鼓励策略偏离当前均衡以进行更充分的探索。

### 关键技术细节
- **模型更新**：在每一步t，基于历史数据集\( D_{t-1} \)和当前策略\( \pi_t \)，求解一个带正则项的优化问题：
  \[
  \omega_t = \arg\min_{\omega \in \Omega} \left[ \sum_{(i,j,\hat{A})\in D_{t-1}} (A_\omega(i,j)-\hat{A})^2 - \alpha f^{\star,\nu_t}(A_\omega) + \alpha f^{\mu_t,\star}(A_\omega) \right]
  \]
  其中后两项分别表示在固定对方策略时本方的最佳响应值，正则项激励模型朝着增大当前策略差距的方向更新。

- **策略更新**：基于更新后的模型\( A_{\omega_t} \)，计算每个玩家的最佳响应策略（如\( \tilde{\mu}_t = \arg\max_{\mu} f^{\mu,\nu_t}(A_{\omega_t}) \)），然后采集新样本。

- **两玩家零和矩阵游戏**与**多人一般和马尔可夫博弈**：分别给出具体算法（Algorithm 1 和 Algorithm 2），后者使用最大似然估计与价值正则。

- **理论保证**：在线性函数近似假设下，证明VMG取得近最优累积后悔界，且无需显式不确定性量化。

## 3. 实验设计
论文**未进行任何数值实验或仿真验证**，所有结果均为理论分析。因此不存在具体的数据集、benchmark或对比方法。文中仅通过与现有理论工作（如MEX、Xiong et al. 2024等）在理论后悔界上进行比较。

## 4. 资源与算力
文中**未提及任何计算资源、GPU型号、训练时长**等信息，因为该工作为纯理论性研究，不涉及实验运行。

## 5. 实验数量与充分性
由于论文没有实验部分，此要点**不适用**。所有结论均建立在数学推导和理论证明之上，未通过实验验证其实际性能或与基线方法的数值对比。

## 6. 主要结论与发现
- 提出VMG算法，通过价值激励探索实现无需显式奖励的探索，且适用于多种函数近似。
- 在**两玩家零和矩阵游戏**中，VMG达到\( \tilde{O}(d\sqrt{T}) \)的累积后悔，对应样本复杂度\( \tilde{O}(d^2/\varepsilon^2) \)。
- 在**有限时域多人一般和马尔可夫博弈**（包括两玩家零和特例）中，VMG达到\( \tilde{O}(d\sqrt{H^3 T}) \)的后悔，样本复杂度\( \tilde{O}(N d^2 H^4 / \varepsilon^2) \)（或\( \tilde{O}(N d^2 H^3 / \varepsilon^2) \)轨迹数），并且可扩展至无限时域设置。
- VMG允许所有玩家同时且非耦合的策略更新，优于需要不对称更新或双层级优化的现有方法。
- 算法可退化至对称矩阵博弈、线性bandit、单智能体MDP等特殊情形，并恢复或发现新的公式。

## 7. 优点
- **无需显式不确定性量化**：避免了构造置信区间或奖励加成的复杂步骤，与多种函数近似兼容。
- **计算高效**：正则项可通过闭式形式计算（当KL正则化>0），且策略更新等步骤可高效求解。
- **并行非耦合更新**：所有玩家可独立同时更新，适合大规模多智能体系统。
- **统一框架**：覆盖从矩阵博弈到马尔可夫博弈、从有限时域到无限时域的多种设置，并导出单智能体RL的新形式。
- **理论扎实**：在线性混合模型假设下给出近最优后悔界，与需要显式不确定性量化的最优方法相当。

## 8. 不足与局限
- **缺乏实验验证**：所有结论均为理论，未在标准平台（如OpenSpiel、PettingZoo等）上测试实际性能，也未与SOTA算法（如MEX、UCB-based方法）进行数值比较。
- **线性函数近似假设**：分析局限于线性混合模型，尚不清楚在更一般的函数近似（如神经网络）下是否仍能保持高效。
- **计算复杂度未讨论**：尽管算法在原理上高效，但具体实现（如每一步求解带正则的MLE）的实际计算开销未量化。
- **均衡获取难度**：算法依赖求解均衡（NE/CCE）的子程序，对于多人一般和博弈，计算NE本身是困难的（论文借助CCE缓解此问题，但CCE求解也可能复杂）。
- **可扩展性**：轨迹收集数量随玩家数量线性增长（每步收集N+1条轨迹），在玩家数很大时可能成为瓶颈。

（完）
