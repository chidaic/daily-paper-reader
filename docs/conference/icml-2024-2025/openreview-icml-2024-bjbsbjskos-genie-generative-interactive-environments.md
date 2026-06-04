---
title: "Genie: Generative Interactive Environments"
title_zh: Genie：生成式交互环境
authors: "Jake Bruce, Michael D Dennis, Ashley Edwards, Jack Parker-Holder, Yuge Shi, Edward Hughes, Matthew Lai, Aditi Mavalankar, Richie Steigerwald, Chris Apps, Yusuf Aytar, Sarah Maria Elisabeth Bechtle, Feryal Behbahani, Stephanie C.Y. Chan, Nicolas Heess, Lucy Gonzalez, Simon Osindero, Sherjil Ozair, Scott Reed, Jingwei Zhang, Konrad Zolna, Jeff Clune, Nando de Freitas, Satinder Singh, Tim Rocktäschel"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=bJbSbJskOS"
tags: ["query:player-ai"]
score: 5.0
evidence: 生成可交互虚拟环境
tldr: 本文提出Genie，第一个从无标签互联网视频中无监督训练的生成式交互环境模型。它通过时空视频分词器、自回归动力学模型和潜在动作模型，能将文本、图像甚至草图转化为可操作的虚拟世界。该模型作为基础世界模型，使AI agent能在生成环境中逐帧行动，无需真实动作标签。这项工作为虚拟游戏环境生成提供了新范式，可支持游戏AI的训练和测试。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 821, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1600, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1661, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 796, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 721, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 762, \"height\": 165, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 466, \"height\": 216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 817, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1758, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1661, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 789, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1760, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 831, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 842, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 861, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1482, \"height\": 2212, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-bjbsbjskos/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1561, \"height\": 1233, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 702, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 887, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 883, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 709, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 528, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 712, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 527, \"height\": 532, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 368, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 370, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1415, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 791, \"height\": 128, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 886, \"height\": 121, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 370, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 528, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 527, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 527, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-bjbsbjskos/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 571, \"height\": 280, \"label\": \"Table\"}]"
motivation: 现有世界模型需要特定领域标签，限制了通用性。
method: 采用无监督视频训练，包含视频分词器、动力学模型和潜在动作模型。
result: 可以生成多种可操作虚拟世界，用户可逐帧控制。
conclusion: Genie是首个无监督训练的生成式交互环境模型，可作基础世界模型。
---

## Abstract
We introduce Genie, the first *generative interactive environment* trained in an unsupervised manner from unlabelled Internet videos. The model can be prompted to generate an endless variety of action-controllable virtual worlds described through text, synthetic images, photographs, and even sketches. At 11B parameters, Genie can be considered a *foundation world model*. It is comprised of a spatiotemporal video tokenizer, an autoregressive dynamics model, and a simple and scalable latent action model. Genie enables users to act in the generated environments on a frame-by-frame basis *despite training without any ground-truth action labels* or other domain specific requirements typically found in the world model literature. Further the resulting learned latent action space facilitates training agents to imitate behaviors from unseen videos, opening the path for training generalist agents of the future.

---

## 论文详细总结（自动生成）

# Genie: Generative Interactive Environments 论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有世界模型（World Models）和视频生成模型通常需要带动作标签或文本标注的数据进行训练，限制了其通用性和可扩展性。同时，缺乏从无标签视频中直接学习可交互环境的方法。
- **目标**：提出第一个**无监督**训练的生成式交互环境模型 Genie，能够从大规模无标签互联网视频中学习，并允许用户通过文本、图像甚至草图生成可逐帧控制的虚拟世界。
- **意义**：Genie 可被视为一个**基础世界模型**（Foundation World Model），为训练通用 AI Agent 提供无限、多样化的交互环境，同时推动生成式 AI 从静态内容生成向动态交互体验演进。

## 2. 方法论：核心思想、关键技术细节

### 2.1 整体架构

Genie 包含三个核心组件，采用两阶段训练：

1. **视频分词器（Video Tokenizer）**：时空 VQ-VAE（ST-ViViT），将原始视频帧压缩成离散 token。
2. **潜在动作模型（Latent Action Model, LAM）**：从相邻帧像素中无监督学习离散潜在动作，编码器-解码器结构，使用 VQ-VAE 约束动作空间大小（默认为 8）。
3. **动力学模型（Dynamics Model）**：MaskGIT 解码器，以过去帧 tokens 和潜在动作为条件，自回归预测下一帧 tokens。

### 2.2 关键技术

- **ST-Transformer**：所有组件均采用改进的时空 Transformer，空间注意力层关注单帧内所有 token，时间注意力层（带因果掩码）关注跨帧同一位置 token，复杂度随帧数线性增长，而非二次增长。
- **两阶段训练**：先单独训练视频分词器，再联合训练 LAM 和动力学模型（LAM 从像素训练，动力学模型在 token 空间训练）。
- **推理流程**：用户输入提示帧（文本生成图像、照片、草图等），指定离散潜在动作，动力学模型逐帧自回归生成，分词器解码回图像。

### 2.3 公式/算法流程（文字说明）

- 训练阶段：
  1. 视频分词器：输入 `x_{1:T}` → 编码为离散 `z_{1:T}`，VQ-VAE 损失。
  2. LAM：从 `x_t` 和 `x_{t+1}` 推断潜在动作 `a_t`，使用 VQ-VAE 约束动作空间。
  3. 动力学模型：给定 `z_{1:t-1}` 和 `a_{1:t-1}`，预测 `z_t`，交叉熵损失（MaskGit 随机掩蔽训练）。
- 推理阶段：
  1. 用户输入第一帧 `x_1`，分词器编码得 `z_1`。
  2. 用户选择离散动作 `a_i`（0~7），查询 LAM 代码本得到嵌入。
  3. 动力学模型迭代生成下一帧 tokens，解码器重建图像。

## 3. 实验设计

### 3.1 数据集

- **Platformers 数据集**：从公开互联网视频中筛选 2D 平台游戏，经关键词过滤和人工标注质量过滤后得到 680 万段 16 秒片段（30,000 小时），分辨率 160×90，10 FPS。
- **Robotics 数据集**：来自 RT-1 的真实机器人操作视频（约 130K 演示），不含动作标签。
- **CoinRun（Procgen）**：用于行为克隆验证的 RL 环境。

### 3.2 评估指标

- **FVD（Frechet Video Distance）**：视频生成质量（保真度）。
- **ΔtPSNR**：可控性指标，通过比较使用真实潜在动作与随机动作生成视频的 PSNR 差异。

### 3.3 对比方法

- **LAM 输入类型**：像素输入 vs Token 输入（自己的消融）。
- **分词器架构**：ViT（空间）、C-ViViT（全时空注意） vs ST-ViViT（自己）。
- **行为克隆**：与 Oracle（使用真实动作）和随机策略对比。
- **文献对比**：PVG、VPT、UniSim、GAIA-1 等（定性讨论，非定量直接比较）。

### 3.4 实验细分

- 缩放实验：7 种模型大小（41M ~ 2.7B），3 种 batch size（128/256/448）。
- 最终 Genie 模型：11B 参数，训练 125k steps，batch size 512。
- 消融实验：LAM 输入、分词器类型、数据集质量（原始 vs 过滤）。
- 跨域验证：Platformers 上测试 OOD 提示（文本生成图、手绘、真实照片）；Robotics 上测试一致性和可玩性。
- 行为克隆：在 CoinRun 上训练策略，用潜在动作标签 + 200 个专家样本进行动作映射。

## 4. 资源与算力

- **硬件**：TPUv2、TPUv3、TPUv5p。
- **最终模型**：256 个 TPUv5p，训练约 125k steps，处理 942B tokens。
- **缩放实验**：小模型使用 64 或 128 TPU（v2/v3），训练 3~16 天不等。
- **可复现性**：提供了一个在单个 TPU/GPU（16G 内存）上 3 天可完成的小规模版本（CoinRun 环境、200M tokenizer、512 参数模型）。

## 5. 实验数量与充分性

- **实验组数**：涵盖缩放（7 个模型大小 × 3 batch size）、3 种 tokenizer 对比、2 种 LAM 输入对比、2 种数据质量对比、2 个领域（Platformers + Robotics）、行为克隆（2 种难度 + Oracle 对比）。
- **充分性**：总体较为充分，展现了模型在不同规模和设置下的表现，关键设计选择有消融支持。但对比方法多为自身变体，缺乏与其他最新可交互生成模型（如 PVG、Dreamer 等）的直接定量比较。行为克隆实验仅在 CoinRun 上进行，未推广到更复杂环境。

## 6. 主要结论与发现

1. Genie 能从无标签视频中无监督学习可控制的交互环境，且模型大小和 batch size 扩展均能带来性能提升。
2. 潜在动作空间（8 个离散动作）在不同提示下表现出语义一致性（如左、右、跳等），用户可凭直觉掌握。
3. 模型能泛化到分布外提示（文本生成图、手绘草图、真实照片），体现出基础模型特性。
4. 学习到的潜在动作可用于行为克隆，在 CoinRun 上达到与 Oracle 相当的分数，且仅需 200 个专家样本映射动作。
5. 在机器人视频上同样有效，能学习到手臂控制、物体交互（如变形袋装薯片）等动态。
6. ST-ViViT 分词器在保真度和可控性上优于空间 ViT 和 C-ViViT。

## 7. 优点

- **完全无监督**：无需动作/文本标签，训练数据易获取。
- **高效结构**：ST-Transformer 线性复杂度，支持长序列。
- **通用性强**：支持多种提示（文本、图像、草图），适用多种领域（游戏、机器人）。
- **可交互性**：用户或 agent 可通过离散动作逐帧控制生成世界。
- **可扩展性**：验证了模型和 batch size 的 scaling law，为更大规模训练提供依据。
- **应用潜力**：可为基础世界模型，用于训练通用 agent。

## 8. 不足与局限

- **时间视野有限**：训练时仅 16 帧记忆，长序列一致性差，易产生幻觉。
- **推理速度慢**：约 1 FPS，无法实时交互。
- **动作空间小**：仅 8 个动作，可能不足以模拟复杂环境。
- **评估场景单一**：主要集中在 2D 平台游戏，未在 3D 或真实世界视频上验证。
- **对比不充分**：未与最强基线（如 DreamerV3、UniSim）进行公平定量比较。
- **未开源**：模型权重和训练数据集未公开，可复现性受限。
- **潜在偏差**：数据集仅包含 2D 游戏，可能引入内容偏见。

（完）
