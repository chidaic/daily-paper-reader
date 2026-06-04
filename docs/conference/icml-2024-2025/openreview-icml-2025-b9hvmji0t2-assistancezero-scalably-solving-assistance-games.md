---
title: "AssistanceZero: Scalably Solving Assistance Games"
title_zh: "AssistanceZero: 可扩展求解辅助游戏"
authors: "Cassidy Laidlaw, Eli Bronstein, Timothy Guo, Dylan Feng, Lukas Berglund, Justin Svegliato, Stuart Russell, Anca Dragan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=b9hVMJi0t2"
tags: ["query:player-ai"]
score: 9.0
evidence: 在Minecraft上可扩展的辅助游戏
tldr: 该论文针对辅助游戏因需要求解不确定决策和建模人类行为而难以扩展的问题，首次提出可扩展的求解方法，并应用于基于Minecraft的新辅助游戏。通过模型强化学习与用户建模，在复杂环境中成功训练出能辅助用户的智能体。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 842, \"height\": 204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 840, \"height\": 205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 839, \"height\": 207, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 853, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 779, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 846, \"height\": 1169, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1654, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1730, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1734, \"height\": 742, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1428, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1790, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b9hvmji0t2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1424, \"height\": 1516, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 878, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1065, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 917, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1762, \"height\": 1252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1105, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1192, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 526, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1777, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 625, \"height\": 844, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 868, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 950, \"height\": 885, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b9hvmji0t2/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1435, \"height\": 1011, \"label\": \"Table\"}]"
motivation: 辅助游戏在复杂环境中因难以处理不确定性和用户行为建模而规模受限。
method: 提出可扩展的求解方法，结合模型强化学习和用户行为建模，应用于Minecraft辅助游戏。
result: 在包含数十亿状态的新Minecraft游戏中成功训练辅助智能体。
conclusion: 可扩展的辅助游戏求解方法为训练实用AI助手开辟了新途径。
---

## Abstract
Assistance games are a promising alternative to reinforcement learning from human feedback (RLHF) for training AI assistants. Assistance games resolve key drawbacks of RLHF, such as incentives for deceptive behavior, by explicitly modeling the interaction between assistant and user as a two-player game where the assistant cannot observe their shared goal. Despite their potential, assistance games have only been explored in simple settings. Scaling them to more complex environments is difficult because it requires both solving intractable decision-making problems under uncertainty and accurately modeling human users' behavior. We present the first scalable approach to solving assistance games and apply it to a new, challenging Minecraft-based assistance game with over $10^{400}$ possible goals. Our approach, AssistanceZero, extends AlphaZero with a neural network that predicts human actions and rewards, enabling it to plan under uncertainty. We show that AssistanceZero outperforms model-free RL algorithms and imitation learning in the Minecraft-based assistance game. In a human study, our AssistanceZero-trained assistant significantly reduces the number of actions participants take to complete building tasks in Minecraft. Our results suggest that assistance games are a tractable framework for training effective AI assistants in complex environments. Code and videos are available at https://anonymous.4open.science/w/scalably-solving-assistance-games/.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **背景**：当前主流AI助手训练范式（如RLHF）存在缺陷：奖励信号易被欺骗，导致助手产生欺骗性行为；不鼓励助手对用户目标保持不确定性（如不会主动询问澄清）；未考虑人类与助手的协作互补关系。
- **动机**：辅助游戏（assistance games）通过将人机交互建模为**两玩家马尔可夫博弈**（助手未知共享目标），从根本上避免了RLHF的上述缺陷。然而，过去辅助游戏只在极简场景（<20种目标）下被研究，无法扩展到现实复杂环境。
- **本文目标**：首次提出**可扩展的辅助游戏求解方法**，应用于一个全新的、基于Minecraft的复杂辅助游戏环境（MBAG），证明辅助游戏在具有指数级目标（>10^400）和巨大状态/动作空间的场景中仍然可行。

## 2. 方法论：核心思想与关键技术细节
- **核心思想**：将辅助游戏求解转化为**部分可观测马尔可夫决策过程（POMDP）**，并设计一种新的模型基强化学习算法 **AssistanceZero**，分离目标预测与动作选择，利用学习到的奖励参数预测和人类动作预测进行规划。
- **关键技术细节**：
  - **神经网络架构**：采用卷积+残差块+LSTM的递归网络，输入包含当前世界状态、历史信息等，输出四个预测头：
    1. **策略头**（πϕ）：预测助手动作分布。
    2. **价值头**（V̂ϕ）：估计状态价值。
    3. **奖励参数预测头**（p̂ϕ(θ|h)）：预测每个位置的方块类型分布（即目标结构）。
    4. **人类动作预测头**（p̂ϕ(a^H|h)）：预测人类下一步动作。
  - **蒙特卡洛树搜索（MCTS）**：在选取助手动作时，利用上述预测头模拟未来的奖励和人类响应，进行规划。MCTS采用**双层动作选择**：先选动作类型（移动、放置、破坏等），再选具体参数。使用PUCT公式平衡探索与利用。
  - **训练损失函数**（公式1）：结合五项损失——策略KL散度（向MCTS输出靠拢）、价值均方误差、奖励参数负对数似然+历史KL正则、人类动作负对数似然。训练时先在环境中收集rollout（使用当前网络运行MCTS），再更新网络。
  - **人类模型**：采用 **piKL** 方法，即结合**行为克隆（BC）** 与MCTS，通过KL正则化使规划策略既接近人类数据又最大化奖励。实验表明piKL人类模型在预测准确性和建房子能力上最接近真实人类。

## 3. 实验设计：数据集、基准、对比方法
- **环境**：**Minecraft Building Assistance Game (MBAG)**，基于CraftAssist数据集，目标结构为11×10×10网格中的房子。训练集和测试集分离，目标数量约10^400种。
- **基准（Baselines）**：
  - **RLHF/助手范式对比**：模拟大语言模型训练管线的**预训练（Pretraining）+监督微调（SFT）** 助手。预训练用BC模型生成10万段无目标信息的轨迹训练，SFT用人类助手演示数据微调。
  - **无助手（人类单独）**。
  - **人类专家助手**（用于人类研究）。
- **对比方法**：
  - **模型无关RL**：PPO（含多种消融变体，如LSTM、奖励工程、辅助损失等）。
  - **人类模型对比**：包括基于奖励的（PPO、AlphaZero）、纯行为克隆（BC-alone/with-assistant/combined）、piKL（基于三种BC的版本）。评估指标包括交叉熵、建房子速度、助手-人类泛化能力。
- **人类研究**：16名受试者，在四种条件下（无助手、SFT助手、AssistanceZero助手、人类专家助手）建造同一房子，采用拉丁方设计控制顺序效应，收集客观指标（动作数）和主观评分（帮助性、理解意图等）。

## 4. 资源与算力（文中信息与说明）
- **明确说明**：文中未给出总训练算力（如GPU小时数）。
- **部分提及**：评估时使用 NVIDIA GeForce 1080 Ti GPU 运行实时Minecraft（20次MCTS模拟）；训练时使用256个并行环境，500次训练迭代，每迭代每环境64步，因此总环境步数约800万步。训练硬件配置未详细注明，但推测为单GPU或少量GPU。附录中提供了完整超参数。
- **结论**：作者未报告总训练资源消耗，但从环境规模（CPU并行）和网络大小（6~8残差块+LSTM）看，训练成本应在单卡数天内可完成。

## 5. 实验数量与充分性
- **数量**：大量实验，涵盖：
  - PPO助手消融（表6）：共约20种超参组合，每个组合在1000个测试集目标上评估。
  - AssistanceZero消融（表7）：包括有无LSTM、有无历史KL正则等。
  - 人类模型对比（表2、图9）：8种人类模型，在交叉熵、单独建房子能力、跨模型助手泛化等方面评估。
  - 助手范式对比（表3）：3种助手，各1000个测试集目标。
  - 人类研究（C.1）：16名参与者，拉丁方设计，收集主客观指标。
- **充分性**：实验设计较全面，消融覆盖关键组件，人类研究采用随机化盲法。但人类研究样本量较小（16人），统计显著性的可靠性有待更大规模验证。模拟实验中指标（如目标完成率、人类动作数）报告了置信区间，结果清晰。
- **公平性**：PPO助手经过广泛调参（表6），AssistanceZero与PPO在同一环境、同一人类模型下比较，且测试时不使用MCTS以排除额外计算优势。助手范式对比中SFT也经过540组超参网格搜索选最优。总体公平。

## 6. 主要结论与发现
1. **PPO无法有效求解复杂辅助游戏**：即使经过奖励工程和辅助损失，PPO助手几乎不帮助人类模型（助理完成目标比例<8%）。
2. **AssistanceZero显著优于PPO**：助理完成目标比例达27%，同时减少人类模型动作42%，在模拟和真实人类实验中均体现优势。
3. **piKL是最有效的人类模型**：结合行为克隆和MCTS的piKL既接近真实人类行为，又能训练出泛化性强的助手。
4. **辅助游戏框架优于Pretraining+SFT**：AssistanceZero助手在模拟中减少人类动作65次，而SFT只减少4-5次；人类研究中用户评分显著更高（3.1 vs 1.7，5分制）。
5. **涌现有用行为**：助手能根据人类纠正（如破坏错误方块）学习正确高度，表现出理解实际意图和从反馈中学习的能力。
6. **仍落后于人类专家**：AssistanceZero助手评分4.0（人类专家），差距表明MBAG仍是挑战性基准。

## 7. 优点
- **问题定义清晰**：将辅助游戏扩展至复杂环境，并提出明确的新基准MBAG（目标数量指数级大，结构结构化）。
- **算法创新**：通过将AlphaZero扩展为预测奖励参数和人类动作，实现了在POMDP下规划，解决了模型无关RL在稀疏噪声奖励下的失败。
- **人类建模成套方法论**：系统对比了多种人类模型，确认piKL是最佳选择，具有实用指导意义。
- **实验完整性**：同时进行了模拟大规模评估和真实人类研究，结果具有说服力。
- **开源贡献**：代码和数据已公开，可复现。

## 8. 不足与局限
- **人类研究样本量小**：仅16名参与者，性别和游戏经验分布不均（多数为男性、有Minecraft经验），可能带来偏差，结论外推性有限。
- **环境简化**：MBAG中助手和人类使用无限方块，忽略了资源收集维度；且目标均为静态房屋，实际用户目标可能更动态、开放。
- **计算资源未报告**：无法评估方法在更大规模（如LLM对话环境）上的训练成本可行性。
- **人类模型仍有误差**：即使piKL，交叉熵仍高于真实人类间差异，可能导致训练出的助手在真实人类面前表现不如预期。
- **安全与伦理讨论不足**：仅声明辅助游戏可减少欺骗动机，但未讨论方法被误用（如助手主动限制人类动作）的风险。
- **泛化性存疑**：所有实验基于Minecraft，方法的通用性（如能否直接用于编程辅助）仅作展望，无实际验证。

（完）
