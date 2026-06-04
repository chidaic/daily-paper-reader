---
title: Agent-Centric Actor-Critic for Asynchronous Multi-Agent Reinforcement Learning
title_zh: 面向异步多智能体强化学习的以智能体为中心的Actor-Critic方法
authors: "Whiyoung Jung, Sunghoon Hong, Deunsol Yoon, Kanghoon Lee, Woohyung Lim"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=323GZNnGqe"
tags: ["query:player-ai"]
score: 7.0
evidence: 面向游戏的异步多智能体强化学习
tldr: 该论文针对多智能体强化学习中宏动作带来的异步问题，提出以智能体为中心的Actor-Critic（ACAC），利用独立轨迹编码和注意力聚合，避免填充导致的相关性偏差，在稀疏奖励游戏环境中提升了协调能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 771, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 786, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 1198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 737, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 846, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1785, \"height\": 1161, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 863, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 861, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1482, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1751, \"height\": 1144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1744, \"height\": 1735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1783, \"height\": 1157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1781, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1784, \"height\": 797, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-323gznngqe/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1290, \"label\": \"Table\"}]"
motivation: 宏动作导致异步性，现有填充方法产生虚假关联。
method: 提出ACAC，用agent-centric编码器和注意力机制处理异步轨迹。
result: 在稀疏奖励MARL任务中，ACAC的协调和样本效率优于基线。
conclusion: 独立处理异步轨迹可提升多智能体游戏训练的稳定性。
---

## Abstract
Multi-Agent Reinforcement Learning (MARL) struggles with coordination in sparse reward environments. Macro-actions —sequences of actions executed as single decisions— facilitate long-term planning but introduce asynchrony, complicating Centralized Training with Decentralized Execution (CTDE). Existing CTDE methods use padding to handle asynchrony, risking misaligned asynchronous experiences and spurious correlations. We propose the Agent-Centric Actor-Critic (ACAC) algorithm to manage asynchrony without padding. ACAC uses agent-centric encoders for independent trajectory processing, with an attention-based aggregation module integrating these histories into a centralized critic for improved temporal abstractions. The proposed structure is trained via a PPO-based algorithm with a modified Generalized Advantage Estimation for asynchronous environments. Experiments show ACAC accelerates convergence and enhances performance over baselines in complex MARL tasks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在稀疏奖励的多智能体环境（如《Overcooked》合作烹饪游戏）中，智能体难以通过细粒度微动作（micro-actions）学习长期协调策略。采用宏动作（macro-actions，即一组微动作的序列作为单一决策）可以促进长期规划，但会导致智能体间决策步调异步——不同智能体完成宏动作的耗时不同，使得观测信息到达集中式Critic的时间不一致。
- **核心挑战**：现有的集中式训练-分散式执行（CTDE）方法为处理异步性，通常采用“填充”（padding）策略，即用智能体最近一次观测替代缺失的观测。但填充会引入重复的、误导性信息，使Critic混淆“新观测”与“陈旧重复观测”，导致虚假相关性，降低历史抽象精度和学习效率。
- **整体意义**：论文旨在不依赖填充的前提下，设计一种能有效处理异步多智能体强化学习的算法，提升稀疏奖励环境中的协调能力和收敛速度，为游戏AI及其他实时多智能体系统提供更稳定的训练方法。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 2.1 核心思想
提出**以智能体为中心的Actor-Critic（Agent-Centric Actor-Critic, ACAC）**。基本思路是：
- 为每个智能体单独编码其局部宏观测历史，而非将所有智能体的观测拼接到一起。
- 通过时间步嵌入（positional encoding）让编码器感知两次观测间的时间间隔。
- 利用注意力机制聚合各智能体的独立历史表示，形成集中式价值函数，从而避免填充带来的信息冗余和虚假关联。

### 2.2 关键技术细节
1. **Agent-Centric Encoder（以智能体为中心的编码器）**：
   - 输入：智能体i的宏观测历史 \(z^i_{\le t}\) 以及每个观测对应的微观时间步 \(p^i_{\le t}\)。
   - 时间步 \(p\) 使用正弦位置编码（类似Transformer中的位置编码），与宏观测拼接后经过MLP和GRU，得到每个智能体的隐状态 \(h^i_t\)。
   - 当智能体未获得新观测时，其隐状态保持上一时刻不变（不更新），只有获得新观测时才更新。

2. **Centralized Critic via Attention Aggregation（基于注意力聚合的集中式Critic）**：
   - 将各智能体的最新隐状态集合 \(\{h^1_t, ..., h^N_t\}\) 输入自注意力模块，然后通过平均池化和MLP得到全局价值估计 \(V_\psi(\tilde{h}_t)\)。
   - 这种设计使得Critic能够灵活处理不同智能体观测到达异步的情况，无需填充。

3. **损失函数与训练算法**：
   - 基于PPO（Proximal Policy Optimization）框架，Actor使用裁剪的重要性采样比率和GAE优势估计。
   - Critic使用均方误差损失，并采用PopArt值归一化技术（与MAPPO一致）。

### 2.3 核心公式与算法流程（文字说明）
- **Actor损失**（类似MAPPO的PPO损失）：
  \[
  L(\theta_i) = \mathbb{E}_\tau \left[ \min\left( \rho_t^i(\theta_i) A_t^\lambda,\; \text{clip}(\rho_t^i(\theta_i), 1-\epsilon, 1+\epsilon) A_t^\lambda \right) \right]
  \]
  其中 \(\rho_t^i(\theta_i) = \pi_{\theta_i}(m_t^i | h_t^i) / \pi_{\theta_i^{\text{old}}}(m_t^i | h_t^i)\)，\(A_t^\lambda\) 为GAE优势估计。

- **Critic损失**：
  \[
  L(\psi) = \mathbb{E}_\tau \left[ \left( \hat{R}_t - V_\psi(\tilde{h}_t) \right)^2 \right]
  \]

- **改进的GAE（适用于异步环境）**：
  - 标准GAE按微观时间步折扣，论文提出按**宏决策步**折扣，即只在新观测到达的节点计算TD误差，并用宏步骤数k作为λ的指数，而非微观时间步数：
    \[
    A^{\lambda,\text{macro}}_{l(0)} = \sum_{k=0}^\infty \lambda^k \gamma^{l(k)-l(0)} \delta_{l(k)}
    \]
    其中 \(l(k)\) 是第k个宏决策发生的微观时间步，\(\delta_{l(k)}\) 为对应TD误差。这种方式使不同长度的宏动作在价值评估中得到公平对待。

### 2.4 算法流程（文字描述）
1. 初始化各智能体的Actor网络 \(\pi_{\theta_i}\) 和集中式Critic网络 \(V_\psi\)。
2. 在每个Episode中：
   - 每个智能体根据其当前宏观测（最新隐状态）选择宏动作。
   - 执行宏动作，直到某智能体完成宏动作并获得新观测。
   - 每当任何智能体获得新观测时，更新该智能体的Agent-Centric Encoder，其余智能体保持隐状态不变。
   - 将各智能体的最新隐状态送入Attention聚合模块，由Critic输出价值估计。
   - 收集经验轨迹，计算GAE优势（使用宏级折扣），存入缓冲区。
3. 定期从缓冲区采样mini-batch，使用PPO更新Actor和Critic。
4. 重复直到收敛。

## 3. 实验设计

### 3.1 环境与场景
- **BoxPushing**：两个智能体合作将箱子推到目标区域，有6×6、8×8、10×10三种地图。箱子分为大（需两人推）和小（可单人推），奖励稀疏。
- **Overcooked**（改编自gym-cooking）：三个智能体合作制作沙拉（番茄、洋葱等），包括切菜、装盘、交付等子任务。地图为7×7，有A、B、C三种配置。
- **Overcooked-Rand**：在Overcooked基础上随机初始化物体和智能体位置，增加随机性和泛化要求。
- **Overcooked-Large**：更困难版本，地图11×11、6个智能体、4套工具，训练步数高达100M。

### 3.2 Benchmark与对比方法
- **Mac-NIACC**：使用单一集中式Critic，填充缺失观测（Xiao et al., 2022）。
- **Mac-IAICC**：每个智能体有独立Critic，填充缺失观测（Xiao et al., 2022）。
- **ACAC-Vanilla**：ACAC架构但不用PPO，采用与基线相同的损失函数。
- **ACAC micro** / **MAPPO micro**：使用微动作（不采用宏动作）的基线。
- 论文还进行了消融变体：**ACAC-Duplicate**（复制观测，模拟填充）和**ACAC（micro-level GAE）**（使用微观步级GAE折扣）。

### 3.3 实验设置
- 每个实验使用5个不同随机种子，报告回报的均值与标准误。
- 超参数：γ=0.98/0.99，GAE λ=0.95，PPO裁剪比ϵ=0.05/0.01，学习率3e-4，minibatch size 8等（见附录F）。

## 4. 资源与算力

- **文中明确提及的算力信息**（附录G）：
  - CPU：AMD EPYC 7453 28-Core Processor
  - GPU：A10（未说明具体数量，推测为单卡或少量GPU）
  - 运行时间：Overcooked环境约24~150小时，BoxPushing环境约30分钟~2小时。
- **未说明的信息**：GPU确切数量、是否多卡并行、训练总样本量对应的wall-clock时间等。整体算力需求中等，属于常规学术实验规模。

## 5. 实验数量与充分性

- **总实验组数**：包括3种BoxPushing、3种Overcooked、3种Overcooked-Rand、6种Overcooked-Large（含Rand变体），共计**15个环境变体**的完整训练曲线。
- **消融实验**：3组消融（去除padding的效果、宏级vs微级GAE、时间嵌入与注意力模块的贡献），每组分环境呈现（图9、13、14、15）。
- **敏感性分析**：对PPO裁剪比ϵ做了敏感性测试（图14）。
- **充分性评价**：
  - 优点：覆盖了从简单到困难、从固定布局到随机布局的多种场景，对比方法全面（包括微动作和宏动作的基线），消融实验针对核心设计（padding、GAE、时间嵌入、注意力）逐一验证。
  - 潜力不足：未在连续动作空间或更复杂的高维视觉输入（如像素观测）上测试；未与其他非填充式异步MARL方法（如ASM-PPO）进行直接对比；随机种子仅5个，统计意义有限但可接受；部分曲线（特别是Overcooked-Large）仅展示均值±标准误，未提供显著检验。

## 6. 主要结论与发现

1. ACAC在所有测试环境中均显著优于填充式基线（Mac-NIACC、Mac-IAICC），收敛更快、最终回报更高。
2. 微动作基线（MAPPO micro）在稀疏奖励环境中表现很差，表明宏动作对于长期规划至关重要。
3. 去除填充（ACAC vs. ACAC-Duplicate）可有效避免学习停滞或陷入次优解，证实填充确实引入有害偏差。
4. 宏级GAE折扣（按决策步数而非微时间步）比微级GAE折扣更优，能更好地处理不定长宏动作。
5. 时间嵌入和自注意力模块对性能均有贡献（消融实验显示缺失任一会下降）。
6. PPO损失函数（ACAC vs. ACAC-Vanilla）进一步提升了稳定性和收敛速度。

## 7. 优点

- **方法设计创新**：首次提出以智能体为中心的独立编码+注意力聚合，从根本上避免填充问题，结构优雅且符合异步场景的物理直觉。
- **理论贡献**：改进了GAE使其适用于宏动作异步环境，推导清晰（附录D）。
- **实验扎实**：在三种难度级别（BoxPushing、Overcooked、Overcooked-Large）上验证，包含随机化版本，证明泛化能力。
- **消融充分**：对每个关键组件（padding去除、GAE类型、时间嵌入、注意力、PPO损失）逐一消融，支撑了设计选择。
- **结果可视化清晰**：图7、8、9等展示了多条训练曲线，易于比较。
- **代码开源**（https://github.com/LGAI-Research/acac），便于复现。

## 8. 不足与局限

- **实验覆盖有限**：
  - 仅测试了离散动作空间和栅格世界类环境，未涉及连续控制（如机器人、自动驾驶）或像素级观测。
  - 未与其他非填充式异步MARL方法（如ASM-PPO、VarLenMARL）比较，导致可能高估相对优势。
  - 只有5个随机种子，统计稳定性一般；应报告置信区间或使用更多种子。
- **应用限制**：
  - 宏动作需预先设计好，对于需要自动发现宏动作的任务不适用。
  - Agent-Centric Encoder与Attention模块增加了计算开销，在大规模智能体（如>100）时可能成为瓶颈。
  - GAE的宏级折扣要求全局同步所有智能体的决策时间点，实现时需额外管理事件队列，增加工程复杂性。
- **偏差风险**：
  - 所有实验使用相同超参数网格，可能对基线方法不公平（基线方法可能未经充分调参）。
  - 基线方法（Mac-NIACC、Mac-IAICC）来自早期工作，可能未使用PPO优化，而ACAC本身是PPO框架，比较可能存在算法框架差异（尽管ACAC-Vanilla部分消减了此差异）。
- **未提供计算图谱**：未分析模型参数量、推理延迟等，实际部署可行性不明确。

（完）
