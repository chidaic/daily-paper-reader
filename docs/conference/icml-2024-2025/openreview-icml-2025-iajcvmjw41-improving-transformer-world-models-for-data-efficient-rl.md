---
title: Improving Transformer World Models for Data-Efficient RL
title_zh: 改进Transformer世界模型以实现数据高效的强化学习
authors: "Antoine Dedieu, Joseph Ortiz, Xinghua Lou, Carter Wendelken, J Swaroop Guntupalli, Wolfgang Lehrach, Miguel Lazaro-Gredilla, Kevin Patrick Murphy"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=IajCvMJw41"
tags: ["query:player-ai"]
score: 8.0
evidence: 在Craftax生存游戏上基于模型的强化学习
tldr: "该论文针对数据高效的模型强化学习，在2D开放世界生存游戏Craftax上提出改进的Transformer世界模型及三个关键改进，仅用100万环境步数即达到69.66%回报，超越人类水平，为游戏AI训练提供了高效的基准方法。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 813, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 742, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 783, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 807, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1718, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1724, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1685, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 810, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1767, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 883, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1462, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1768, \"height\": 834, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 845, \"height\": 1480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1474, \"height\": 693, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 611, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 812, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 719, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1653, \"height\": 991, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1476, \"height\": 712, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1258, \"height\": 716, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1076, \"height\": 813, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1602, \"height\": 824, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1605, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1516, \"height\": 392, \"label\": \"Table\"}]"
motivation: 在复杂游戏如Craftax上，现有MBRL方法样本效率不足，难以超越人类表现。
method: 构建基于CNN和RNN的策略架构，并在标准MBRL设置上添加三项关键改进。
result: "在Craftax-classic基准上以1M步达到69.66%回报，超越DreamerV3和人类表现。"
conclusion: 精心设计的模型RL组件可显著提升游戏中的样本效率和最终性能。
---

## Abstract
We present an approach to model-based RL that achieves a new state of the art performance on the challenging Craftax-classic benchmark, an open-world 2D survival game that requires agents to exhibit a wide range of general abilities---such as strong generalization, deep exploration, and long-term reasoning. With a series of careful design choices aimed at improving sample efficiency, our MBRL algorithm achieves a reward of 69.66% after only 1M environment steps, significantly outperforming DreamerV3, which achieves $53.2\%$, and, for the first time, exceeds human performance of 65.0%. Our method starts by constructing a SOTA model-free baseline, using a novel policy architecture that combines CNNs and RNNs.
We then add three improvements to the standard MBRL setup: (a) "Dyna with warmup", which trains the policy on real and imaginary data, (b) "nearest neighbor tokenizer" on image patches, which improves the scheme to create the transformer world model (TWM) inputs, and (c) "block teacher forcing", which allows the TWM to reason jointly about the future tokens of the next timestep.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有的基于Transformer世界模型（TWM）的模型强化学习（MBRL）方法在复杂开放世界游戏（如Craftax-classic）中样本效率不足，其性能甚至低于精心调优的无模型方法（MFRL），且始终未能超越人类专家水平。
- **研究动机**：Craftax-classic是一个2D生存游戏，要求智能体具备强泛化、深度探索、长期推理等多种能力，是评估通用智能体的理想基准。先前MBRL方法（如DreamerV3、IRIS）在Craftax-classic上奖励远低于人类（65.0%），需要更高效的学习算法。
- **整体含义**：通过一系列针对性的设计改进，使得MBRL在极少量环境交互（1M步）下首次超越人类表现，为后续数据高效RL提供了可复用的技术框架。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：在标准MBRL框架（TWM + 想象轨迹训练策略）上叠加三项互补改进，并首先构建一个更强的MFRL基线作为基础。
- **关键技术细节**：
  - **强MFRL基线**：采用CNN（Impala ResNet变体）提取图像特征，结合GRU赋予策略记忆；使用PPO训练，并改动模型大小和RNN维度（强制记忆只关注当前图像无法提取的历史信息）。
  - **改进①：Dyna with warmup**  
    - 同时使用真实环境轨迹（步骤2）和TWM生成的想象轨迹（步骤4）训练策略，而以往方法仅用想象轨迹。  
    - 引入“热身”期（前200k步仅在真实数据上训练策略），确保TWM足够精确后再使用想象数据，避免模型误差损害策略（若热身步为0，奖励从67.42%暴跌至33.54%）。
  - **改进②：最近邻居分词器（NNT）**  
    - 将图像分解为$7\times7$块（与Craftax网格对齐），对每个块独立进行最近邻匹配与码本更新。  
    - 码本一旦添加就不再更新，使TWM目标分布稳定，大幅简化学习；相比VQ-VAE（码本持续更新），NNT使奖励从58.92%提升至64.96%。
  - **改进③：块教师强制（BTF）**  
    - 修改TWM的注意力掩码为“块因果”，同一时间步内所有token可并行预测下一时间步的对应token，不再依赖已生成的前序token。  
    - 提升预测准确性（奖励从64.96%升至67.42%），同时采样速度加快一倍。
- **算法流程**（Algorithm 1的文字说明）：
  1. 多环境并行收集真实轨迹，存入缓冲池。
  2. 使用PPO在真实轨迹上更新策略。
  3. 从缓冲池采样轨迹，更新TWM（先更新分词器，再更新Transformer）。
  4. 若环境步数超过热身阈值（$T_{BP}=200k$），则从缓冲池采样初始观测，用TWM生成想象轨迹，再使用PPO在想象轨迹上更新策略（重复多次）。

## 3. 实验设计：数据集/场景、基准、对比方法
- **主要基准**：Craftax-classic（2D开放世界生存游戏，63×63图像，9×9个7×7块，22个成就，稀疏奖励）。
- **额外验证**：
  - Craftax Full（难度更高的扩展版本，130×110图像，226个成就）。
  - MinAtar（四个简化Atari游戏：Asterix、Breakout、Freeway、SpaceInvaders，10×10×K二进制观测）。
- **对比方法**：
  - 无模型：Moon et al. 2024 基线（MFRL）、本文优化的MFRL、DreamerV3。
  - 模型基：IRIS、Δ-IRIS、Curious Replay（DreamerV3 + PER）。
  - 人类专家表现（来自Hafner 2021）。
- **评估指标**：奖励（算术平均，百分比）和得分（几何平均，更关注稀有成就）。

## 4. 资源与算力
- **硬件**：每个实验在8块H100 GPU上运行（部分计时使用1块A100）。
- **训练时长**（1M环境步）：
  - 最优MFRL：15分钟（1 A100）。
  - 最优MBRL（快速版）：759分钟（约12.7小时）。
  - 最优MBRL（慢速版）：2749分钟（约45.8小时，即近2天）。
- **其他**：DreamerV3耗时约2100分钟；IRIS约8330分钟。
- **结论**：文中明确给出了GPU型号、数量及训练时长，资源信息完整。

## 5. 实验数量与充分性
- **实验数量**：
  - 所有结果基于10个随机种子，报告均值和标准误。
  - 主实验（Craftax-classic）对比7种方法，并构建5级改进阶梯（M1~M5）。
  - 消融实验：图5（块尺寸、量化必要性、每一级改进、热身起始步）、表2（定量消融）。
  - 额外实验：Craftax Full（对比MFRL和MBRL）、MinAtar（4个游戏 × 5级方法）。
  - 世界模型质量定量评估（符号准确率、L2重建误差）及定性可视化（图6）。
- **充分性与公平性**：
  - 对比方法使用了已有论文公布结果或本论文复现（如DreamerV3）。
  - 消融实验覆盖了所有关键组件，验证了每项改进的必要性。
  - 在MinAtar上的迁移实验证明了方法的一般性。
  - **局限**：主要实验集中在网格世界环境（Craftax、MinAtar），未在连续控制或3D环境中验证；Craftax Full仅简单对比，未给出先前MBRL得分误差；人类专家分数基于100局5位玩家，统计量有限。

## 6. 论文的主要结论与发现
1. 提出的MBRL方法（“改进阶梯”M5）在Craftax-classic上达到 **69.66%奖励** 和 **31.77%得分**，首次超越人类专家（65.0%奖励）。
2. 每一项改进（Dyna + warmup、补丁分词、NNT、BTF）都带来显著提升，缺一不可。
3. 优化的MFRL基线（55.49%奖励）本身已优于DreamerV3（53.2%）和IRIS（25.0%）。
4. 静态码本（NNT）和块教师强制（BTF）是提升TWM准确性与训练效率的关键。
5. 方法在Craftax Full和MinAtar上同样取得SOTA或显著改进，表明泛化性良好。

## 7. 优点：方法与实验设计的亮点
- **系统性的“改进阶梯”**：类似Rainbow，清晰展示每个组件贡献，便于研究者理解和使用。
- **简单有效的NNT**：利用Craftax网格结构，通过静态码本避免非平稳分布问题，简化训练。
- **块教师强制**：加速采样并提升预测精度，且可适用于任意Transformer架构。
- **Dyna with warmup**：巧妙平衡真实和想象数据的使用，避免早期模型误差污染策略。
- **全面的实验**：在两个难度级别的Craftax和MinAtar上进行验证，消融实验设计完备。
- **量化+质化评估**：不仅给出奖励/得分，还比较了TWM的符号准确率、重建误差和视觉样例，深入分析模型行为。

## 8. 不足与局限
- **环境局限性**：方法高度依赖Craftax的固定网格块结构（7×7）；对于非网格、连续控制或3D环境（如DM Lab、Minecraft）的普适性未验证。
- **NNT的潜在问题**：码本可能随外观变化（光照、纹理）而膨胀，影响效率；在非网格游戏中如何自动确定块大小仍未解决。
- **实验覆盖**：未与决策时规划方法（如MuZero、EfficientZero）或非生成式世界模型方法进行对比；Craftax Full上仅给出少数结果，缺乏详细消融。
- **训练时间**：慢速MBRL版本仍需约2天（8 H100），虽比IRIS快，但实用中可能仍较高；快速版本（~12h）更合理。
- **人类基线**：人类分数基于少量玩家和样本，统计可靠性有限。
- **未处理的偏差**：论文未讨论智能体可能出现的偏见或公平性问题（如对某些游戏区域的偏好）。

（完）
