---
title: "FactorSim: Generative Simulation via Factorized Representation"
title_zh: FactorSim：通过因子化表示进行生成式仿真
authors: "Fan-Yun Sun, Harini S I, Angela Yi, Yihan Zhou, Alex Zook, Jonathan Tremblay, Logan Cross, Jiajun Wu, Nick Haber"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=wBzvYh3PRA"
tags: ["query:player-ai"]
score: 8.0
evidence: 从语言输入生成仿真环境用于训练游戏Agent
tldr: 针对从自然语言生成完整仿真环境以训练游戏Agent的挑战，本文提出FactorSim，利用因子化POMDP表示逐步生成代码仿真。该方法能有效减少上下文依赖，在生成仿真基准上表现优异，为自动化游戏Agent训练提供了端到端解决方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-wbzvyh3pra/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1410, \"height\": 797, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wbzvyh3pra/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 987, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wbzvyh3pra/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 920, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wbzvyh3pra/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wbzvyh3pra/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1427, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wbzvyh3pra/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 694, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wbzvyh3pra/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1422, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wbzvyh3pra/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1420, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wbzvyh3pra/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1395, \"height\": 2024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wbzvyh3pra/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1438, \"height\": 979, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-wbzvyh3pra/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wbzvyh3pra/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wbzvyh3pra/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1371, \"height\": 319, \"label\": \"Table\"}]"
motivation: 从自然语言生成完整的仿真环境用于Agent训练仍是难题。
method: 采用因子化POMDP表示，逐步生成仿真代码。
result: 在生成仿真基准上优于现有方法。
conclusion: 为语言驱动的仿真生成提供了高效框架。
---

## Abstract
Generating simulations to train intelligent agents in game-playing and robotics from natural language input, user input, or task documentation remains an open-ended challenge. Existing approaches focus on parts of this challenge, such as generating reward functions or task hyperparameters. Unlike previous work, we introduce FACTORSIM that generates full simulations in code from language input that can be used to train agents. Exploiting the structural modularity specific to coded simulations, we propose to use a factored partially observable Markov decision process representation that allows us to reduce context dependence during each step of the generation. For evaluation, we introduce a generative simulation benchmark that assesses the generated simulation code’s accuracy and effectiveness in facilitating zero-shot transfers in reinforcement learning settings. We show that FACTORSIM outperforms existing methods in generating simulations regarding prompt alignment (i.e., accuracy), zero-shot transfer abilities, and human evaluation. We also demonstrate its effectiveness in generating robotic tasks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：从自然语言输入（如用户描述、任务文档）自动生成完整的、可运行的仿真环境代码，并利用这些仿真环境训练智能体（如游戏AI或机器人），是一个尚未充分解决的挑战。
- **研究动机**：仿真环境在训练Agent时具有低成本、安全、可大量生成的巨大潜力，但手工设计和开发仿真环境成本高昂，尤其当需要生成大规模、符合详细设计规范的仿真分布时。现有工作大多聚焦于仿真中的某个子任务（如生成奖励函数、超参数、任务配置），而无法生成完整的仿真代码。
- **整体含义**：本文提出FactorSim，首次尝试从文本描述直接生成完整的、可用于强化学习的仿真代码，从而为规模化、低成本地生成训练环境提供了新路径。

## 2. 论文提出的方法论

### 2.1 核心思想
- **利用仿真代码的结构模块化特点**，将仿真生成过程分解为多个步骤，每个步骤只关注一个独立的模块。
- **引入因子化部分可观测马尔可夫决策过程（Factored POMDP）表示**，在每个生成步骤中只选择与当前模块相关的上下文（状态变量和已有因子），从而减少对大段上下文的依赖，提升LLM生成准确性。

### 2.2 关键技术细节
1. **建模仿真为POMDP**：将仿真形式化为一个POMDP元组 M = ⟨S, A, O, T, Ω, R⟩。
2. **Chain-of-Thought分解**：将输入的自然语言描述Qtext分解为一系列步骤 (q1, ..., qK)，每一步对应一个子模块。
3. **因子化表示**：定义因子化POMDP，状态空间分解为多个状态变量 S = S[1] × ... × S[n]，转移函数和奖励函数也因子化。定义作用域 Z ⊆ {1,...,n}，只考虑相关状态变量。
4. **逐步生成算法**（Algorithm 1）：
   - 初始化一个最小POMDP M1（只包含得分状态变量，键盘动作，恒等转移，奖励为得分变化）。
   - 对每一步 qk：
     - 更新状态空间：p(Sk+1 | Sk, qk)
     - 选择相关状态变量作用域 Zk：p(S[Zk] | Sk+1, qk)
     - 更新**控制器组件**（动作相关部分）：p(T^(a)_{k+1} | S[Zk], A, qk)
     - 更新**模型组件**（动作无关部分）：p(T^(s)_{k+1} | T[Zk], S[Zk], qk)
     - 更新**视图组件**（观测模型）：p(Ω_{k+1} | S[Zk], qk)
   - 每一步生成的函数不超过三个：handle_key_press（控制器）、collision_logic（模型）、render_red_dot（视图）。
5. **上下文选择**：仅选择与当前步骤相关的现有因子（T[Zk]、R[Zk]）作为上下文，避免全部代码作为输入。

### 2.3 算法流程（文字说明）
- 输入：自然语言描述Qtext、LLM
- 输出：完整的仿真代码（POMDP）
- 第一步：用Chain-of-Thought将Qtext分解为步骤计划。
- 循环执行每一模块：
  1. 识别需要增加的变量和已有相关变量（状态空间更新）。
  2. 选择相关状态变量集合。
  3. 生成控制器函数（处理输入事件，如按键）。
  4. 生成模型函数（更新游戏状态，如碰撞逻辑）。
  5. 生成视图函数（渲染UI）。
- 最终将所有生成的代码片段合并成完整仿真。

## 3. 实验设计

### 3.1 数据集/场景
- **2D RL游戏基准**：PyGame Learning Environment中的8个游戏：Flappy Bird, Catcher, Snake, Pixelcopter, Pong, Puckworld, Waterworld, Monster Kong。输入提示来自游戏文档（手动补充不完整部分）。
- **机器人任务基准**：GenSim的50个机器人任务，在CLIPort框架中运行（物理引擎仿真）。

### 3.2 Benchmark
- 作者提出了一个新的**生成式仿真基准（Generative Simulation Benchmark）**，包含：
  - **系统测试（System Tests）**：程序化自动检查生成的仿真行为是否符合提示规格（如关键动作、碰撞逻辑等）。统计通过率。
  - **零样本迁移（Zero-shot Transfer）**：在10个生成环境上训练PPO Agent（10M步），直接测试在原始“真实”环境上的表现，并归一化奖励（0=随机策略，1=在真实环境上训练的PPO性能）。
  - **人工评估**：参与者（共320次评估，每游戏40次）从1-4分对游戏的“可玩性”进行评分（4=完全可玩，1=无法启动）。

### 3.3 对比方法
- **Baselines**：
  - Vanilla（一次性生成全部代码）
  - Self-debug（根据错误反馈重试，最多10次）
  - Chain-of-Thought + Self-debug
  - AgentCoder（多Agent代码生成框架）
  - 以上所有方法均使用了两种LLM：GPT-4 和 Llama-3（70B）
- **消融**：对比不含因子化POMDP的CoT+Self-debug（即FactorSim的消融）。

### 3.4 机器人任务生成实验
- 对比GenSim的三种基线：Vanilla（一次生成）、Chain-of-Thought（topdown）、Chain-of-Thought（bottom-up）。
- 评估指标：语法正确率、运行时通过率、任务完成率（oracle agent收集99%奖励）、人工通过率（检查任务描述与生成结果是否一致）。

## 4. 资源与算力

- **硬件**：8块Nvidia A40 GPU、1008G RAM。
- **代码生成耗时**：一次生成约30秒到5分钟。
- **强化学习训练**：一次试验（在10个环境上共训练10M步）约3-5小时。
- 论文明确给出了这些信息，因此算力资源是公开的。

## 5. 实验数量与充分性

- **实验数量**：
  - 2D游戏生成：8个游戏 × 多种基线 + 多次运行（10个环境） → 上百次生成。
  - 零样本迁移：每种方法生成10个环境，训练PPO，测试一次 → 多个方法对比。
  - 人工评估：320次评估（每游戏40次）。
  - 机器人任务：50个任务 × 4种方法 + 消融。
- **公平性**：所有方法均使用相同的输入提示（文档+手动补全），LLM参数一致（如temperature固定为1）。系统测试自动化，避免主观偏差。人工评估有明确评分标准。
- **充分性**：覆盖了代码正确性、迁移有效性、人类使用体验；对比了开源和闭源LLM；消融实验验证了因子化表示的效果。实验设计较为充分。

## 6. 论文的主要结论与发现

1. **FactorSim在系统测试通过率上显著优于所有基线**（7/8个游戏），GPT-4+FactorSim平均通过率最高（如Flappy Bird 78% vs 基线最高35%）。
2. **零样本迁移结果更好**：FactorSim生成的仿真训练的PPO Agent在真实环境上归一化奖励更高，说明代码更接近规范。
3. **人工评估显示FactorSim生成更多“可玩”游戏**：评分分布优于最强的GPT-4 CoT+Self-debug基线。
4. **在机器人任务生成上，FactorSim在运行时通过率和人工通过率上均超过GenSim基线**，尤其擅长处理包含空间关系（如“在上方”、“在左边”）的任务。
5. **因子化分解有效减少了LLM的上下文依赖**，提升了生成准确率，同时使用更少的token（相比CoT+Self-debug），因此更高效。

## 7. 优点

- **方法创新性**：首次将因子化POMDP表示引入仿真代码生成，有效降低上下文长度和生成错误。
- **完整性**：生成的仿真不仅是部分组件，而是完整可运行的代码，可用于直接训练RL Agent。
- **可解释性与可控性**：代码形式便于人类检查、修改和调试，比神经网络世界模型更透明。
- **高效性**：相比迭代调试方法（如Self-debug），FactorSim token消耗更少且准确率更高。
- **迁移能力验证**：不仅测试代码正确性，还验证了训练出的策略能泛化到未见过环境，实用价值高。
- **机器人任务扩展**：展示了在物理仿真机器人任务中的有效性。

## 8. 不足与局限

- **规模限制**：文中提到“复杂仿真代码可能超过现有LLM上下文窗口”，大型3D游戏尚未处理。
- **多智能体未涉及**：仅针对单Agent仿真，多Agent场景需未来工作。
- **机器人实验的局限性**：评估中的“任务完成率”不完美（如oracle agent可能因物理原因失败）；需要进一步验证仿真到真实环境的迁移。
- **实验覆盖**：
  - 仅测试了2D游戏和简单机器人任务，未涉及复杂3D环境。
  - 机器人任务仅使用GenSim数据集和CLIPort框架，泛化性可能有限。
- **偏差风险**：人工评估可能受审美/难度因素干扰，尽管已提示排除；系统测试可能无法覆盖所有游戏行为。
- **LLM依赖**：方法效果受限于底层LLM的能力（如Llama-3在一些游戏中表现较差，存在“模式崩溃”）。

（完）
