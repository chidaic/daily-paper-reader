---
title: Learning Strategic Language Agents in the Werewolf Game with Iterative Latent Space Policy Optimization
title_zh: 通过迭代潜在空间策略优化学习狼人杀游戏中的战略语言智能体
authors: "Zelai Xu, Wanjun Gu, Chao Yu, Yi Wu, Yu Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=N2mOBiSqhc"
tags: ["query:player-ai"]
score: 9.0
evidence: 通过潜在空间策略优化在狼人杀中训练战略语言智能体
tldr: 针对LLM智能体在战略语言游戏中探索不足和偏差问题，提出迭代潜在空间策略优化（LSPO），结合博弈论和LLM微调，通过潜在空间策略优化逐步提升智能体在狼人杀游戏中的决策和语言能力，实验表明LSPO显著优于现有LLM和RL方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-n2mobisqhc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1736, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-n2mobisqhc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1742, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-n2mobisqhc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1735, \"height\": 388, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1575, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1400, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1354, \"height\": 192, \"label\": \"Table\"}]"
motivation: 现有LLM智能体在战略游戏中表现次优，探索受限。
method: 引入潜在空间策略优化，迭代结合博弈论和LLM微调。
result: 在狼人杀任务中，LSPO胜率大幅超越基线。
conclusion: LSPO为构建战略语言智能体提供了有效框架。
---

## Abstract
Large language model (LLM) agents have recently demonstrated impressive capabilities in various domains like open-ended conversation and multi-step decision-making. However, it remains challenging for these agents to solve strategic language games, such as Werewolf, which demand both strategic decision-making and free-form language interactions. Existing LLM agents often suffer from intrinsic bias in their action distributions and limited exploration of the unbounded text action space, resulting in suboptimal performance. To address these challenges, we propose Latent Space Policy Optimization (LSPO), an iterative framework that combines game-theoretic methods with LLM fine-tuning to build strategic language agents. LSPO leverages the observation that while the language space is combinatorially large, the underlying strategy space is relatively compact. We first map free-form utterances into a finite latent strategy space, yielding an abstracted extensive-form game. Then we apply game-theoretic methods like Counterfactual Regret Minimization (CFR) to optimize the policy in the latent space. Finally, we fine-tune the LLM via Direct Preference Optimization (DPO) to align with the learned policy. By iteratively alternating between these steps, our LSPO agents progressively enhance both strategic reasoning and language communication. Experiment on the Werewolf game shows that our agents iteratively expand the strategy space with improving performance and outperform existing Werewolf agents, underscoring their effectiveness in free-form language games with strategic interactions.

---

## 论文详细总结（自动生成）

# 基于论文《Learning Strategic Language Agents in the Werewolf Game with Iterative Latent Space Policy Optimization》的详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：大型语言模型（LLM）智能体在开放式对话和多步决策等领域展现了强大能力，但在处理如“狼人杀”这类战略语言游戏时仍面临巨大挑战。这类游戏不仅要求自由形式的自然语言交互（如讨论、说谎、推理），还要求高层次的战略决策（如投票、伪装）。
- **核心问题**：现有LLM智能体存在两个主要缺陷：
  - **内在偏差（Intrinsic Bias）**：由于预训练数据的不平衡，智能体的动作分布存在固有偏向，容易被对手利用。
  - **探索不足（Limited Exploration）**：语言动作空间是无限的，现有方法（如提示工程）只能覆盖有限子集，导致策略容易被未见过的动作所利用。
- **解决思路**：作者提出，尽管语言空间巨大，但背后的**策略空间相对紧凑**。因此，可以通过将自由形式话语映射到一个有限的潜在策略空间，结合博弈论方法优化策略，再通过迭代微调LLM来扩展策略空间，逐步提升智能体的性能。
- **整体含义**：该工作为构建能够进行自由形式语言交互的战略性智能体提供了一种新颖的迭代框架，将结构化博弈论与LLM的灵活性相结合，在狼人杀这一测试床上取得了显著优于现有方法的效果。

## 2. 论文提出的方法论：核心思想、关键技术细节、流程

### 2.1 核心思想
- 将无限的语言动作空间抽象为有限离散的**潜在策略空间**，在此空间上应用博弈论方法（如CFR）求解近似纳什均衡策略，再通过偏好优化（DPO）微调LLM使其生成的语言与该策略对齐，并通过迭代扩展策略空间来逐步逼近完整游戏。

### 2.2 关键技术细节与流程（三阶段循环）

**阶段一：潜在空间构建（Latent Space Construction）**
- **生成**：使用当前LLM智能体自对弈，为每个角色（狼人、预言家、女巫、村民）收集大量讨论阶段的发言。在每个状态，提示LLM生成N个策略上不同的候选发言（通过额外提示“考虑一个与现有动作在策略上不同的新动作”），然后随机选一个执行，以增加多样性。
- **聚类**：使用文本嵌入模型（如 `text-embedding-3-small`）将每个发言映射为向量，然后应用k-means聚类将发言划分为k个簇，每个簇代表一个潜在策略。这样将无限文本空间转化为有限离散的策略集。

**阶段二：潜在空间策略优化（Policy Optimization in Latent Space）**
- **抽象博弈构建**：将原始自由形式语言游戏中的讨论动作替换为离散的潜在策略，保留秘密动作和投票动作为固定离散动作。状态包含玩家角色、历史潜在策略等信息。由此得到抽象扩展式博弈（Extensive-Form Game）。
- **优化**：使用**深度反事实遗憾最小化（Deep CFR）** 在该抽象博弈中迭代优化策略。CFR通过计算每个信息集上每个动作的遗憾值，采用遗憾匹配更新策略，最终收敛到近似纳什均衡。使用神经网络拟合遗憾值以处理大规模博弈。

**阶段三：潜在空间扩展（Latent Space Expansion）**
- **与策略对齐**：利用DPO（Direct Preference Optimization）微调LLM。构造偏好数据集：将游戏轨迹中的语言观测作为prompt，该状态下生成的N个候选发言作为响应候选，根据它们对应的潜在策略的遗憾值（值越小越优）定义偏好标签。DPO训练使LLM生成更接近最优策略的发言。
- **扩展空间**：微调后的LLM能够产生更广泛、更符合策略的发言。重复阶段一的生成和聚类过程，更新并扩大潜在策略空间（每轮增加新簇）。然后返回阶段二重新优化，形成迭代循环。

### 2.3 迭代流程图示
1. 初始LLM（如Llama-3-8B-Instruct）生成初始策略空间；
2. 构建抽象博弈，用CFR学习最优潜在策略；
3. 用DPO微调LLM以对齐该策略；
4. 用微调后的LLM生成新发言，扩展潜在空间；
5. 回到步骤2，重复迭代。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **场景**：七人版狼人杀文字游戏（两狼人、一预言家、一女巫、三村民），全部通过自然语言进行，排除语音、表情等额外信息。
- **基准测试（Benchmark）**：狼人杀游戏本身作为测试环境。主要评估指标包括：
  - **胜率（Win Rate）**：狼人方或村民方获胜比例。
  - **预测准确率（Prediction Accuracy）**：在投票前让智能体预测其他玩家的角色。
- **对比方法（Baselines）**：
  - **ReAct**（Yao et al., 2022b）：经典的推理-行动提示方法。
  - **ReCon**（Wang et al., 2023b）：为Avalon游戏设计的递归沉思方法。
  - **Cicero-like**（Meta et al., 2022）：类似Cicero的架构，预定义13种原子动作，用RL学习策略选择，然后生成语言。
  - **SLA**（Xu et al., 2023c）：结合RL和LLM，通过生成候选动作并学习RL策略来缓解偏差。
- **实验设置**：
  - 两轮头对头评估：(1) LSPO智能体为狼人方，四个基线分别为村民方，比较村民方胜率；(2) 角色互换，LSPO为村民方，基线为狼人方，比较狼人方胜率。各进行100局游戏。
  - 另评估不同迭代轮次（Iter 1, 2, 3）下LSPO智能体自身的预测准确率和胜率（固定对手为最终迭代的LSPO）。
  - 也进行了概念验证实验：在五动作的石头剪刀布-蜥蜴-斯波克游戏上测试动作分布与可剥削性。

## 4. 资源与算力

- 论文中**未明确说明**使用的GPU型号、数量及训练总时长等具体算力信息。仅在超参数部分提及使用学习率、批大小、迭代次数等，但未提供硬件细节。
- 隐性信息：基座模型为 **Llama-3-8B-Instruct**，使用DPO微调（2 epoch，batch size 64），Deep CFR训练1500迭代，batch size 4096。自对弈收集数据1000局。这些操作在8B模型上通常可以在单卡或少量GPU上完成，但具体资源未报告。

## 5. 实验数量与充分性

- **主要实验**：
  - 概念验证（五动作游戏）：展示LSPO在3次迭代后学到均衡分布，对比ReAct和SLA，结果清晰。
  - 狼人杀实验：
    - 迭代性能评估（表1）：报告了3次迭代下狼人方和村民方的预测准确率及胜率，各100局，附带标准误差。
    - 与SOTA对比（表2）：两种角色设置（LSPO为狼人方、LSPO为村民方），各与四个基线对比，100局。
    - 消融实验（表3）：对比完整LSPO与“w/o Fine-Tuning”和“w/o Policy Learning”，报告胜率。
    - 聚类数量敏感度（表4）：在简化4人局中测试k=1,2,3的效果。
    - DPO超参数敏感度（表5）：测试β值0.05,0.1,0.2。
    - 更多迭代收敛性（表7，附录）：5次迭代的胜率变化。
  - 潜在空间可视化（图3）：用t-SNE展示狼人和预言家在3次迭代中的聚类演化。
- **充分性评述**：
  - 实验覆盖了主要假设（迭代提升有效性、与基线对比、关键组件消融、超参数鲁棒性、收敛性）。
  - 样本量（100局）提供了合理的统计稳定性，误差线显示了波动范围。
  - 消融实验明确了各组件（策略优化、微调）的贡献，聚类数和DPO β的影响较小，说明方法对参数不敏感。
  - 在4人局中进行了敏感度分析，可视为初步验证，但未在7人局中重复该部分，略有不足。
  - 整体实验设计较为充分、客观，对比方法均保持核心设计不变，角色对调避免了偏好性。

## 6. 论文的主要结论与发现

- **LSPO智能体在迭代过程中预测准确率和胜率持续提升**（表1）：从Iter 1到Iter 3，狼人方胜率从54%升至73%，村民方从18%升至27%；角色预测准确率也同步提高。
- **LSPO智能体在两种角色设置下均超越所有对比基线**（表2）：狼人方胜率73%（次优SLA 69%），村民方胜率27%（次优SLA 25%），整体胜率50%（次优SLA 47%）。
- **LSPO的成功归因于三组件的协同作用**：潜在空间策略优化（CFR）克服内在偏差，LLM微调（DPO）扩展策略空间并提升泛化，迭代扩展解决了探索不足问题。
- **潜在策略空间随迭代变得更加多样和结构化**（图3）：从简单的声明、沉默到复杂的伪装、诬陷、协调投票等高级策略。
- **在简单游戏中（五动作游戏）**，LSPO经过3次迭代学到纳什均衡，而ReAct和SLA分别受困于偏差和探索不足。

## 7. 优点

- **方法论创新**：将博弈论（CFR）与LLM微调（DPO）巧妙结合，通过潜在空间抽象解决了自由形式语言游戏的策略优化难题，避免了直接处理无限动作空间。
- **迭代框架**：通过迭代扩展策略空间，自然实现了对动作空间的渐进式探索，避免了手动预设动作集、固定策略空间的局限性。
- **实验全面**：包含概念验证、主要场景对比、消融、超参数分析、可视化、收敛性分析，论证充分。
- **结果强劲**：在狼人杀这一复杂社交推理游戏中，LSPO取得了明显的性能优势，且随着迭代次数增加稳定提升，展示了框架的有效性和可扩展性。
- **鲁棒性**：超参数（聚类数、DPO β）敏感度低，方法在不同设置下表现稳定。

## 8. 不足与局限

- **算力开销未报告**：缺少训练所需GPU型号、数量、时长等具体信息，不利于实际复现和成本评估。
- **实验规模限制**：
  - 所有实验仅在7人狼人杀环境下进行，未在更大规模或其他自由形式语言游戏（如Avalon、外交）上验证泛化性。
  - 消融和超参数分析仅在简化的4人局中完成，在7人局中未重做，可能影响结论的可靠性。
- **依赖LLM和嵌入API**：方法依赖于特定LLM（Llama-3-8B）和商业嵌入服务（text-embedding-3-small），不同模型或API可能导致性能差异，但论文未比较多模型。
- **潜在空间聚类简化**：k-means聚类可能无法捕捉策略的连续变化或非球形分布；每轮增加固定数量簇也是一种简单策略，可能不是最优。
- **伦理风险**：论文虽在影响声明中提到需警惕操纵和错误信息，但并未提供具体防护措施。该技术可被滥用于生成欺骗性内容。
- **对提示工程的依赖**：在候选动作生成和游戏过程中仍需要精心设计的提示来引导LLM，可能引入新的偏差。

（完）
