---
title: Generative Modeling of Individual Behavior at Scale
title_zh: 大规模个体行为生成式建模
authors: "Nabil Omi, Lucas Caccia, Anurag Sarkar, Jordan T. Ash, Siddhartha Sen"
date: 2024-05-15
pdf: "https://openreview.net/pdf?id=QsxldAFMFx"
tags: ["query:player-ai"]
score: 9.0
evidence: 对国际象棋中个体玩家行为进行生成式建模，实现行为模拟
tldr: 本文提出了个体行为生成模型，专注于国际象棋领域。与以往仅从大量玩家中识别个体的方法不同，该方法能够生成符合特定玩家风格的动作序列。通过将行为风格测量与生成式建模结合，不仅可以识别玩家，还能模拟和影响个体玩家行为，为虚拟玩家建模提供了新途径。
source: NeurIPS-2024-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-qsxldafmfx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qsxldafmfx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 582, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qsxldafmfx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 846, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qsxldafmfx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1353, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qsxldafmfx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 396, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qsxldafmfx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 521, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qsxldafmfx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 591, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qsxldafmfx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 693, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qsxldafmfx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 697, \"height\": 511, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-qsxldafmfx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1381, \"height\": 510, \"label\": \"Table\"}]"
motivation: 现有行为建模多为聚合级别，难以生成个体风格的动作。
method: 将行为风格测量与生成式建模结合，从大量玩家数据中学习个体行为模型。
result: 能够生成符合特定玩家风格的动作序列。
conclusion: 该方法可用于理解、模拟和影响个体行为。
---

## Abstract
Recent years have seen a growing interest in using AI to model human behavior, particularly in domains where humans learn from or collaborate with this technology. While most existing work attempts to model human behavior at an aggregate level, our goal is to model behavior at the individual level. Recent work in the domain of chess has shown that behavioral stylometry, or the task of identifying a person from their actions alone, can be achieved with high accuracy among a pool of a few thousand players. However, this approach cannot generate actions in the style of each player, and hence cannot reason about or influence player behavior in practice. We provide a new perspective on behavioral stylometry that addresses these limitations, by drawing a connection to the vast literature of transfer learning in NLP. Specifically, by casting the stylometry problem as a multi-task learning problem---where each task represents a distinct---we show that parameter-efficient fine-tuning (PEFT) methods can be adapted to model individual behavior in an explicit and generative manner, at unprecedented scale. We apply our approach at scale to two very different games: chess (47,864 players) and Rocket League (2,000 players).

Our approach leverages recent modular PEFT methods to learn a shared set of skill parameters that can be combined in different ways via style vectors. Style vectors enable two important capabilities. First, they are generative: we can generate actions in the style of a player simply by conditioning on the player's style vector. Second, they induce a latent style space that we can interpret and manipulate algorithmically. This allows us to compare different player styles, as well as synthesize new (human-like) styles, e.g. by interpolating between the style vectors of two players.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有行为建模多专注于聚合级别（如模拟平均人类行为），缺乏对个体玩家风格的建模能力；已有的个体风格测量方法（如国际象棋中的 stylometry）虽然能够识别玩家，但**无法生成符合该玩家风格的动作**，因而无法用于实际的行为模拟、分析和干预。
- **整体意义**：本文旨在**实现大规模、生成式的个体行为建模**，使得模型既能从动作中识别玩家，又能生成该玩家风格的动作，从而为个性化 AI 教练、对手、协作工具等应用提供基础。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将行为风格测量视为**多任务学习问题**，每个玩家对应一个任务，利用**参数高效微调（PEFT）** 方法学习一组共享的“技能”参数，并通过每个玩家的**风格向量**（style vector）来选择性地组合这些技能，从而生成个体风格的动作。
- **关键技术细节**：
  - **基础模型**：象棋采用 Squeeze-and-Excitation 残差网络（15.7M 参数）；火箭联盟采用 GPT-2 架构（87.7M 参数）。
  - **适配器结构**：使用 **Multi-Head Routing (MHR)**，将输入/输出维度分割为多个头，每个头独立进行 Poly 风格的线性组合，提升灵活性。
  - **LoRA 适配器**：在每个 MHR 层中，存储一个适配器库（inventory），每个适配器为低秩矩阵对 \(A, B\)，通过路由矩阵 \(Z\) 的 softmax 权重组合成最终的适配器 \(A_\tau, B_\tau\)。
  - **风格向量**：路由矩阵 \(Z\) 的每一行对应一个玩家的风格向量，它指定了该玩家对各适配器的选择权重。该向量与所有 MHR 层共享。
  - **训练流程**：
    1. 使用所有玩家的数据训练基础 BC 模型。
    2. 冻结基础模型，训练 MHR 适配器和路由矩阵（使用双倍学习率加速风格向量学习）。
    3. 对于新玩家，采用 **routing-only fine-tuning**（固定适配器，仅微调风格向量），实现少样本学习。
  - **风格转向**：通过计算具有期望属性（如高王安全性）的玩家风格向量的平均，减去总体平均得到“风格增量向量”，将其加到任意玩家的风格向量上即可引导其风格。

### 3. 实验设计：数据集、场景、benchmark 和对比方法

- **数据集**：
  - **国际象棋**：来自 Lichess 的 Blitz 对局（2013-2020），筛选后包含 **47,864 名玩家**，共 2.44 亿局游戏。额外构建了 400 名玩家的子集以便与先前工作直接比较。
  - **火箭联盟**：来自 Ballchasing.com 的 1v1 回放（2015-2022），共 220 万局，选取 **2,000 名玩家**（每人至少 100 局）用于微调。
- **benchmark**：主要对比两种先前方法：
  - **McIlroy-Young et al. (2022)**：为每个玩家独立微调 Maia 模型（个体模型）。
  - **McIlroy-Young et al. (2021)**：基于 Transformer 的嵌入方法（不可生成动作）。
- **评估任务**：
  - **行为风格测量（stylometry）**：给定查询游戏集，识别玩家身份。
  - **动作匹配准确率**：生成模型预测玩家下一步动作的正确率。
  - **风格向量分析**：一致性（跨数据分割）、合并新风格、插值强度、属性转向。

### 4. 资源与算力

- 论文**未明确报告**具体使用的 GPU 型号、数量或训练时长。
- 仅提供了模型参数规模：象棋模型基础 15.7M + 适配器 5M；火箭联盟模型基础 87.7M + 适配器 13.8M。
- 附录中提到使用了标准模型，但未披露计算资源细节。

### 5. 实验数量与充分性

- **实验数量**：较为丰富，包括：
  - 风格测量实验（表 1）：多个 player 规模（400、10,000、47,864）、不同 query 游戏数（30、100）。
  - 动作匹配实验（图 2）：不同游戏数（25~10,000）下与个体微调对比。
  - 风格一致性实验（图 3-5）：玩家内/玩家间相似度分析。
  - 风格合成实验（图 6-7）：插值强度与胜率关系、属性转向（bishop pair / king danger）。
  - 火箭联盟风格测量和动作匹配实验（文中给出数据）。
- **充分性与公平性**：
  - 象棋部分与最先进方法直接对比，结果具有竞争力。
  - 火箭联盟因缺乏先前工作，仅与自身基线对比，但展示了方法的可迁移性。
  - 缺失对适配器超参数（如 rank、head 数）的消融实验；缺少计算开销与存储对比。

### 6. 论文的主要结论与发现

- 提出 **MHR + 风格向量** 的框架实现了**大规模、生成式个体行为建模**，在两个差异很大的游戏中均有效。
- 风格测量准确率：国际象棋 47,864 玩家中达 **94.4%**（100 局查询），火箭联盟 2,000 玩家中达 **86.7%**。
- 动作匹配准确率：在少量游戏（如 100 局）下与个体微调性能相近（约 58-62%），证明少样本学习的有效性。
- 风格向量具有**可解释性和可操作性**：可以合并、插值、转向，生成新的、人类般的风格，且影响符合预期（如增加 bishop pair 使用会相应提升该指标）。

### 7. 优点：方法或实验设计上的亮点

- **方法新颖**：将多任务学习与 PEFT 结合，首次实现可生成个体风格的建模，兼顾识别与生成能力。
- **通用性强**：在两个截然不同的游戏（棋盘策略 vs. 实时3D竞技）中验证，展示了跨域适用性。
- **风格向量可解释与可操作**：不仅用于识别，还能用于风格合成与引导，为个性化 AI 提供工具。
- **实验规模大**：象棋使用了 47,864 名玩家，远超此前工作（几百~几千）。
- **少样本学习高效**：仅学习路由参数即可适应新玩家，计算成本极低。

### 8. 不足与局限

- **火箭联盟实验不够充分**：仅用了 2,000 名玩家，且缺乏外部基准对比（无先前风格测量工作）；风格转向实验仅对象棋进行，火箭联盟未展示。
- **缺乏消融与敏感性分析**：未系统研究适配器库大小、head 数量、rank 等超参数的影响。
- **计算资源未公开**：无法复现或评估大规模训练的实际成本；存储开销（风格向量仅 256/1024 维，但适配器参数仍需存储）未与个体微调详细比较。
- **潜在偏差与应用风险**：数据来自公开平台，可能存在玩家风格分布不均；模型可能被用于模拟特定玩家行为，需警惕滥用（论文仅提及相关伦理讨论未展开）。
- **假设每位玩家风格稳定**（未考虑对手、时间等变化），但附录提及可扩展至子集分割（如开局/中局/残局），未实验。

（完）
