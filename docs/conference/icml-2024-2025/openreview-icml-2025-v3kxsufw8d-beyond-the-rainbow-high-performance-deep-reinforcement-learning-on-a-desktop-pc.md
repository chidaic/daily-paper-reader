---
title: "Beyond The Rainbow: High Performance Deep Reinforcement Learning on a Desktop PC"
title_zh: 超越彩虹：在桌面PC上实现高性能深度强化学习
authors: "Tyler Clark, Mark Towers, Christine Evers, Jonathon Hare"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=V3KXsUFw8D"
tags: ["query:player-ai"]
score: 9.0
evidence: 在Atari和3D游戏上训练出高性能深度强化学习代理
tldr: Rainbow DQN虽结合多项增强，但在3D游戏等复杂场景中仍有局限。本文提出Beyond The Rainbow (BTR)算法，融合六项RL改进，在Atari-60上达到人类标准化IQM 7.6，并成功训练代理玩超级马里奥银河等3D游戏。BTR在普通桌面电脑即可高效训练，推动了强化学习在游戏中的应用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 747, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1576, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 715, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1767, \"height\": 594, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1525, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 775, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1710, \"height\": 2264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1757, \"height\": 932, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1776, \"height\": 1037, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1509, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1753, \"height\": 1174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1752, \"height\": 865, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1613, \"height\": 1650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1748, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1763, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1745, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1750, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3kxsufw8d/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1752, \"height\": 1082, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1467, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1509, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1482, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1320, \"height\": 2033, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1536, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1478, \"height\": 428, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 614, \"height\": 454, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 843, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1481, \"height\": 1789, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1509, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1599, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3kxsufw8d/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1127, \"height\": 408, \"label\": \"Table\"}]"
motivation: 现有RL算法在复杂3D游戏上训练效率低下，且对计算资源要求高。
method: 融合六项RL改进至Rainbow DQN，并针对计算效率优化，形成BTR算法。
result: 在Atari-60上达到新最优，并成功训练多种3D游戏代理。
conclusion: BTR在桌面PC上实现了高性能，使复杂游戏代理训练更易获取。
---

## Abstract
Rainbow Deep Q-Network (DQN) demonstrated combining multiple independent enhancements could significantly boost a reinforcement learning (RL) agent’s performance. In this paper, we present “Beyond The Rainbow” (BTR), a novel algorithm that integrates six improvements from across the RL literature to Rainbow DQN, establishing a new state-of-the-art for RL using a desktop PC, with a human-normalized interquartile mean (IQM) of 7.6 on Atari-60. Beyond Atari, we demonstrate BTR’s capability to handle complex 3D games, successfully training agents to play Super Mario Galaxy, Mario Kart, and Mortal Kombat with minimal algorithmic changes. Designing BTR with computational efficiency in mind, agents can be trained using a high-end desktop PC on 200 million Atari frames within 12 hours. Additionally, we conduct detailed ablation studies of each component, analyzing the performance and impact using numerous measures.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：深度强化学习（Deep RL）虽然在复杂序列决策任务上取得了巨大成功，但近年来最先进的算法（如 Agent57、MEME、Dreamer-v3 等）对计算资源的要求越来越高，通常需要多 GPU/TPU 集群和数天甚至数周的训练时间。这使得 RL 研究对资源有限的小型实验室、爱好者和普通公众越来越不友好。Rainbow DQN 虽然通过组合多个独立改进获得了显著性能提升，但其训练仍需 34,200 GPU 小时。因此，开发一种能在普通桌面 PC 上快速训练的高性能 RL 算法具有重要价值。
- **论文目标**：提出一种名为“Beyond The Rainbow”（BTR）的新算法，在 Rainbow DQN 基础上集成六项来自 RL 文献的改进，在保持计算效率的同时，在 Atari 基准和现代 3D 游戏中达到新的最优性能，使 RL 研究更加普及。

## 2. 方法论：核心思想、关键技术细节与算法流程

- **核心思想**：延续 Rainbow DQN 的集成思路，将多个独立验证有效的改进组合成一个单一算法，但选择那些既能提升性能又能降低计算开销的组件。
- **BTR 增加的六大改进（相对于 Rainbow DQN）**：
  1. **Impala 架构 + 自适应最大池化**：使用 Espeholt 等人提出的卷积残差网络（Impala），宽度缩放为 2，并在卷积层后添加 6×6 自适应最大池化层，可加速学习并支持不同输入分辨率。
  2. **谱归一化（Spectral Normalization）**：对每个残差块的卷积层应用谱归一化，控制 Lipschitz 常数，稳定训练，尤其适合大型网络。
  3. **隐式分位数网络（IQN）**：替代 Rainbow 中的 C51 分布学习方式，从概率空间学习回报分布，消除对 Q 值范围的人为限制，能学习任意分位数的期望回报。
  4. **Munchausen RL**：在引导（bootstrapping）过程中加入缩放后的对数策略项，将 DQN 转化为 Soft-DQN，同时消除对 Double DQN 的需求。更新规则为：
     `Qθ(st, at) = rt + ατ ln πθ'(at|st) + γ Σ πθ'(a'|st+1)[Qθ'(st+1, a') - τ ln πθ'(a'|st+1)]`
  5. **向量化环境（Vectorization）**：同时运行 64 个并行环境，每个环境步进 1 步后进行一次梯度更新（批大小 256），大幅减少壁钟时间。回放比率（replay ratio）为 1/64。
  6. **超参数调整**：
     - 目标网络更新频率：每 500 梯度步（即 32,000 环境步）。
     - 学习率：1×10⁻⁴（Rainbow 使用 6.25×10⁻⁵）。
     - 折扣因子 γ：0.997（借鉴 MuZero Re-analyse）。
     - PER 优先级 α：0.2（配合 IQN 的推荐值）。
     - 同时使用噪声网络和 ε-贪心探索，但 ε 在前 100M 帧后设为 0。
- **保留的 Rainbow 组件**：N-Step TD Learning（n=3）、优先经验回放（PER）、Dueling 架构、噪声网络。
- **移除的组件**：Double DQN（因 Munchausen 已消除其必要性）、C51（升级为 IQN）。

## 3. 实验设计：数据集/场景、Benchmark、对比方法

- **基准测试**：
  - **Atari-60**：使用 Bellemare 等人的 60 个 Atari 游戏（遵循 Machado 等人协议，不使用生命信息）。评估指标主要为人类标准化分数（Human Normalized Score）的 IQM、中位数、均值、最优性差距。
  - **Procgen**：16 个程序生成的环境，测试泛化能力。
  - **现代 3D 游戏**：通过 Dolphin 模拟器训练代理玩三款 Wii 游戏：*Super Mario Galaxy*（最终关卡）、*Mario Kart Wii*（彩虹之路赛道）、*Mortal Kombat: Armageddon*（耐力模式）。这些游戏首次被 RL 解决。
- **对比方法**：
  - Atari：DQN（Nature）、Rainbow DQN（标准版与大记忆版）、Munchausen-IQN（M-IQN）、Fast & Efficient Rainbow（FE-Rainbow）、Dreamer-v3、MEME、BBF、EfficientZero-v2（EZV2）等。
  - Procgen：Rainbow DQN + Impala（宽度 4x）。
  - 此外，在消融研究中对比了去掉各个组件的 BTR 变体。
- **评估设置**：
  - 每次评估运行 100 个 episode，每 1M 帧记录一次。最终分数取训练期间各游戏的最大平均分数（而非 200M 帧时的即时分数），这是 Atari 标准做法。
  - BTR 在 Atari 上使用 4 个随机种子，Procgen 使用 5 个种子，消融实验使用 3-4 个种子。

## 4. 资源与算力

- **训练硬件**：
  - 桌面 PC：Nvidia RTX 4090 GPU、Intel i9-14900k CPU、64GB DDR5 6000MHz RAM。训练 200M Atari 帧约需 **11.5 小时**。
  - 也使用了内部集群（A100、V100、RTX 8000 等），但桌面 PC 因 CPU 更适合环境步进计算，实际表现反而更好。
- **与 Rainbow DQN 的对比**：Rainbow DQN 在桌面 PC 上训练 200M 帧约需 **35 小时**，而 BTR 仅需 11.5 小时，速度为 3 倍以上。去除向量化后 BTR 壁钟时间增至 48 小时（+328%），凸显向量化的重要性。
- **参数规模**：BTR 模型包含约 2.91M 参数（2.52M 在线性层），去掉最大池化后参数增至 8.8M。

## 5. 实验数量与充分性

- **总体实验量**：
  - Atari-60 上 4 种子完整训练。
  - Atari-5 子集（BattleZone、DoubleDunk、NameThisGame、Phoenix、QBert）上进行了详细的消融研究（去掉每个组件），使用 4 种子。
  - Procgen 上 5 种子。
  - 3 款 Wii 游戏各 1 种子（因资源限制），但展示了重复成功率 > 90% 的稳定完成能力。
  - 额外进行了超参数扫描、环境变体（无粘滞动作、使用生命信息）等实验。
  - 模型分析：测量动作间隙、策略抖动、休眠神经元比例、权重 L2 范数等，使用 3 种子 5 游戏平均。
- **充分性与公平性**：
  - 消融实验遵循标准做法，每个组件独立删除，控制变量。
  - 使用了 95% 自助法置信区间（Agarwal 等人框架），统计报告规范。
  - 对比方法来自公开文献结果，BTR 展示了性能与效率的双重优势。
  - 但 Wii 游戏实验仅单个种子，统计分析较弱；Atari-5 的回归预测与实际中位数有偏差（作者已指出）。

## 6. 主要结论与发现

- **性能突破**：BTR 在 Atari-60 上达到 **IQM 7.6**，远超 Rainbow DQN 的 1.9，超过人类水平 52/60 个游戏，实现无循环网络的新最优。
- **3D 游戏能力**：BTR 成功训练代理完成三款现代 3D 游戏（Super Mario Galaxy 最终关卡、Mario Kart Wii 彩虹之路、Mortal Kombat 耐力模式），而 Rainbow DQN 未能学会任何一款。
- **计算可及性**：在桌面 PC 上 12 小时内完成 200M 帧训练，壁钟时间远低于 Rainbow DQN（35 小时）和 Dreamer-v3（>7 天）。
- **组件贡献**：
  - **Impala 架构**贡献最大（+142% IQM），单独使用 Impala+Rainbow 无法达到 BTR 水平，说明其他组件不可少。
  - **Munchausen 和 IQN** 在需要精细控制的游戏（如 Phoenix）中至关重要，它们能增大动作间隙、减少动作交换、稳定策略。
  - **最大池化**大幅减少参数（77%），提升策略鲁棒性（抗噪声、抗 ε-贪心），尽管轻微降低性能。
  - **谱归一化**和**向量化**主要影响训练稳定性和效率。
- **分析发现**：BTR 显著增大动作间隙（减少近似误差影响）、对观测噪声更鲁棒、降低神经元休眠率和权重矩阵范数（有助于保持训练过程中的可塑性）。

## 7. 优点

- **算法创新与集成的平衡**：BTR 不是简单堆砌组件，而是系统性地选择了六项改进，并为了性能与效率进行了超参数调优，使得单桌面 PC 即可训练。
- **计算效率优先的设计**：通过向量化、最大池化、低回放比率等措施，在保持高性能的同时大幅降低训练时间，降低了 RL 研究门槛。
- **跨域泛化能力**：不仅在下棋类 Atari 游戏中表现优异，还能在无架构调整的情况下扩展到 3D 图形和复杂物理引擎的游戏，展示了算法的通用性。
- **详尽的分析消融**：不仅报告性能，还深入分析了策略抖动、动作间隙、神经元活跃度等内部机制，有助于理解各组件的作用。
- **开放性与可复现**：代码开源（GitHub），并提供训练视频，推动了社区发展。

## 8. 不足与局限

- **实验覆盖**：
  - 现代 3D 游戏仅使用了单种子，统计可靠性不足；且仅测试了三个游戏，泛化性有待更多验证。
  - Atari-5 的消融实验虽然包含 5 个游戏（Aitchison 推荐），但回归预测与真实中位数存在偏差，作者也承认了这一点。
- **与顶尖算法的差距**：在 Atari 上，BTR 的 IQM（7.6）仍低于 MEME 和 Dreamer-v3（均为 9.6），虽然 BTR 资源消耗远低，但绝对性能并非最高。
- **样本效率**：BTR 需要 200M 帧，相较于 BBF（100K 帧）等样本高效算法仍有差距，不适用于数据稀缺场景。
- **难探索游戏**：BTR 在蒙特祖玛的复仇等硬探索任务上得分极低（0），缺少显式探索组件，未来可结合 Never Give Up 等方法。
- **无循环机制**：BTR 为纯前馈网络，无法处理部分可观测性。作者指出循环网络会损害计算可及性，但仍是性能提升的重要方向。
- **超参数敏感度**：论文虽报告了超参数调优，但未充分讨论不同设置下的鲁棒性，例如 PER 的 α 值、目标网络更新频率等可能需针对新环境重新调整。
- **Wii 游戏环境的构建细节**：依赖模拟器读取内存设计奖励函数，这种手工设计可能难以迁移到其他游戏，且模拟器并行运行对 CPU 要求高。

（完）
