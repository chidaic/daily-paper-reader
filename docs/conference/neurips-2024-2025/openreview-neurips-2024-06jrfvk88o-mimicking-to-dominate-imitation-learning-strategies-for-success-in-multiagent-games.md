---
title: "Mimicking To Dominate: Imitation Learning Strategies for Success in Multiagent Games"
title_zh: 模仿以制胜：多智能体游戏中的模仿学习策略
authors: "The Viet Bui, Tien Anh Mai, Thanh Hong Nguyen"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=06JRFVK88O"
tags: ["query:player-ai"]
score: 9.0
evidence: 在多智能体游戏中利用模仿学习进行对手建模
tldr: 针对多智能体游戏中对手策略导致的不确定性，本文利用模仿学习预测对手动作，并结合多智能体强化学习（MARL）训练Agent。该方法能处理隐藏动作和局部观测，在多个游戏环境中表现出更快的收敛和更强的性能，显著提升了Agent在复杂竞争环境中的决策能力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-06jrfvk88o/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-06jrfvk88o/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1461, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-06jrfvk88o/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-06jrfvk88o/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1186, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-06jrfvk88o/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1187, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-06jrfvk88o/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1047, \"height\": 1217, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-06jrfvk88o/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1310, \"height\": 959, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-06jrfvk88o/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 781, \"height\": 846, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-06jrfvk88o/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1196, \"height\": 384, \"label\": \"Table\"}]"
motivation: 多智能体游戏中对手策略复杂，现有方法收敛慢且不稳定。
method: 设计新的多智能体模仿学习模型预测对手动作，并与MARL算法结合。
result: 在多个游戏环境中实现更快收敛和更高胜率。
conclusion: 模仿学习有效提升多智能体游戏中的Agent表现。
---

## Abstract
Training agents in multi-agent games presents significant challenges due to their intricate nature. These challenges are exacerbated by dynamics influenced not only by the environment but also by strategies of opponents. Existing methods often struggle with slow convergence and instability.
To address these challenges, we harness the potential of imitation learning (IL) to comprehend and anticipate actions of the opponents, aiming to mitigate uncertainties with respect to the game dynamics.
Our key contributions include:
(i) a new multi-agent IL model for predicting next moves of the opponents - our model works with hidden actions of opponents and local observations;
(ii) a new multi-agent reinforcement learning (MARL) algorithm that combines our IL model and policy training into one single training process;
and (iii) extensive experiments in three challenging game environments, including an advanced version of the Star-Craft multi-agent challenge (i.e., SMACv2).
Experimental results show that our approach achieves superior performance compared to state-of-the-art MARL algorithms.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 一、核心问题与整体含义（研究动机和背景）

多智能体游戏中，环境动态不仅受环境本身影响，还受对手策略影响，导致现有强化学习方法收敛慢、不稳定。传统MARL方法（如QMIX、MADDPG、MAPPO）在面对复杂竞争场景时性能有限。本文旨在利用模仿学习（Imitation Learning, IL）来理解和预测对手动作，从而减少关于游戏动态的不确定性，提升智能体决策能力。

## 二、方法论：核心思想、关键技术细节

### 2.1 核心思想
- **问题设定**：部分可观测马尔可夫博弈，盟友智能体无法观测对手的动作，只能获取局部观测（包括自身和邻域内对手/盟友的状态）。
- **关键洞察**：将对手策略模仿问题转化为对手下一状态预测问题，因为对手动作不可观测，但下一状态可由环境转移间接反映。
- **创新点**：
  - 提出新的多智能体IL模型，**仅基于局部观测和隐藏动作**预测对手下一状态。
  - 将IL模型与多智能体PPO（MAPPO）整合到统一训练框架中，形成 **IMAX-PPO** 算法。

### 2.2 关键技术细节
1. **对手下一状态预测作为IL问题**：
   - 定义“专家”状态对 \(W = (S, A^\alpha_-)\)，其中 \(S\) 为全局状态，\(A^\alpha_-\) 为前一时刻盟友联合动作。
   - 专家“动作”空间即为原始状态空间，即预测下一全局状态 \(S'\)。
   - 采用最大熵逆强化学习框架，并借鉴 **IQ-Learn** 的思想，将奖励学习转化为Q函数学习。

2. **局部观测下的IL实现**：
   - 每个盟友智能体 \(i\) 使用局部观测 \(o_i^\alpha\) 和自身前一动作 \(a_{i,-}^\alpha\)，预测邻域内敌方的下一状态 \(S_i^{e,\text{next}}\)。
   - 使用共享策略网络 \(\hat{\Pi}^e_{\psi_\pi}\) 和Q网络 \(\hat{Q}^e_{\psi_Q}\)，所有智能体共享参数。
   - 损失函数为基于局部观测的IQ-Learn目标，包含值函数项和熵正则项。

3. **IMAX-PPO算法流程**：
   - 每个时间步，首先利用当前盟友策略收集轨迹，存入回放缓冲区。
   - **IL更新**：使用IQ-Learn方式更新Q网络和策略网络（基于局部观测）。
   - **盟友策略更新**：将原始观测 \(o_i^\alpha\) 与IL预测的敌方下一状态 \(S_i^{e,\text{next}}\) 拼接成增强输入，用于PPO策略网络（actor）和价值网络（critic）的更新。
   - 使用GAE计算优势函数，actor目标函数包含裁剪项，critic使用裁剪MSE损失。

4. **理论分析**：
   - 证明了IL目标对盟友策略变化具有稳定性：若盟友策略KL散度有界（\(\leq \epsilon\)），则IL损失的变化量级为 \(O(\sqrt{\epsilon})\)。

## 三、实验设计

### 3.1 数据集/场景与Benchmark
- **SMACv2**：星际争霸多智能体挑战的进阶版，包含15个子任务（三大种族：Protoss、Terran、Zerg，每个种族5种规模：5v5, 10v10, 10v11, 20v20, 20v23）。
- **Google Research Football (GRF)**：三个子任务（3_vs_1_with_keeper、easy counterattack、hard counterattack）。
- **Gold Miner**：修改版，包含三个难度级别（easy、medium、hard），每个为2v2场景。

### 3.2 对比方法
- 标准/基线：**MAPPO**、**IPPO**、**QMIX**、**QPLEX**
- 变体：
  - **Sup-MAPPO**：使用监督学习预测对手下一状态。
  - **IMAX-PPO (GAIL)**：使用GAIL替代IQ-Learn。
  - **IMAX-PPO (InQ)**：本文主算法（基于IQ-Learn的IMAX-PPO）。
- 每个实验报告32次独立运行的胜率（win-rate）。

## 四、资源与算力

论文附录C.3中提到：所有子任务在**GPU加速的HPC（高性能计算）**上同时训练。平均每个子任务需要**4-7天**的训练时间，取决于难度。由于计算资源限制，未测试其他超参数设置。未明确给出GPU型号和数量。

## 五、实验数量与充分性

- **SMACv2**：15个子任务 × 7种算法（MAPPO, IPPO, QMIX, QPLEX, Sup-MAPPO, IMAX-PPO(GAIL), IMAX-PPO(InQ)），结果呈现在表1和图2中。
- **GRF**：3个子任务 × 7种算法，结果在表1和图4。
- **Gold Miner**：3个子任务 × 7种算法，结果在表1和图5。
- **消融实验**：附录D将IMAX框架应用于QMIX（QMIX-IMAX），与QMIX、MAPPO、MAPPO-IMAX对比，涵盖6个SMACv2子任务。
- 所有实验均使用32随机种子取平均值，报告胜率曲线和最终胜率，具有统计显著性。
- **公平性**：对比方法使用了原作者推荐的超参数和架构，且IMAX-PPO与MAPPO共享相同的基础网络（MLP+GRU）和大部分超参数。

评价：实验覆盖三个不同复杂度环境，包含多种任务规模，对比了多种基线和方法变体，消融实验验证了IMAX框架的通用性。实验设计充分、客观、公平。

## 六、主要结论与发现

1. **IMAX-PPO (InQ) 在所有15个SMACv2子任务、3个GRF任务和3个Gold Miner任务上均显著优于所有基线**，尤其在复杂任务（如20v23）上提升幅度最大。
2. **IQ-Learn-based IL优于GAIL和监督学习**：IMAX-PPO(InQ) 稳定地高于 IMAX-PPO(GAIL) 和 Sup-MAPPO，表明逆Q方法在局部观测下的预测效果更好。
3. **快速收敛**：IMAX-PPO在训练早期即可达到较高胜率，得益于IL模块加速了对对手策略的理解。
4. **IMAX框架具有通用性**：消融实验显示 QMIX-IMAX 也能提升 QMIX 性能，但不如 MAPPO-IMAX 效果好。

## 七、优点

- **方法创新**：将IQ-Learn成功适配到多智能体竞争环境，解决了动作不可观测和局部观测的难题，理论分析了IL对盟友策略变化的稳定性。
- **训练效率**：IL与MARL端到端联合训练，无需分阶段或额外收集专家数据。
- **实验全面**：涵盖多个主流基准，对比多种SOTA方法和变体，消融实验验证了核心组件。
- **结果显著**：在几乎所有任务中大幅度超越现有方法，尤其在困难场景下表现出色。

## 八、不足与局限

- **前提假设**：假定敌方策略在训练过程中固定不变（虽然这是合作多智能体RL的标准设置，但限制了在对手持续学习场景下的适用性）。
- **计算资源**：训练时间较长（每个任务4-7天），且未充分探索超参数调优，可能影响最佳性能。
- **理论分析**：仅给出了IL损失对盟友策略变化的界，但未分析IL预测误差对最终策略性能的直接影响。
- **可扩展性**：方法基于MAPPO，可能无法直接迁移到其他MARL框架（如值分解方法），虽然消融实验显示对QMIX也有提升，但提升幅度较小。
- **实验局限性**：未涉及更多类型的竞争环境（如粒子世界、自动驾驶等）；也未测试不同IL方法在完全可观测环境下的对比。

（完）
