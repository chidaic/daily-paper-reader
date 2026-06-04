---
title: Robust Multi-Agent Reinforcement Learning with Stochastic Adversary
title_zh: 鲁棒多智能体强化学习与随机对抗者
authors: "Ziyuan Zhou, Guanjun Liu, Mengchu Zhou, Weiran Guo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=bnhFueOeav"
tags: ["query:player-ai"]
score: 4.0
evidence: 鲁棒多智能体强化学习与对抗训练
tldr: 该论文针对多智能体强化学习对观测扰动敏感的问题，提出随机对抗训练(ATSA)方法，在线训练一个随机对手与主角智能体共同进化，在多个MARL基准上显著增强鲁棒性，可应用于游戏中的多智能体训练。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 775, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 849, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 846, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1736, \"height\": 967, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1775, \"height\": 691, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1248, \"height\": 1005, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1769, \"height\": 1759, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1758, \"height\": 549, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1764, \"height\": 443, \"label\": \"Table\"}]"
motivation: 多智能体强化学习模型对观测扰动敏感，现有对抗训练方法过拟合特定扰动。
method: 提出ATSA，训练一个由随机导向器和生成器组成的随机对手与主角智能体在线对抗。
result: 在多智能体基准上提升了对抗鲁棒性。
conclusion: 随机对抗训练可有效增强多智能体系统的鲁棒性。
---

## Abstract
The performance of models trained by Multi-Agent Reinforcement Learning (MARL) is sensitive to perturbations in observations, lowering their trustworthiness in complex environments. Adversarial training is a valuable approach to enhance their performance robustness. However, existing methods often overfit to adversarial perturbations of observations and fail to incorporate prior information about the policy adopted by their protagonist agent, i.e., the primary one being trained. To address this important issue, this paper introduces Adversarial Training with Stochastic Adversary (ATSA), where the proposed adversary is trained online alongside the protagonist agent. The former consists of Stochastic Director (SDor) and SDor-guided generaTor (STor). SDor performs policy perturbations by minimizing the expected team reward of protagonists and maximizing the entropy of its policy, while STor generates adversarial perturbations of observations by following SDor's guidance. We prove that SDor's soft policy converges to a global optimum according to factorized maximum-entropy MARL and leads to the optimal adversary. This paper also introduces an SDor-STor loss function to quantify the difference between a) perturbations in the agent's policy and b) those advised by SDor. We evaluate our ATSA on StarCraft II tasks and autonomous driving scenarios, demonstrating that a) it is robust against diverse perturbations of observations while maintaining outstanding performance in perturbation-free environments, and b) it outperforms the state-of-the-art methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：多智能体强化学习（MARL）模型在复杂环境中对观测扰动高度敏感，导致可信度下降。现有的对抗训练方法（如FGSM、PAAD）往往过拟合于最强的观测扰动，在无扰动或弱扰动场景下性能显著退化；同时，这些方法未能充分利用主角智能体的策略先验信息来指导对手的学习。
- **整体含义**：本文旨在通过引入**随机对手**（Stochastic Adversary）来提升MARL的鲁棒性，避免过拟合问题，并使对手在训练中能自适应地利用主角策略信息，从而在不同扰动条件下均保持稳定性能。

### 2. 论文提出的方法论

- **核心思想**：在线联合训练一个**随机对手**和一个**主角智能体**。对手由两个组件构成：
  - **随机导向器（SDor）**：负责给出策略扰动建议（即动作层面的修改方向），其目标是最小化主角智能体团队的期望奖励，同时最大化自身策略的熵，从而鼓励探索、避免确定性过拟合。
  - **导向器引导的生成器（STor）**：负责根据SDor的建议，生成实际作用于观测的扰动（在ℓ∞球内），使主角智能体的决策变化与SDor的建议方向一致。
- **关键技术细节**：
  - 将问题建模为策略对抗Dec-POMDP（PD-POMDP），并引入因子化最大熵MARL框架。SDor的联合策略可因子化为个体策略的乘积，满足个体-全局最优条件。
  - 推导了最优联合软策略和个体软策略的解析形式（基于软Q函数与软价值函数），并证明了因子化软策略迭代的收敛性（Theorem 3.4）。
  - 设计**SDor-STor损失函数**（基于KL散度或交叉熵），量化SDor建议与STor实际产生的策略变化之间的差异，并通过梯度下降更新SDor的策略网络，使两者对齐。
- **算法流程**（文字说明）：
  1. 初始化SDor（含权重网络、联合/个体软价值网络、软Q网络）和主角智能体的策略网络。
  2. 每一时间步：SDor采样策略扰动建议 → STor根据该建议通过FGSM生成观测扰动 → 主角智能体基于扰动后的观测执行动作 → 环境返回奖励和下一状态。
  3. 存储经验到各自的经验池。每隔一定步数更新网络：SDor根据软贝尔曼误差更新Q网络和价值网络；根据策略梯度（含SDor-STor损失项）更新策略网络；主角智能体按原算法更新。

### 3. 实验设计

- **数据集/场景**：
  - **StarCraft II（SMAC）**：3个地图——3m（3个陆战队员）、3s3z（3个追猎者 vs 3个狂热者）、8m（8个陆战队员）。
  - **Connected and Autonomous Vehicles（CAV）**：高速道路自动驾驶混合交通场景（3辆自动驾驶车辆+1~4辆人类驾驶车辆）。
- **基准方法**：以VDN和QMIX为基础MARL算法，对比以下方法：
  - 无对手（NoAdv）、随机噪声（RN）
  - 对抗训练：FGSM、ATLA、PAAD
  - 鲁棒学习：PR、PR-REP、ERNIE
  - 随机对手：RAP、ROMANCE-p/s
  - 本文方法：ATSA
- **评估指标**：SMAC中使用胜率（Win Rate），CAV中使用平均累积奖励和碰撞率（Crash Rate）。报告了在不同对手（NoAdv、RN、FGSM、ATLA、PAAD、ATSA）下的平均性能。

### 4. 资源与算力

- 论文**未明确说明**所使用的算力资源（如GPU型号、数量、训练总时长等），仅在附录中描述了网络结构（MLP+GRU，隐藏层64维）和优化器（RMSprop，学习率0.0005）。因此无法评估其实际计算开销。

### 5. 实验数量与充分性

- **实验数量**：
  - 4个主要场景（3个SMAC + 1个CAV），每个场景下测试6种对手，报告了平均性能。
  - 消融实验：在3m和3s3z上移除SDor-STor损失函数（记为κ=0）进行对比。
  - 不同扰动范围测试：在3m上测试扰动上界0~0.25，步长0.05，比较ATSA与PAAD、NoAdv的鲁棒性。
  - 连续动作空间初步实验：在MPE环境的捕食者-猎物任务中使用MADDPG和FACMAC作为基础算法。
  - 涉及42次统计显著性检验（Wilcoxon秩和检验，p<0.05）。
- **充分性与客观性**：实验覆盖了离散动作、大小型场景、多种对抗方法，并进行了随机种子下的多次重复。消融和扰动范围测试验证了各组件的贡献和泛化性。但连续动作空间实验仅一个场景，且性能提升不显著，说明该方法在连续控制上仍有局限。整体上实验设计较全面，结论可信。

### 6. 论文的主要结论与发现

- ATSA在SMAC和CAV上均取得了最高的平均胜率/奖励，且**在无扰动环境下的性能并未下降**，克服了以往对抗训练方法的过拟合问题。
- 理论证明了SDor的因子化软策略迭代收敛到全局最优，且与STor结合能导出最优随机观测对手。
- SDor-STor损失函数有效缩小了策略扰动建议与实际观测扰动之间的差距，进一步提升了鲁棒性。
- 在攻击性能分析中，ATSA训练的对手能够暴露其他方法的弱点（如FGSM对自身扰动过拟合），体现了更强的攻击多样性。

### 7. 优点

- **方法创新**：首次在MARL中引入基于最大熵的随机对手，有效缓解了过拟合问题；设计了对齐策略扰动的损失函数，使理论最优性与实际可操作性统一。
- **理论贡献**：证明了因子化软策略迭代的收敛性以及随机对手的最优性，为方法提供了理论支撑。
- **实验验证**：在多个标准基准上进行了全面对比，包含消融、扰动范围分析和统计检验，结果具有说服力。
- **实用性**：方法基于CTDE范式，可与现有价值分解算法（VDN、QMIX）无缝集成。

### 8. 不足与局限

- **连续动作空间局限性**：在MPE连续任务中，ATSA在FACMAC上表现不突出，作者承认高维连续动作域下的对抗优化困难，未来需改进。
- **算力消耗未报告**：未提供训练所需GPU型号、数量和时长，难以评估实际部署成本。
- **超参数敏感性**：损失函数权重κ需根据环境和基础算法手动调参（0.001~0.025），可能增加调优难度。
- **适用场景限制**：当前仅验证了离散动作空间的MARL（SMAC和CAV中的动作均为离散），对连续动作领域的推广尚不成熟。
- **模型复杂度**：引入了额外的对手网络（SDor含多种网络），可能增加训练内存和计算时间，但文中未量化。

（完）
