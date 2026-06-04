---
title: Language Agents with Reinforcement Learning for Strategic Play in the Werewolf Game
title_zh: 基于强化学习的语言智能体在狼人杀游戏中的战略玩法
authors: "Zelai Xu, Chao Yu, Fei Fang, Yu Wang, Yi Wu"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=usUPvQH3XK"
tags: ["query:player-ai"]
score: 9.0
evidence: 基于强化学习的语言智能体玩狼人杀游戏
tldr: 针对纯LLM智能体在复杂决策游戏中的内在偏差问题，提出强化学习框架，在狼人杀游戏中训练智能体产生灵活语言动作并提升决策能力，实验证明RL显著改善战略性能，胜率超过纯LLM基线。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-usupvqh3xk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 807, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-usupvqh3xk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1749, \"height\": 934, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-usupvqh3xk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1761, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-usupvqh3xk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1737, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-usupvqh3xk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 818, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-usupvqh3xk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 852, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1750, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 829, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 848, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1410, \"height\": 838, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 565, \"height\": 795, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 772, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1022, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 891, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1032, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 894, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-usupvqh3xk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 820, \"height\": 197, \"label\": \"Table\"}]"
motivation: 纯LLM智能体存在行为偏差，决策次优。
method: 使用RL微调LLM，结合游戏反馈信号优化策略。
result: 在狼人杀游戏中，RL增强智能体相比纯LLM基线胜率提升明显。
conclusion: RL可有效提升语言智能体的战略游戏能力，拓展LLM应用。
---

## Abstract
Agents built with large language models (LLMs) have shown great potential across a wide range of domains. However, in complex decision-making tasks, pure LLM-based agents tend to exhibit intrinsic bias in their choice of actions, which is inherited from the model's training data and results in suboptimal performance. To develop *strategic language agents*, i.e., agents that generate flexible language actions and possess strong decision-making abilities, we propose a novel framework that powers LLM-based agents with reinforcement learning (RL). We consider Werewolf, a popular social deduction game, as a challenging testbed that emphasizes versatile communication and strategic gameplay. To mitigate the intrinsic bias in language actions, our agents use an LLM to perform deductive reasoning and generate a diverse set of action candidates. Then an RL policy trained to optimize the decision-making ability chooses an action from the candidates to play in the game. Extensive experiments show that our agents overcome the intrinsic bias and outperform existing LLM-based agents in the Werewolf game. We also conduct human-agent experiments and find that our agents achieve human-level performance and demonstrate strong strategic play.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：基于大语言模型（LLM）构建的智能体在复杂决策任务中，其动作选择存在**固有偏差**（例如在石头剪刀布游戏中系统性地偏好出“石头”），导致策略性能次优。这种偏差源于LLM预训练数据的统计特性，使其难以在需要灵活、战略性地选择动作的场景中（如多人博弈）达到最优表现。
- **研究动机**：为了解决纯LLM智能体的固有偏差，实现既能生成灵活自然语言动作又具备强决策能力的**战略性语言智能体**。
- **整体含义**：提出将**强化学习**与LLM结合的框架，以狼人杀（Werewolf）这一典型的社交推理游戏为测试平台。借助RL优化动作选择，克服LLM的内在偏好，显著提升智能体在复杂竞争-合作环境中的战略水平，达到人类级别的游戏能力。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用LLM进行推理并生成一组多样化的候选动作，然后使用一个独立训练的RL策略从候选动作中选择最合适的动作执行。通过RL优化动作分布，消除LLM的固有偏差，提升决策质量。

- **关键技术细节（三个组件）**：
  1. **隐藏角色推理**：LLM将原始观察转换为结构化信息记录（区分事实、潜在真相、潜在谎言），并推理每个玩家的隐藏角色、可信度、推理过程和证据链。该组件为后续决策提供结构化输入。
  2. **多样化动作生成**：对不同类型的动作采用不同策略：
     - *秘密动作与投票动作*：单次推断一次性生成N个多样化候选人（简单有效）。
     - *陈述动作*：迭代提示LLM多次，每次要求生成与已有候选策略不同的新动作（质量更高）。
  3. **基于群体的RL训练**：
     - 采用自注意力网络策略，输入为玩家嵌入、观察嵌入及所有动作候选嵌入，通过缩放点积注意力计算各候选动作的采样概率。
     - 使用**MAPPO算法**进行训练。
     - 采用**群体训练**：对手池包括RL策略自身及其历史检查点，以及具有预设玩法风格的纯LLM智能体（如低调狼、活跃狼、激进指责狼等），增强策略的鲁棒性与非传递性博弈下的表现。

### 3. 实验设计：数据集/场景、基准与对比方法

- **场景**：7人狼人杀游戏（2狼人、1预言家、1女巫、3村民），纯文本环境。
- **基准方法**：
  - *ReAct*：直接使用LLM基于原始观察生成推理与动作。
  - *ReCon*：从自身和对手视角进行规划，原用于Avalon游戏，经适配后在狼人杀中运行。
  - *Concurrent*：采用启发式信息检索和经验反思的狼人杀智能体。
  - *Atomic*：类似Cicero，预定义13个原子动作（如“瞄准玩家0”、“声称是预言家”等），用RL策略选择原子动作，再触发LLM生成具体语言。
- **评估方式**：
  - 循环赛：每对智能体互相作为狼人/村民进行100局比赛，生成5×5的胜率矩阵。
  - 案例研究：对比纯LLM智能体与本文智能体在三个典型场景下的动作分布（首夜狼人杀人、首夜女巫救人、有两人自称预言家时的投票）。
  - 人类评估：160名人类玩家，两种设置（一名人类/智能体与6个副本智能体玩；一名智能体/人类与6名人类玩家玩），各100局。
  - 消融实验：逐步移除三个关键组件、推理属性、群体训练等，并与其他提示技术比较、不同动作类型贡献、候选动作数影响、零样本迁移到其他LLM（GPT-4, LLaMA-7B, ChatGLM-6B）、泛化到6人/8人局等。

### 4. 资源与算力

- 文中**未明确说明**所使用的GPU型号、数量或训练时长。
- 提到使用**分布式RL训练系统**、**多个API账户**并行调用LLM以最大化吞吐量。
- RL训练采用MAPPO算法，总步数为**10M步**，并使用行为克隆初始化策略。
- 由于依赖GitHub? OpenAI API服务（如gpt-3.5-turbo, text-embedding-ada-002），实际算力需求较高，但具体细节未提供。

### 5. 实验数量与充分性

- **实验数量**：涵盖了多组实验：
  - 循环赛：5个智能体 × 5个对手组合，每组100局，共2500局。
  - 人类评估：两种设置 × 各100局，共200局。
  - 案例研究：3种场景，可视化动作分布。
  - 消融实验：至少7组（表2-4、7-9），覆盖组件、属性、训练方式、动作类型、候选数量、LLM类型、玩家数量等。
- **充分性与公平性**：
  - 对比了当前主流相关方法（ReAct, ReCon, Concurrent, Atomic），并且所有基线均适配到相同环境。
  - 消融实验系统地验证了每个设计的重要性。
  - 人类评估同时考虑了AI与人类互为队友/对手的情况，结果可信。
  - 通过零样本迁移实验验证了RL策略的泛化能力。
- **客观性**：论文报告了标准误差（括号内数值），并进行了统计学意义上的比较。实验设计较为全面、合理。

### 6. 论文的主要结论与发现

- 本文提出的组合LLM与RL的框架有效克服了纯LLM智能体的固有动作偏差。
- 在狼人杀循环赛中，本文智能体作为村民和狼人两个角色均取得最高胜率，显著优于所有基线。
- 人类评估表明，本文智能体达到人类水平的表现：与6个人类玩家对战时，胜率与人类相当；与6个副本智能体对战时，甚至超过人类玩家。
- 消融实验证实：三个组件（隐藏角色推理、多样化动作生成、群体RL训练）均至关重要，其中RL策略对优化动作分布最关键。
- 该框架具有零样本迁移能力，可将用GPT-3.5训练的策略直接应用于GPT-4、LLaMA-7B等模型并提升性能。

### 7. 优点：方法或实验设计上的亮点

- **方法方面**：
  - 创新性地将LLM的灵活语言生成能力与RL的决策优化能力结合，突破纯LLM智能体的偏差瓶颈。
  - 多样化动作生成避免了单一动作的偏性，RL策略进一步优化分布，实现真正战略性选择。
  - 群体训练增强了对不同对手的鲁棒性，模拟真实博弈中的非传递性。
  - 使用自注意力网络处理动态语言动作空间，无需预定义动作集，适用于开放域语言游戏。
- **实验设计方面**：
  - 全面的基准覆盖：既包括通用LLM智能体（ReAct），也包括专用于社交推理的智能体（ReCon, Concurrent, Atomic）。
  - 人类评估真实反映智能体的泛化能力与自然交互水平。
  - 大量消融实验揭示各组件贡献，以及零样本迁移和泛化实验展示了框架的通用性。

### 8. 不足与局限

- **实验覆盖**：
  - 仅测试了7人狼人杀场景，对其他角色数量或规则变体的泛化性虽有初步验证，但深度不足。
  - 未与基于深度学习的传统游戏智能体（如DeepRole）进行对比，但这些智能体通常不具备自然语言能力。
- **偏差风险**：
  - RL策略可能学到与LLM生成偏差相关的局部最优，尽管实验显示有所改善，但理论上仍存在风险（如女巫在首晚依然有6%概率救别人）。
  - 人类评估中参与者知道对手可能是AI，实际匿名环境下表现可能不同。
- **应用限制**：
  - 目前仅支持纯文本交互，忽略语气、表情等非语言线索，与现实狼人杀有差距。
  - RL训练依赖大量环境交互与API调用，计算成本高；微调LLM本身可能带来伦理问题（如学习更有效的欺骗策略）。
  - 策略以7人局为设计，迁移到其他游戏（如Avalon）需要重写部分提示和群体配置，未必直接适用。

（完）
