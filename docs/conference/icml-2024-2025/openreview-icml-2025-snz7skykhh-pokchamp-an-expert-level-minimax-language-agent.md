---
title: "PokéChamp: an Expert-level Minimax Language Agent"
title_zh: PokéChamp：专家级极小极大语言智能体
authors: "Seth Karten, Andy Luu Nguyen, Chi Jin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=SnZ7SKykHh"
tags: ["query:player-ai"]
score: 9.0
evidence: 基于LLM的Pokémon对战极小极大智能体，含对手建模
tldr: "本文提出PokéChamp，一个基于大语言模型（LLM）的Pokémon对战极小极大智能体。该框架利用LLM的通用能力替代传统minimax搜索中的动作采样、对手建模和值函数估计三个模块，无需额外训练。在Gen 9 OU格式中，使用GPT-4o的PokéChamp对最强LLM基准胜率达76%，规则基准为84%。该工作展示了LLM在复杂游戏AI中的应用潜力。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-snz7skykhh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-snz7skykhh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1371, \"height\": 743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-snz7skykhh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 615, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-snz7skykhh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 771, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-snz7skykhh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1353, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-snz7skykhh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 822, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-snz7skykhh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 805, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-snz7skykhh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1687, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-snz7skykhh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 844, \"height\": 757, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-snz7skykhh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1012, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-snz7skykhh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1197, \"height\": 442, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-snz7skykhh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-snz7skykhh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1060, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-snz7skykhh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1200, \"height\": 454, \"label\": \"Table\"}]"
motivation: 复杂游戏如Pokémon中，传统AI面临状态空间大和部分可观测问题。
method: 用LLM替代minimax搜索中的动作采样、对手建模和值函数估计。
result: "对最强LLM基准胜率76%，规则基准84%。"
conclusion: LLM可有效提升游戏AI搜索性能。
---

## Abstract
We introduce PokéChamp, a minimax agent powered by Large Language Models (LLMs) for Pokémon battles. Built on a general framework for two-player competitive games, PokéChamp leverages the generalist capabilities of LLMs to enhance minimax tree search. Specifically, LLMs replace three key modules: (1) player action sampling, (2) opponent modeling, and (3) value function estimation, enabling the agent to effectively utilize gameplay history and human knowledge to reduce the search space and address partial observability. Notably, our framework requires no additional LLM training. We evaluate PokéChamp in the popular Gen 9 OU format. When powered by GPT-4o, it achieves a win rate of 76\% against the best existing LLM-based bot and 84\% against the strongest rule-based bot, demonstrating its superior performance. Even with an open-source 8-billion-parameter Llama 3.1 model, PokéChamp consistently outperforms the previous best LLM-based bot, Pokéllmon powered by GPT-4o, with a 64\% win rate. PokéChamp attains a projected Elo of 1300-1500 on the Pokémon Showdown online ladder, placing it among the top 30\%-10\% of human players. In addition, this work compiles the largest real-player Pokémon battle dataset, featuring over 3 million games, including more than 500k high-Elo matches. Based on this dataset, we establish a series of battle benchmarks and puzzles to evaluate specific battling skills. We further provide key updates to the local game engine. This work establishes Pokémon as a benchmark to integrate LLM technologies with game-theoretic algorithms addressing general multi-agent problems. Videos, code, and dataset are available online.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**： Pokémon 对战是一个复杂的、部分可观测的、双人零和马尔可夫博弈，其状态空间在首回合即高达 \(10^{354}\)，且每回合有时间限制（150 秒总时间 + 15 秒增量）。传统的强化学习方法（如 AlphaZero）虽在棋类、星际争霸等游戏中取得超人表现，但需要大量任务特异性训练和工程。而大语言模型（LLM）作为通用智能体，具备先验知识和常识，但在复杂游戏中的规划能力弱，常不及基于规则的启发式机器人。
- **核心问题**： 如何在不进行额外微调的情况下，利用 LLM 的通用能力来增强博弈树搜索，从而在庞大状态空间和部分可观测性下实现专家级表现？
- **整体含义**： 本文提出 PokéChamp，将 LLM 集成到最小最大树搜索的三个关键模块（动作采样、对手建模、值函数估计）中，无需任务特异性训练即可达到人类专家水平。这为结合 LLM 与博弈论算法解决一般多智能体问题提供了新范式。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**： 利用 LLM 的先验知识来约束最小最大搜索的空间：用 LLM 生成少数有意义的候选动作（剪枝），预测对手最可能的动作（处理部分可观测性），以及对深度截断的叶子节点进行局面评估（代替终端奖励）。
- **关键技术细节**：
    - **世界模型与近似转移**： 利用历史对战数据（超 300 万场）和统计信息（技能配置、道具使用率等）推断隐藏状态（如对手的攻防属性），结合本地模拟器进行一步前瞻，计算每个动作下的“最少回合数击败对手”作为可采纳启发式信息。
    - **玩家动作采样**： 提示 LLM 包含团队策略、可观测状态、历史回合、一步前瞻启发式和合法动作集，输出少量候选动作。同时补充一步前瞻的最优攻击和 Abyssal 机器人的最优换人建议。
    - **对手建模**： 分两部分：①利用历史数据估计对手隐藏的攻防属性分布；② LLM 基于对手视角预测其动作。
    - **值函数估计**： LLM 对深度截断 \(k\) 步后的局面进行评分，考虑剩余 Pokémon 数量、速度优势、对手招式效果等正面和负面因素。
- **算法流程**（文字描述）：
    在每回合 \(h\)，智能体观察到信息集 \(x_h\)，通过 LLM 采样 \(m\) 个候选动作；对每个候选动作，用对手模型采样 \(n\) 个最可能的对手反应；通过世界模型模拟转移至新信息集 \(x_{h+1}\)；重复展开至深度 \(k\) 后，使用 LLM 值函数评估叶子节点；反向传播最小最大值，选择最优动作 \(\hat{a}_h = \arg\max_{a_h} \min_{b_h} \mathbb{E}\left[\dots \max_{a_{h+k-1}} \min_{b_{h+k-1}} \mathbb{E}[V(x_{h+k})]\right]\)。

### 3. 实验设计：数据集、场景、Benchmark 与对比方法

- **数据集**： 从 Pokémon Showdown 平台收集超过 **300 万场**对战回放，其中 **50 万场以上为高 Elo（>1600）**，覆盖多种格式（Gen 8 Random Battles、Gen 9 OU 等），用于估计转移概率和对手策略分布。
- **评测场景**：
    - **动作预测**： 在收集的数据集上预测玩家和对手的动作（Top-1 到 Top-5 准确率）。
    - **小游戏谜题**： ① 1000 个 1v1 场景（随机对战格式），测试最优动作序列；② 特殊机制谜题（Terastalization、Dynamax）。
    - **完整对战（Gen 9 OU）**： 含 Terastalization 的定制队伍对战，以及镜像阵容（无 Terastalization）对战。
    - **完整对战（Gen 8 Random Battles）**： 含/不含 Dynamax 机制。
    - **在线天梯（Gen 9 OU）**： 2024 年 9 月 1-7 日与真实人类对战 50 场。
- **Benchmark 与对比方法**：
    - **Abyssal Bot**（官方规则启发式机器人）
    - **PokéLLMon**（基于 GPT-4o 的 LLM 智能体）
    - **One Step Lookahead Bot**（仅用一步前瞻启发式，无 LLM）
    - **Max Power Bot**（仅选最高威力招式）
    - **Random Bot**（随机动作）
- **LLM 配置**： GPT-4o-2024-05-13 和 Llama 3.1 8B。

### 4. 资源与算力

- **未明确说明**： 论文未提供训练所需的 GPU 型号、数量或时长（因为方法无需微调）。推理阶段使用了 OpenAI 的 GPT-4o API 以及本地部署的 Llama 3.1 8B 模型，但未给出具体推理算力消耗或时间。

### 5. 实验数量与充分性

- **实验数量**：
    - 每对方法之间至少进行 **25 场**比赛，总比赛数至少 **100 场**用于 Elo 计算。
    - 在线天梯进行 **50 场**对战人类。
    - 1v1 谜题使用 **1000 个**场景。
- **充分性评估**：
    - 对比方法全面（规则型、LLM 型、基础启发式、随机），涵盖两种主流格式（Gen 9 OU 和 Gen 8 Random Battles），并测试了特殊机制的影响。
    - 消融实验通过更换 LLM 类型（GPT-4o vs Llama 3.1）以及开关特殊机制（Terastalization/Dynamax）进行了验证。
    - 在线人类对战部分，作者指出约 1/3 比赛因超时失利，对剩余 2/3 分析得到 76%胜率，并调整后估计 Elo 范围。
    - 实验设计较为公平：所有方法均在同一模拟器环境下运行，且 LLM 智能体使用相同的前序知识（一步前瞻计算结果）。
    - **不足**：缺乏与强化学习训练方法的直接对比（如 Deep RL 方法）；在线评估样本量较小（50 场），且对 stall 和 excessive switching 策略的局限性仅定性分析；未进行多次重复以计算置信区间。

### 6. 论文的主要结论与发现

- **主要结论**：
    - PokéChamp（GPT-4o）在 Gen 9 OU 中对最强 LLM 基准 PokéLLMon 胜率 **76%**，对规则基准 Abyssal 胜率 **84%**。
    - 使用 8B Llama 3.1 的 PokéChamp 仍以 **64%** 胜率击败 GPT-4o 驱动的 PokéLLMon，证明框架的有效性。
    - 在线天梯预估 Elo **1300-1500**，位居人类玩家前 **30%-10%**（专家级）。
    - 实验表明：LLM 可以显著提升最小最大搜索在部分可观测、大状态空间游戏中的表现，且无需领域微调。

### 7. 优点：方法或实验设计上的亮点

- **方法亮点**：
    - 无需额外训练或微调 LLM，可直接利用现成模型的先验知识。
    - 模块化设计（动作采样、对手建模、值函数）可迁移至其他双人零和博弈。
    - 综合历史统计与 LLM 推理来处理部分可观测性（如对手隐藏属性估计）。
    - 提供开源的本地模拟器更新和最大真实玩家对战数据集（超 300 万场）。
- **实验设计亮点**：
    - 同时评估了两种格式（常规 OU 和随机战），涵盖不同机制（Terastalization、Dynamax）。
    - 除完整对战外，设计了专项谜题（1v1、特殊机制）来分离测试特定能力。
    - 与多种基线（包括此前最强的 LLM 智能体）进行了系统比较，并报告了 Elo 和胜率。
    - 通过在线天梯验证了实际对战人类的效果。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制

- **实验覆盖**：
    - 缺少与深度学习/强化学习方法（如 deep RL self-play）的直接对比，无法说明 LLM 方法相对于训练型方法的优劣。
    - 在线天梯评估仅 50 场，且因超时失利占比大（~1/3），Elo 估计存在偏差。
    - 未涉及双打或其他复杂格式。
- **偏差风险**：
    - LLM 预训练数据截止日期可能导致对当前流行策略的认知滞后（作者在 fast 变体中观察到这一现象）。
    - 对手建模是静态的（基于历史平均），无法适应实时对手的针对性策略（如 stall、频繁换人）。
- **应用限制**：
    - 时间约束严格，导致在线比赛中频繁超时；尝试的加速变体（PokéChamp-Fast）表现反而下降。
    - 方法依赖 LLM API 调用，延迟和成本可能在实时场景中成为瓶颈。
    - 对 stall 和 excessive switching 策略防御薄弱，说明在长时程规划方面仍有提升空间。
    - 在线评估可能干扰平台人类用户体验，作者也建议未来研究者限制使用在线天梯。

（完）
