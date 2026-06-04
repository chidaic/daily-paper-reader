---
title: Heterogeneous Adversarial Play in Interactive Environments
title_zh: 交互环境中的异质对抗性游戏
authors: "Manjie Xu, Xinyi Yang, Jiayu Zhan, Wei Liang, Chi Zhang, Yixin Zhu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=8Q4xTf2SYC"
tags: ["query:player-ai"]
score: 8.0
evidence: 通过异质对抗性游戏进行AI代理训练
tldr: 该论文针对传统自博弈在非对称开放学习场景中的不足，提出了异质对抗性游戏框架。通过模拟人类教学系统中的非对称指导机制，让系统自动生成适合不同学习者的挑战课程。该方法有望用于游戏AI训练中自动调整对手难度，提升智能体的适应能力，但当前主要关注通用框架而非具体游戏实现。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-8q4xtf2syc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 597, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8q4xtf2syc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 748, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8q4xtf2syc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8q4xtf2syc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8q4xtf2syc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8q4xtf2syc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 645, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8q4xtf2syc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1412, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8q4xtf2syc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1433, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8q4xtf2syc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 723, \"height\": 508, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 878, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1014, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1130, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1114, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 591, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1072, \"height\": 814, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1084, \"height\": 958, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1083, \"height\": 965, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 808, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1086, \"height\": 963, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8q4xtf2syc/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 936, \"height\": 240, \"label\": \"Table\"}]"
motivation: 对称自博弈在异质开放环境中无法有效产生学习课程。
method: 提出非对称自适应对抗机制，模拟人类教学系统。
result: 框架能自动生成适应个体学习者的课程。
conclusion: 异质对抗性游戏为开放式学习提供了一种新的范式。
---

## Abstract
Self-play constitutes a fundamental paradigm for autonomous skill acquisition, whereby agents iteratively enhance their capabilities through self-directed environmental exploration. Conventional self-play frameworks exploit agent symmetry within zero-sum competitive settings, yet this approach proves inadequate for open-ended learning scenarios characterized by inherent asymmetry. Human pedagogical systems exemplify asymmetric instructional frameworks wherein educators systematically construct challenges calibrated to individual learners' developmental trajectories. The principal challenge resides in operationalizing these asymmetric, adaptive pedagogical mechanisms within artificial systems capable of autonomously synthesizing appropriate curricula without predetermined task hierarchies. Here we present Heterogeneous Adversarial Play (HAP), an adversarial Automatic Curriculum Learning framework that formalizes teacher-student interactions as a minimax optimization wherein task-generating instructor and problem-solving learner co-evolve through adversarial dynamics. In contrast to prevailing automatic curriculum learning methodologies that employ static curricula or unidirectional task selection mechanisms, HAP establishes a bidirectional feedback system wherein instructors continuously recalibrate task complexity in response to real-time learner performance metrics. Experimental validation across multi-task learning domains demonstrates that our framework achieves performance parity with SOTA baselines while generating curricula that enhance learning efficacy in both artificial agents and human subjects.

---

## 论文详细总结（自动生成）

# 论文《异质对抗性游戏：交互环境中的自动课程学习》详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统自博弈（Self-play）依赖智能体之间的对称性（相同角色和目标），在零和竞争环境中有效，但在开放、异质的学习场景中（如教师与学生角色不同）难以自动生成合适的课程。人类教学系统天然具有非对称性：教师根据学习者的发展状态动态调整挑战难度。如何在人工智能系统中实现这种自适应、非对称的课程机制，是本文要解决的核心问题。
- **背景**：现有的自动课程学习（ACL）方法（如TSCL、EXP3）采用静态或单向的任务选择策略（基于成功率或损失），缺乏教师与学生之间的双向反馈循环，容易导致任务难度错配、过拟合或灾难性遗忘。
- **整体含义**：本文提出HAP框架，将教师-学生交互建模为零和博弈中的对抗优化，使教师自动生成挑战性任务而学生努力解决，从而形成持续自适应的课程。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：
  - 将自动课程学习形式化为一个最小-最大（minimax）优化问题：学生最大化任务奖励，教师最小化学生奖励（即选择学生最可能失败的任务）。
  - 利用不对称的对抗动态来替代传统手工课程，教师和学生共享相同环境但拥有不同角色和目标。
- **关键技术细节**：
  - **学生**：优化策略参数θ，最大化在教师生成的任务分布p_ϕ(T)下的期望累积奖励。
  - **教师**：神经网络，输入学生最近的行为历史（如N步奖励序列），输出任务选择概率（softmax归一化）。教师的目标是最小化学生的期望奖励，从而倾向于选择学生尚不能胜任的任务。
  - **训练流程**（伪代码见算法1）：循环执行教师任务采样 → 学生执行并收集轨迹 → 学生策略更新 → 教师对抗更新（基于策略梯度定理）。
  - **解决实际问题**：
    - **冷启动问题**：在训练开始时，教师和学生均无先验，通过预热阶段让学生独立探索所有任务，建立基线。
    - **任务过载**：引入熵正则化，防止教师均匀选择过多任务导致学生注意力分散。
    - **灾难性遗忘**：对每个任务的采样概率施加下界，确保学生不会完全遗忘已掌握技能。
- **公式**：
  - 学生目标：max_θ J_student(θ) = E_{T~p_ϕ} [E_{τ~π(·|T;θ)} R(τ;T)]
  - 教师目标：min_ϕ J_teacher(ϕ) = E_{T~p_ϕ} [E_{τ~π(·|T;θ)} -R(τ;T)] + λ H(p_ϕ)
  - 教师梯度：∇_ϕ J_teacher = -E_{T~p_ϕ} [∇_ϕ log p_ϕ(T) · E_τ R(τ;T)]

## 3. 实验设计：使用的数据集 / 场景、benchmark、对比方法

- **环境**：
  1. **Minigrid**（网格导航）：包含6个任务（Empty, Crossing, DoorKey, FourRooms, MultiRoom, Playground），按难度分为Easy/Middle/Hard。
  2. **CRAFT**（Minecraft风格）：包含多个递进式任务（采集、制作、建造），共23个任务，同样三级难度。
  3. **Crafter**（开放世界）：包含对抗和生存元素，修改后移除生存要求，评估16个成就，三级难度。
- **监督学习扩展**：CIFAR-100（图像分类，含类别不平衡模拟）、RTE（自然语言推理，含标签噪声），使用CurBench基准。
- **人类研究**：30名被试在Minigrid中进行学习，比较三种条件：无教程、专家教程、HAP自动教程。
- **对比方法**：
  - 标准RL：DQN, A2C, PPO, SAC, TD3.
  - SOTA世界模型：DreamerV3.
  - 课程学习：TSCL, EXP3, 手动Easy-to-Hard课程.
  - 监督课程：TTCL, SPL, LRE, ScreenerNet, MW-Net.
  - 人类专家作为性能上界。

## 4. 资源与算力

- 论文在**初步实验**（导航任务）和主要实验中明确提到使用**单个NVIDIA A100 GPU**进行训练。
- **未明确说明**整体训练时长、总GPU天数、具体模型参数数量（除附录表格外）。例如，Minigrid和CRAFT等主要实验的迭代次数、收敛时间未量化报告。

## 5. 实验数量与充分性

- **实验覆盖**：在三个RL环境（分别有6, 23, 16个任务）上对比了6~8种基线；监督学习扩展测试了2个数据集；人类研究30名被试。还包含了消融研究（历史长度、熵正则、冷启动、概率下界）。
- **充分性评价**：
  - 实验设计较为全面，涵盖了从简单到复杂的多任务场景，且包含人类验证。
  - 对比了多个类别的基线（标准RL、世界模型、课程学习），可客观反映HAP的优势。
  - 消融研究证实了各组件的重要性（熵正则化、冷启动、概率下界）。
  - **不足**：未在更多真实世界或机器人任务上验证；未与其他对抗课程学习（如无监督环境设计PAIRED）直接比较；监督学习部分仅用两个基准测试，样本规模较小。

## 6. 论文的主要结论与发现

- **性能提升**：HAP在Minigrid、CRAFT和Crafter上均达到或超越SOTA基线，尤其在中等和困难任务上表现突出。在CRAFT困难任务上，HAP得分0.31，远超DreamerV3的0.27；整体得分0.562，将人机差距缩小约30%。
- **自适应课程特性**：教师自动增加失败任务的采样概率，降低已掌握任务的采样概率，形成正负反馈循环，加速学习。
- **缓解遗忘和过拟合**：动态调整任务分布使得学生能够平衡地学习所有难度等级，避免对简单任务的过度训练。
- **泛化至监督学习**：在CIFAR-100（类别不平衡）和RTE（标签噪声）上，HAP匹配甚至超越现有课程学习方法，显示对抗课程原则的通用性。
- **人类学习验证**：HAP生成的教程与专家教程在最终表现上相近，且HAP能提供更个性化的自适应指导，加速早期技能获取。
- **局限**：所有算法在困难任务上仍远低于人类表现；在开放环境Crafter中增益较温和；深度依赖超参数（如熵权重、下限值）。

## 7. 优点：方法或实验设计上的亮点

- **方法论亮点**：
  - 将课程学习重新定义为零和博弈，利用了对抗训练的自适应特性，无需手工任务排序。
  - 通过简单实用的技巧（冷启动、熵正则、概率下界）解决了对抗训练中常见的崩溃和遗忘问题。
  - 框架可自然扩展至监督学习场景，展示通用性。
- **实验设计亮点**：
  - 从离散导航到开放世界再到真实人类研究，多层面验证。
  - 消融实验系统，明确分析每个组件的贡献。
  - 人类研究不仅验证了算法生成的教程质量，还揭示了与专家策略的一致性，增加了可信度。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制

- **实验覆盖不足**：
  - 仅使用模拟环境，未在真实机器人或更复杂的开放世界（如Minecraft完整版）测试。
  - 未与最新的对抗无监督环境设计（PAIRED, PLR等）进行对比。
  - 监督学习测试仅涉及两个数据集，规模较小。
- **偏差风险**：
  - 环境任务的设计由作者划分难度等级，可能引入主观偏差。
  - 教师获得的反馈仅基于历史奖励，忽略了更丰富的学生内部状态（如梯度、特征空间变化）。
- **应用限制**：
  - 对抗训练对超参数敏感，需要仔细调参（如熵权重λ、概率下限）。
  - 教师更新频率与环境动态有关，在复杂环境中可能需要大量评估步骤。
  - 性能在高度随机、长任务依赖的开放世界场景中提升有限，可能需要额外机制（如分层抽象或外部记忆）。
  - **计算资源**未充分报告，难以复现且评估效率。
- **其他**：未讨论公平性、安全性等社会影响；未提供开源代码（仅声称将在项目网站发布）。

（完）
