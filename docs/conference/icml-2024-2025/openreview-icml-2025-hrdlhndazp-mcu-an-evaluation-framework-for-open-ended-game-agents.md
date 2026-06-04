---
title: "MCU: An Evaluation Framework for Open-Ended Game Agents"
title_zh: MCU：开放式游戏智能体评估框架
authors: "Xinyue Zheng, Haowei Lin, Kaichen He, Zihao Wang, QIANG FU, Haobo Fu, Zilong Zheng, Yitao Liang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hrdLhNDAzp"
tags: ["query:player-ai"]
score: 8.0
evidence: Minecraft中开放式游戏智能体的评估框架
tldr: "针对开放式游戏智能体评估困难的问题，提出MCU框架，包含3452个可组合原子任务和11大类挑战，任务组合机制可生成无限多样任务，评估结果与人类评分91.5%一致，为游戏智能体训练提供可靠基准。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hrdlhndazp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1734, \"height\": 1929, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrdlhndazp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1569, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrdlhndazp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1725, \"height\": 810, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrdlhndazp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrdlhndazp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1740, \"height\": 1001, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrdlhndazp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1720, \"height\": 1484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrdlhndazp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1760, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrdlhndazp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1686, \"height\": 2216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrdlhndazp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1779, \"height\": 2227, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 104, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1426, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1771, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 849, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1731, \"height\": 1333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1769, \"height\": 701, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1767, \"height\": 1103, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1062, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1749, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1748, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1753, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrdlhndazp/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1342, \"height\": 59, \"label\": \"Table\"}]"
motivation: 现有基准难以扩展，无法充分评估开放式游戏智能体。
method: 构建原子任务集合和任务组合机制，并提供通用评估框架。
result: MCU评估与人类评分高度一致，支持复杂任务泛化。
conclusion: MCU为开放式游戏智能体提供了可扩展的评估工具，促进AI训练。
---

## Abstract
Developing AI agents capable of interacting with open-world environments to solve diverse tasks is a compelling challenge. However, evaluating such open-ended agents remains difficult, with current benchmarks facing scalability limitations. To address this, we introduce \textit{Minecraft Universe} (MCU), a comprehensive evaluation framework set within the open-world video game Minecraft. MCU incorporates three key components: (1) an expanding collection of 3,452 composable atomic tasks that encompasses 11 major categories and 41 subcategories of challenges; (2) a task composition mechanism capable of generating infinite diverse tasks with varying difficulty; and (3) a general evaluation framework that achieves 91.5\% alignment with human ratings for open-ended task assessment. Empirical results reveal that even state-of-the-art foundation agents struggle with the increasing diversity and complexity of tasks. These findings highlight the necessity of MCU as a robust benchmark to drive progress in AI agent development within open-ended environments. Our evaluation code and scripts are available at https://github.com/CraftJarvis/MCU.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：开放式游戏智能体（如能在《我的世界》这样动态、开放世界中完成多样任务的AI）的评估面临重大挑战。现有基准（如MineDojo）存在任务质量低、多样性不足、缺乏自动化评估套件等问题，难以有效衡量智能体的泛化能力。
- **整体含义**：为弥补这一空白，论文提出 **Minecraft Universe (MCU)**，一个在《我的世界》中构建的综合性评估框架。MCU旨在通过大规模可组合任务、动态难度生成和自动化多维度评估，为开放式游戏智能体提供可扩展、可靠的基准，推动AI在开放世界环境中的发展。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：将评估分解为原子任务（atomic tasks），作为基本测试单元。原子任务可被组合成更复杂的复合任务，并通过LLM自动配置初始化状态，利用VLM进行多维度自动评分。
- **关键技术细节**：
  1. **原子任务集**：收集3,452个原子任务，覆盖11个大类（如挖掘、合成、战斗、建造、探索等）和41个子类别。来源包括现有基准、Minecraft Wiki、游戏内数据合成、专家与LLM头脑风暴。
  2. **任务组合机制**：支持通过逻辑运算符（AND/OR）和条件约束（如“时、地、方式”）将原子任务组合成无限多样的新任务，例如 `[mine oak log] OR [mine grass]`。
  3. **任务配置生成**：使用LLM（GPT-4o）为每个任务生成初始化配置（如生成矿石、怪物、物品等），通过自我反射（Reflexion）和模拟器反馈进行验证，确保配置可执行且具有随机性（如不同生物群系、天气）。
  4. **自动评估系统 AutoEval**：基于VLM（GPT-4o with vision）对智能体轨迹视频进行六维度评分：任务进度、动作控制、材料使用、任务效率、错误识别、创意尝试。评分前由LLM根据任务生成具体评分标准，提升一致性。
- **公式/算法流程**（文字说明）：
  - 输入：任务描述 → LLM生成环境初始化命令和验证 → 智能体在环境中执行 → 记录轨迹视频 → 抽取帧 → VLM结合任务特定标准给出各维度分数（0-1，五档）。比较评估时比较两个轨迹的各维度分数得出优劣。

## 3. 实验设计
- **环境与数据集**：
  - 环境：Minecraft 1.16.5 生存模式，640×360 RGB 图像输入，鼠标键盘动作空间。基于MineStudio实现。
  - 评估数据：500条轨迹（60个任务），包括智能体（VPT、STEVE-1等）和人类玩家的视频。由20名Minecraft专家进行人工标注（比较评估和绝对评分）。
- **基准（Benchmark）**：
  - **主实验**：30个原子任务（来自6个类别）+ 5个复合任务，每个任务30个随机种子（简单模式）；6个任务同时测试简单/困难模式，各10种子。
  - **大规模实验（附录E）**：90个原子任务（困难模式）+ 60个复合任务（简单模式），每个任务10种子。
  - **MCU-Turbo标准子集**：80个原子任务+20个复合任务，两种难度。
- **对比方法**：
  - 智能体：VPT (BC)、VPT (RL)、STEVE-1、GROOT（仅主实验）。GROOT使用视频指令，STEVE-1使用文本指令，VPT无指令。
  - 自动评估基线：MineCLIP（CLIP fine-tune on Minecraft frames）。
  - AutoEval中对比了不同VLM：MiniCPM、JarvisVLA、GPT-4o。

## 4. 资源与算力
- 文中在附录D的泛化实验中提到：使用在线PPO训练25M步，训练集状态从100到1,000,000，耗时约50小时，使用3块GPU（未明确型号）。主实验的算力未详细披露，推测使用类似配置。
- MCU自动评估使用GPT-4o API，文中称其成本仅为人工标注的1/8.1，效率为4.8倍。

## 5. 实验数量与充分性
- **实验数量**：主实验30+5任务；大规模实验90+60任务；消融实验包括AutoEval与MineCLIP对比（500轨迹/236对）、不同VLM对比、人类一致率分析；另有泛化实验（状态空间大小对泛化影响）等。整体实验量充足。
- **充分性**：实验设计相对公平，所有智能体在相同初始化条件下评估；人类标注经过一致性筛选（问卷正确率>75%）。但存在一定局限性：
  - 主实验仅30任务，且多数为简单模式，可能不能完全代表MCU的多样性。
  - 比较的智能体种类有限（仅4种），缺少基于LLM规划器或VLA的智能体。
  - 自动评估在创意维度与人类评分相关性较低（Pearson=0.63），说明主观维度评估仍有偏差。

## 6. 论文的主要结论与发现
- **AutoEval有效性**：在比较评估中，AutoEval (GPT-4o) 与人类判断的平均F1达91.5%；绝对评分中任务进度维度Pearson相关系数0.78。远优于MineCLIP（平均F1=34.6%）。
- **现有智能体能力不足**：即便是最优的GROOT，在30个简单原子任务上的平均任务进度仅为约0.5（各种类别差异大）。在困难模式下性能下降明显（如“睡床”任务从0.85降至0.50）。
- **创意与错误识别是短板**：所有智能体在“创意尝试”和“错误识别”维度得分极低，说明当前智能体缺乏创造性行为和自我修正能力。
- **复合任务更难**：复合任务的平均进度明显低于原子任务（GROOT在复合任务上仅0.23）。
- **状态空间影响泛化**：训练状态空间越大，泛化缺口越小（附录D实验），验证了Minecraft巨大状态空间对泛化评估的重要性。

## 7. 优点
- **大规模、高质量原子任务池**：3,452个任务覆盖全面，经过筛选和验证，避免重复和不可解任务。
- **全自动任务生成与评估**：LLM/VLM驱动，减少人工成本，支持无限任务变体，评估结果与人类高度一致。
- **多维度评估**：不仅关注任务完成率，还评估动作控制、创意、错误识别等，提供更丰富的智能体能力画像。
- **可扩展性**：支持任务组合、动态难度，可随时扩充任务集。代码和MCU-Turbo子集已开源，便于标准化对比。
- **与现有平台集成**：基于MineStudio，兼容多种智能体模型（VPT、STEVE-1、GROOT），易于使用。

## 8. 不足与局限
- **自动评估在某些维度仍不够可靠**：创意、错误识别等主观维度的VLM评分与人类相关性较低（Pearson 0.63/0.68），可能需要更细化的标准或更强VLM。
- **基准覆盖的智能体种类有限**：当前只评估了基于BC/RL的方法，未评估近期基于LLM规划器（如Voyager）或VLA（如Jarvis-VLA）的智能体，未来应扩展。
- **实验场景的潜在偏差**：主实验仅使用30个简单原子任务，可能高估或低估智能体能力；任务配置中随机因素可能引入不易控制的变化。
- **计算成本**：AutoEval依赖GPT-4o API，大规模评估可能产生较高成本；LLM配置生成也可能需要多次调用。
- **环境特定性**：MCU基于Minecraft，结论向其他开放世界环境的迁移性未验证。
- **人类标注的绝对一致性**：人类评分者之间Pearson相关系数约为0.83（任务进度）到0.69（创意），存在分歧，影响评估基准的精确性。

（完）
