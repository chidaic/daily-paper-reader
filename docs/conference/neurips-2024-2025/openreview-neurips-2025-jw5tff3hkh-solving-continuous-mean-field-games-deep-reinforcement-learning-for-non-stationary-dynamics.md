---
title: "Solving Continuous Mean Field Games: Deep Reinforcement Learning for Non-Stationary Dynamics"
title_zh: 求解连续平均场博弈：面向非平稳动力学的深度强化学习
authors: "Lorenzo Magnino, Kai Shao, Zida Wu, Jiacheng Shen, Mathieu Lauriere"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Jw5TFF3HkH"
tags: ["query:player-ai"]
score: 6.0
evidence: 平均场博弈建模大规模智能体交互，与玩家行为模拟相关
tldr: 本文针对现有平均场博弈方法局限于有限空间或平稳模型的不足，提出一种面向非平稳连续平均场博弈的深度强化学习算法。该方法基于虚构博弈框架，利用深度RL进行最佳响应计算，结合监督学习刻画平均策略，并学习时变群体分布的表示。该工作为模拟大规模玩家行为提供了可扩展的解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1410, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1415, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1424, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 544, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1104, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1316, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1189, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1316, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1220, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1214, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1412, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1408, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 857, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1429, \"height\": 1354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1430, \"height\": 1353, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jw5tff3hkh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1336, \"height\": 348, \"label\": \"Table\"}]"
motivation: 现有平均场博弈方法无法处理连续非平稳动力学，限制了在现实问题中的应用。
method: 提出基于虚构博弈的DRL算法，结合深度RL最佳响应和条件归一化流学习时变分布。
result: 在连续非平稳环境下实现了有效策略学习。
conclusion: 为大规模多智能体系统（包括玩家行为模拟）提供了新的建模工具。
---

## Abstract
Mean field games (MFGs) have emerged as a powerful framework for modeling interactions in large-scale multi-agent systems. Despite recent advancements in reinforcement learning (RL) for MFGs, existing methods are typically limited to finite spaces or stationary models, hindering their applicability to real-world problems. This paper introduces a novel deep reinforcement learning (DRL) algorithm specifically designed for non-stationary continuous MFGs. The proposed approach builds upon a Fictitious Play (FP) methodology, leveraging DRL for best-response computation and supervised learning for average policy representation. Furthermore, it learns a representation of the time-dependent population distribution using a Conditional Normalizing Flow. To validate the effectiveness of our method, we evaluate it on three different examples of increasing complexity. By addressing critical limitations in scalability and density approximation, this work represents a significant advancement in applying DRL techniques to complex MFG problems, bringing the field closer to real-world multi-agent systems.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：平均场博弈（Mean Field Games, MFGs）是建模大规模多智能体系统交互的强有力框架，可将智能体数量极大的多智能体强化学习问题简化为一个代表性智能体与群体分布之间的博弈。
- **现有局限**：目前的 RL 方法大多局限于**有限状态/动作空间**或**平稳（stationary）的平均场模型**，无法处理连续状态-动作空间以及非平稳（时间依赖）的群体动力学。此外，已有的连续空间方法（如 Perrin et al., 2021）只能学习一系列最佳响应策略的集合，不能直接输出纳什均衡策略；其他方法（如 Zaman et al., 2020）局限于线性二次型（LQ）模型；而 Laurière et al., 2022a 虽然能学习均衡策略，但仅限于离散空间。
- **动机**：因此，本文旨在设计一种**面向连续状态-动作空间且适用于非平稳动力学**的深度强化学习 MFG 求解器，能够同时学到均衡策略和时变的群体分布。

## 2. 方法论

- **核心思想**：基于**虚构博弈（Fictitious Play, FP）**框架，在每次迭代中：
  1. 用深度强化学习（DRL）计算针对上一轮平均分布的最佳响应策略；
  2. 通过监督学习（最小化负对数似然）将历史最佳响应策略平均化，得到一个参数化的平均策略网络；
  3. 利用**条件归一化流（Conditional Normalizing Flow, CNF）**学习时变的群体分布，从而能够既采样又直接计算密度。
- **关键技术细节**：
  - **最佳响应计算**：采用 Soft Actor-Critic (SAC) 或 Proximal Policy Optimization (PPO) 作为 DRL 算法（根据问题选择）。
  - **平均策略学习**：维护一个回放缓冲区，存储所有历史最佳响应产生的 (时间, 状态, 动作) 三元组；然后训练一个策略网络（MLP，输出高斯分布均值和方差）最小化负对数似然损失。
  - **平均分布学习**：使用**时间条件神经样条流（Time-Conditioned Neural Spline Flow）**学习密度 \(p(x|t)\)，通过最大似然估计训练，以便在训练和推理时快速采样并查询密度。
- **算法流程（DEDA-FP, Algo.3）**：
  1. 初始化策略网络和 CNF，以及回放缓冲区；
  2. 对于每次迭代 \(k=1..K\)：
     - 使用当前平均策略 \(\bar{\pi}_{k-1}\) 与环境交互，计算最佳响应 \(\pi^*_k\)（DRL）；
     - 收集新样本加入回放缓冲区；
     - 通过监督学习更新平均策略 \(\bar{\pi}_k\)；
     - 用 \(\bar{\pi}_k\) 生成轨迹，训练 CNF 更新平均分布 \(\bar{G}_k\)；
  3. 返回最终的平均策略 \(\bar{\pi}_K\) 和平均分布 \(\bar{G}_K\)。
- **收敛性分析**：定理1给出了可开发利用度（exploitability）的上界，表明算法收敛到近似纳什均衡的误差由最佳响应误差、平均策略误差和分布误差三者累积决定。

## 3. 实验设计

- **使用场景/数据集**：论文在三个连续空间非平稳 MFG 上验证：
  1. **Beach Bar Problem**：连续版沙酒吧问题（一维状态 \([0,1]\)），奖励包含密度依赖（拥堵避免）；
  2. **线性二次型（LQ）模型**：一维线性动力学，奖励含均值场耦合；
  3. **4-rooms Exploration**：二维连续空间，含障碍物（四房间），奖励含熵最大化（对数密度），群体从角落均匀扩散。
  此外，附录中还有一个**市场模型（Price Impact Model）**作为补充。
- **基准方法（Benchmark）**：
  - **Algo.1（Simple Approach）**：纯粹的 FP，使用均匀采样历史策略模拟群体，不学习平均策略或分布；
  - **Algo.2（Learning NE Policy）**：仅学习平均策略网络，但不显式建模平均分布，而是通过采样大量轨迹来近似；
  - **DEDA-FP (本文方法)**：同时学习策略网络和条件归一化流。
- **对比指标**：近似开发利用度（exploitability）和采样时间（用于评估效率）。

## 4. 资源与算力

- **明确说明**：使用一块 **NVIDIA RTX 4090 GPU（24 GB RAM）**进行所有实验。
- 训练时长：未给出具体总训练小时数，但给出每次实验的迭代次数（K=20 或更多），并报告了生成 5000 条轨迹的采样时间（DEDA-FP仅需1.52秒，而 Algo.1/2 需约15-16秒）。论文未提供完整的训练时间对比。

## 5. 实验数量与充分性

- **实验数量**：主实验涵盖 3 个场景（Beach Bar, LQ, 4-rooms），外加附录中 1 个场景（Market Model）。每个场景均执行 **4 次独立运行（4个随机种子）**，报告均值和标准差。
- **充分性与公平性**：
  - 对比了两种有代表性的基准方法，方法间的设置尽量一致（DRL 超参数等）。
  - 通过 exploitability 曲线和最终分布热力图进行定性定量对比。
  - 在 4-rooms 实验中专门讨论了固定时间预算下的采样效率，展示了 DEDA-FP 的显著优势。
  - 但缺乏消融实验（如单独去掉 CNF 或监督学习组件的效果），且仅在三个场景上验证，未见更大规模或更高维度的验证。

## 6. 主要结论与发现

- DEDA-FP 能够**首次**在连续状态-动作空间、非平稳 MFG 中同时学习纳什均衡策略和时变群体分布。
- 在三个测试场景中，DEDA-FP 的 exploitability 与基准方法相当或更优，且由于 CNF 能直接查询密度，在涉及局部密度依赖（如拥堵、熵）的问题中无需额外卷积近似，从而更加准确。
- **采样效率显著提升**：生成 5000 条轨迹的速度比采样基准方法快 **10 倍以上**（1.52s vs 15~16s），使大规模模拟成为可能。
- 定理1提供的误差传播分析从理论上支撑了算法的收敛性。

## 7. 优点

- **方法论创新**：首次将条件归一化流用于学习非平稳 MFG 的时变分布，兼具采样和密度估计功能，解决了现有方法在局部密度依赖场景中的短板。
- **实用性强**：模型无关，适用于一般形式的动力学和奖励，不局限于 LQ 等特例。
- **理论分析**：提供了收敛性分析（尽管在简化假设下），为算法提供了理论支撑。
- **实验设计合理**：采用多个复杂度递增的例子，并对比了消除 CNF 的基准（Algo.2），清晰展示了 CNF 带来的效率提升。
- **代码可复现**：虽然未在版本中公开代码，但提供了详细的超参数和架构描述，有利于复现。

## 8. 不足与局限

- **理论分析的局限**：收敛性分析依赖于 Lipschitz 假设，且并未证明算法在最一般形式下的严格收敛，对深度神经网络训练的分析仍不够深入。
- **实验覆盖不足**：
  - 仅验证了低维（1D 和 2D）问题，未在高维连续空间（如 10D+）中测试，尺度提升可能面临 CNF 训练困难。
  - 缺乏消融实验（例如单独评估最佳响应误差或分布误差的影响）。
  - 仅在 4 个种子下报告结果，统计稳定性有待更多实验验证。
- **评估依赖近似**：开发利用度本身是近似估计（基于有限样本的 DRL 最佳响应），无法获得真实纳什均衡的精确值。
- **尚未处理常见噪声和更复杂的设定**：如公共噪声、多群体 MFG、图博弈等扩展方向未被研究。
- **计算资源**：虽然采样快，但 CNF 的训练本身可能耗时（论文未给出 CNF 训练的详细时间），且 RL 部分的训练成本在复杂环境中可能很高。

（完）
