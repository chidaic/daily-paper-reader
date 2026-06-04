---
title: "M³HF: Multi-agent Reinforcement Learning from Multi-phase Human Feedback of Mixed Quality"
title_zh: M³HF：融合混合质量多阶段人类反馈的多智能体强化学习
authors: "Ziyan Wang, Zhicheng Zhang, Fei Fang, Yali Du"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=2Sl6Ex7Vmo"
tags: ["query:player-ai"]
score: 6.0
evidence: 在游戏类环境中利用人类反馈进行多智能体强化学习训练
tldr: 多智能体强化学习中奖励函数设计困难，常导致行为次优。本文提出M3HF框架，整合多阶段、不同质量的人类反馈，通过LLM解析反馈并暂停学习进行策略评估。在协作游戏环境中，该方法有效提升了多智能体协调能力和任务成功率，为人类反馈融入多智能体学习提供了新范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1699, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1710, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1727, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1057, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 667, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1697, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1620, \"height\": 904, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 888, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 885, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 884, \"height\": 492, \"label\": \"Table\"}]"
motivation: 多智能体强化学习中奖励函数难以设计，需要人类反馈引导以对齐复杂行为。
method: 提出M3HF框架，在训练中周期性暂停由人类评价，利用大语言模型解析反馈并更新策略。
result: 在协作环境实验表明，该方法有效提升了多智能体协调性和性能。
conclusion: M3HF成功将混合质量的人类反馈融入多智能体RL，具有实用价值。
---

## Abstract
Designing effective reward functions in multi-agent reinforcement learning (MARL) is a significant challenge, often leading to suboptimal or misaligned behaviors in complex, coordinated environments. We introduce Multi-agent Reinforcement Learning from Multi-phase Human Feedback of Mixed Quality ($\text{M}^3\text{HF}$), a novel framework that integrates multi-phase human feedback of mixed quality into the MARL training process. By involving humans with diverse expertise levels to provide iterative guidance, $\text{M}^3\text{HF}$ leverages both expert and non-expert feedback to continuously refine agents' policies. During training, we strategically pause agent learning for human evaluation, parse feedback using large language models to assign it appropriately and update reward functions through predefined templates and adaptive weights by using weight decay and performance-based adjustments. Our approach enables the integration of nuanced human insights across various levels of quality, enhancing the interpretability and robustness of multi-agent cooperation. Empirical results in challenging environments demonstrate that $\text{M}^3\text{HF}$ significantly outperforms state-of-the-art methods, effectively addressing the complexities of reward design in MARL and enabling broader human participation in the training process.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

在多智能体强化学习（MARL）中，设计有效的奖励函数是一项重大挑战，尤其是在复杂、需要高度协调的环境中。稀疏或难以学习的奖励信号会导致智能体收敛缓慢或收敛到次优策略。传统的手工设计奖励函数困难且容易产生偏差。近年来，人类反馈（RLHF）在单智能体和大语言模型微调中取得了成功，但在多智能体场景中，如何利用多样化的、混合质量的人类反馈（既有专家也有非专家）来引导学习仍然是一个开放问题。本文提出 **M³HF** 框架，通过引入多阶段、混合质量的人类反馈，迭代地优化智能体的策略，以解决奖励设计难题。

### 2. 论文提出的方法论：核心思想、关键技术细节

**核心思想**：将马尔可夫博弈扩展为“多阶段人类反馈马尔可夫博弈（MHF-MG）”，在训练过程中周期性地暂停智能体学习，收集人类对智能体当前行为的评估（通过 rollout 视频），利用大语言模型（LLM）解析反馈文本，将其转化为针对每个智能体的结构化奖励函数模板，并通过自适应权重机制组合所有历史反馈奖励，从而引导下一阶段的策略更新。

**关键技术细节**：

- **MHF-MG 定义**：在标准马尔可夫博弈基础上增加人类反馈集合 \(U\) 和人类政策 \(\pi^h\)。每代（generation）\(k\) 智能体与环境交互收集经验，然后生成 rollout 轨迹供人类观察。
- **反馈解析**：人类提供自然语言反馈 \(u_k\)，由 LLM 解析为针对每个具体智能体的指令（\(u_{ik}\)）和全局指令（\(u^{all}_k\)）。
- **奖励函数生成**：使用预定义的奖励模板集合 \(\mathcal{F}\)（包括距离型、动作型、状态型、时间型、成功型等），LLM 根据反馈选择合适的模板并参数化，生成新的奖励函数 \(R_{ik}(s,a)\)。例如，反馈“红色厨师应该去拿洋葱”会生成一个距离奖励函数，鼓励红色智能体靠近洋葱位置。
- **奖励函数池与权重调整**：每个智能体维护一个奖励函数池，包含原始奖励和所有历史反馈生成的奖励。新奖励的初始权重设为 \(1/|\mathcal{P}_i|\)，旧权重应用指数衰减（乘 \(\alpha^{M-m}\)），然后归一化。额外引入性能反馈调整：比较使用新奖励函数后的策略在原始奖励上的表现差异，若提升则增加其权重，若下降则减小（最多裁剪到0）。最终形成组合奖励 \(\hat{R}^{k+1}_i(s,a) = \sum_m w_{i,m} \cdot R_{i,m}(s,a)\)。
- **理论分析**：证明了在合理假设下（有界奖励、学习算法收敛、性能估计准确），算法对低质量反馈具有鲁棒性——低质量反馈的影响被限制在一个有界常数内，而高质量反馈的累积正效应可以持续增长（Proposition 4.2）。

### 3. 实验设计

- **场景与基准**：使用改造后的 **Overcooked** 多智能体协作环境，有三个厨师智能体需要合作制作沙拉并送达。包含三种厨房布局（A、B、C，难度递增）和两种沙拉食谱（西红柿-生菜、西红柿-生菜-洋葱）。智能体使用宏观动作（macro-actions）以简化操作。
- **对比方法**：
  - IPPO（独立 PPO）
  - MAPPO（集中批判的 PPO）
  - Macro-Action-Based Baseline（取自 Xiao et al. 2022 的最佳方法 Mac-IAICC 和 Mac-CAC 的平均表现）
  - 变体：单独解析反馈（无权重调整）、原始反馈（无解析）、单阶段反馈（仅初始一次）、内在奖励方法（IRAT 变体 rw1/rw2/rw3）
- **评价指标**：每轮迭代的平均 episode return。

**额外扩展**：在 Google Research Football 5v5 环境下进行了进一步验证（详见附录 E），对比 IPPO、MAPPO、MACCS，并报告了胜率、射门质量、拦截等指标。

### 4. 资源与算力

文中在附录 D.3 明确给出：实验在异构计算集群（Ubuntu Linux）上进行，CPU 包含 Dual Intel Xeon E5-2650、E5-2680 v2、E5-2690 v3 等型号，使用 **3 块 NVIDIA A30 GPU**，总计算资源为 180 CPU 核心和 500GB 系统内存。训练时长未具体说明（但每个环境共 25k episodes，共 1000 迭代，五个世代）。

### 5. 实验数量与充分性

- **主实验**：在 Overcooked 的 3 种布局 × 2 种食谱 = 6 个任务上，每个任务使用 3 个不同的随机种子运行，绘制了学习曲线并报告了均值和标准差（图 3）。充分展示了稳定性。
- **消融实验**：进行了三组消融：
  1. 反馈解析与权重调整对比（表 1），比较原始反馈、仅解析、完整 M³HF；
  2. 单阶段 vs 多阶段反馈（表 2）；
  3. 与内在奖励方法（IRAT）对比（表 3），在 400/600/800/1000 迭代处评价。
- **鲁棒性实验**：测试了低质量反馈和 VLM 替代人类反馈的效果（图 4）。
- **扩展实验**：在 Google Football 5v5 上进行了额外验证（附录 E）。
- **公平性**：所有基线均进行了超参数调优（学习率、批次大小、剪裁值等），且 M³HF 使用 IPPO 作为 backbone，保证了对比的公平性。

总体而言，实验覆盖了多种环境和反馈质量，消融充分，统计可靠（3 种子）。结论有说服力。

### 6. 论文的主要结论与发现

1. M³HF 在所有 Overcooked 任务上均显著优于 IPPO、MAPPO 和宏动作基线，尤其在复杂布局中优势更明显。
2. 多阶段、混合质量的人类反馈能够有效加速学习并提升最终性能；即使包含低质量反馈，算法也能通过自适应权重保持性能，不会显著退化（支持理论鲁棒性）。
3. 使用 VLM 代替人类反馈目前效果接近人类但仍有差距（VLM 反馈不够具体），但具有未来潜力。
4. 消融表明：结构化解析和性能权重调整都是关键组件；多阶段反馈优于单次反馈；M³HF 远优于传统内在奖励设计方法（IRAT）。

### 7. 优点

- **创新性**：首次将混合质量、多阶段人类反馈系统性地融入在线 MARL 训练，提出 MHF-MG 形式化框架。
- **实用性**：通过 LLM 解析自然语言反馈，无需人类标注偏好，降低人类参与门槛；权重衰减与性能反馈机制自动过滤低质量反馈，鲁棒性强。
- **理论贡献**：提供了低质量反馈影响有界、正积累的数学证明。
- **实验充分**：在多种环境、多种反馈质量、多种对比方法下验证，消融实验设计合理，结果清晰。

### 8. 不足与局限

- **环境局限**：主要在 Overcooked 和足球两个领域测试，未在更复杂、更通用的多智能体基准（如 SMAC、多机器人任务）上验证，泛化性有待确认。
- **反馈频率**：当前假设人类反馈在每个世代末提供（最多五次），但实际部署中可能需要更动态的反馈时机。
- **LLM 成本**：使用 GPT-4o 和 Gemini Pro 等模型进行解析和生成，计算成本和 API 调用开销较大，可能不适合资源受限场景。
- **人类质量假设**：虽然考虑了混合质量，但人类反馈的有效性仍然依赖于人类对任务的基本理解；在非常复杂或抽象的任务中，非专家反馈可能仍然难以利用。
- **VLM 替代**：目前 VLM 反馈效果不理想，限制了自动化扩展的可能性。
- **理论分析**：Proposition 4.2 的假设较强（算法收敛到 \(\epsilon\)-最优、性能估计准确），在实践中可能不完全成立。

（完）
