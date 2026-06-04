---
title: "DipLLM: Fine-Tuning LLM for Strategic Decision-making in Diplomacy"
title_zh: DipLLM：微调大语言模型用于Diplomacy策略决策
authors: "Kaixuan Xu, Jiajun Chai, Sicheng Li, Yuqian Fu, Yuanheng Zhu, Dongbin Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hfPaOxDWfI"
tags: ["query:player-ai"]
score: 9.0
evidence: 针对Diplomacy游戏策略决策微调LLM
tldr: 本文提出DipLLM，一个针对复杂多人游戏Diplomacy进行微调的LLM智能体。Diplomacy要求合作与竞争，传统方法需要大量计算资源。DipLLM采用两阶段训练：首先通过行为克隆模仿专家轨迹，然后通过迭代自我改进学习均衡策略。实验表明，DipLLM在多种评估指标上达到领先水平，展示了LLM在复杂游戏决策中的能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hfpaoxdwfi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 839, \"height\": 798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfpaoxdwfi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfpaoxdwfi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 884, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfpaoxdwfi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 675, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfpaoxdwfi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 709, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfpaoxdwfi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 818, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfpaoxdwfi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 775, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfpaoxdwfi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1776, \"height\": 720, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hfpaoxdwfi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1779, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfpaoxdwfi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 788, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfpaoxdwfi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 648, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfpaoxdwfi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 594, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfpaoxdwfi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1592, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfpaoxdwfi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1616, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfpaoxdwfi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1471, \"height\": 235, \"label\": \"Table\"}]"
motivation: Diplomacy游戏动作组合指数级增长，传统方法计算昂贵。
method: 两阶段训练：行为克隆后迭代自我改进，学习均衡策略。
result: 在多种指标上达到领先水平。
conclusion: LLM微调可有效解决复杂游戏决策问题。
---

## Abstract
Diplomacy is a complex multiplayer game that re- quires both cooperation and competition, posing significant challenges for AI systems. Traditional methods rely on equilibrium search to generate extensive game data for training, which demands substantial computational resources. Large Lan- guage Models (LLMs) offer a promising alterna- tive, leveraging pre-trained knowledge to achieve strong performance with relatively small-scale fine-tuning. However, applying LLMs to Diplo- macy remains challenging due to the exponential growth of possible action combinations and the intricate strategic interactions among players. To address this challenge, we propose DipLLM, a fine-tuned LLM-based agent that learns equilib- rium policies for Diplomacy. DipLLM employs an autoregressive factorization framework to sim- plify the complex task of multi-unit action assign- ment into a sequence of unit-level decisions. By defining an equilibrium policy within this frame- work as the learning objective, we fine-tune the model using only 1.5% of the data required by the state-of-the-art Cicero model, surpassing its per- formance. Our results demonstrate the potential of fine-tuned LLMs for tackling complex strategic decision-making in multiplayer games.

---

## 论文详细总结（自动生成）

# DipLLM: 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）
- **游戏复杂性**：Diplomacy 是一款七人混合合作与竞争的复杂棋盘游戏，每回合玩家需为多达 34 个单元分配动作，动作组合可达 \(10^{64}\) 种，远超传统博弈（如象棋、围棋、扑克）。
- **传统方法局限**：现有方法（如 Cicero、DORA、DNVI）依赖 **均衡搜索**（如 piKL-Hedge）生成大量游戏数据进行训练，需要巨额计算资源（Cicero 使用 448 块 GPU 进行 rollout）。这些方法的可扩展性受限。
- **LLM 的潜力与挑战**：大语言模型（LLM）具备强大的泛化推理能力，但直接应用于 Diplomacy 面临**动作组合指数级增长**和**玩家间复杂策略交互**两大难题。论文核心问题：**能否通过微调 LLM 学习均衡策略，并以远少于传统方法的数据量超越现有最好模型？**

## 2. 方法论：核心思想、关键技术细节
### 2.1 核心思想：自回归分解（Autoregressive Factorization）
- 将单个玩家的**多单元联合动作决策**分解为**一系列单元级决策**，每个单元的动作依赖于棋盘状态 \(s\) 和之前单元已选动作序列 \(a^{1:d-1}\)。
- 策略分解：
  \[
  \pi_i(a^{1:D} | s) = \prod_{d=1}^D \pi_i^d(a^d | s, a^{1:d-1})
  \]
- 该分解将 \(10^{64}\) 的动作空间降为每个单元约 26 个候选动作的序列决策，使 LLM 的 next-token prediction 框架自然适配。

### 2.2 学习目标：均衡策略定义
- 借鉴 piKL-Hedge 的最终迭代策略，定义自回归框架下的均衡学习目标：
  \[
  \pi_i^{d,*}(a^d | s, a^{1:d-1}) \propto \exp\left\{ Q_i^d(s, a^{1:d-1}, a^d) \right\}
  \]
  其中单元级 Q 值 \(Q_i^d\) 通过对剩余动作求和得到，兼顾累积奖励和贴近锚策略（anchor policy \(\tau_i\)）的约束。
- **理论保证**：
  - **定理 1（等价性）**：自回归分解得到的联合策略与原 piKL-Hedge 策略等价。
  - **定理 2（双人零和博弈最优性）**：在双人零和博弈中，按此目标更新平均策略收敛到 \((\max \beta_i \delta_i)\)-近似纳什均衡，为多人博弈的推广提供理论支持。

### 2.3 微调过程（Fine-tuning Pipeline）
- **数据收集**：
  1. 使用领域特定模型 **DipNet** 与环境交互产生原始游戏数据。
  2. 应用均衡搜索 **piKL-Hedge**（以 DipNet 作为锚策略 \(\tau_i\)）生成**联合动作 Q 值** \(Q_i\)。
  3. 通过 **log-sum-exp 的紧下界**（基于采样 \(a^{1:D} \sim \pi_i^*\)）近似单元级 Q 值 \(Q_i^d\)，避免计算整个子动作空间的求和。
  4. 将状态、动作、Q 值转换为**文本格式**，形成自回归分解形式的训练样本 \((s, a^{1:d-1}, a^d, Q^d)\)。
- **损失函数**：
  - 最小化 LLM 策略与目标均衡策略的 **KL 散度**，推导为等效的最大化加权对数似然：
    \[
    \max_{\pi_\phi} \mathbb{E}_{(s,a^{1:d-1},a^d) \sim D} \left[ \log \pi_\phi(a^d | s, a^{1:d-1}) \cdot \exp(Q_i^d) \right]
    \]
  - 可视为**带权重的监督微调（SFT）**，权重 \(\exp(Q_i^d)\) 使策略偏向高均衡价值的动作。
- **模型与训练**：以 **LLaMA 3 8B** 为骨干，使用 **LoRA** 高效微调，学习率 2e-4，5 个 epoch。

## 3. 实验设计：数据集、基准、对比方法
### 3.1 评估设置
- 采用 **1v6 比赛形式**：智能体控制一个势力，其余六个势力由同一对手模型的六个副本控制（无通信的 no-press Diplomacy）。
- **推理阶段所有模型不使用额外均衡搜索**（除专门实验外），以确保公平。
- **指标**：**SoS 分数**（sum-of-squares scoring，平均约 14.3%）、胜率（控制 ≥18 个补给中心）、最多 SC、存活率、失败率。

### 3.2 对比基准
| 方法 | 说明 |
|------|------|
| **Cicero**（SOTA） | 2.7B 参数，大规模人类演示 + CoShar-piKL 均衡搜索 |
| **DNVI** | 基于 DipNet，策略/价值网络从行为克隆初始化，用均衡搜索训练 |
| **DORA** | 类似 DNVI，但从零训练 |
| **DipNet** | 0.3B 参数，纯模仿学习 |
| **Prompt** | 基于提示的 LLM 智能体（Richelieu 风格） |
| **SFT** | 在相同数据上直接监督微调（无自回归分解） |

### 3.3 实验场景
- **主实验**：在包含所有基准的种群中交叉 1v6 比赛。
- **与 Cicero+搜索对比**：DipLLM 对抗配备不同 rollout 次数均衡搜索的 Cicero。
- **数据效率对比**：DipLLM 与 DipNet 在不同数据集大小（100~500 局）下对比微调性能。
- **消融实验**：分别去除自回归分解（AF）和微调（FT）。
- **动作分布分析**：对比微调前后 vs 均衡策略的相似度。
- **案例研究**：展示战略欺骗场景。
- **附录扩展**：与 GPT-4o、DeepSeek-R1、OpenAI o3-mini 对比；与自博弈+搜索初步实验；与 PPO、DPO 对比。

## 4. 资源与算力
- **Cicero 参考**：使用 448 块 GPU 进行游戏 rollout 和数据生成。
- **DipLLM**：
  - 训练数据量仅为 Cicero 的 **1.5%**（约 500 局游戏）。
  - 模型：LLaMA 3 8B（80 亿参数），微调使用 LoRA。
  - **GPU 型号、数量、训练时长未在正文明确给出**，仅提供超参数（AdamW, 2e-4, 5 epoch, batch size 4, max seq len 2048）。附录 D 提及 LoRA 配置（alpha=32, dropout=0.05, rank=16）。
- **推理效率**：DipLLM 每回合仅需 Cicero **10%~20%** 的推理时间。

## 5. 实验数量与充分性
- **充分性**：
  - 主实验覆盖 5 个领域特定模型 + 2 个 LLM baseline，SoS 和四项结果指标。
  - 消融实验清晰展示了 AF 和 FT 的独立贡献。
  - 数据效率实验揭示了 LLM 相比领域模型的优势。
  - 与 Cicero+搜索对比验证了即使对手启用搜索，DipLLM 仍超越均衡线（14.3%）。
  - 附录补充了与最强通用 LLM 的对比、自博弈搜索、偏好学习对比，进一步佐证。
- **客观性与公平性**：
  - 所有模型在基准评估中均不使用额外搜索（除专门实验），比较公平。
  - 对比 DipNet 时，DipNet 也在相同数据上微调（遵循原论文方式）。
  - 动作分布分析直接验证微调后策略是否接近均衡。
- **可能不足**：未对多个 LLM 基座（如 LLaMA 不同规模、其他架构）进行消融；自博弈探索受限于算力，仅提供初步结果。

## 6. 主要结论与发现
- **性能超越 SOTA**：DipLLM 在种群 SoS 得分上达 **23.0%**，高于 Cicero 的 20.8%（提升 2.2%），胜率也领先 1.8%（22.3% vs 20.5%）。
- **数据效率极高**：仅用 Cicero 1.5% 的数据量即超越其性能。100 局微调即可匹敌 DipNet，500 局以 6.7% 优势大幅领先。
- **自回归分解 + 微调不可或缺**：单独使用任一技术效果有限，两者结合带来质的飞跃（SoS 从 0.2% 提升至 29.4%）。
- **微调有效对齐均衡策略**：动作分布从随机转向均衡策略（如英格兰开局移向 SIL/RUH 的概率显著提升）。
- **战略能力展示**：通过案例（英国声东击西击败法国）证明 DipLLM 能执行复杂欺骗和多线作战策略。

## 7. 优点
- **理论支撑**：严格证明自回归分解与原始策略的等价性，以及在双人零和中的收敛性。
- **高效动作空间处理**：自回归分解将指数级联合动作简化为序列单元决策，是解决超大动作空间的关键。
- **实用性强**：相比 Cicero，训练数据需求降低两个数量级，推理速度快 5~10 倍，便于实际部署。
- **方法可迁移**：该框架（均衡策略 + 自回归分解 + LLM 微调）可推广至其他复杂决策任务。
- **实验设计全面**：覆盖多种 baseline、消融、数据效率、案例分析，并进行了与最强 prompt 模型和通用 LLM 的对比。

## 8. 不足与局限
- **数据生成依赖外部模型**：当前 DipLLM 的微调数据仍由 DipNet + piKL-Hedge 产生，并非完全自主。自博弈产生数据是未来方向，但论文仅提供初步验证。
- **计算资源报告不完整**：未给出训练 DipLLM 的具体 GPU 型号、数量和时长，可重复性略有折扣。
- **基座局限性**：仅使用 LLaMA 3 8B，未探索更大或不同类型 LLM 的影响；prompt 基线的构建可能受限于提示工程。
- **场景限制**：仅针对 no-press Diplomacy，不包含语言通信的完整游戏（press Diplomacy）。方法向带通信环境的扩展需要额外处理。
- **公平性讨论**：Cicero 的性能在其原始论文中包含了均衡搜索，而 DipLLM 主实验未使用搜索。虽然作者提供了对比实验（DipLLM vs Cicero+搜索），但在种群评估中 Cicero 不使用搜索可能未发挥其全部潜力。然而 DipLLM 依然胜出，证明其策略质量高。
- **消融深度**：未对比不同自回归顺序策略（如按单元重要度排序）的影响；未分析损失函数中权重 \(\exp(Q_i^d)\) 与其他加权方式（如 softmax 温度）的差异。

（完）
