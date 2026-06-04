---
title: Learning Imperfect Information Extensive-form Games with Last-iterate Convergence under Bandit Feedback
title_zh: 在bandit反馈下学习不完美信息扩展式博弈的最后迭代收敛
authors: "Canzhe Zhao, Yutian Cheng, Jing Dong, Baoxiang Wang, Shuai Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=G5xO7oD5G7"
tags: ["query:player-ai"]
score: 8.0
evidence: 不完美信息博弈中的bandit反馈学习
tldr: 针对两人零和扩展式博弈中的学习问题，现有算法依赖全信息反馈或仅提供渐近收敛。本文提出一种基于负熵正则化和虚拟转移的算法，在bandit反馈设置下实现最后迭代收敛。理论证明收敛性，实验验证有效性，为不完美信息博弈中的在线学习提供了新方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-g5xo7od5g7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 1771, \"label\": \"Figure\"}]"
motivation: 现有不完美信息博弈学习算法需要全信息反馈或仅渐近收敛，缺乏bandit反馈下的高效方法。
method: 提出负熵正则化结合虚拟转移的算法，在信息集-动作空间上更新策略。
result: 理论证明算法具有最后迭代收敛性，实验验证了有效性。
conclusion: 该方法填补了bandit反馈下不完美信息博弈学习的空白，具有理论价值。
---

## Abstract
We investigate learning approximate Nash equilibrium (NE) policy profiles in two-player zero-sum imperfect information extensive-form games (IIEFGs) with last-iterate convergence guarantees. Existing algorithms either rely on full-information feedback or provide only asymptotic convergence rates. In contrast, we focus on the bandit feedback setting, where players receive feedback solely from the rewards associated with the experienced information set and action pairs in each episode. Our proposed algorithm employs a negentropy regularizer weighted by a "virtual transition" over the information set-action space to facilitate an efficient approximate policy update. Through a carefully designed virtual transition and leveraging the entropy regularization technique, we demonstrate finite-time last-iterate convergence to the NE with a rate of $\widetilde{\mathcal{O}}(k^{-\frac{1}{8}})$ under bandit feedback in each episode $k$. Empirical evaluations across various IIEFG instances show its competitive performance compared to baseline methods.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：在不完美信息扩展式博弈（IIEFGs）中，现有算法要么依赖全信息反馈（full-information feedback），要么仅能保证渐近收敛率。然而在现实场景中，玩家通常只能获得bandit反馈（即仅观察到自己所经历的信息集-动作对的奖励），且往往需要有限时间内的最后迭代收敛（last-iterate convergence）保证，而非平均策略收敛。
- **核心问题**：能否在bandit反馈下实现IIEFGs的有限时间最后迭代收敛？该问题曾被Fiegel等人（2023）明确提出。
- **整体含义**：本文首次证明在bandit反馈下，通过精心设计的虚拟转移加权负熵正则化器，可实现最后迭代收敛，填补了该方向的理论空白，并为实际不完美信息博弈（如扑克、麻将等）提供了可证明高效的学习算法。

#### 2. 方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：利用熵正则化技术将原双线性博弈转化为强凸-强凹结构，从而确保最后迭代收敛。关键创新在于使用“虚拟转移”（virtual transition）加权的负熵正则化器，而非传统膨胀负熵（dilated negentropy），以解决bandit反馈下稳定性项难以界定的问题。
- **关键技术细节**：
  - **虚拟转移构造**：通过动态规划（Algorithm 2）计算一个虚拟转移概率 \(p^x\)，最大化所有信息集上的最小“访问概率”，保证每个信息集都有足够的下界（Lemma B.1: \(1/p^x_{1:h}(x_h) \leq X\)），从而控制稳定性项中的放大因子。
  - **损失估计器**：使用乐观偏差损失估计器（Eq. 7），包含重要性加权项和熵正则化项。
  - **策略更新**：基于OMD（Online Mirror Descent）框架，在约束集 \(\Pi^{k+1}_{\max}\) 上进行投影（Algorithm 1），但实际可通过闭式解高效近似更新（Appendix A，Proposition A.1）。
  - **参数设置**：学习率 \(\eta_k = k^{-5/8}\)，探索参数 \(\gamma_k = k^{-3/8}\)，正则化强度 \(\varepsilon_k = k^{-1/8}\)。
- **算法流程**（文字说明）：
  1. 初始化：均匀策略，预计算虚拟转移 \(p^x\)。
  2. 每轮 \(k\)：玩家执行策略，观测轨迹，构造损失估计器。
  3. 使用OMD更新策略：\(\mu^{k+1} = \arg\min_{\mu \in \Pi^{k+1}_{\max}} \eta_k \langle \mu, \hat{\ell}^k \rangle + D_\psi(\mu, \mu^k)\)。
  4. 重复直至收敛。

#### 3. 实验设计
- **数据集/场景**：四个标准的IIEFG实例：Lewis Signaling、Kuhn Poker、Leduc Poker、Liars Dice（实现来自OpenSpiel库）。
- **基准方法**：三种平均迭代收敛算法——IXOMD (Kozuno et al., 2021)、BalancedOMD (Bai et al., 2022)、BalancedFTRL (Fiegel et al., 2023)。这些算法在理论上不具备最后迭代收敛保证。
- **对比方式**：绘制NE Gap（Eq. 1）随episode的变化曲线，对比最后迭代策略的性能。

#### 4. 资源与算力
- **硬件**：服务器配备Intel Xeon Gold CPU和251GiB系统内存，未使用GPU。
- **运行时长**：各游戏实例的运行时间分别为约10小时（Lewis Signaling）、12小时（Kuhn Poker）、13小时（Leduc Poker）、16小时（Liars Dice）。
- **超参数调整**：对所有算法进行了对数网格搜索（logarithmic grid search）选择学习率。

#### 5. 实验数量与充分性
- **实验数量**：在4个游戏实例上各进行了一组实验，没有明确的消融实验（如不同虚拟转移设计、不同正则化强度等），但通过超参数搜索进行了优化。
- **充分性与客观性**：实验覆盖了不同复杂度的IIEFG实例，对比了所有已知的平均迭代收敛基线方法，公平性较好。但缺少与最后迭代收敛算法的直接对比（因为本文是首个），且未给出多次随机种子下的统计结果或error bar，可能影响鲁棒性判断。总体而言，实验足够支撑论文的主要结论，但可进一步丰富。

#### 6. 主要结论与发现
- **理论**：算法在bandit反馈下以高概率达到 \(\widetilde{\mathcal{O}}((X+Y)[(XA+YB)^{1/2}+(X+Y)^{1/4}H]k^{-1/8})\) 的最后迭代收敛率；若只要求期望NE Gap，收敛率为 \(\widetilde{\mathcal{O}}((X+Y)[(X^2A+Y^2B)^{1/2}+(X+Y)^{1/4}H]k^{-1/6})\)。
- **实验**：所提算法在所有四个游戏实例中均取得具有竞争力或最佳的性能，尤其在大信息集/动作空间的游戏中优势更明显，验证了理论的有效性。

#### 7. 优点
- **理论创新**：首次在bandit反馈下证明IIEFGs的有限时间最后迭代收敛，解决了Fiegel等人提出的开放问题。
- **算法设计**：虚拟转移加权负熵巧妙地避免了耦合问题，且可通过动态规划高效计算；策略更新有闭合形式，计算效率高。
- **解耦性**：算法完全解耦（uncoupled），无需玩家间通信或共享随机数，适用于多智能体场景。
- **理论深度**：对稳定性项、偏差项、正则化项进行了精细分析，导出了依赖于信息集大小和动作空间的次优收敛率。

#### 8. 不足与局限
- **收敛率**：上界 \(\widetilde{\mathcal{O}}(k^{-1/8})\) 远低于信息论下界 \(\Omega(k^{-1/2})\)，间隙较大，作者承认可考虑乐观OMD/FTRL来改进。
- **知识要求**：构造虚拟转移需要已知游戏树结构，虽然可以通过单次遍历获得，但在大规模游戏（如无限制德州扑克）中可能不实用。作者也提供了使用普通负熵的替代方案（Theorem F.1），但收敛率更差且无闭式解。
- **实验局限**：
  - 未报告多次重复实验的统计波动（如标准差或置信区间）。
  - 缺少与最后迭代收敛算法的直接对比（因为该领域暂无其他同类算法）。
  - 未进行消融研究（如不同虚拟转移设计的影响、不同参数设置的影响）。
- **偏差风险**：由于仅测试了四个游戏实例，可能在某些更复杂的IIEFG中表现不如基线，结论的泛化性有限。

（完）
