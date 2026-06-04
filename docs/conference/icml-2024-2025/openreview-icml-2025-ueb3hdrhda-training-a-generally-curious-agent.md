---
title: Training a Generally Curious Agent
title_zh: 训练通用好奇智能体
authors: "Fahim Tajwar, Yiding Jiang, Abitha Thankaraj, Sumaita Sadia Rahman, J Zico Kolter, Jeff Schneider, Russ Salakhutdinov"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=UeB3Hdrhda"
tags: ["query:player-ai"]
score: 6.0
evidence: 训练通用好奇智能体进行决策
tldr: 该论文研究了语言模型在探索和决策中的泛化问题，提出Paprika微调方法，通过多任务合成交互数据训练，使模型能基于上下文反馈在未见环境中自适应，虽然并非专为游戏设计，但其通用决策能力可迁移至游戏场景。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1588, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1755, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1759, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1766, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1767, \"height\": 1088, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1769, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1761, \"height\": 1084, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1765, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1767, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1769, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1326, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1324, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1327, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1762, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1749, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1748, \"height\": 523, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1625, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1814, \"height\": 2137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1252, \"height\": 113, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 941, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 420, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 332, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 330, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1679, \"height\": 1471, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1700, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1736, \"height\": 95, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1427, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1765, \"height\": 1058, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1410, \"height\": 1850, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1759, \"height\": 2140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1237, \"height\": 2093, \"label\": \"Table\"}]"
motivation: 语言模型在需要策略信息获取的场景中探索能力不足。
method: 在多样合成任务上微调语言模型，使其学会基于环境反馈自适应决策。
result: 微调模型能零样本迁移到全新决策任务，包括部分游戏环境。
conclusion: 多任务训练可赋予语言模型通用决策能力。
---

## Abstract
Efficient exploration is essential for intelligent systems interacting with their environment, but existing language models often fall short in scenarios that require strategic information gathering. In this paper, we present **Paprika**, a fine-tuning approach that enables language models to develop general decision-making capabilities that are not confined to particular environments. By training on synthetic interaction data from different tasks that require diverse strategies, Paprika teaches models to explore and adapt their behavior on a new task based on environment feedback in-context without more gradient updates. Experimental results show that models fine-tuned with Paprika can effectively transfer their learned decision-making capabilities to entirely unseen tasks without additional training. Unlike traditional training, our approach's primary bottleneck lies in sampling useful interaction data instead of model updates. To improve sample efficiency, we propose a curriculum learning strategy that prioritizes sampling trajectories from tasks with high learning potential. These results suggest a promising path towards AI systems that can autonomously solve novel sequential decision-making problems that require interactions with the external world.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有语言模型（LLM）在需要战略性信息获取的多轮交互决策任务中表现不佳。虽然 LLM 具有上下文学习能力，但缺乏通用的决策与探索技能，难以在完全陌生的环境中自主完成任务。
- **整体含义**：本文旨在训练一个“通用好奇智能体”，使其具备跨任务迁移的序贯决策能力——在不额外梯度更新、不依赖特定任务先验的情况下，仅通过环境反馈在上下文中调整行为。这为构建能自主与外部世界交互的 AI 系统提供了可行路径。

## 2. 论文提出的方法论
### 核心思想
- 提出 **Paprika** 微调框架：在多个不同决策任务上生成合成交互数据，利用偏好优化（DPO 变体）使模型倾向于更成功的轨迹，从而学习通用的探索与决策策略。训练后的模型可零样本迁移到未见任务。

### 关键技术细节
1. **任务设计**：设计 10 个纯文本任务组（如 20 问、Wordle、Battleship、Bandit 等），要求多轮交互、部分可观测、策略多样化。部分任务使用 LLM（GPT-4o-mini）作为环境，部分使用硬编码程序。
2. **数据生成**：对每个任务以高温度（1.5）和 Min-p 采样生成大量轨迹，过滤后为每个任务构建一个偏好对（最佳轨迹 vs 随机低分轨迹）。
3. **优化目标**：
   - 监督微调（SFT）：最大化获胜轨迹的似然。
   - 多轮直接偏好优化（DPO）：对每个时间步的动作 token 计算偏好损失。
   - 最终使用 **RPO** 损失（SFT + DPO 加权组合，α=1.0）。
4. **课程学习**：基于“变异系数”（标准差/均值）度量每个任务的“学习潜力”，使用上置信界（UCB）算法动态选择最有希望的任务组进行数据采样，提高数据效率。

### 公式与算法（文字说明）
- SFT 损失：对获胜轨迹中所有动作 token 的对数似然求和取负期望。
- DPO 损失：对获胜和失败轨迹的所有动作 token，计算对数概率比之差后再做 logistic 损失，仅考虑动作 token。
- RPO 损失：DPO 损失 + α * SFT 损失（这里 α=1.0）。
- 课程学习：每组任务的 ν = 标准差/均值，UCB 选择公式为 θ_k = 平均表现 + sqrt(2·ln(总采样数)/组采样数)。

## 3. 实验设计
- **任务场景**：10 个任务组（20 问、猜城市、Wordle、细胞自动机、客户服务、谋杀谜案、Mastermind、Battleship、Minesweeper、Bandit 最优臂选择）。训练/测试集分开。
- **基准模型**：Llama-3.1-8B-Instruct、Gemma-3-12B-IT，对比 GPT-4o-mini 以及原始指令模型。
- **评估指标**：平均成功率、Pass@k 成功率、平均解决轮数。同时评估标准 NLP 基准（MT-Bench、AlpacaEval、GPQA、Math、MMLU-Pro、IFEval）以检测能力退化。
- **对比方法**：
  - 原始指令模型
  - Paprika（完整训练）
  - 留一法（LOO）训练（只在除目标组以外的 9 组上训练）
  - 单任务组训练
  - 仅 SFT 无 RPO
  - 统一采样 vs 课程学习
  - 在 WildChat（100k 多轮对话）上微调的基线
  - 不同温度（0.3, 0.7, 1.0）评估

## 4. 资源与算力
- **训练硬件**：
  - Llama-3.1-8B-Instruct：1 节点 × 8 张 NVIDIA L40S GPU。
  - Gemma-3-12B-IT：1 节点 × 8 张 NVIDIA H100 GPU。
  - 推理与数据生成：单张 NVIDIA A40 GPU。
- **API 成本**：整个项目约 20,000 USD；单次完整实验约 1,000 USD。
- **训练时长**：论文未明确给出具体时长（如小时数），但强调瓶颈在于数据生成而非模型更新。

## 5. 实验数量与充分性
- 实验覆盖广泛：10 个任务组 × 多种变体（全训练、留一、单任务、SFT only、课程 vs 均匀等）。
- 消融实验：SFT vs RPO、课程 vs 均匀、不同基模型、不同温度、Pass@k 分析。
- 迁移测试：留一法验证零样本迁移，额外在 LMRL-Gym 的独立分割上评估，以及非 5 字母 Wordle 变体。
- 标准基准评估：6 个常见 NLP 评估集（各 3 个种子），证明没有性能退化。
- 总体实验设计较充分，对比方法合理，统计误差（标准误差）已报告，结果具有可复现性。

## 6. 论文的主要结论与发现
- Paprika 显著提升 LLM 在各类决策任务上的成功率和效率，平均相对提升约 47%。
- 训练后的策略可零样本迁移到完全未见任务（留一法实验），且多任务联合训练优于单任务训练。
- 课程学习（基于 UCB 和变异系数）比均匀采样更高效，提升约 1.4%–3.3%。
- Paprika 不会损害模型的标准 NLP 能力。
- 多轮 DPO/RPO 比纯 SFT 进一步带来增益。

## 7. 优点
- **方法简洁可扩展**：仅需自生成数据 + 标准偏好优化，无需外部专家轨迹或任务特定算法。
- **强泛化性**：零样本迁移至全新任务组，表明学到的探索策略具有通用性。
- **课程学习创新**：利用变异系数度量学习潜力，结合多臂赌博机选择高效任务，解决了数据生成瓶颈。
- **评估全面**：涵盖多种任务类型、基模型、迁移场景，并验证标准能力无退化，结果可信。

## 8. 不足与局限
- **依赖基模型质量**：若基础模型本身性能过低，生成轨迹中高奖赏轨迹少，Paprika 效果受限。
- **离线优化限制**：使用离线 DPO/RPO，未探索在线 RL（如 PPO），预期在线方法可能更强（作者已指出）。
- **人工设计任务开销大**：尽管部分环境用 LLM 自动生成，但实现和调试仍需大量人力。
- **课程学习依赖任务分组先验**：分组质量影响课程效果，缺乏完全自动的分组机制。
- **环境漏洞风险**：对使用 LLM 作为环境的任务，存在被“hack”获得虚假成功的问题（作者已承认约 1.5% 污染）。
- **未在更大规模（如 70B）或推理模型上验证**：计算资源有限，未来应扩展到更强模型。

（完）
