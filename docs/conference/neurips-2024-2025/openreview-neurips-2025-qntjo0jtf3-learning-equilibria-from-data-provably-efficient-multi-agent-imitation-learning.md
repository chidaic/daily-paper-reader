---
title: "Learning Equilibria from Data: Provably Efficient Multi-Agent Imitation Learning"
title_zh: 从数据中学习均衡：高效的多智能体模仿学习
authors: "Till Freihaut, Luca Viano, Volkan Cevher, Matthieu Geist, Giorgia Ramponi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QNtJO0jTf3"
tags: ["query:player-ai"]
score: 8.0
evidence: 在马尔可夫博弈中进行多智能体模仿学习以学习均衡
tldr: 本文首次刻画了在马尔可夫博弈中从专家数据学习纳什均衡所需的专家样本复杂度。针对行为克隆在复杂对弈中的不足，提出了MAIL-BRO和MURMAIL两种算法，分别通过最佳响应查询和绕过集中性系数的方式高效学习均衡，为多智能体博弈中的AI agent训练提供了理论保障。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qntjo0jtf3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 768, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qntjo0jtf3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qntjo0jtf3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 591, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qntjo0jtf3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 728, \"height\": 341, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qntjo0jtf3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 515, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qntjo0jtf3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 2077, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qntjo0jtf3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1277, \"height\": 1000, \"label\": \"Table\"}]"
motivation: 现有模仿学习方法缺乏对博弈环境中样本复杂度的理论分析，且行为克隆在高集中性系数场景下表现不佳。
method: "提出MAIL-BRO算法，利用最佳响应预言机以O(ε^{-4})次专家和预言机查询学习ε-纳什均衡；以及MURMAIL算法绕过集中性系数。"
result: 在理论上给出了非交互模仿学习中不可避免的集中性系数下界，并证明了所提算法的样本有效性。
conclusion: 为多智能体博弈中从专家数据学习均衡提供了理论基础和高效算法。
---

## Abstract
This paper provides the first expert sample complexity characterization for learning a Nash equilibrium from expert data in Markov Games.
We show that a new quantity named the *single policy deviation concentrability coefficient* is unavoidable in the non-interactive imitation learning setting, and we provide an upper bound for behavioral cloning (BC) featuring such coefficient. BC exhibits substantial regret in games with high concentrability coefficient, leading us to utilize expert queries to develop and introduce two novel solution algorithms: MAIL-BRO and MURMAIL. The former employs a best response oracle and learns an $\varepsilon$-Nash equilibrium with $\mathcal{O}(\varepsilon^{-4})$ expert and oracle queries. The latter bypasses completely the best response oracle at the cost of a worse expert query complexity of order  $\mathcal{O}(\varepsilon^{-8})$. Finally, we provide numerical evidence, confirming our theoretical findings.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在多智能体系统中（如自动驾驶、交通灯控制、游戏），设计奖励函数非常困难，因为需要定义多个可能冲突的目标。然而，专家数据通常可得，因此多智能体模仿学习（MAIL）成为一种重要方法，以学习在未知奖励的马尔可夫博弈（MG）中表现良好的策略。与单智能体模仿学习不同，MAIL中策略的性能依赖于其他智能体的策略。目标是达到一个无需任何智能体单方面偏离其策略的状态，即纳什均衡（NE）。本文关注两人零和马尔可夫博弈，并采用纳什差距（Nash Gap）作为衡量策略对接近NE程度的指标。
- **背景与问题**：现有工作（Tang et al., 2024）虽然提出了MAIL的误差传播分析，但未能刻画从专家数据学习ε-NE所需的专家样本复杂度，且其算法（BLADES和MALICE）的计算复杂度随状态数呈指数增长。本文旨在提供首个关于MAIL样本复杂度的理论分析，并实现多项式复杂度，避免指数依赖。
- **核心挑战**：在非交互式MAIL中，行为克隆（BC）面临“全策略偏差集中性系数”（all policy deviation concentrability coefficient）的困境，该系数在非交互设置中不可避免。当该系数无限大时，即使拥有无限专家数据且已知转移模型，任何非交互算法也无法学习到均衡，从而严格区分了MAIL与单智能体模仿学习。

## 2. 论文提出的方法论

### 核心思想

论文首先分析行为克隆（BC）在两人零和马尔可夫博弈中的样本复杂度上界，揭示其依赖于一个名为“全策略偏差集中性系数”的新量。为克服该系数，论文提出两种交互式模仿学习算法：

- **MAIL-BRO**（Multi-Agent Imitation Learning with Best Response Oracle）：假设存在一个“最佳响应预言机”（Best Response Oracle），可生成针对当前策略的最佳响应策略。利用该预言机，算法通过在线镜像下降（Online Mirror Descent）更新策略，并构造无偏梯度估计，从而避免集中性系数。
- **MURMAIL**（Maximum Uncertainty Response Multi-Agent Imitation Learning）：在无法获得最佳响应预言机的情况下，用“最大不确定性响应”策略来上界替代最佳响应。该策略通过求解一个单智能体MDP（奖励为当前策略与专家策略的平方距离）来最大化访问不确定状态的几率。内层使用UCBVI算法求解该MDP，外层仍采用在线镜像下降更新。

### 关键技术细节

1. **行为克隆（BC）上界**：使用性能差异引理、总变差距离和集中不等式，导出Nash Gap上界为 $O\left(C_{\max} \frac{8}{(1-\gamma)^2} \sqrt{\frac{|S||A_{\max}|\log^2(2|S|/\delta)}{N}}\right)$，其中 $C_{\max}$ 是全策略偏差集中性系数。
2. **MAIL-BRO**（算法1）：
   - 每次迭代查询BR预言机获取 $\mu_k^* \in \text{br}(\nu_k)$ 和 $\nu_k^* \in \text{br}(\mu_k)$。
   - 从分布 $d_{\mu_k,\nu_k^*}$ 和 $d_{\mu_k^*,\nu_k}$ 采样状态，从专家策略采样动作，构建无偏梯度估计 $g_{\mu_k}, g_{\nu_k}$。
   - 使用指数权重更新策略：$\mu_{k+1}(a|s) \propto \mu_k(a|s)\exp(-\eta g_{\mu_k}(s,a))$（KL散度做Bregman散度的镜像下降）。
   - 复杂度：$O(\varepsilon^{-4})$ 次专家和预言机查询，得到 $\varepsilon$-NE。
3. **MURMAIL**（算法2）：
   - 不使用BR预言机，代之以求解两个单智能体MDP的最大不确定性回应：$y_k \in \arg\max_{\nu \in \Pi} \mathbb{E}_{s\sim d_{\mu_k,\nu}}[\|\mu_E(\cdot|s)-\mu_k(\cdot|s)\|^2]$（对$\nu$），以及 $z_k$ 类似。
   - 使用UCBVI算法求解该MDP（内层循环T步），获得近似最优策略。
   - 外循环与MAIL-BRO类似，使用采样和镜像下降更新策略。
   - 复杂度：$O(\varepsilon^{-8})$ 次专家查询。
4. **下界**：构造了一个两人零和马尔可夫博弈（图1），其中 $C(\mu_E,\nu_E)=\infty$，证明任何非交互算法在此博弈上的Nash Gap至少为 $(1-\gamma)^{-1}$，即使已知转移模型也无法避免。

## 3. 实验设计

- **使用场景/环境**：
  - 下界构造中的马尔可夫博弈（图1）：通过调整不同纯纳什均衡的混合比例来控制系统 $C(\mu_E,\nu_E)$ 的大小。包括 $C(\mu_E,\nu_E)\le 2, \le 1000, \le 10000$ 以及 $\infty$ 四种情况。
  - 另一个随机生成的10状态、3动作的零和马尔可夫博弈（$C(\mu_E,\nu_E)<\infty$），用于额外对照。
- **基准方法**：对比了行为克隆（BC）和MURMAIL（算法2）。注意MAIL-BRO需要BR预言机，实验未包含。
- **评估指标**：Nash Gap（衡量策略对接近NE的程度）。
- **实验设置**：折扣因子 $\gamma=0.9$，使用标准值迭代计算Nash Gap，每个设置运行1000次不同随机种子，取平均结果。

## 4. 资源与算力

论文未明确提及使用的GPU型号、数量或训练时长。实验均在标准笔记本电脑上完成，因为环境规模较小（状态数最多10个，动作空间3个），仅作为概念验证。因此算力需求很低，不具备大规模计算资源的参考价值。

## 5. 实验数量与充分性

- **实验组数**：主要报告了4种 $C(\mu_E,\nu_E)$ 取值下的对比（图2），以及一个随机环境下的额外对比（图4）。每个条件运行1000次随机种子。
- **充分性评估**：
  - 实验展示了BC在 $C$ 有限时随数据量增加Nash Gap下降，在 $C=\infty$ 时失败；MURMAIL在所有情况下均能降低Nash Gap，但收敛速度较慢。结果与理论预测一致。
  - 但实验仅包含单一博弈构造和一个随机博弈，环境规模较小（状态数少）。缺乏对更复杂博弈（如多动作、大状态空间）的验证，且未与MAIL-BRO比较（因需BR预言机）。
  - 只对比了BC和MURMAIL，未包含其他MAIL算法（如Tang等人的BLADES和MALICE），因为那些算法计算复杂度指数级难以运行。
- **客观性**：误差棒（标准差）显示在各设置下结果稳定。整体实验设计合理，但广度有限。

## 6. 论文的主要结论与发现

1. **首次给出MAIL的专家样本复杂度刻画**：BC的Nash Gap上界依赖于全策略偏差集中性系数 $C_{\max}$，且该系数在非交互设置中不可避免（定理3.1和3.2）。
2. **分离MAIL与单智能体模仿学习**：展示了一个已知转移模型也无法挽救的零和博弈，证明非交互MAIL中必须依赖集中性系数或交互式专家。
3. **提出两种交互式算法**：
   - **MAIL-BRO**：利用最佳响应预言机，以 $O(\varepsilon^{-4})$ 复杂度实现 $\varepsilon$-NE，完全避免集中性系数。
   - **MURMAIL**：无需预言机，通过最大不确定性回应和内层RL求解，以 $O(\varepsilon^{-8})$ 复杂度实现 $\varepsilon$-NE。
4. 实验验证了理论：BC在集中性系数高时失败，MURMAIL成功。

## 7. 优点

- **理论贡献突出**：首次提供了MAIL中学习纳什均衡的样本复杂度分析，明确了不可避免的集中性系数，严格证明了非交互设置的局限性。
- **算法设计创新**：
  - MAIL-BRO通过镜像下降和BR预言机高效学习，具有多项式复杂度。
  - MURMAIL提出“最大不确定性回应”概念，将多智能体问题转化为可求解的单智能体MDP，避免了BR预言机。
- **算法可扩展到n玩家一般和博弈**（附录H），且避免了多智能体的指数 curse，具有分散化执行的性质。
- **数值实验**作为概念验证，清晰展示了理论预测的行为，支持结论。

## 8. 不足与局限

- **实验覆盖有限**：仅在小规模（状态数≤10）的构造环境和随机环境上验证，未在更大规模或更具挑战性的多智能体任务（如ATARI、StarCraft等）上测试。缺乏与现有MAIL算法（如BLADES/MALICE）的对比，虽然这些算法计算代价高昂。
- **理论界限可能不紧**：论文指出 $C_{\max} \ge C(\mu_E,\nu_E)$，但未回答是否存在博弈使得 $C(\mu_E,\nu_E)$ 有界而 $C_{\max}$ 无限且非交互算法仍然失败，即理论下界与上界之间的差距未完全闭合。
- **MURMAIL复杂度高**：专家查询复杂度为 $O(\varepsilon^{-8})$，在实际中可能变得很大。作者也承认可以尝试用更快的 regret 分析来改进。
- **依赖专家查询**：交互式算法需要能够在线查询专家策略，这在某些应用中不可行。
- **深度强化学习扩展未验证**：分析基于表格马尔可夫博弈，扩展到深度神经网络时，内层的UCBVI需替换为DQN/SAC等，会引入理论和实践上的差距。
- **计算资源未报告**：虽然实验规模小，但论文未提供任何算力相关细节，对可重复性有一定影响。

（完）
