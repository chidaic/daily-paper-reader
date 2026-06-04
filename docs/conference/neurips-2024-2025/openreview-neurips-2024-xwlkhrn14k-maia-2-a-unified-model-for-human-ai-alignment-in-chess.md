---
title: "Maia-2: A Unified Model for Human-AI Alignment in Chess"
title_zh: Maia-2：国际象棋中人类-AI对齐的统一模型
authors: "Zhenwei Tang, Difan Jiao, Reid McIlroy-Young, Jon Kleinberg, Siddhartha Sen, Ashton Anderson"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=XWlkhRn14K"
tags: ["query:player-ai"]
score: 9.0
evidence: 统一模型用于国际象棋中的人类-AI对齐与玩家行为建模
tldr: 针对国际象棋中人类行为建模的挑战，本文提出Maia-2统一模型，能对不同水平棋手的决策进行连贯建模。该模型在多个技能层次上精准预测人类走法，并支持个性化AI教学。工作为游戏领域的人类行为模拟与AI对齐设立了新标杆，可用于分析棋手决策和改进教学。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-xwlkhrn14k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1275, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xwlkhrn14k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1353, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xwlkhrn14k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xwlkhrn14k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1363, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xwlkhrn14k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1355, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xwlkhrn14k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1286, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xwlkhrn14k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1185, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xwlkhrn14k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 840, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xwlkhrn14k/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1279, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xwlkhrn14k/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 987, \"height\": 546, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-xwlkhrn14k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1364, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xwlkhrn14k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 692, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xwlkhrn14k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 697, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xwlkhrn14k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1041, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xwlkhrn14k/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 746, \"height\": 714, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xwlkhrn14k/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 645, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xwlkhrn14k/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 734, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xwlkhrn14k/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1409, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xwlkhrn14k/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1463, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xwlkhrn14k/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1381, \"height\": 402, \"label\": \"Table\"}]"
motivation: 现有模型无法连贯建模不同技能水平的人类棋手行为。
method: 提出统一模型，联合学习多个技能层次的人类决策模式。
result: Maia-2在不同水平上均能精准预测人类走法，优于独立模型。
conclusion: 为游戏中的AI对齐与教学提供了有力工具。
---

## Abstract
There are an increasing number of domains in which artificial intelligence (AI) systems both surpass human ability and accurately model human behavior. This introduces the possibility of algorithmically-informed teaching in these domains through more relatable AI partners and deeper insights into human decision-making. Critical to achieving this goal, however, is coherently modeling human behavior at various skill levels. Chess is an ideal model system for conducting research into this kind of human-AI alignment, with its rich history as a pivotal testbed for AI research, mature superhuman AI systems like AlphaZero, and precise measurements of skill via chess rating systems. Previous work in modeling human decision-making in chess uses completely independent models to capture human style at different skill levels, meaning they lack coherence in their ability to adapt to the full spectrum of human improvement and are ultimately limited in their effectiveness as AI partners and teaching tools. In this work, we propose a unified modeling approach for human-AI alignment in chess that coherently captures human style across different skill levels and directly captures how people improve. Recognizing the complex, non-linear nature of human learning, we introduce a skill-aware attention mechanism to dynamically integrate players’ strengths with encoded chess positions, enabling our model to be sensitive to evolving player skill. Our experimental results demonstrate that this unified framework significantly enhances the alignment between AI and human players across a diverse range of expertise levels, paving the way for deeper insights into human decision-making and AI-guided teaching tools.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：国际象棋是研究人类-AI对齐的理想领域，已有超人类AI（如Stockfish、AlphaZero）和成熟的等级分系统，但现有模型（如Maia系列）用完全独立的模型分别建模不同技能水平的棋手，导致预测行为不连贯（volatile），无法平滑反映人类随技能提升的进步路径。这种不连贯性限制了AI作为教学工具或伙伴的效果。
- **整体含义**：论文旨在建立一个统一模型（Maia-2），能够连贯地捕获不同棋力水平的人类决策风格，并直接建模人们如何改进（改善路径平滑、单调）。该模型有望推动AI辅助教学和更深入理解人类决策。

### 2. 论文提出的方法论

- **核心思想**：提出一个端到端的统一架构，将技能水平（主动棋手和对手的等级分）与棋局位置编码通过**技能感知注意力（Skill-aware Attention）**机制动态融合，使模型适应不同技能水平的决策模式。
- **关键技术细节**：
  - **技能等级编码器**：使用分类嵌入（categorical embeddings）而非数值等级分，以捕捉非线性关系并分组玩家。
  - **位置编码器**：采用ResNet骨干网络（12个卷积块）编码当前棋盘（仅用当前局面，而非历史6步，符合马尔可夫性质）。
  - **技能感知注意力模块**：
    - **通道级分块（Channel-wise patching）**：将ResNet输出的特征图（C×8×8）展平为C个长度为64的patch，再线性投影到注意力的隐藏维度。
    - **多头自注意力中注入技能**：将主动棋手和对手的技能嵌入相加到查询（Q）上，使注意力根据技能水平动态调整对不同特征的关注。
    - 堆叠两个技能感知注意力块，逐步融合技能和位置信息。
  - **多任务训练**：
    - **策略头（Policy head）**：预测人类走法（交叉熵）。
    - **辅助信息头（Auxiliary head）**：预测合法走法、移动棋子、被吃棋子、来源格、目标格、是否将军等（二值交叉熵），提供细粒度理解。
    - **价值头（Value head）**：预测比赛结果（回归，标签为1/0/-1）。
  - **数据平衡**：对非对称技能配对（对手等级相差大）进行过采样，避免偏向于水平相近的对局。
- **公式/算法流程（文字说明）**：
  - 输入当前棋盘P_input → ResNet → P_encoded → 通道分块得到P_patched → 线性投影到d_att → 加上技能嵌入后的查询Q*，计算多头注意力 → 层归一化和FFN → 输出P_out → 重复一次注意力块 → 最终表示P_ → 分别连接策略头、辅助头、价值头进行预测。

### 3. 实验设计

- **数据集**：
  - 训练集：Lichess平台上2013年1月至2023年11月的Rapid对局（除2019年12月用于测试），经过过滤（剔除短对局、时间压力局面）和平衡后得到约**1.69亿对局（91亿局面）**。还训练了Maia-2_subset（仅使用Maia原始训练数据）以控制数据量影响。
  - 测试集：
    - **Maia Testset**（原Maia测试集）：2019年12月的对局，按等级分分为三组：Skilled（<1600）、Advanced（1600-1999）、Master（≥2000）。
    - **Cross-skill Testset**：2023年12月对局，覆盖多种主动/对手技能组合。
    - **Grounded Testset**：45万局面，附有Stockfish深度20评估，用于分析走法质量。
- **基准（Benchmark）**：
  - 对比方法：Stockfish（传统引擎）、Leela（AlphaZero开源版）、Maia（9个独立模型：1100-1900分）。
  - 评估指标：走法预测**准确率**（Top-1）、**困惑度**、**连贯性**（单调性比例、转变性比例、预测一致性）、**走法质量**（胜率损失下的准确率、中心兵损失、失误率）、**概念探测**（线性探针）。
- **消融实验**：去除技能感知注意力（直接拼接技能嵌入）和去除辅助信息头，在Maia-2_subset上比较准确率。

### 4. 资源与算力

- **训练硬件**：2×A100 (80G) GPU。
- **训练时长**：约13天（默认超参数设置）。
- **显式说明**：论文附录B明确提到“It took approximately 13 days to train Maia-2 with 2 × A100 (80G) GPUs under our default settings.”

### 5. 实验数量与充分性

- **实验数量**：论文进行了多组实验：
  - 主结果表1（各模型在三个技能组的准确率）及扩展表9（不同技能组合准确率矩阵）。
  - 困惑度比较（表2）。
  - 消融实验（表3）。
  - 连贯性指标：单调性/转变性比例（表4）、预测一致性热图（图3B）、走法质量分析（图10、图7）。
  - 概念探测（图4、图9）。
  - 案例研究（Mate-in-1 puzzle，图5）。
  - 人类对局干预实验（重赛率）。
- **充分性与公平性**：
  - 实验覆盖了多个测试集和指标，对比了多种类型模型（传统引擎、独立模型、统一模型）。
  - 通过Maia-2_subset控制了数据量，有效分离了架构创新和更多数据带来的收益（73%来自架构，27%来自数据）。
  - 消融实验验证了核心组件（技能感知注意力和辅助信息头）的有效性。
  - 在跨技能水平预测中，Maia-2始终优于Maia独立模型，证明了统一建模的优势。
  - 评估了走法质量（从最优到失误），结果更全面。
  - **结论**：实验设计较为充分、客观、公平。

### 6. 论文的主要结论与发现

- **准确率**：Maia-2在所有技能组上平均Top-1准确率比最佳Maia模型（Maia 1900）高出近2个百分点（53.25% vs 44.53%），且仅用23.3M参数（Maia九专家共92M）。
- **困惑度**：从Maia 1900的4.67 bits降低到4.07 bits，尤其是中高技能组改善显著。
- **连贯性**：
  - 单调性比例：Maia-2为27%，Maia仅约1%。
  - 转变性比例：Maia-2约22%，Maia约17%。
  - 预测一致性：改变主动棋手等级分对预测影响远大于改变对手等级分，符合直觉。
- **走法质量**：Maia-2在几乎所有失误程度（最优、错误、漏着）上分配更高概率给人类实际走法，尤其对失误走法更自信。
- **概念探测**：技能相关的概念（如棋盘整体评估）随技能水平改善；技能无关概念（如是否拥有双象）不随技能变化，符合认知。
- **人类对局实验**：与Maia-2对战后玩家重赛率略高（41.2% vs 40.3%），表明更受用户接受。

### 7. 优点

- **统一模型更高效**：单模型（23.3M参数）优于9个独立模型（92M参数），实现了跨技能水平的平滑过渡。
- **无需历史局面**：仅需当前棋盘，大幅提升训练效率（数据量小）和应用灵活性（可用于训练谜题）。
- **技能感知注意力**创新性地将技能嵌入注入查询，使模型动态调整注意力，自然捕捉非线性学习特征。
- **对手技能建模**：首次显式建模对手技能并影响预测，更符合真实人类决策。
- **辅助信息头**：通过多粒度标签提供丰富监督，提升了模型对棋局的深层理解。
- **数据平衡策略**：充分利用非对称对局数据，避免了独立模型无法处理的情况。
- **概念探针分析**：定性地验证了模型学到的概念与人类认知一致。

### 8. 不足与局限

- **未集成搜索**：论文未尝试结合MCTS（如KL正则化搜索），之前工作[26]表明搜索可进一步提升预测性能。
- **最强玩家分组粗糙**：将2000+分玩家合并为一个桶，实际上顶级大师之间差异极大，建模困难。
- **应用未实现**：论文侧重于建模，并未开发具体的AI教练或人类-AI协作工具，这部分工作留待未来。
- **计算成本高**：虽然模型比Maia轻量，但13天的训练时间仍显昂贵；未评估推理效率。
- **数据偏见风险**：训练数据来自Lichess，可能不代表所有玩家（如不同平台、离线对局），且仅使用Rapid时限，可能对极速或慢棋泛化性不足。
- **人类干预实验有限**：重赛率提升0.9p.p.，统计显著性未报告，且仅衡量了一个维度（重赛），其他用户体验（如学习效果、乐趣）未评估。
- **道德考量**：论文虽简短讨论了伦理，但未深入探讨模型可能被用于作弊或过度依赖AI建议的风险。

（完）
