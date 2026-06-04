---
title: Learning to Play Atari in a World of Tokens
title_zh: 在Token世界中学习玩Atari游戏
authors: "Pranav Agarwal, Sheldon Andrews, Samira Ebrahimi Kahou"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=w8BnKGFIYN"
tags: ["query:player-ai"]
score: 9.0
evidence: 使用离散token进行Atari游戏游玩
tldr: 该论文针对强化学习中连续表征难以建模离散世界的问题，提出DART方法，利用Transformer和离散表征进行自回归世界模型与行为学习，在Atari游戏中实现了更优的样本效率。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-w8bnkgfiyn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1701, \"height\": 883, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-w8bnkgfiyn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-w8bnkgfiyn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 850, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-w8bnkgfiyn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 844, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-w8bnkgfiyn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1510, \"height\": 956, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-w8bnkgfiyn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1412, \"height\": 1243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w8bnkgfiyn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1403, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w8bnkgfiyn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 826, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w8bnkgfiyn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 731, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w8bnkgfiyn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1394, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w8bnkgfiyn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 728, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w8bnkgfiyn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 640, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w8bnkgfiyn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 726, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w8bnkgfiyn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 620, \"height\": 1106, \"label\": \"Table\"}]"
motivation: 基于模型的RL使用连续表征难以处理真实世界的离散属性。
method: 提出DART，用Transformer编码器-解码器架构学习离散抽象表征和策略。
result: 在Atari游戏中样本效率优于现有基于模型的方法。
conclusion: 离散表征结合Transformer可有效提升游戏AI的样本效率。
---

## Abstract
Model-based reinforcement learning agents utilizing transformers have shown improved sample efficiency due to their ability to model extended context, resulting in more accurate world models. However, for complex reasoning and planning tasks, these methods primarily rely on continuous representations. This complicates modeling of discrete properties of the real world such as disjoint object classes between which interpolation is not plausible. In this work, we introduce discrete abstract representations for transformer-based learning (DART), a sample-efficient method utilizing discrete representations for modeling both the world and learning behavior. We incorporate a transformer-decoder for auto-regressive world modeling and a transformer-encoder for learning behavior by attending to task-relevant cues in the discrete representation of the world model. For handling partial observability, we aggregate information from past time steps as memory tokens. DART outperforms previous state-of-the-art methods that do not use look-ahead search on the Atari 100k sample efficiency benchmark with a median human-normalized score of 0.790 and beats humans in 9 out of 26 games. We release our code at https://pranaval.github.io/DART/.

---

## 论文详细总结（自动生成）

# 论文总结：Learning to Play Atari in a World of Tokens

## 1. 核心问题与整体含义（研究动机和背景）

基于模型的强化学习（MBRL）方法（如 Dreamer 系列）通过学习环境动态来提升样本效率，但这些方法主要依赖连续表示（如 VAE 的连续潜变量）。连续表示难以捕捉真实世界中离散的属性（例如不相交的对象类别，在其之间插值不合理），这限制了模型在复杂推理和规划任务上的表现。现有 Transformer 世界模型（如 IRIS）开始使用离散 token（VQ-VAE）建模世界，但策略学习仍依赖 CNN 和 LSTM，性能受限。论文旨在提出一种**全离散化的 Transformer 框架**，同时用于世界模型和策略学习，以提升样本效率并增强可解释性。

## 2. 方法论：核心思想与关键技术细节

论文提出 **DART（Discrete Abstract Representations for Transformer-based learning）**，整体遵循三步流程：

- **表示学习**：使用 VQ-VAE 将原始观测 \(x_t\)（64×64 RGB）编码为 \(K\) 个离散 token \( \hat{z}^k_{qt} \)（来自大小为 512 的码本）。损失包括重建损失、码本损失、承诺损失以及感知损失。
- **世界模型学习**：采用 GPT 风格的 Transformer-decoder，以自回归方式预测下一时刻的 token 序列。输入为当前 token 序列和动作，输出下一时刻的 token 分布、奖励预测和终止预测。训练使用交叉熵（token/终止）和均方误差（奖励）。
- **策略学习**：采用 ViT 风格的 Transformer-encoder。输入为当前观测的 \(K\) 个 token 加上一个 **CLS token**（用于聚合信息）和一个 **MEM token**（记忆单元，来自上一时间步的 CLS 输出），并添加可学习的位置编码。经过多层自注意力后，CLS 输出作为状态表示 \(h_t\)，用于动作采样和值函数估计，同时作为下一时间步的 MEM token。策略优化沿用 DreamerV2 的想象轨迹目标函数。

**关键技术细节**：
- 世界模型使用 10 层因果 Transformer，策略使用 6 层自注意力 Transformer。
- 每个时间步输入策略的 token 数为 \(K+2\)（K 个观测 token + CLS + MEM）。
- 采用 layer normalization 替代 warm-up，稳定训练。

## 3. 实验设计

- **基准（Benchmark）**：Atari 100k 基准，包含 26 个 Atari 游戏，每游戏仅允许 100k 环境步（由于 frame skip=4，实际 400k 帧），约 2 小时实时游戏。
- **对比方法**：包括基于模型的方法 SimPLe、DreamerV3、TWM、IRIS，以及无模型方法 CURL、DrQ、SPR。主要对比 IRIS（同为离散 token + Transformer 世界模型但策略使用 CNN+LSTM）和 DreamerV3。
- **消融实验**：选取 5 个游戏（Boxing、Amidar、RoadRunner、Seaquest、KungFuMaster）测试以下变体：
  - 移除位置编码（w/o PE）
  - 无随机探索（w/o epsilon）
  - 掩码记忆 token（Masked MEM）
  - 随机掩码观测 token（25%/50%/75%/100%）
- **附加实验**：
  - Crafter 环境（1M 步，评估长时任务能力）
  - 150k 步 Atari 实验（验证扩展性）
  - 与 STORM（另一 Transformer 世界模型）对比
  - 策略注意力热力图分析（揭示记忆 token 在不同游戏中的重要性）

## 4. 资源与算力

文中未明确说明使用的 GPU 型号、数量和训练时长。仅提及使用 Digital Research Alliance of Canada 的计算资源。附录中提供了模型参数量（DART 约 3.07M，IRIS 3.04M，DreamerV3 18M）及详细超参数（批次大小 64，学习率 1e-4 等），但未提供训练时间或 GPU 小时数。

## 5. 实验数量与充分性

- **主实验**：在 26 个 Atari 游戏上评估，每个游戏用 5 个随机种子，报告 100 个 episode 的平均分。统计指标包括中位数、均值、IQM 和最优差距（OG），并绘制性能分布图和改善概率图。
- **消融实验**：仅在 5 个游戏上进行，覆盖了代表性场景（如需要记忆的 Breakout、PrivateEye 和不需要长期记忆的 Boxing、Amidar），但样本量较少，可能无法全面反映所有游戏的影响。
- **附加实验**：Crafter 环境（5 种子）、150k 步实验（3 个游戏 5 种子）、与 STORM 对比（26 个游戏）。
- **公平性**：对比方法均采用公开报告结果或作者提供的多个种子数据。DART 结果取 5 种子均值，但未提供方差或区间估计。消融实验仅展示单数值，未说明方差。

总体实验较为充分，主要指标覆盖全面，但消融实验范围有限；计算资源未详述，可能影响可重复性。

## 6. 主要结论与发现

- DART 在 Atari 100k 上取得不使用搜索方法的新 SOTA：**中位数 0.790**（优于 IRIS 的 0.289、DreamerV3 的 0.466），IQM 0.575，OG 0.458。
- 在 26 个游戏中**9 个超越人类**，**18 个优于 IRIS**。
- 消融实验验证了：
  - **位置编码**对需要精细交互的游戏（如 Boxing、KungFuMaster）至关重要。
  - **随机探索**对世界模型训练不可或缺。
  - **记忆 token**在需要跟踪物体轨迹的游戏（Breakout、PrivateEye）中显著提升性能；在无需长期记忆的游戏（Boxing、Amidar）中影响较小。
- 热度图显示：记忆 token 在快节奏游戏（Breakout）中注意力高，在静态游戏（Amidar）中注意力低，展示了自适应性。
- Crafter 实验 DART 平均回报 12.2 ± 1.67，高于 DreamerV3（11.7）和 IRIS（9.23），证明长程任务能力。
- 与 STORM 对比，DART 中位数更高（0.790 vs 0.584），尤其在 Pong、Breakout 等小物体游戏中优势明显，归因于离散 token 的细粒度注意力。

## 7. 优点

- **全 Transformer 架构**：世界模型使用 decoder（GPT），策略使用 encoder（ViT），统一离散 token 处理，避免了 CNN/LSTM 的局限性。
- **创新的记忆机制**：通过 CLS token 与 MEM token 在自注意力中传递历史信息，无需额外 RNN，简单高效且可解释。
- **可解释性强**：可通过注意力权重可视化分析策略关注的时空特征，为模型调试提供直观依据。
- **样本效率高**：在 100k 步限制下达到接近人类水平，且无需搜索算法。
- **消融实验设计清晰**：明确了位置编码、探索、记忆、观测 token 等因素的贡献。

## 8. 不足与局限

- **仅支持离散动作空间**：论文指出当前方法主要适用于离散动作环境（Atari），连续动作空间需要额外训练动作 tokenizer，虽在附录中提供了思路，但未实际验证。
- **未集成搜索**：DART 未使用 look-ahead 搜索（如 MCTS），限制了利用世界模型进行前瞻规划的能力（附录中虽给出融合搜索的算法，但无实验结果）。
- **消融实验范围有限**：仅 5 个游戏，可能无法泛化到所有 26 个游戏；且未对记忆 token 的维度、数量进行敏感性分析。
- **计算资源未透明**：未报告 GPU 型号、训练时长、能耗等，不利于成本评估和复现。
- **部分游戏性能下降**：在 CrazyClimber、Frostbite 等游戏中显著低于 IRIS 或 DreamerV3，表明离散 token 可能在某些全局信息丰富的场景中丢失关键特征。
- **方差信息缺失**：主结果仅给出均值，未提供标准差或置信区间，消融实验更是仅有单值，难以判断稳健性。
- **超参数固定**：论文未探讨不同游戏是否需要不同超参数（如 token 数、Transformer 层数），固定设置可能限制泛化。

（完）
