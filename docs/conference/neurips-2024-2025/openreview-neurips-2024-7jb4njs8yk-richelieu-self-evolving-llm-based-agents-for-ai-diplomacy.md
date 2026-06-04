---
title: "Richelieu: Self-Evolving LLM-Based Agents for AI Diplomacy"
title_zh: "Richelieu: 用于AI外交的自进化LLM代理"
authors: "Zhenyu Guan, Xiangyu Kong, Fangwei Zhong, Yizhou Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=7Jb4NJS8Yk"
tags: ["query:player-ai"]
score: 9.0
evidence: 用于外交游戏的LLM代理，具有自进化能力
tldr: 外交游戏涉及多智能体协商与长期规划，对AI极具挑战。该论文提出Richelieu，一种基于大型语言模型的自进化代理系统，能够利用经验进行推理和策略调整。通过自举和改进，代理在外交游戏中表现出类人水平。该工作展示了LLM在复杂多智能体博弈中的潜力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-7jb4njs8yk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1348, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7jb4njs8yk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1384, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7jb4njs8yk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1226, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7jb4njs8yk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 689, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7jb4njs8yk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7jb4njs8yk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1282, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7jb4njs8yk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1256, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7jb4njs8yk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1405, \"height\": 615, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-7jb4njs8yk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 711, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7jb4njs8yk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 711, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7jb4njs8yk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 887, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7jb4njs8yk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1456, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7jb4njs8yk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 663, \"height\": 186, \"label\": \"Table\"}]"
motivation: 外交游戏需要社会化推理和长期规划，现有AI难以胜任。
method: 构建基于LLM的自进化代理，利用经验库和推理模块，实现策略的自动改进。
result: Richelieu在外交游戏中达到与人类玩家竞争的水平。
conclusion: LLM结合自进化机制可有效解决复杂多智能体博弈任务。
---

## Abstract
Diplomacy is one of the most sophisticated activities in human society, involving complex interactions among multiple parties that require skills in social reasoning, negotiation, and long-term strategic planning. Previous AI agents have demonstrated their ability to handle multi-step games and large action spaces in multi-agent tasks. However, diplomacy involves a staggering magnitude of decision spaces, especially considering the negotiation stage required. While recent agents based on large language models (LLMs) have shown potential in various applications, they still struggle with extended planning periods in complex multi-agent settings. Leveraging recent technologies for LLM-based agents, we aim to explore AI's potential to create a human-like agent capable of executing comprehensive multi-agent missions by integrating three fundamental capabilities: 1) strategic planning with memory and reflection; 2) goal-oriented negotiation with social reasoning; and 3) augmenting memory through self-play games for self-evolution without human in the loop. Project page: https://sites.google.com/view/richelieu-diplomacy.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：外交博弈（Diplomacy）是一种涉及多方互动、需要社会化推理、谈判与长期规划的高度复杂任务。此前AI方法（如Meta的Cicero）虽取得突破，但严重依赖大量人类游戏数据进行训练，且模型难以泛化到其他场景，无法自我持续进化。
- **核心问题**：能否构建一种不依赖人类数据、能够通过自对弈自主进化、兼具战略规划、目标导向谈判与社交推理能力的AI外交代理？
- **整体含义**：论文提出Richelieu，一种基于大型语言模型（LLM）的自进化代理系统，首次在无人类标注数据条件下，在外交游戏中达到超越现有最优方法（Cicero）的性能，证明了LLM在多智能体复杂交互中的巨大潜力。

### 2. 方法论：核心思想、关键技术细节

- **核心思想**：将LLM与记忆、反思、社会推理、谈判和自对弈机制融合，构建一个可自我进化的单一代理框架。无需人类演示，通过自对弈积累经验并不断反思优化。
- **关键技术细节**：
  - **社会推理（Social Reasoning）**：分析当前游戏状态，构建社会信念（包括对其他玩家的意图推断和关系评估），识别盟友、敌人和潜在威胁。
  - **战略规划与反思（Planner with Reflection）**：基于社会信念和长期目标，提出当前子目标；利用记忆中的历史经验（通过相似度检索）对子目标进行反思和优化，避免短视行为。
  - **谈判器（Negotiator）**：基于子目标、社会信念和对方消息，通过多步推理（判断对方是否说谎、真实意图、是否需欺骗等），生成谈判话语以达成合作或策略欺骗。
  - **行动器（Actor）**：在谈判后更新社会信念，执行具体军事行动。
  - **记忆管理（Memory Management）**：记录每回合的状态、子目标、谈判消息、所有玩家行动及评估（子目标合理性、玩家可信度），形成经验库供后续反思使用。
  - **自进化（Self-Evolution via Self-Play）**：通过多代理自对弈（所有国家由Richelieu控制）生成多样化经验，经验随训练增加而丰富，推动代理性能持续提升直至收敛。

### 3. 实验设计

- **数据集/场景**：使用开源Diplomacy游戏平台（Paquette et al., 2019），包含数千局人类游戏数据（但Richelieu未使用）。实验分为无谈判（No-Press）和有谈判（Press）两种设定。
- **Benchmark与对比方法**：
  - No-Press：对比SL-DipNet、RL-DipNet、BRPI、SearchBot、DORA、Cicero。
  - Press：对比Cicero（SOTA）以及基于AutoGPT的LLM代理。
  - 泛化实验：使用GPT-4、Llama 3、ERNIE Bot、Spark Desk四种LLM。
  - 额外验证：狼人杀游戏（附录C）。
- **评估指标**：
  - 胜率（Win）、最多补给中心率（Most SC）、存活率（Survived）、失败率（Defeated）。
  - 使用C-Diplo Argir评分系统（国际外交比赛常用，每局总分99分）。

### 4. 资源与算力

- **未明确说明**：论文中没有具体提及使用的GPU型号、数量或训练时长。实验依赖于调用大语言模型API（如GPT-4、Llama 3等），可能主要耗费API调用成本，而非本地训练。在“Experiments Compute Resources”部分只简单声明提供了足够信息，但正文未列出具体数值。因此，算力细节缺失。

### 5. 实验数量与充分性

- **实验数量**：
  - No-Press设置：7种方法两两对比，产生分数热图（图4）。
  - Press设置：Richelieu vs. Cicero（多组子实验：3 vs. 4配置，共约7组子结果），Richelieu vs. AutoGPT（多组子结果）。
  - 不同LLM泛化：4种LLM、每个LLM进行不同训练轮次（图5，横轴对数训练次数，共约32个数据点）。
  - 消融实验：逐步添加模块（共6种配置），结果见表3。
  - 社会推理成功率评估（表4）。
  - 附加狼人杀实验（附录C）。
- **充分性与客观性**：实验覆盖无谈判和有谈判两种关键场景，消融实验验证每个模块的必要性，不同LLM泛化证明框架通用性。每组实验进行1000局游戏取平均，使用随机分配国家，统计合理。但缺乏多个随机种子或误差线（文中仅报告均值，未明确显示方差），这是常见不足。

### 6. 主要结论与发现

- **无谈判设定**：Richelieu在No-Press中显著优于所有基于人类数据的基线方法（包括Cicero），分数高出约10%。
- **有谈判设定**：Richelieu对战Cicero时，胜率约高0.7%，胜率+Most SC率约高2%，失败率低0.6%，C-Diplo评分高出约10%。
- **与AutoGPT对比**：Richelieu大幅领先AutoGPT（胜率9.1% vs. 1.63%）。
- **自对弈进化有效**：随着训练迭代增加，胜率稳步提升，失败率下降，最终趋于稳定（图5）。
- **框架泛化性强**：不同LLM（GPT-4、Llama 3等）通过本框架训练后性能均显著提升，弱模型也能接近Cicero水平。
- **消融证实模块贡献**：社会推理、规划反思、谈判管道、自对弈记忆均显著提升最终性能。

### 7. 优点

- **无需人类数据**：首次在外交领域实现完全无人类演示的自进化，降低对昂贵标注数据的依赖。
- **模块化设计**：社会推理、反思、谈判等模块可独立调整，易于迁移至其他多智能体协同/社交任务（如狼人杀验证）。
- **自进化机制**：通过记忆驱动的反思和自对弈实现持续改进，性能随经验积累提升。
- **综合能力强**：同时处理长期规划、短期战术、社交欺骗、信任评估等多重挑战。
- **框架通用性**：在多种LLM上均有效，且可推广到狼人杀等其他社交博弈。

### 8. 不足与局限

- **游戏设定局限性**：外交游戏动作空间相对结构化，且信息公开程度高（除谈判内容外）；现实外交充满不完全信息和无限决策空间，本框架尚需适配。
- **自对弈收益递减**：随着经验库增长，相似经验增多可能降低多样性和信息增益，性能提升趋于饱和。
- **计算成本未披露**：未报告LLM调用次数、训练时间、API费用等指标，不利于复现和成本评估。
- **实验统计力度不足**：结果未提供标准差或置信区间，仅靠1000局均值的稳定性有待进一步验证（尤其胜率差异较小时）。
- **伦理风险**：论文虽讨论了伦理考虑（可能被用于欺诈），但未提出具体缓解措施。框架中的欺骗和操纵能力若被滥用可能带来风险。
- **泛化验证有限**：仅在外交和狼人杀两个任务测试，尚未在更多类型的社会交互场景（如经济谈判、多人协作任务）中验证。
- **消融实验的基线**：仅对比了逐步增加模块的情况，未与其他端到端LLM框架（如ReAct、Reflexion等）对比，公平性可进一步提升。

（完）
