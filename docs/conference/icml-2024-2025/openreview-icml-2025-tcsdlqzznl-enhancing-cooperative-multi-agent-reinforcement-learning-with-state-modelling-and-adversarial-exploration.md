---
title: Enhancing Cooperative Multi-Agent Reinforcement Learning with State Modelling and Adversarial Exploration
title_zh: 利用状态建模与对抗探索增强合作多智能体强化学习
authors: "Andreas Kontogiannis, Konstantinos Papathanasiou, Yi Shen, Giorgos Stamou, Michael M. Zavlanos, George Vouros"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=TCsdlqzZNL"
tags: ["query:player-ai"]
score: 7.0
evidence: 合作多智能体强化学习的状态建模与对抗探索
tldr: 本文针对分布式部分可观测环境中的多智能体合作问题，提出一种状态建模框架。每个智能体从局部观测推断有意义的状态信念表示，结合对抗性探索策略，过滤冗余信息以优化合作策略。实验表明，该方法在多种合作任务中显著提升协同性能。该工作可应用于游戏中的多智能体团队协作场景。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1482, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1411, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1047, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1696, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1258, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 710, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 463, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 485, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 752, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 947, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1470, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1459, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1762, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 734, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1567, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1765, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 580, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 569, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 567, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1728, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 682, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 691, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1457, \"height\": 890, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1687, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 568, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1653, \"height\": 1026, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 532, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 724, \"height\": 1143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 744, \"height\": 1012, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 537, \"height\": 795, \"label\": \"Table\"}]"
motivation: 部分可观测环境下无通信的多智能体合作挑战大。
method: 提出状态建模框架，智能体推断信念表示，结合对抗性探索。
result: 在合作任务中协同性能显著提升。
conclusion: 状态建模与对抗探索有效增强MARL合作。
---

## Abstract
Learning to cooperate in distributed partially observable environments with no communication abilities poses significant challenges for multi-agent deep reinforcement learning (MARL). This paper addresses key concerns in this domain, focusing on inferring state representations from individual agent observations and leveraging these representations to enhance agents' exploration and collaborative task execution policies. To this end, we propose a novel state modelling framework for cooperative MARL, where agents infer meaningful belief representations of the non-observable state, with respect to optimizing their own policies, while filtering redundant and less informative joint state information. Building upon this framework, we propose the MARL SMPE$^2$ algorithm. In SMPE$^2$, agents enhance their own policy's discriminative abilities under partial observability, explicitly by incorporating their beliefs into the policy network, and implicitly by adopting an adversarial type of exploration policies which encourages agents to discover novel, high-value states while improving the discriminative abilities of others. Experimentally, we show that SMPE$^2$ outperforms a plethora of state-of-the-art MARL algorithms in complex fully cooperative tasks from the MPE, LBF, and RWARE benchmarks.

---

## 论文详细总结（自动生成）

# 1. 核心问题与整体含义（研究动机和背景）

- 论文聚焦于**分布式部分可观测、无通信**环境下的**合作多智能体强化学习（MARL）**问题。
- 关键挑战：智能体仅能观测局部信息，难以推断全局状态；非平稳性使协作困难；稀疏奖励场景中探索效率低下。
- 现有方法（如对手建模）往往存在以下不足：
  - 状态表示的学习与策略优化目标**脱节**；
  - 未过滤冗余/非信息性状态特征，损害策略性能；
  - 未利用状态表示指导探索，在稀疏奖励任务中效果差。
- 本文旨在回答两个核心问题：
  - Q1：能否从局部观测中推断出**有助于策略优化的有意义状态信念**？
  - Q2：能否利用该信念表示**高效探索**，发现更优策略？

# 2. 方法论

## 2.1 核心思想

- 提出**状态建模（State Modelling, SM）**优化框架：每个智能体 i 从局部观测 o_i 推断出潜在信念 z_i，使得 z_i 包含对**优化自身策略有益**的未观测状态信息，同时**过滤冗余**特征。
- 基于该框架设计算法 **SMPE²**（State Modelling for Policy Enhancement through Exploration），包含两个并行模块：
  1. **自监督状态建模**：通过变分自编码器（VAE）重建其他智能体的**过滤后观测**，学习信念表示。
  2. **对抗性探索**：基于信念 z_i 的计数内在奖励（SimHash），激励智能体发现新观测，从而帮助其他智能体改善建模能力。

## 2.2 关键技术细节

- **VAE 结构**：
  - 编码器 q_{ω_i}(z_i|o_i) 输出高斯分布；
  - 解码器 p_{ϕ_i}(w_i·o_{-i}|z_i) 重建经**AM滤波器** w_i 加权后的其他智能体观测。
- **AM滤波器** w_i：
  - 可学习权重（sigmoid 激活），表示其他智能体观测中各特征对智能体 i 的重要程度。
  - 目标：滤除非信息性特征（既不能从 z_i 推断、又对奖励最大化和策略无益的特征）。
- **损失函数**：
  - 重建损失 L_rec：均方误差，目标为 ˜w_i·o_{-i}（使用目标网络 ˜w_i 稳定训练）。
  - KL 散度 L_KL：使 z_i 接近标准正态先验。
  - L2 正则化 L_norm：防止 w_i 衰减为 0。
  - 额外 critic 损失 L_w_critic：基于过滤后状态 ŝ = o_i ⊕ (w_i·o_{-i}) 的 TD 误差，确保 w_i 与策略优化对齐。
  - 总编码损失：L_encodings = L_w_critic + λ_rec L_rec + λ_norm L_norm + λ_KL L_KL。
- **策略与批评**：
  - Actor：π_{ψ_i}(a_i^t|h_i^t, z_i^t)，即策略网络额外输入信念 z_i。
  - 两个 Critic：标准 V_ξ(s) 和基于过滤状态的 V_k(ŝ)，均采用 MAA2C 的 TD 损失。
- **对抗性探索**：
  - 对 z_i 进行 SimHash，计算内在奖励 ˆr_i = 1/√n(SH(z_i))，总奖励 ˜r_i = r_i + β ˆr_i。
  - 动机：智能体 i 探索新观测 → 产生新 z_i → 他智能体的重建误差增大 → 迫使他们改进建模，形成对抗性合作探索。
  - 为稳定训练，对 VAE 参数进行周期性硬更新。

## 2.3 算法流程（文字描述）

1. 初始化环境和网络参数。
2. 每个时间步：智能体 i 观测 o_i → 采样 z_i → 依据 π_{ψ_i}(a_i|h_i, z_i) 选择动作 → 执行并得到奖励 → 计算内在奖励 → 存储经验。
3. 批次训练：更新 actor、两个 critic、VAE 和 AM 滤波器（依据各损失项）。
4. 定期更新目标网络。

# 3. 实验设计

## 3.1 使用的基准与场景

- **MPE**（Multi-agent Particle Environment）：Spread（3/4/5/8 agents）和 Double Speaker-Listener（2 agents）。密集奖励，用于验证状态建模效果（不使用内在奖励）。
- **LBF**（Level-Based Foraging）：6 个任务，难度递增（如 2s-9x9-3p-2f、4s-11x11-3p-2f、7s-20x20-5p-3f）。稀疏奖励，测试完整 SMPE²。
- **RWARE**（Multi-Robot Warehouse）：3 个困难任务（tiny-2ag-hard, tiny-4ag-hard, small-4ag-hard）。稀疏奖励，高部分可观测性。

## 3.2 对比方法

- 基础 MARL 算法：MAA2C、COMA、MAPPO、QMIX、ATM（Transformer-based）。
- 内在探索方法：EOI（多样性）、EMC（好奇心）、MASER（子目标生成）。
- 对手建模方法：LIAM（多智能体扩展 MLIAM）、SIDE。
- 消融变体：SMPE（无内在奖励）、SMPE²（无 filters、无 KL、无 L2 norm、标准 SimHash 替代对抗探索、单 critic 等）。

# 4. 资源与算力

- **论文未明确说明使用的 GPU 型号、数量或具体训练时长**（仅给出了部分任务的总运行时间比较，如 LBF 2s-12x12-2p-2f 任务上 SMPE² 耗时 1h13m，而 EMC 需 1d5h）。
- 未提及训练时使用的计算集群或硬件配置细节，因此无法准确评估其算力需求。

# 5. 实验数量与充分性

- **实验数量**：在三个基准上共约 **13 个任务**（MPE 5 个，LBF 6 个，RWARE 3 个），每个任务平均 6 个随机种子。
- **充分性**：
  - 对比了 7 种以上 SOTA 方法，覆盖不同类别（CTDE、值分解、内在探索、对手建模）。
  - 消融实验：验证组件（filters、KL、L2 正则、内在奖励类型、critic 数量）、超参数（λ_rec、λ_norm）敏感性。
  - 可视化：t-SNE 分析信念 z_i 的聚类质量；AM filters 的可解释性展示。
  - 灵活性实验：将 SMPE² 与 MAPPO 结合（SMPE PPO），验证泛化性。
- **公平性**：使用相同评价指标（平均回合回报，25%-75% 置信区间），训练步数一致（MPE/LBF 10M，RWARE 40M）。多种随机种子确保统计可靠性。
- **结论**：实验设计全面、客观，充分支持论文结论。

# 6. 主要结论与发现

- **SMPE² 在所有复杂合作任务中显著优于现有 SOTA 方法**，特别是在 LBF 和 RWARE 的高难度稀疏奖励任务中，其他方法几乎零回报，而 SMPE² 能学习到有效策略。
- **状态建模**：通过 AM filters 过滤冗余信息、结合策略优化目标学习信念表示，是性能提升的关键。
- **对抗性探索**：基于信念的计数内在奖励能高效引导探索，并促进智能体间的建模协作。
- **消融验证**：缺失任何核心组件（filters、KL、内在奖励、双 critic）都会导致性能下降。
- **可解释性**：AM filters 能明确展示每个智能体关注哪些其他智能体的观测特征，与人类直觉一致。

# 7. 优点

- **方法创新性**：首次将状态建模与策略优化直接对齐（通过 L_w_critic 和双 critic），而非仅作为辅助任务。
- **AM filters 设计**：可学习、可解释，有效过滤干扰信息，提升表示质量。
- **对抗探索机制**：新颖的“以帮助他人建模为目标的探索”，内在奖励计算简单高效。
- **无需通信**：训练时利用全局信息，执行时仅需局部观测加信念，符合 CTDE 范式。
- **广泛适用**：与多种骨干算法（MAA2C、MAPPO）兼容，性能一致提升。
- **实验详实**：涵盖多种环境、多维度消融、可视化分析，使结论可信。
- **运行效率**：相比 EMC、MASER 等探索方法，SMPE² 训练时间显著缩短（如 LBF 任务中快 25~30 倍）。

# 8. 不足与局限

- **理论保证有限**：仅证明了状态建模目标与原始 Dec-POMDP 目标等价（Proposition 2.1），但未提供收敛性证明或样本复杂度分析。
- **超参数敏感**：λ_rec、λ_norm、λ_KL、β 等需任务调节，文中给出了参考值但未系统讨论其鲁棒性。
- **假设限制**：假设智能体在训练时可获取全局状态或他智能体观测（用于重建），在某些完全分布式训练设置中可能不现实。
- **未扩展到随机环境**：仅测试了确定性动力学环境；未论证在随机观测、嘈杂传感器等场景下的表现。
- **可扩展性未深入**：虽在 MPE 8 个智能体上测试，但 LBF 最大 7 个智能体，RWARE 最大 4 个；大规模（如 20 以上）情况有待验证。
- **代码开源但细节不足**：附录虽提供了实现细节和超参数表，但部分训练技巧（如网络结构层数、优化器选择）的讨论较简略。
- **与完全通信方法的对比缺失**：未与基于通信的 MARL 方法（如 CommNet、TarMAC）对比，尽管论文强调非通信场景，但这种对比能凸显建模的有效性。

（完）
