---
title: "Decoding Rewards in Competitive Games: Inverse Game Theory with Entropy Regularization"
title_zh: 竞争游戏中奖励的解码：基于熵正则化的逆博弈理论
authors: "Junyi Liao, Zihan Zhu, Ethan X Fang, Zhuoran Yang, Vahid Tarokh"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=L47M0km5dq"
tags: ["query:player-ai"]
score: 7.0
evidence: 从玩家行为恢复奖励函数用于玩家建模
tldr: 针对从玩家行为估计奖励函数的逆问题，提出结合熵正则化的统一框架，建立基于线性假设的量化反应均衡可辨识性，并设计算法从有限观测中恢复奖励，实验验证了方法的准确性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-l47m0km5dq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 834, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l47m0km5dq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 524, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-l47m0km5dq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 574, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-l47m0km5dq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 736, \"height\": 285, \"label\": \"Table\"}]"
motivation: 逆游戏中奖励函数恢复具有固有歧义性和非唯一性，数据覆盖有限。
method: 利用量化反应均衡建立可辨识性，提出基于熵正则化的奖励恢复算法。
result: 在矩阵博弈和马尔可夫博弈中成功恢复奖励，优于基线。
conclusion: 提供逆博弈理论的实用方法，有助于理解玩家行为。
---

## Abstract
Estimating the unknown reward functions driving agents' behavior is a central challenge in inverse games and reinforcement learning. This paper introduces a unified framework for reward function recovery in two-player zero-sum matrix games and Markov games with entropy regularization. Given observed player strategies and actions, we aim to reconstruct the underlying reward functions. This task is challenging due to the inherent ambiguity of inverse problems, the non-uniqueness of feasible rewards, and limited observational data coverage. To address these challenges, we establish reward function identifiability using the quantal response equilibrium (QRE) under linear assumptions. Building on this theoretical foundation, we propose an algorithm to learn reward from observed actions, designed to capture all plausible reward parameters by constructing confidence sets. Our algorithm works in both static and dynamic settings and is adaptable to incorporate other methods, such as Maximum Likelihood Estimation (MLE). We provide strong theoretical guarantees for the reliability and sample-efficiency of our algorithm. Empirical results demonstrate the framework’s effectiveness in accurately recovering reward functions across various scenarios, offering new insights into decision-making in competitive environments.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在两人零和博弈（静态矩阵博弈和动态马尔可夫博弈）中，从观测到的玩家策略和动作序列中逆向恢复未知的奖励函数。这是一类**逆强化学习（IRL）**在竞争环境下的扩展，即**逆博弈理论**问题。
- **挑战**：
  - 逆问题本身的不适定性（ill-posed），即多个奖励函数可能对应同一个均衡策略。
  - 非唯一性：若无额外约束，可行奖励参数不唯一。
  - 离线情境下数据集覆盖有限，难以保证稳健的恢复。
- **研究动机**：在经济学、网络安全、机器人、自主系统中理解敌方或对手的决策动机；优化资源配置、建模战略互动等。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用**熵正则化**（Soft-Q学习/Quantal Response Equilibrium, QRE）将逆问题转化为可辨识的线性系统，并构建置信集以捕捉所有可行奖励参数。
- **技术细节**：
  - **强可辨识性**：假设奖励函数为线性形式 \( Q(a,b) = \langle \phi(a,b), \theta^* \rangle \)。在QRE均衡下，最优策略满足固定点方程，可简化为关于θ的线性方程组（公式2）。通过秩条件（式3）判断唯一性。
  - **两阶段估计法**：
    1. 用频率估计器从样本估计QRE策略 \(\hat{\mu}, \hat{\nu}\)。
    2. 通过最小二乘（或Moore–Penrose伪逆）求解θ，得到闭式解（式5）。
  - **部分可辨识时的置信集**：当秩条件不满足时，构造形如式(6)的置信集 \(\hat{\Theta}_N\)，包含所有满足约束且满足 \(\|\theta\|\le M\) 的参数。证明Hausdorff距离以 \(O(N^{-1/2})\) 收敛于真实可行集。
  - **扩展到马尔可夫博弈**：
    - 假设线性MDP（特征映射ϕ），将Q函数和奖励函数参数化。
    - 逐时间步构建类似线性系统（式12），得到Q函数的置信集。
    - 使用岭回归估计转移核。
    - 通过Bellman方程（式14）从Q函数和V函数恢复奖励。
  - **选择最小范数解**：当系统秩不足时，采用伪逆得到最小范数估计，避免过拟合。

### 3. 实验设计：数据集/场景、benchmark、对比方法

- **实验场景**：仅展示了**熵正则化的两人零和马尔可夫博弈**（矩阵博弈的实验文中提到但未展开）。
  - 状态空间 \(S=4\)，动作空间 \(m=n=5\)，水平线 \(H=6\)，特征维度 \(d=2\)。
  - 真实参数 \(\omega_h = (0.8, -0.6)^\top\)，熵正则化系数 \(\eta=0.5\)。
  - 置信集参数：\(\theta\) 范数界 \(R=10\)，阈值 \(\kappa_h = 10^3/N\)，岭回归 \(\lambda=0.01\)。
- **评估指标**：
  - 奖励函数重建误差 \(\|\hat{r}_h - r_h^*\|_F\)。
  - QRE误差：总变差距离 \(TV(\hat{\mu}_h, \mu_h^*) + TV(\hat{\nu}_h, \nu_h^*)\)。
- **对比方法**：**未提及任何基线/对比方法**，只是单独展示了本算法的结果随样本量变化。
- **数据集**：模拟生成的轨迹数据，样本量从 \(10^4\) 到 \(10^5\)。

### 4. 资源与算力

- 文中仅在实验开头提到“All experiments are conducted in Google Colab”，**未明确说明GPU型号、数量、训练时长等具体资源信息**。

### 5. 实验数量与充分性

- **实验数量**：马尔可夫博弈实验中，每个样本量（10k, 20k, 50k, 100k）进行了 **100次重复**（repetitions），并报告均值和95%置信区间（Table 1）。
- **充分性**：
  - 正向：重复实验提供了统计可靠性，置信区间较窄。
  - 不足：
    - 仅测试了单一特征维度（d=2）、单一奖励参数、单一动作空间大小、单一状态空间大小。
    - 未做消融实验（如不同熵参数η、不同正则化强度、不同线性假设的破坏等）。
    - 未与任何基线方法（如直接MLE、无正则化的逆强化学习等）比较。
    - 矩阵博弈部分没有给出数值实验，仅提及“数值实验验证”，但文中未显示具体结果。

### 6. 论文的主要结论与发现

- 理论上建立了熵正则化零和博弈中奖励函数可辨识的充要条件（秩条件）。
- 证明了所提算法在有限样本下估计误差以 \(O(N^{-1/2})\) 收敛，且置信集以相同速率收敛于真实可行集。
- 数值实验中，随着样本量从10k增加到100k，奖励重建误差和QRE策略误差均显著下降，验证了理论的一致性。
- 即使奖励函数估计误差相对较大（约1.4~2.5），对应的QRE策略误差却很小（~10^{-3}量级），表明该方法能很好地解释观测行为。

### 7. 优点：方法或实验设计上的亮点

- **理论贡献扎实**：完整给出了强可辨识性的秩条件，以及部分辨识时的置信集收敛性定理，证明严格。
- **框架统一**：同时覆盖静态矩阵博弈和动态马尔可夫博弈，并且可扩展至MLE等估计器。
- **处理非唯一性**：不强行选择一个点估计，而是输出所有可行奖励参数的集合，更符合逆问题本质。
- **样本效率有保证**：理论误差界明确依赖特征维数和动作空间大小，给出实际指导。

### 8. 不足与局限

- **实验覆盖不全面**：
  - 无矩阵博弈的数值结果。
  - 仅测试了一种线性特征（d=2），未测试高维或非线性情况。
  - 未与其他逆强化学习/逆博弈方法（如MaxEnt IRL、对抗性IRL）做对比。
  - 缺少消融实验（如去掉熵正则化、改变η、不同正则化强度的影响）。
- **偏差风险**：
  - 假设线性MDP和C-well-posedness（每个状态被充分访问），在实际复杂环境中可能难以满足。
  - 只使用了频率估计器，虽然可扩展至MLE，但未比较不同估计器的效果。
- **应用限制**：
  - 仅适用于两人零和博弈，未扩展到一般和博弈或其他多人博弈。
  - 离线场景假设数据集是独立同分布且来自真实QRE，若行为策略有偏差或部分可观测性，则方法可能失效。
- **算力与复现**：未提供开源代码或详细超参数调节细节，依赖Google Colab，可复现性不够透明。

（完）
