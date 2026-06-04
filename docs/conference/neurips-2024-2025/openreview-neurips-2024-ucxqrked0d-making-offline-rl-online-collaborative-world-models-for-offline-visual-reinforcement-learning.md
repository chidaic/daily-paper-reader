---
title: "Making Offline RL Online: Collaborative World Models for Offline Visual Reinforcement Learning"
title_zh: 将离线RL在线化：适用于离线视觉强化学习的协作世界模型
authors: "Qi Wang, Junming Yang, Yunbo Wang, Xin Jin, Wenjun Zeng, Xiaokang Yang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=ucxQrked0d"
tags: ["query:player-ai"]
score: 6.0
evidence: 利用现成RL模拟器作为离线策略的测试床，可应用于游戏智能体训练
tldr: 本文针对离线视觉强化学习中的过拟合和过估计问题，提出CoWorld方法，通过利用现成的在线RL模拟器作为测试床，建立更灵活的值函数约束。该方法有效缓解了跨领域分布偏移，为游戏智能体等离线训练场景提供了实用工具。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 757, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1330, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1436, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 1924, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1418, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1358, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ucxqrked0d/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1289, \"height\": 478, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1392, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1432, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1428, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1415, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1402, \"height\": 1038, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1447, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1373, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1394, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1356, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ucxqrked0d/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1214, \"height\": 515, \"label\": \"Table\"}]"
motivation: 离线视觉RL面临过拟合和过估计问题，现有保守行为方案限制了探索。
method: 提出CoWorld模型基RL方法，将在线模拟器与离线学习结合，通过世界模型实现知识迁移。
result: 在多个视觉控制任务上验证了CoWorld能有效提升离线策略性能。
conclusion: 证明了利用在线模拟器辅助离线RL的有效性，适用于游戏等视觉环境。
---

## Abstract
Training offline RL models using visual inputs poses two significant challenges, *i.e.*, the overfitting problem in representation learning and the overestimation bias for expected future rewards. Recent work has attempted to alleviate the overestimation bias by encouraging conservative behaviors. This paper, in contrast, tries to build more flexible constraints for value estimation without impeding the exploration of potential advantages. The key idea is to leverage off-the-shelf RL simulators, which can be easily interacted with in an online manner, as the “*test bed*” for offline policies. To enable effective online-to-offline knowledge transfer, we introduce CoWorld, a model-based RL approach that mitigates cross-domain discrepancies in state and reward spaces. Experimental results demonstrate the effectiveness of CoWorld, outperforming existing RL approaches by large margins.

---

## 论文详细总结（自动生成）

# 论文总结：CoWorld——将离线RL在线化

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：离线视觉强化学习（Offline Visual RL）面临两大核心挑战：
  1. **表征学习的过拟合问题**：从有限的、高维视觉输入中提取隐状态，容易过拟合。
  2. **值函数估计的过估计偏差**：对未来预期回报的估计容易偏乐观，导致策略不稳定。
- **现有局限**：已有工作通过鼓励保守行为来缓解过估计，但可能过度限制了对有潜力状态空间的探索。
- **核心思路**：利用现成的、可以在线交互的RL模拟器，作为离线策略的“测试床”，通过跨域知识迁移来同时缓解过拟合和过估计问题。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：将离线视觉RL重新框架化为一个**离线→在线→离线**的迁移学习问题，利用辅助在线环境训练一个“有知识的”源域智能体，为目标域离线策略提供更灵活的值函数约束。
- **关键技术细节**（CoWorld框架包含三个迭代阶段）：
  1. **Stage A：离线到在线的状态对齐**
     - 目标世界模型 \( M_{\phi} \) 与源世界模型 \( M_{\phi'} \) 共享相同架构。
     - 通过最小化源、目标编码器输出之间的KL散度（Domain Alignment Loss），对齐隐状态空间。
     - 防止目标模型在离线数据上过拟合，并获得更通用的隐状态。
  2. **Stage B：在线到离线的奖励对齐**
     - 使用混合数据（源域数据 + 目标域数据）训练源奖励预测器 \( r_{\phi'} \)。
     - 当使用目标域数据时，对源奖励进行**重标定**（Relabel）：\( \tilde{r}^{(S)}_t = (1-k) \cdot r_{\phi'}(\tilde{h}_t, \tilde{z}_t) + k \cdot r^{(T)}_t \)。
     - 使源智能体在评估目标策略时也了解目标任务的奖励信息。
  3. **Stage C：在线到离线的极小最大值值约束**
     - 引入一个**极小最大值值约束**（Min-Max Value Constraint）到目标评论家 \( v_{\xi} \) 的训练目标中。
     - 约束项：\( \alpha \cdot \max(v_{\xi}(\hat{z}^{(T)}_t), sg(v_{\xi'}(\hat{z}^{(T)}_t))) \)，其中 \( sg \) 为停止梯度。
     - **机制**：如果目标评论家过估计（\( v_{\xi} > v_{\xi'} \)），则惩罚目标评论家以降低估值；如果源评论家估值更高（\( v_{\xi'} > v_{\xi} \)），则约束项不贡献梯度，允许探索有潜力的状态。这实现了“温和保守”。
- **算法流程**：
  1. 预训练源智能体（DreamerV2）并收集源经验池 \( B^{(S)} \)。
  2. 循环迭代：
     - **离线阶段**：从 \( B^{(T)} \) 采样，更新目标世界模型（含状态对齐项），生成想象轨迹，用约束项更新目标评论家，更新目标演员。
     - **在线阶段**：从 \( B^{(S)} \) 和 \( B^{(T)} \) 采样，重标定源奖励，更新源世界模型（含奖励对齐），生成源域想象轨迹，更新源演员和评论家，并用源演员在在线环境中交互采集新数据。

## 3. 实验设计

- **数据集与场景**：
  - **Meta-World**：6种机械臂操作任务（如关窗、按钮等），用于**跨任务**迁移实验。
  - **RoboDesk → Meta-World**：**跨环境**迁移，源域为Meta-World，目标域为RoboDesk（物理动力学、动作空间、奖励尺度、视觉外观均不同）。
  - **DeepMind Control Suite (DMC)**：Walker和Cheetah机器人的变体（上下坡、无脚/无掌），用于**跨动力学**迁移实验。
- **Benchmark与对比方法**：
  - **模型基方法**：Offline DV2（基线）、LOMPO。
  - **模型无关方法**：DrQ+BC、CQL、CURL。
  - **迁移学习方法**：DV2 Finetune（在源域预训练后直接在目标域微调）、DV2 Finetune + EWC（弹性权重巩固，防止灾难性遗忘）、LOMPO Finetune。
  - **CoWorld变体**：CoWorld (Single-Source)、CoWorld (Multi-Source - 自适应选择最佳源域)。

## 4. 资源与算力

- 论文在附录B.7中报告了计算效率：
  - 在Meta-World (HP → BT) 任务上，使用**单张RTX 3090 GPU**。
  - CoWorld总训练时间为**3346分钟**（约2.3天），收敛（达到90%最高回报）约需**14小时**。
  - 与DV2 Finetune（总1933分钟，收敛约13小时）相比，CoWorld的训练墙钟时间相当，但性能显著更好。
- 未明确说明使用的GPU数量，但推断为单卡实验。

## 5. 实验数量与充分性

- **实验数量与覆盖**：
  - **跨任务实验**（Meta-World, 6类任务 × 3 seeds）：报告了每种方法在30个任务对上的平均回报。
  - **跨环境实验**（Meta-World → RoboDesk, 4个任务 × 3 seeds）：展示了CoWorld在显著域差距下的性能。
  - **跨动力学实验**（DMC, 6个任务对 × 3 seeds）。
  - **消融实验**：分别移除Stage A（状态对齐）、Stage B（奖励对齐）、Stage C（极小最大值值约束）以及将约束替换为暴力约束（w/o Max）进行验证。
  - **超参数敏感性分析**：对 \( \beta_2 \)（状态对齐）、\( k \)（奖励重标定因子）、\( \alpha \)（值约束权重）进行了敏感性分析。
  - **附加实验**：多源域自适应选择、不同观察空间（低维状态 vs 高维图像）、不同奖励形式（稀疏 vs 密集）、中专家混合数据集（Medium-Expert）、与预训练视觉基础模型（R3M）对比。
- **充分性与公平性**：实验设计全面，覆盖了多种域差距形式和核心设计选择。对比方法涵盖当前主流模型基和模型无关离线RL算法，且所有实验报告了3 seeds的均值和标准差，结果统计上可靠。消融实验充分验证了各模块的必要性。

## 6. 主要结论与发现

- **核心性能提升**：CoWorld在所有基准测试中大幅优于现有离线视觉RL方法。
  - 在Meta-World上，平均回报达4241，远高于Offline DV2（2730）和DV2 Finetune（3781）。
  - 在RoboDesk（跨环境）上，CoWorld以显著优势超越Offline DV2和DV2 Finetune。
  - 在DMC（跨动力学）上，平均回报达488，比Offline DV2（181）提升169.6%，比DrQ+BC（355）提升37.5%。
- **有效解决值过估计**：对比“CoWorld w/o Max”（暴力约束）和其他方法，CoWorld的估值与真实值偏差最小，实现了温和保守，避免了过度保守或过估计。
- **域差距鲁棒性**：在显著的观察空间、物理动力学、动作空间、奖励定义差异下，CoWorld依然能实现正向迁移，而DV2 Finetune和LOMPO Finetune常出现负迁移。
- **多源域自适应**：多源CoWorld能自动识别并选择最佳辅助域，性能接近手动选择最佳源域时的结果。

## 7. 优点

- **问题框架创新**：将离线视觉RL重新定义为离线→在线→在线的迁移学习问题，利用现成模拟器提供外部知识，而非仅依赖保守约束。
- **技术设计精巧**：通过“极小最大值”约束巧妙地实现了温和保守，避免了传统保守方法的过度限制；奖励重标定和状态对齐有效弥合了域差异。
- **实验全面且扎实**：覆盖多种环境、任务类型和域差距，消融实验充分，与多种基线公平对比，并报告了统计不确定性。
- **实用性**：在多个任务上对超参数不敏感，且在显著不同的观察空间和奖励形式下仍能工作，放宽了对源域相似性的要求。

## 8. 不足与局限

- **计算复杂度**：论文在附录B.7中指出，CoWorld的训练计算量高于DV2 Finetune（CoWorld 3346分钟 vs DV2 Finetune 1933分钟），虽远低于R3M等预训练模型，但训练效率有提升空间。
- **对模拟器的依赖**：方法假设存在可交互的在线辅助模拟器。在完全没有模拟器的任务（如某些医疗、物流场景）中，CoWorld不适用。
- **域差距的下限**：虽然论文展示了RoboDesk下的强域差距，但若源域和目标域在任务类型、物理定律上完全无关（如机器人操作 vs 自动驾驶），仍需验证性能边界（论文附录D对此有初步定性讨论）。
- **负迁移风险**：在多源域实验中，虽然自适应选择机制有效，但论文未深入探讨在所有源域都较差时，多源CoWorld是否可能降低（附录C仅展示了有限子集）。
- **泛化性声明的局限**：论文在结论中提及“易扩展到多源域”，但实验仅验证了2个源域的设置，对更大规模源域集合的可扩展性未作充分证明。

（完）
