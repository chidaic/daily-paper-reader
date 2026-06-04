---
title: Sample-Efficient Tabular Self-Play for Offline Robust Reinforcement Learning
title_zh: 面向离线鲁棒强化学习的表格型自对弈样本有效方法
authors: "Na Li, Zewu Zheng, Wei Ni, Hangguan Shan, Wenjie Zhang, Xinyu Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=xVsC90U8yl"
tags: ["query:player-ai"]
score: 8.0
evidence: 在双人零和马尔可夫博弈中采用自对弈的鲁棒RL，直接适用于游戏AI
tldr: 本文聚焦离线环境下鲁棒双人零和马尔可夫博弈，提出RTZ-VI-LCB算法，通过乐观鲁棒值迭代结合数据驱动的Bernstein惩罚项，在部分覆盖条件下实现了近最优样本复杂度。该方法为游戏智能体在离线数据下学习鲁棒策略提供了理论保证。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xvsc90u8yl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1420, \"height\": 412, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xvsc90u8yl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1173, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xvsc90u8yl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 834, \"height\": 147, \"label\": \"Table\"}]"
motivation: 多智能体强化学习面临环境不确定性，离线策略需要鲁棒性以应对模拟到现实的差距。
method: 提出RTZ-VI-LCB算法，结合乐观值迭代和伯恩斯坦惩罚项进行鲁棒值估计。
result: 建立了近最优样本复杂度保证，适用于部分覆盖的离线数据集。
conclusion: 为离线鲁棒多智能体博弈学习提供了高效算法，可用于游戏AI训练。
---

## Abstract
Multi-agent reinforcement learning (MARL), as a thriving field, explores how multiple agents independently make decisions in a shared dynamic environment. Due to environmental uncertainties, policies in MARL must remain robust to tackle the sim-to-real gap. We focus on robust two-player zero-sum Markov games (TZMGs) in offline settings, specifically on tabular robust TZMGs (RTZMGs). We propose a model-based algorithm (*RTZ-VI-LCB*) for offline RTZMGs, which is optimistic robust value iteration combined with a data-driven Bernstein-style penalty term for robust value estimation. By accounting for distribution shifts in the historical dataset, the proposed algorithm establishes near-optimal sample complexity guarantees under partial coverage and environmental uncertainty. An information-theoretic lower bound is developed to confirm the tightness of our algorithm's sample complexity, which is optimal regarding both state and action spaces. To the best of our knowledge, RTZ-VI-LCB is the first to attain this optimality, sets a new benchmark for offline RTZMGs, and is validated experimentally.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：多智能体强化学习（MARL）在游戏、自动驾驶等领域备受关注。离线MARL利用历史数据降低交互成本，但现实环境的不确定性（如模型误差、噪声、sim-to-real差距）导致标准算法极易发生灾难性失败。鲁棒性因此成为关键。
- **核心问题**：针对离线环境下鲁棒双人零和马尔可夫博弈（RTZMG），如何在**部分状态-动作覆盖**（即历史数据仅覆盖部分空间）以及**环境不确定性**的双重挑战下，以最少的样本数量学习到ε-最优鲁棒纳什均衡策略。
- **意义**：现有方法（如P2M2PO）样本复杂度较高，且未能刻画不确定性水平的影响。本文首次在表格型RTZMG中实现关于状态空间大小S和动作空间大小A、B的最优样本复杂度依赖，为离线鲁棒多智能体学习建立了新基准。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程（文字说明）

- **算法名称**：RTZ-VI-LCB（Robust Tabular Zero-sum Value Iteration with Lower Confidence Bounds）
- **整体思路**：构建经验名义MDP（基于历史数据估计转移核$\hat{P}^0$和奖励$\hat{r}$），然后执行**乐观鲁棒值迭代**，并在每次更新时引入**数据驱动的Bernstein风格惩罚项**来刻画不确定性，保证估计的乐观性（即真实最优值被上界覆盖）。
- **关键技术细节**：
  1. **两阶段子采样（Algorithm 1）**：将数据集分为两个不重叠的子集，利用“修剪计数”消除样本间依赖，使得后续分析可假定样本独立。
  2. **鲁棒Q值更新**：对每个时间步$h$和状态-动作对$(s,a,b)$，计算：
     $$
     \hat{Q}^+_h(s,a,b) = \min\left\{ \hat{r}_h(s,a,b) + \inf_{P \in \mathcal{U}^{\sigma^+}(\hat{P}^0_{h,s,a,b})} P \hat{V}^+_{h+1} + \beta_h(s,a,b,\hat{V}^+_{h+1}), H \right\}
     $$
     $\hat{Q}^-_h$ 同理（使用上确界）。
  3. **惩罚项**：采用Bernstein型惩罚：
     $$
     \beta_h(s,a,b,\hat{V}) = \min\left\{ \max\left\{ \sqrt{\frac{C_n \log(KH/\delta)}{N_h(s,a,b)} \cdot \mathrm{Var}_{\hat{P}^0_{h,s,a,b}}(\hat{V})},\; \frac{2C_n H \log(KH/\delta)}{N_h(s,a,b)} \right\}, H \right\}
     $$
  4. **对偶问题求解**：利用TV距离的强对偶性，将内层$\inf/\sup$转化为可计算的形式（见Lemma B.1），避免直接优化$S$维概率单纯形。
  5. **策略提取**：对每个状态$s$，求解零和矩阵博弈的纳什均衡得到$\mu^+_h(s),\nu^+_h(s)$以及$\mu^-_h(s),\nu^-_h(s)$。最终输出策略为$\hat{\mu}=\{\mu^-_h\},\hat{\nu}=\{\nu^+_h\}$。
- **新概念**：提出“鲁棒单边剪枝集中性系数”$C^*_r$（Definition 4.1），衡量历史数据与目标策略下的分布差异，是理论分析的关键。

### 3. 实验设计：数据集/场景、基准、对比方法

- **场景**：采用随机生成的转移核（代码基于[39]），状态数$S=50$，每个玩家的动作数$A=B=2$，时域$H=100$，**不涉及真实数据集**或标准游戏benchmark（如围棋、Atari等）。数据集由行为策略收集的$K$条独立轨迹构成。
- **对比方法**：仅与**RTZ-VI**（即不含下置信界（LCB）的鲁棒值迭代）对比，未与其他现有算法（如P2M2PO）进行实验对比（作者仅在表中理论比较）。
- **评估指标**：值函数差距 $|V^{*,+}(\varrho) - V^{*,-}(\varrho)|$ 随状态索引的变化，以及随样本量$K$的变化。

### 4. 资源与算力

- 文中明确指出：实验使用 **PyTorch 2.0.0**，**单张NVIDIA RTX 4090 24GB GPU**。
- **训练时长**：未明确给出具体小时数，仅提及“averaged over 100 seeds”，实验规模较小（$S=50$, $H=100$, $A=B=2$），计算资源需求不高。

### 5. 实验数量与充分性

- **实验数量**：主要呈现三张图：图1(a)展示值差距与状态索引（$K=e^5$），图1(b)展示值差距与样本量$K$（从$10^2$到$10^4$），图1(c)展示log-log关系以验证理论斜率$-0.49$。
- **充分性评价**：实验较为**有限**，仅有自对比且未在多样化的游戏场景或真实离线数据集上评估。作者将其作为理论结果的辅助验证，而非全面基准测试。性测试在100个随机种子下进行，具有一定的统计可靠性，但**缺乏与SOTA算法的直接比较**（如P2M2PO），公平性难以评估。

### 6. 论文的主要结论与发现

- **样本复杂度上界**：RTZ-VI-LCB在TV距离不确定性集下，使用$K$条轨迹，可达到：
  $$
  \mathrm{Gap}(\hat{\mu},\hat{\nu}) \le c_1 \sqrt{\frac{C^*_r H^3 S(A+B)\log(KH/\delta)}{K} \cdot f(\sigma^+,\sigma^-,H)}
  $$
  其中$f$刻画不确定性水平影响。当样本数超过$\tilde{O}\left( C^*_r H^4 S(A+B)/\varepsilon^2 \cdot f \right)$时，算法找到$\varepsilon$-鲁棒NE。
- **下界匹配**：定理4.4给出了信息论下界，表明上述复杂度关于$S$和$A+B$是最优的。
- **扩展**：算法可推广至多玩家一般和博弈（Multi-RTZ-VI-LCB），避免多智能体诅咒。

### 7. 优点：方法或实验设计上的亮点

- **理论贡献突出**：首次在离线RTZMG中实现关于$S$和$A+B$的最优样本复杂度，填补了领域空白。
- **算法设计精巧**：
  - 两阶段子采样方案有效解耦统计依赖。
  - Bernstein惩罚项自适应地利用方差信息，比传统Hoeffding型惩罚更紧。
  - 引入“鲁棒单边剪枝集中性”系数替代全局集中性，更贴合部分覆盖设定。
- **对偶形式计算高效**：利用TV距离的强对偶将鲁棒优化转化为可求解的形式。
- **实验验证理论**：图1(c)的log-log线性拟合斜率$-0.49$与理论预测$-0.5$吻合，增强了置信度。

### 8. 不足与局限

- **实验覆盖不足**：仅在随机生成的表格型问题上测试，未与现有主流算法（如P2M2PO、DRO-based方法）横向对比，也未在标准MDP/MARL benchmark（如围棋、电网、自动驾驶模拟）上评估。
- **假设较强**：算法基于TV距离不确定性集、表格型状态-动作空间、奖励已知且确定性等假设，实际应用可能不满足。
- **可扩展性问题**：算法需要求解每个状态-动作对的鲁棒优化和矩阵博弈，当$S,A,B$较大时计算成本高（文中未提供时间分析）。
- **未讨论局限性**：论文未在单独章节讨论限制，例如对行为策略覆盖质量的依赖$C^*_r$无法显式估计，以及奖励确定性的假设对实际噪声的鲁棒性。
- **泛化能力**：仅证明表格型下理论最优，向连续状态/函数近似推广仍需后续工作。

（完）
