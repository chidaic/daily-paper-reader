---
title: Opponent Modeling based on Subgoal Inference
title_zh: 基于子目标推断的对手建模
authors: "XiaoPeng Yu, Jiechuan Jiang, Zongqing Lu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=Lt6wO0oZ8k"
tags: ["query:player-ai"]
score: 9.0
evidence: 通过子目标推断实现对对手的建模，用于多智能体环境
tldr: 本文提出基于子目标推断的对手建模方法，从历史轨迹中推断对手的子目标。由于子目标可能在不同对手策略中共享，这种方法能更好地泛化到未知对手。在复杂多智能体任务中，该方法比单纯预测动作的对手建模具有更好的适应性和性能。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 583, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1374, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1416, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1299, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1357, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1181, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1420, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1335, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1027, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1050, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lt6wo0oz8k/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1423, \"height\": 437, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-lt6wo0oz8k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 723, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lt6wo0oz8k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1039, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lt6wo0oz8k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 881, \"height\": 144, \"label\": \"Table\"}]"
motivation: 预测对手动作的方法对未知对手适应性有限。
method: 通过历史轨迹推断对手的子目标，利用子目标的共享性提高泛化。
result: 在复杂任务中优于预测动作的基线方法。
conclusion: 子目标推断是对手建模的有效策略。
---

## Abstract
When an agent is in a multi-agent environment, it may face previously unseen opponents, and it is a challenge to cooperate with other agents to accomplish the task together or to maximize its own rewards. Most opponent modeling methods deal with the non-stationarity caused by unknown opponent policies via predicting the opponent’s actions. However, focusing on the opponent’s action is shortsighted, which also constrains the adaptability to unknown opponents in complex tasks. In this paper, we propose opponent modeling based on subgoal inference, which infers the opponent’s subgoals through historical trajectories. As subgoals are likely to be shared by different opponent policies, predicting subgoals can yield better generalization to unknown opponents. Additionally, we design two subgoal selection modes for cooperative games and general-sum games respectively. Empirically, we show that our method achieves more effective adaptation than existing methods in a variety of tasks.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在多智能体环境中，自利智能体（autonomous agent）经常需要面对事先未知的对手策略。传统对手建模方法主要通过预测对手的下一动作来应对环境非平稳性，但这种“短视”的方法在复杂任务中泛化能力不足，因为同一目标可由多种不同的动作序列实现，且动作空间复杂度远高于目标空间。
- **整体含义**：论文提出基于**子目标推断**的对手建模（OMG），即从对手的历史轨迹中推断其长远的子目标（subgoal），而非仅关注即时动作。由于不同对手策略可能共享相同的子目标（如都走向某个地图点），预测子目标能显著提升对未知对手的泛化能力，并降低学习难度。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将对手的轨迹视为由一连串子目标构成，子目标对应对手未来要达到的某个状态的特征嵌入。通过推断子目标，智能体可以更好地预测对手意图，并据此优化自身策略。
- **关键技术细节**：
  - **子目标推断模型**：采用**条件变分自编码器（CVAE）**，以历史轨迹 $\tau_t$ 为条件，推断对手的子目标 $\hat{g}_t$。优化目标为：
    \[
    \arg\max_{\theta,\phi} \mathbb{E}_{q_\phi(\hat{g}_t|\tau_t,s_t)}[\log p_\theta(s_t|\hat{g}_t,\tau_t)] - \text{KL}\big(q_\phi(\hat{g}_t|\tau_t,s_t) \parallel p_\psi(\bar{g}_t|s_{g_t})\big)
    \]
    其中 $p_\psi$ 是预训练的VAE（用环境状态训练），提供子目标先验分布。
  - **子目标选择器**：在更新阶段，从未来 $H$ 步的状态集合 $N_t^H$ 中，基于价值函数 $V(s,g)=\mathbb{E}_a Q(s,g,a)$ 选择子目标状态 $s_{g_t}$：
    - 合作博弈（cooperative games）：选择使 $V(s,g)$ 最大的状态（乐观策略，类似 maximax）。
    - 一般和博弈（general-sum games）：选择使 $V(s,g)$ 最小的状态（保守策略，类似 minimax）。
  - **策略学习**：将推断的子目标 $\hat{g}$ 与当前状态 $s$ 共同作为Q函数的输入，更新方式（公式4）：
    \[
    Q(s_t,g_t,a_t) = \mathbb{E}_{P}[r + \gamma \max_a Q(s_{t+1},g_t,a)]
    \]
    训练初期使用混合目标 $g_t = \hat{g}_t$ 或 $\bar{g}_t$（按衰减概率替换），以稳定训练。
- **算法流程**（Algorithm 1）：
  1. 预训练子目标先验VAE。
  2. 交互阶段：用当前推断子目标 $\hat{g}$ 选择动作。
  3. 更新阶段：用子目标选择器获得 $\bar{g}$，结合 $\hat{g}$ 得到 $g$，更新Q网络和CVAE。

### 3. 实验设计：使用了哪些数据集/场景，它的 benchmark 是什么，对比了哪些方法
- **场景**：
  - **Foraging**（$8\times8$ 网格世界）：收集食物，与对手竞争资源。
  - **Predator-Prey**（连续空间）：三个捕食者协作追捕猎物，智能体控制其中一个捕食者。
  - **SMAC**（StarCraft II 多人对战高维环境）：智能体与一组未知对手协作完成战斗任务（地图：8m、3s_vs_5z、2c_vs_64zg）。
- **基准（baseline）**：
  - **Naïve OM**：预测对手动作。
  - **LIAM**：基于编码-解码器提取对手表征。
  - **D3QN / PPO / IQL**：无对手建模的经典强化学习算法（分别用于不同场景）。
  - 此外比较了OMG的两种变体：**OMG-optimistic**（乐观子目标选择）和**OMG-conservative**（保守子目标选择）。
- **对手策略**：训练时使用10种不同预训练策略；测试时使用30种不同策略（由IQL、VDN、QMIX训练的同质/异质策略）。

### 4. 资源与算力
- 文中明确说明（附录B）：
  - CPU：**Intel(R) Xeon(R) Platinum 8280 CPU @ 2.70GHz**。
  - GPU：**NVIDIA A100-PCIE-40GB**。
  - 未提供具体训练时长或GPU数量，仅提到上述硬件配置。

### 5. 实验数量与充分性
- **实验数量**：
  - 三个主要场景（Foraging、Predator-Prey、SMAC），SMAC下用了三个地图。
  - 消融实验：对比了CVAE vs 监督学习、不同子目标选择策略（随机、第1步、第3步）、子目标输入方式（$g$ vs $\hat{g}$ vs $\bar{g}$）、超参数 $H$（1,3,5,10）。
  - 子目标命中率分析。
  - 附录中还对CTDE方法（QMIX）在自主智能体任务上的表现进行了补充实验。
- **充分性**：实验较为充分，覆盖了离散/连续状态空间、合作/一般和博弈、同质/异质对手、多角度消融。所有方法重复5个随机种子并报告均值±标准差，统计合理。但测试集对手数量（30个）及训练对手多样性（10种）对于泛化性验证尚有提升空间。

### 6. 论文的主要结论与发现
- OMG（尤其是乐观变体）在三个场景中均优于所有基于动作建模的基线，在SMAC上对未知对手的泛化能力显著更强。
- 子目标推断比动作推断学习更快，因为 $(s,g)$ 对的数量远少于 $(s,a_{-i})$，缩小了状态-动作空间。
- 乐观子目标选择适用于合作游戏，保守选择适用于一般和游戏；乐观变体在SMAC合作任务中表现最好。
- 子目标命中率随训练逐步提高，说明模型能够学到有意义的未来状态预测。
- 适当选择子目标窗口 $H$（实验中 $H=5$ 或 $10$ 较优）对性能至关重要。

### 7. 优点
- **方法论创新**：从预测动作转向预测子目标，抓住了对手长期意图，降低了策略波动和状态空间复杂度。
- **泛化性强**：利用子目标的组合特性，提升了对未见对手的适应能力。
- **灵活性**：两种子目标选择模式适配不同类型博弈，可嵌入Q学习或策略梯度算法。
- **实验设计全面**：覆盖经典基准、多种环境、消融分析、子目标可视化，验证了各组件有效性。

### 8. 不足与局限
- **开放多智能体系统**：无法处理智能体在交互过程中加入或离开的动态场景。
- **对手策略固定**：假设测试时对手策略固定，未考虑对手在线学习（如Meta-MAPG场景）。
- **子目标命中率中等**：由于多步预测和对手行为受自身影响，子目标命中率在训练结束时仍不够高（约0.14）。
- **计算开销**：在SMAC等大规模环境中，CVAE和子目标选择器可能增加训练时间（未量化比较）。
- **超参数敏感**：窗口 $H$ 需要调优，选择不当会损害性能。
- **实验限制**：对手策略主要基于统一框架（QMIX、VDN、IQL），现实场景中对手可能更加多样，泛化性需进一步验证。

（完）
