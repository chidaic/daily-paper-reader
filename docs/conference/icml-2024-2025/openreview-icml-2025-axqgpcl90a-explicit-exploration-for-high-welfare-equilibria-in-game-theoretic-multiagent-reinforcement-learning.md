---
title: Explicit Exploration for High-Welfare Equilibria in Game-Theoretic Multiagent Reinforcement Learning
title_zh: 面向高福利均衡的显式探索：博弈论多智能体强化学习方法
authors: "Austin A. Nguyen, Anri Gu, Michael P. Wellman"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=AxqgpcL90a"
tags: ["query:player-ai"]
score: 8.0
evidence: 多人博弈中面向AI智能体的均衡选择
tldr: 该论文针对多智能体博弈中均衡选择问题，在PSRO框架中引入显式探索以偏向高福利均衡，通过模仿高收益行为并正则化训练，无需额外仿真即可在复杂博弈中找到更优解。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1683, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 690, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1646, \"height\": 783, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 863, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 1360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 867, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1606, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1552, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1623, \"height\": 1719, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 415, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1761, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1358, \"height\": 981, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 890, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 747, \"height\": 469, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 894, \"height\": 125, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1341, \"height\": 1476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1236, \"height\": 1516, \"label\": \"Table\"}]"
motivation: 多智能体博弈中存在多个均衡，需选择具有特定性质的解。
method: 在PSRO中创建模仿高福利行为的探索策略，并正则化响应训练。
result: 在多种博弈中，该方法找到的均衡具有更高社会福利。
conclusion: 显式探索可有效指导多智能体博弈的均衡选择。
---

## Abstract
Iterative extension of empirical game models through deep reinforcement learning (RL) has proved an effective approach for finding equilibria in complex games. When multiple equilibria exist, we may also be interested in finding solutions with particular characteristics. We address this issue of equilibrium selection in the context of Policy Space Response Oracles (PSRO), a flexible game-solving framework based on deep RL, by skewing the strategy exploration process towards higher-welfare solutions. At each iteration, we create an exploration policy that imitates high welfare-yielding behavior and train a response to the current solution, regularized to be similar to the exploration policy. With no additional simulation expense, our approach, named Ex$^2$PSRO, tends to find higher welfare equilibria than vanilla PSRO in two benchmarks: a sequential bargaining game and a social dilemma game. Further experiments demonstrate Ex$^2$PSRO's composability with other PSRO variants and illuminate the relationship between exploration policy choice and algorithmic performance.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：多智能体强化学习（MARL）面临两大挑战：**可扩展性**（策略空间随智能体数量指数增长）和**非平稳性**（智能体策略相互影响导致学习环境动态变化）。Policy Space Response Oracles（PSRO）是一种通过深度强化学习迭代扩展经验博弈模型的有效框架，它通过集中训练一个智能体而固定其他智能体策略来解决上述挑战。
- **核心问题**：当博弈中存在多个纳什均衡时，如何从中选出**具有偏好的解**，特别是**社会福利更高的均衡**。现有PSRO方法可能收敛到帕累托占劣的均衡（例如图1中的例子），而单纯优化社会福利的响应目标（如GRO）也无法发现需要协同探索的高福利策略。
- **研究意义**：提出一种**显式探索**的方法，在不增加仿真开销的前提下，引导策略探索偏向高福利均衡，从而解决均衡选择问题。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：在PSRO的每次迭代中，从已经产生的仿真轨迹中筛选出**高福利的轨迹**，利用**行为克隆（Behavior Cloning, BC）**训练一个**探索策略**，然后通过在训练最佳响应时加入**KL散度正则化**项，使得新策略偏向该探索策略，从而引导策略发现更高福利的均衡。
- **关键技术细节**：
  - **轨迹筛选准则**：采用**最大最小福利（maximin welfare）**准则，即选择轨迹中最小玩家回报最大的N条轨迹，以保证高福利的同时避免牺牲任何单一玩家。
  - **探索策略训练**：对筛选出的轨迹使用行为克隆（交叉熵损失）训练一个策略网络π_ex^i，该策略不被加入经验博弈，仅用于正则化。
  - **正则化响应目标**：在训练第i次迭代的最佳响应π_θ^i时，在原始回报最大化目标J_i(θ)上加入β_i倍的KL散度惩罚项R_i(θ) = D_KL(π_ex^i || π_θ)，目标为：π_θ^i ≈ argmax_{π_θ} (J_i(θ) - β_i R_i(θ))。其中KL散度通过采样来自RL回放缓冲区的观测来估计。
  - **算法流程**（Ex²PSRO）：
    1. 初始化策略集Π（含随机策略），初始化经验博弈Γ，初始化轨迹缓冲B。
    2. 对于每次迭代i：
       - 若i>1，用缓冲B中前N条高福利轨迹训练探索策略π_ex^i。
       - 使用当前β_i和π_ex^i，通过SAC（Soft Actor-Critic）训练一个**正则化的最佳响应**π_θ^i。
       - 将π_θ^i加入Π，更新Γ，将本次仿真轨迹加入缓冲并重新筛选前N条高福利轨迹。
       - 元策略求解器（MSS）如正则化复制者动力学（RRD）输出当前联合策略σ^{i+1}。
       - 线性退火β_i直至0。
    3. 返回策略集Π和最终联合策略σ^T。
  - **关键区别**：采用SAC而非值函数方法（因正则化需要策略分布），且第一轮不进行正则化（初始随机策略生成的轨迹信息不足）。

### 3. 实验设计：使用了哪些数据集/场景，它的benchmark是什么，对比了哪些方法

- **实验场景**：
  1. **手工设计的MDP**：用于概念验证，有两个均衡——低福利的左右移动+1奖励与高福利的交替到达s7/s8。
  2. **Harvest（社交困境）**：网格世界游戏，玩家收集苹果（+1奖励），可以发射激光移除其他玩家。两个变种：
     - **Harvest-Dense**：苹果密集，初始靠近出生点。
     - **Harvest-Sparse**：苹果集中，需要更多协调。
  3. **Bargaining（讨价还价）**：两玩家轮流对物品分配出价，有私有估值，若协议超时则双方得零。两个变种：折扣因子γ=0.99和γ=0.95。
- **基准方法（Baselines）**：
  - **Vanilla PSRO**：标准PSRO，使用SAC训练最佳响应，无正则化。
  - **GRO（Generalized Response Objectives）**：优化社会福利的响应目标（α=0.8），属于竞争方法但论文主要用于展示可组合性。
  - **Ablation-π_ex**：四种探索策略变体：Uniform（均匀策略）、MinWelfare（低福利轨迹）、MaxWelfare（高福利但忽略分布）、PrevBR（上一轮最佳响应）。用于分析Ex²PSRO是否因正则化本身还是因特定任务选择而有效。
- **对比方法**：主要对比Vanilla PSRO以及Ablation-π_ex各变体。同时展示Ex²PSRO与GRO的组合使用（GRO+Ex²PSRO）。

### 4. 资源与算力

- **算力资源**：所有实验在**密歇根大学研究计算集群**上运行，使用**CPU**（未明确说明GPU）。每个PSRO/Ex²PSRO/Ablation运行需**2–4天**（共训练30个RL策略）。Ex²PSRO变体需要**8–12 GB RAM**（存储轨迹缓冲），Vanilla PSRO需5 GB，Ablation及组合实验需12–15 GB。额外的真实遗憾计算需**3–4天**和5 GB RAM。
- **算力规模**：未提供GPU型号或数量，表明实验可能完全基于CPU。

### 5. 实验数量与充分性

- **实验总数**：每个游戏变体进行了：40次Vanilla PSRO（调参λ）、105次Ex²PSRO（100次网格搜索 + 5次最终参数复现）、40次Ablation-π_ex（每种变体10次）。共4个基准，总计**740次独立试验**。
- **充分性**：
  - 进行了**超参数调优**：SAC超参数、β_init、λ等，采用网格搜索并报告最佳参数下的10次平均结果（Ex²PSRO最终为10次，调参阶段为5次）。
  - 提供了**显著性检验**（Welch t-test），比较Ex²PSRO与Baseline的福利差异。
  - 进行了**消融实验**：改变探索策略、改变β_init或λ。
  - **可组合性实验**：与GRO结合。
  - **遗憾-福利分析**：不仅报告最终福利，还提供遗憾值（近似真实博弈遗憾），并注意了Ex²PSRO遗憾计算更严格（额外评估了正则化策略），使对比偏向保守。
- **公平性**：作者承认Vanilla PSRO经过更充分的调优（每个λ 10次），而Ex²PSRO调优较保守（5次后选最佳再5次），可能导致Ex²PSRO性能被低估。总体上实验设计系统且较为全面。

### 6. 论文的主要结论与发现

- **Ex²PSRO在所有四个基准中均比Vanilla PSRO找到更高福利的均衡**，且P值均低于0.05（Harvest-Dense p<0.01, Harvest-Sparse p<0.01, Bargaining γ=0.99 p=0.04, γ=0.95 p=0.03）。
- **在与Ablation-π_ex的对比中**，Ex²PSRO一致优于均匀、最低福利、上一轮最佳响应等变体（Harvest中与Uniform差异不显著，但Bargaining中显著）。表明**正则化方向（任务选择）比单纯的正则化强度更重要**。
- **可组合性**：Ex²PSRO可与GRO结合，进一步改善福利（除了Harvest-Sparse中GRO+Ex²PSRO略低于Ex²PSRO，但P值0.07不显著，其他场景显著优于GRO）。
- **遗憾分析**：Ex²PSRO通常能较快收敛到低遗憾、高福利解，且遗憾评估对其更严格但依然表现良好。
- **方法无需额外仿真**（利用已有轨迹），是一种简单而有效的扩展。

### 7. 优点

- **方法简单且高效**：不增加仿真开销，只利用已有数据训练探索策略并加入正则化项。
- **与现有PSRO框架兼容**：可无侵入地整合到任何基于策略梯度的PSRO变体中（如GRO）。
- **实验设计系统**：在多场景、多基准、多组合下验证，包含消融、显著性检验、遗憾分析。
- **公平性注意**：作者明确指出了自己方法在遗憾计算上更严格，并承认可能低估性能，增强了可信度。

### 8. 不足与局限

- **计算资源**：完全依赖CPU，训练耗时较长（每试验2–4天），未利用GPU加速，可能限制扩展性。
- **调优保守**：Ex²PSRO超参数调优仅5次，可能未达到最优；而Vanilla PSRO有10次调优，对比可能不公平（但已向有利于Baseline的方向）。
- **实验环境有限**：仅测试了两种博弈（Harvest和Bargaining）及各自两个变种，通用性仍需更广泛的基准（如扑克、混合合作竞争等）验证。
- **对非对称博弈的讨论不足**：论文仅处理对称博弈，提到扩展到非对称博弈需进行玩家回报归一化及独立探索策略，但未实验验证。
- **轨迹缓冲区大小与准则的鲁棒性**：缓冲大小和筛选准则（前N条）为启发式选择，未经系统性调优；随机性可能影响结果（局部最优轨迹污染）。
- **正则化可能引入偏差**：若高福利轨迹中包含偶然成功或次优行为，行为克隆可能误导探索策略，尤其是在稀疏奖励环境中。
- **未能完全解决帕累托占优问题**：如手工MDP示例中，该方法成功发现高福利均衡，但未理论保证总能找到全局最高福利均衡。

（完）
