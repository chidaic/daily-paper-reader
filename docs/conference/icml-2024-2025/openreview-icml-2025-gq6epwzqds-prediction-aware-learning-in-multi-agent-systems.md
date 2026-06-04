---
title: Prediction-Aware Learning in Multi-Agent Systems
title_zh: 多智能体系统中的预测感知学习
authors: "Aymeric Capitaine, Etienne Boursier, Eric Moulines, Michael I. Jordan, Alain Oliviero Durmus"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=GQ6epWZqdS"
tags: ["query:player-ai"]
score: 7.0
evidence: 多人博弈中的预测感知学习
tldr: 该工作针对时变博弈中现有遗憾界变松的问题，提出预测感知学习框架，使智能体能基于未来收益预测调整策略，在博弈论框架下提升了多智能体系统的理论稳健性，对游戏AI中动态环境建模有参考价值。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gq6epwzqds/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 514, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gq6epwzqds/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 519, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gq6epwzqds/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1411, \"height\": 297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gq6epwzqds/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 522, \"height\": 354, \"label\": \"Figure\"}]"
motivation: 时变博弈中现有方法无法利用可预测的收益变化，导致遗憾界失效。
method: 引入预测感知框架，智能体基于状态预测未来收益并自适应调整策略。
result: 理论分析表明新框架在可预测变化下获得更紧的遗憾界。
conclusion: 收益预测能力可显著提升博弈学习算法的鲁棒性。
---

## Abstract
The framework of uncoupled online learning in multiplayer games has made significant progress in recent years. In particular, the development of  time-varying games has considerably expanded its modeling capabilities. However, current regret bounds quickly become vacuous when the game undergoes significant variations over time, even when these variations are easy to predict. Intuitively, the ability of players to forecast future payoffs should lead to tighter guarantees, yet existing approaches fail to incorporate this aspect. This work aims to fill this gap by introducing a novel prediction-aware framework for time-varying games, where agents can forecast future payoffs and adapt their strategies accordingly. In this framework, payoffs depend on an underlying state of nature that agents predict in an online manner. To leverage these predictions, we propose the POMWU algorithm, a contextual extension of the optimistic Multiplicative Weight Update algorithm, for which we establish theoretical guarantees on social welfare and convergence to equilibrium. Our results demonstrate that, under bounded prediction errors, the proposed framework achieves performance comparable to the static setting. Finally, we empirically demonstrate the effectiveness of POMWU in a traffic routing experiment.

---

## 论文详细总结（自动生成）

# 多智能体系统中的预测感知学习 (Prediction-Aware Learning in Multi-Agent Systems) —— 详细中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：在多人博弈的在线学习（uncoupled online learning）领域，现有方法（如动态遗憾分析）在处理时变博弈时，其遗憾界往往随着博弈变化幅度增大而变得无效。然而，许多时变博弈的变化模式是**可预测**的（例如确定性周期变化），如果智能体能利用预测能力，理应获得更紧的遗憾界。现有文献忽视了这一预测能力。
- **核心问题**：如何将智能体对未来收益的预测能力纳入多智能体学习框架，从而在时变博弈中同时保证社会福祉（social welfare）和均衡收敛性能？
- **整体含义**：本文首次提出了**预测感知学习（prediction-aware learning）** 框架，允许智能体在线预测未来收益并动态调整策略。理论上证明了在预测误差有界时，该框架可达到与静态博弈相当的性能，显著改进了现有时变博弈的遗憾界。

## 2. 论文提出的方法论

### 核心思想
- 每个时变博弈的状态由一个潜在的**自然状态（state of nature）** \(Z_t \in \mathcal{Z}\) 决定（\(\mathcal{Z}\) 为有限集）。智能体 \(j\) 在每一轮获得对 \(Z_t\) 的私人预测 \(\hat Z_{jt}\)，然后基于该预测选择混合策略 \(w_{jt} \in \Delta^K\)（\(K\) 为动作数）。
- 收益函数为线性形式：\(c_j(w, Z) = \langle Z, \Phi_j(w_{-j}) w_j \rangle\)，其中 \(\Phi_j(w_{-j})\) 是依赖对手策略的矩阵。
- 框架分为三阶段：① 预测状态；② 选择动作；③ 观察真实状态和收益，更新策略和预测器。

### 算法：POMWU（Predictive Optimistic Multiplicative Weight Update）
- 是乐观乘法权重更新（OMWU）的上下文（contextual）扩展。
- 为每个上下文（即每个可能的自然状态 \(z\)）维护一个独立的 OMWU 实例，包括初始权重 \(\rho_z\) 和参考矩阵 \(\Psi_z\)。
- 每轮，智能体使用预测 \(\hat Z_{jt}\) 对应的 OMWU 实例生成混合策略 \(w_{jt}\)。
- 观察到真实状态 \(Z_t\) 后，更新对应状态的 \(\rho_{Z_t}\) 和 \(\Psi_{Z_t}\)。
- 算法伪代码见 Algorithm 1（略），本质上是对每个上下文执行乐观镜像下降（Optimistic Mirror Descent）。

### 关键技术细节
- **新遗憾概念**：定义了**上下文外部遗憾**（contextual external regret）和**上下文交换遗憾**（contextual swap regret），允许比较器随上下文变化但固定在每个上下文内最优。
- **上下文 RVU 界**：提出了新的**Regret bounded by Variation Utility (RVU)** 分析，依赖于每个上下文内的策略变化和收益变化，而不是全局路径长度。关键引理（Proposition 5）给出了遗憾上界，依赖于预测错误次数 \(L_{jT}\)。
- **均衡定义**：扩展了粗相关均衡（CCE）和关联均衡（CE）到上下文场景（Definition 1 & 2），并证明个体遗憾与均衡收敛之间的关系（Proposition 2 & 3）。
- **社会福利**：利用 Roughgarden 平滑性条件（H3），证明了平均社会成本与最优成本之差受个体遗憾和约束（Proposition 4）。
- **理论保证**：
    - 当所有智能体使用 POMWU 且学习率 \(\eta = \Theta(J^{-1/2}T^{-1/4}[\ln K (L_T+m)]^{1/4})\) 时，个体遗憾为 \(O([\ln K (L_T+m)]^{3/4}T^{1/4}J^{1/2})\)（Proposition 6）。
    - 社会福利方面，\(\eta = (4(J-1))^{-1}\) 时，总遗憾 \(O(J\ln K (L_T + mJ))\)（Proposition 7）。
    - 对抗性鲁棒性：单方使用 POMWU 可达到 \(O(\sqrt{T})\) 遗憾（Proposition 8）。

## 3. 实验设计

- **场景**：Sioux Falls 交通路由问题（LeBlanc et al., 1975），基于公开数据集（含网络拓扑、边成本、交通需求量）。
    - 图结构：24个节点，76条边。
    - 智能体：每个节点到其他节点有一对（origin-destination）智能体，排除那些路径长度差异小的，最终保留 \(J=91\) 个智能体。
    - 动作集：每个智能体可选 \(K=5\) 条最短路径。
    - 上下文：\(m=5\) 个随机生成的天气/路况状态，每个状态对边成本添加指数分布噪声。
- **预测方法**：使用在线逻辑回归（online logistic regression）预测上下文：每个智能体观察协变量 \(X_t\)，预测 \(\hat Z_t = \arg\max \zeta(\hat\beta_z, X_t)\)，并在线更新参数。
- **对比方法**：
    - **POMWU**（本文算法）。
    - **OMWU**（原始的乐观乘法权重更新，忽略状态变化）。
- **评估指标**：
    - 平均遗憾（每轮每个智能体的外部遗憾）。
    - 平均预测错误率。
    - 不同上下文下网络中的智能体分布（展示近似粗相关均衡）。
    - 误预测轮次贡献的遗憾比例。

## 4. 资源与算力

- **文中未明确说明**使用的 GPU 型号、数量、训练时长等算力信息。实验仅涉及 CPU 可完成的模拟（T=20000 轮，91个智能体，K=5，m=5），计算规模较小。未提及分布式训练或大规模并行。

## 5. 实验数量与充分性

- **实验组数**：仅有一个主要实验场景（Sioux Falls 交通），但包含多个分析维度：
    - 平均遗憾曲线（Figure 2）。
    - 预测误差曲线（Figure 3）。
    - 误预测贡献比例（Figure 4）。
    - 均衡分布示意图（Figure 1）。
- **充分性分析**：
    - 作为理论论文，实验主要验证理论结果，场景选择合理且与上下文博弈相关。
    - 但实验**多样性不足**：仅测试一种博弈类型（交通路由），未在合成博弈、零和博弈或其他经典时变博弈上验证。
    - 未进行**消融实验**（如不同学习率、不同预测器质量、不同智能体数量等）。
    - 对比基线仅 OMWU，未与近期时变博弈方法（如 Zhang et al. 2022 或 Anagnostides et al. 2024）对比。
    - 整体上，实验作为理论补充是足够的，但不够广泛或深入。

## 6. 论文的主要结论与发现

1. **预测能力可显著改善时变博弈的遗憾**：在预测误差有界时，POMWU 可实现与静态博弈相当的遗憾界（即与 \(T\) 的次线性关系而非线性）。
2. **稳定的均衡收敛**：所有智能体使用 POMWU 时，经验分布收敛到近似上下文粗相关均衡和关联均衡，速率依赖预测误差。
3. **社会福利有保障**：在满足平滑性假设的游戏中，平均社会成本接近最优社会成本的常数倍（price of anarchy）。
4. **鲁棒性**：即使对手非合作，单边使用 POMWU 仍能保持次线性遗憾。
5. **实验验证**：在 Sioux Falls 交通仿真中，POMWU 显著优于忽略上下文的 OMWU，遗憾几乎仅由误预测轮次引起。

## 7. 优点

- **理论创新性**：首次将预测能力系统性地融入多智能体在线学习框架，重新定义了遗憾、均衡等概念，并建立了与 RVU 分析的联系。
- **分析细致**：不仅给出了外部遗憾保证，还通过 Blum-Mansour 缩减给出了交换遗憾保证；同时处理了社会福利和对抗性场景。
- **算法简洁实用**：POMWU 是 OMWU 的自然扩展，易于实现，且每个上下文独立维护，计算开销低。
- **实验具有代表性**：交通路由是经典的上下文博弈问题，结果直观展示了预测的重要性。

## 8. 不足与局限

- **假设限制较强**：
    - 假设上下文集合 \(\mathcal{Z}\) 有限（H2），扩展至连续上下文需额外设计（作者在附录 B 简要讨论，但未给出完整方案）。
    - 假设收益函数线性于状态（式 (2)），限制了应用范围。
    - 全信息反馈（full-information feedback），而非更现实的 bandit 反馈。
- **实验覆盖不足**：
    - 仅测试一个场景，未在多种博弈（如拍卖、资源分配、零和博弈）上验证。
    - 未与近期时变博弈算法（如 Daskalakis et al. 2021, Zhang et al. 2022）进行定量对比。
    - 未进行超参数敏感性分析或大规模验证。
- **预测误差分析**：理论中预测误差项 \(L_{jT}\) 的界依赖于在线学习算法（如 Littlestone 维度），但实验中使用逻辑回归，未给出实际误差界匹配理论。
- **可复现性**：未提供代码或详细超参数（如学习率、优化器设置），但数据集和网络结构有公开资源。
- **算力需求未提及**：对于大规模多智能体系统（如数百智能体、连续状态），算法效率未讨论。

（完）
