---
title: Enhancing Chess Reinforcement Learning with Graph Representation
title_zh: 使用图表示增强国际象棋强化学习
authors: "Tomas Rigaux, Hisashi Kashima"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=97OvPgmjRN"
tags: ["query:player-ai"]
score: 9.0
evidence: 使用图表示增强国际象棋强化学习
tldr: 该论文针对传统网格卷积网络在国际象棋等棋盘游戏中架构僵化、难以迁移的问题，提出使用图表示游戏状态，替代固定网格。基于图神经网络的方法能够处理不同尺寸的棋盘，提高模型泛化能力。在Chess上实验表明，图表示方法在同等资源下取得了更优的博弈水平，且能迁移至不同棋盘变体。该方法为游戏中的强化学习提供了更灵活的架构选择。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 768, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1347, \"height\": 124, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1403, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 934, \"height\": 127, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 651, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 727, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 650, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 662, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 652, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 648, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 653, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 653, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 651, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-97ovpgmjrn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 648, \"height\": 474, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-97ovpgmjrn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1124, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-97ovpgmjrn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1234, \"height\": 304, \"label\": \"Table\"}]"
motivation: 传统棋盘游戏中使用的卷积神经网络对网格结构依赖强，难以适应不同尺寸棋盘或游戏变体。
method: 提出基于图结构的游戏状态表示，结合图神经网络，使模型能够处理非均匀输入。
result: 实验表明图表示方法在国际象棋上性能超越传统网格方法，且支持模型迁移。
conclusion: 图表示为游戏强化学习提供了更通用且可扩展的表示方法。
---

## Abstract
Mastering games is a hard task, as games can be extremely complex, and still fundamentally different in structure from one another. While the AlphaZero algorithm has demonstrated an impressive ability to learn the rules and strategy of a large variety of games, ranging from Go and Chess, to Atari games, its reliance on extensive computational resources and rigid Convolutional Neural Network (CNN) architecture limits its adaptability and scalability. A model trained to play on a $19\times 19$ Go board cannot be used to play on a smaller $13\times 13$ board, despite the similarity between the two Go variants.
In this paper, we focus on Chess, and explore using a more generic Graph-based Representation of a game state, rather than a grid-based one, to introduce a more general architecture based on Graph Neural Networks (GNN). We also expand the classical Graph Attention Network (GAT) layer to incorporate edge-features, to naturally provide a generic policy output format.
Our experiments, performed on smaller networks than the initial AlphaZero paper, show that this new architecture outperforms previous architectures with a similar number of parameters, being able to increase playing strength an order of magnitude faster. We also show that the model, when trained on a smaller $5\times 5$ variant of chess, is able to be quickly fine-tuned to play on regular $8\times 8$ chess, suggesting that this approach yields promising generalization abilities.
Our code is available at https://github.com/akulen/AlphaGateau.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **传统方法的局限**：AlphaZero 等基于卷积神经网络（CNN）的国际象棋强化学习代理虽然性能强大，但其架构依赖于固定的网格状输入（如 \(19 \times 19\) 围棋棋盘），导致模型难以迁移到不同尺寸的棋盘或游戏变体，且训练需要大量计算资源。
- **图表示的动机**：国际象棋的走法天然对应于节点（格子）之间的边，且棋盘尺寸变化不影响图结构。因此，使用图神经网络（GNN）代替 CNN 可以更灵活地表示博弈状态，并自然地处理不同大小的棋盘，同时使策略输出维度与边数挂钩，从而提高泛化能力和训练效率。
- **研究目标**：在保持 AlphaZero 强化学习框架的基础上，用图表示替代网格表示，并设计一种能同时处理节点特征和边特征的 GNN 层（GATEAU），从而在更少的参数和计算量下达到更优或相当的博弈强度，并展示从简化变体向标准版迁移的能力。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- **图结构设计**：将棋盘上的 \(n \times n\) 个格子作为图节点，将合法走法作为有向边。节点特征（119 维）包含当前棋子信息、历史局面、步数等；边特征（15 维）包含走法合法性、方向、升变信息、棋子类型等。
- **网络架构 AlphaGateau**：
  - 输入图经过线性嵌入后，送入多个残差 GATEAU 块（ResGATEAU）。
  - **值头（Value Head）**：使用注意力池化将节点特征汇聚为全局向量，再通过 BatchNorm、ReLU、线性层和 tanh 输出 \([-1,1]\) 的胜率估计。
  - **策略头（Policy Head）**：基于更新后的边特征，经过线性层和 BatchNorm 后输出每个边对应的走法 logit，再通过 softmax 得到策略概率。
- **关键技术：GATEAU 层**：
  - 改进传统 GAT，将边特征融入注意力计算中。
  - 节点特征更新公式：\(h'_i = W_0 h_i + \sum_{j \in N_i} \alpha_{ij} (W_h h_j + W_g g_{ij})\)，其中 \(\alpha_{ij}\) 由边特征和节点特征共同计算。
  - 边特征更新：\(g'_{ij} = W_u h_i + W_e g_{ij} + W_v h_j\)（对称处理源节点和目标节点）。
- **训练算法**：基于 AlphaZero 的自对弈框架，采用 Gumbel MuZero 变体进行蒙特卡洛树搜索（MCTS），使用 128 次模拟，损失函数为策略交叉熵与价值 MSE 之和。

## 3. 实验设计：数据集 / 场景、基准、对比方法

- **场景与基准**：
  - 标准 \(8 \times 8\) 国际象棋（从零训练）。
  - 简化版 \(5 \times 5\) 国际象棋（Gardner 布局）→ 微调到 \(8 \times 8\)。
  - 对比方法：缩小版的 AlphaZero（CNN 架构，5 个残差块，约 2.2M 参数），与 AlphaGateau（5 个 ResGATEAU 块，约 1.0M 参数）进行公平比较。
- **评估指标**：Elo 评分，通过自对弈比赛数据使用加权最小二乘法（WLS）拟合，并估计 2-sigma 置信区间。
- **关键实验组**：
  1. **学习速度实验**：5 层模型对比，训练 500 轮。
  2. **微调实验**：10 层模型先在 \(5 \times 5\) 上训练 100 轮，再在 \(8 \times 8\) 上微调 100 轮，与 5 层基础模型比较。
  3. **帧窗口与自对弈游戏数影响实验**：比较不同帧窗口大小（131k vs 1M）和生成游戏数（256 vs 1024）对学习效果的影响。
- **额外验证**：将最终模型部署到 Lichess 机器人上，在子弹、闪电、快棋模式下取得约 1829–1991 的 Elo。

## 4. 资源与算力

- **硬件**：
  - 训练：多张 Nvidia RTX A5000 GPU（学习速度实验用 8 张，微调实验用 6 张）。
  - Elo 评估用 6 张 GPU。
- **训练时长**：
  - 5 层 AlphaGateau（500 轮）：13 天 16 小时。
  - 5 层 AlphaZero（500 轮）：10 天 3 小时。
  - 10 层 AlphaGateau 微调实验：初始 \(5 \times 5\) 训练 2 天 7 小时，微调 5 天 15 小时。
- **参数规模**：
  - 5 层 AlphaGateau：~1.0M 参数。
  - 5 层 AlphaZero：~2.2M 参数。
  - 10 层 AlphaGateau：~1.7M 参数。

## 5. 实验数量与充分性

- **实验数量**：主要进行了 **3 组核心实验**（学习速度、微调、超参数影响），每组仅训练一次。额外进行了 Lichess 实战验证。
- **公平性**：
  - 对比模型使用相同层数和相似的训练流程，但 AlphaGateau 参数量更少（1.0M vs 2.2M），硬件配置一致。
  - 提供 Elo 置信区间（基于 match 数据的统计学方法），但未对不同训练随机种子重复实验，因此置信区间仅反映 Elo 估计的不确定性，不反映训练本身的方差。
- **充分性评价**：
  - 实验覆盖了从零训练、迁移微调、超参数分析三个角度，基本验证了方法优势。
  - 但每组只运行一次，且仅测试了国际象棋一种游戏，未在更多变体或棋类（如将棋、围棋）上验证，充分性有限。
  - 作者承认由于计算资源限制，未进行深度达 40 层的实验（如原始 AlphaZero）。

## 6. 论文的主要结论与发现

- **性能大幅提升**：在相同参数规模下，AlphaGateau 学习速度比 AlphaZero 快约一个数量级，在 500 轮后达到 Elo 2105，而 AlphaZero 仅 667。
- **迁移能力**：先在 \(5 \times 5\) 棋盘训练 100 轮，然后微调到 \(8 \times 8\)，仅用 100 轮就达到 Elo 1876，接近从头训练的 5 层模型，证明图表示具有良好的泛化性。
- **超参数影响**：更多新生成的自对弈游戏和更大的帧窗口有助于更快学习，但会线性增加训练时间。
- **实际验证**：在 Lichess 上作为机器人运行，在快棋模式下取得约 1884–1991 Elo。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：
  - 首次将具有边特征的自注意力 GNN 层（GATEAU）应用于 AlphaZero 框架，自然支持不同棋盘尺寸且无需重新设计输出层。
  - 通过图结构统一了各种棋类的表示，使跨游戏迁移成为可能。
- **实用性**：
  - 在更少的参数和计算资源下取得显著优于 CNN 基线的结果，降低了训练门槛。
  - 开源完整代码和部分模型检查点，便于复现和扩展。
- **实验设计**：
  - 提供了详细的 Elo 评估方法（含置信区间推导附录），统计处理规范。
  - 探讨了帧窗口和自对弈游戏数的影响，为后续研究提供实践指导。

## 8. 不足与局限

- **实验覆盖不足**：
  - 仅在国际象棋上验证，未推广到将棋、围棋、奥赛罗等其他棋盘游戏，也未测试混合训练。
  - 只训练了浅层网络（5/10 层），未验证 40 层深度下的性能，可能无法充分体现图表示在大规模下的潜力。
- **可重复性风险**：
  - 每组实验仅运行一次，缺乏多随机种子平均值，置信区间未覆盖训练随机性，结果可能存在偏差。
  - 并行 GPU 代码非完全确定性，严格复现有困难。
- **计算成本仍较高**：
  - 虽然比 AlphaZero 快，但单次训练仍需数天，并且生成自对弈数据占总训练时间一半。
  - 帧窗口设计简单（均匀采样过往经验），未尝试更优的采样策略（如基于多样性或重要性）。
- **应用限制**：
  - 当前方法假设游戏信息完全且确定，无法直接用于包含随机性、隐藏信息或多玩家的游戏（如 Risk）。
  - 节点和边特征需针对不同游戏手工设计，缺乏自动特征提取能力。

（完）
