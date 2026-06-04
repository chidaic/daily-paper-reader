---
title: Enhancing the Hierarchical Environment Design via Generative Trajectory Modeling
title_zh: 通过生成式轨迹建模增强层次化环境设计
authors: "Dexun Li, Pradeep Varakantham"
date: 2024-05-14
pdf: "https://openreview.net/pdf?id=O6YRAOfHGt"
tags: ["query:player-ai"]
score: 8.0
evidence: AI代理训练环境设计
tldr: 该论文针对资源受限场景下无监督环境设计效率低的问题，提出了一个层次化MDP框架。其中上层RL教师代理为下层学生代理生成合适的训练环境，通过生成式轨迹建模优化课程。该方法在有限环境数量下仍能有效训练智能体，提升了零样本迁移性能，为游戏AI训练环境的自动生成提供了技术支撑。
source: NeurIPS-2024-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 632, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 645, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1373, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 816, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1409, \"height\": 841, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1414, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1384, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 672, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1371, \"height\": 1641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1369, \"height\": 1080, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-o6yraofhgt/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1347, \"height\": 521, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-o6yraofhgt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1187, \"height\": 258, \"label\": \"Table\"}]"
motivation: 现有无监督环境设计方法在资源受限时无法高效生成训练课程。
method: 提出层次化MDP框架，由上层RL教师代理生成环境课程。
result: 在有限环境数量下实现了更好的零样本迁移性能。
conclusion: 层次化环境设计可在资源约束下有效训练泛化性强的智能体。
---

## Abstract
Unsupervised Environment Design (UED) is a paradigm that automatically generates a curriculum of training environments, enabling agents trained in these environments to develop general capabilities, i.e., achieving good zero-shot transfer performance. However, existing UED approaches focus primarily on the random generation of environments for open-ended agent training. This is impractical in resource-limited scenarios where there is a constraint on the number of environments that can be generated. In this paper, we introduce a hierarchical MDP framework for environment design under resource constraints. It consists of an upper-level RL teacher agent that generates suitable training environments for a lower-level student agent. The RL teacher can leverage previously discovered environment structures and generate environments at the frontier of the student's capabilities by observing the student policy's representation. Additionally, to alleviate the time-consuming process of collecting the experience of the upper-level teacher, we utilize recent advances in generative modeling to synthesize a trajectory dataset for training the teacher agent. Our method significantly reduces the resource-intensive interactions between agents and environments, and empirical experiments across various domains demonstrate the effectiveness of our approach.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

无监督环境设计（Unsupervised Environment Design, UED）旨在自动生成训练环境的课程（curriculum），使得在这些环境中训练的智能体具备通用能力（即良好的零样本迁移性能）。然而，现有UED方法主要依赖开放式的随机环境生成，这在资源受限场景（如环境生成数量有限）下不切实际。本文的核心问题是如何在有限环境预算下，高效地生成适合学生智能体当前能力水平的环境，从而在较短训练时间内提升学生的通用能力。研究动机来源于UED在现实应用中对环境数量和训练时间有严格约束，而现有方法（如PAIRED、ACCEL、域随机化）要么计算成本高，要么探索效率低，无法有效利用先前发现的环境结构。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
提出一个层次化马尔可夫决策过程（Hierarchical MDP）框架，称为 **SHED（Synthetically-enhanced Hierarchical Environment Design）**。该框架包含：
- **上层RL教师智能体**：负责生成适合下层学生智能体的训练环境参数。
- **下层学生智能体**：在生成的环境中进行训练，提升其通用能力。

教师智能体通过观察学生策略的表示（性能向量）来生成处于学生能力前沿的环境，从而更精准地设计课程。

### 关键技术细节

1. **上层教师MDP**：
   - **状态空间** \( S^u \)：学生策略的表示，即学生在 \( m \) 个多样化评估环境上的性能向量 \( s^u = [p_1, \ldots, p_m] \)。
   - **动作空间** \( A^u \)：环境参数向量 \( \theta \)，用于生成具体环境实例。
   - **转移动态** \( P^u \)：学生在生成的训练环境中训练后，性能向量发生变化。
   - **奖励函数** \( R^u \)：设计为考虑公平性的改进奖励，鼓励教师公平地提升学生在所有评估环境中的表现：  
     \[
     R(s^u, a^u, s^{u'}) = \sum_{i=1}^m (p'_i - p_i) - \eta \cdot cv(s^u, a^u, s^{u'})
     \]  
     其中 \( cv \) 是性能改进的变异系数，用于衡量公平性。

2. **下层学生MDP**：学生在由教师参数生成的POMDP环境中训练，最大化累积奖励。

3. **生成式轨迹建模**：
   - 由于上层MDP的每次转移涉及学生完整的训练周期，数据收集极其耗时。本文利用扩散概率模型（Diffusion Probabilistic Model）学习学生性能演变轨迹的分布，生成合成经验数据。
   - **扩散模型**：以 \( (s^u, a^u) \) 为条件，生成下一状态 \( s^{u'} \)。训练目标为去噪噪声预测：
     \[
     L(\phi) = \mathbb{E}_{(s^u, a^u, s^{u'}) \sim \tau, k \sim \mathcal{U}, \epsilon \sim \mathcal{N}(0,I)} \left[ \|\epsilon - \epsilon_\phi(s_k^{u'}, s^u, a^u, k)\|^2 \right]
     \]
   - 生成合成轨迹时，先采样随机动作 \( a^u \)（或训练另一个扩散模型模仿教师策略），再通过反向去噪链生成 \( s^{u'} \)，然后计算奖励，将 \( (s^u, a^u, r^u, s^{u'}) \) 加入合成经验池，用于训练教师智能体。教师使用离策略算法（DDPG）训练。

4. **伪代码（Algorithm 1）**：
   - 初始化：扩散模型 \( D \)，教师策略 \( \Lambda \)，真实和合成回放缓冲区 \( B_{real}, B_{syn} \)。
   - 外层循环每个episode：初始化学生策略，评估其性能向量。
   - 内层循环每个预算步骤：教师生成环境参数 → 学生在该环境中训练 → 重新评估学生 → 计算奖励 → 存入真实缓冲 → 训练扩散模型 → 生成合成经验 → 教师从混合缓冲区训练（按比例 \( \psi \)）。

## 3. 实验设计

### 数据集/场景
- **Lunar Lander**：经典的火箭着陆优化问题。环境参数包括重力、风力、湍流强度。
- **BipedalWalker**（修改版）：控制双足机器人穿越地形。教师选择8个地形参数（地面粗糙度、台阶数、坑宽、树桩高、楼梯高等）。
- **部分可观察迷宫（Maze）**：导航任务，智能体视野为3×3网格。迷宫非参数化，通过大型语言模型（ChatGPT）结合检索增强生成（RAG）生成迷宫，教师选择关键因素（尺寸、结构、目标位置等）。

### Benchmark与对比方法
- **Domain Randomization (DR)**：随机生成环境。
- **ACCEL**：基于手动划分难度等级的自适应课程。
- **Edited ACCEL**：略作修改，不重访之前生成的环境。
- **PAIRED**：基于最小最大遗憾的RL生成器。
- **h-MDP**：本文提出的层次化方法，但**不使用扩散模型**辅助训练（作为消融对比）。

### 评价指标
- 学生性能：在随机固定的一组测试环境上的零样本迁移性能。
- **评估环境**：用于构建学生性能向量（观察教师）；**测试环境**：用于衡量通用能力，两者不重叠且训练中不可见。

### 训练细节
- 学生使用PPO训练，教师使用DDPG（离策略）。
- Lunar Lander: 1e6环境步；BipedalWalker: 1e7环境步；Maze: 类似时长。

## 4. 资源与算力

论文附录D.2明确说明：
- **所有模型**在单张 **NVIDIA GeForce RTX 3090 GPU** 和 **16 CPUs** 上训练。
- 未给出具体每类实验的绝对训练时长，但指出所有模型均使用上述配置。

## 5. 实验数量与充分性

- **主要实验**：在三个不同域（Lunar Lander, BipedalWalker, Maze）上进行，每个域对比了5种方法（DR, ACCEL, Edited ACCEL, PAIRED, h-MDP, SHED）。
- **消融实验**（附录C和E）：
  - 评估扩散模型生成合成轨迹的质量（通过分布匹配和噪声敏感性实验）。
  - 评估评估环境集合大小的影响（5, 30, 40）。
  - 评估不同公平性权重 \(\eta\) 的影响。
  - 评估更长训练时间下的表现。
- 实验次数：每个设置报告均值和标准误差（多次运行，种子数未明确但通常3-5次）。
- **充分性评价**：实验覆盖了三个不同难度的环境、多种对比方法和消融因素，总体上较为充分。但迷宫域仅显示单条曲线，未提供多次运行误差线（图4），可能影响可靠性。此外，未报告统计显著性检验（如t检验）。

## 6. 主要结论与发现

1. **SHED在所有三个域中均优于或持平于现有UED方法**，尤其在资源受限（有限环境数量）下，学生零样本迁移性能更高，且方差更小。
2. **层次化设计**能够有效利用学生策略表示生成合适的环境，避免随机搜索的盲目性。
3. **扩散模型生成的合成轨迹**显著减少了教师经验收集的成本，使得教师能够在有限真实数据下学习更优策略。
4. 在公平性奖励下，教师生成的环境能更均衡地提升学生在各评估环境上的表现，避免过度牺牲某些环境。
5. 增加评估环境集合大小有助于更准确地表示学生策略，但过度增加会提高扩散模型训练难度。

## 7. 优点

- **方法创新性**：将层次化强化学习与生成式建模（扩散模型）结合，解决了UED中资源受限和训练低效的问题。
- **理论支撑**：附录A提供定理1，证明存在有限评估环境集足以近似表示学生策略的通用能力。
- **实验设计全面**：跨多个领域（连续控制、离散导航），对比多种经典和SOTA方法，并做多角度消融。
- **实际意义**：针对真实应用中的计算预算限制，提出可行解决方案，对游戏AI训练环境自动生成等技术有直接参考价值。

## 8. 不足与局限

- **实验覆盖的局限性**：
  - 迷宫实验中未显示多次运行的标准误差，结果可靠性存疑。
  - 未在高维复杂环境（如3D场景、像素输入）中验证，论文自述UED限于参数化环境，实验域相对简单。
  - 未与最新UED变种（如PLR, REPLAY等）全面比较。
- **偏差风险**：
  - 评估环境和测试环境虽然不重叠，但均基于同一参数空间随机生成，可能不足以代表真正未知的分布外场景。
  - 教师奖励设计中的公平项 \(\eta\) 需要手工调节，可能影响泛化。
- **应用限制**：
  - 扩散模型生成合成轨迹的质量依赖于真实数据量，初始阶段教师经验不足时效果可能受限。
  - 层次化框架需要额外维护评估环境集合，增加了系统复杂度。
- **可重复性**：代码虽附在补充材料中，但未提供详尽的环境配置和种子列表，可能影响完全复现。

（完）
