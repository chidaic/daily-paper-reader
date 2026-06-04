---
title: Extensive-Form Game Solving via Blackwell Approachability on Treeplexes
title_zh: 通过Treeplex上的Blackwell可逼近性求解扩展形式博弈
authors: "Darshan Chakrabarti, Julien Grand-Clément, Christian Kroer"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=8aA3DHLK5h"
tags: ["query:player-ai"]
score: 7.0
evidence: 扩展形式博弈的博弈论算法
tldr: 该论文提出了第一个在序列形式多面体上的Blackwell可逼近性算法框架，为双人零和扩展形式博弈的纳什均衡计算提供了新的遗憾最小化算法。基于预测性在线镜像下降，介绍了Predictive Treeplex Blackwell+，并证明了在自博弈中O(1/√T)的收敛速度。该工作为游戏AI中的策略求解提供了高效的理论工具。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 347, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1450, \"height\": 312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-8aa3dhlk5h/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1448, \"height\": 303, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-8aa3dhlk5h/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1022, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8aa3dhlk5h/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1318, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-8aa3dhlk5h/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1024, \"height\": 487, \"label\": \"Table\"}]"
motivation: 现有扩展形式博弈求解算法依赖于步长选择，缺乏不变性。
method: 将Blackwell可逼近性扩展到序列形式多面体，结合预测性在线镜像下降。
result: 新算法PTB+在自博弈中以O(1/√T)速率收敛到纳什均衡。
conclusion: 该框架为现代博弈求解提供了步长无关的高效算法。
---

## Abstract
We introduce the first algorithmic framework for Blackwell approachability on the sequence-form polytope, the class of convex polytopes capturing the strategies of players in extensive-form games (EFGs).
This leads to a new class of regret-minimization algorithms that are stepsize-invariant, in the same sense as the Regret Matching and Regret Matching$^+$ algorithms for the simplex.
Our modular framework can be combined with any existing regret minimizer over cones to compute a Nash equilibrium in two-player zero-sum EFGs with perfect recall, through the self-play framework. Leveraging predictive online mirror descent, we introduce *Predictive Treeplex Blackwell$^+$* (PTB$^+$), and show a $O(1/\sqrt{T})$ convergence rate to Nash equilibrium in self-play. We then show how to stabilize PTB$^+$ with a stepsize, resulting in an algorithm with a state-of-the-art $O(1/T)$ convergence rate. 
We provide an extensive set of experiments to compare our framework with several algorithmic benchmarks, including CFR$^+$ and its predictive variant, and we highlight interesting connections between practical performance and the stepsize-dependence or stepsize-invariance properties of classical algorithms.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在双人零和扩展形式博弈（EFG）中，如何高效计算纳什均衡。经典方法如CFR⁺及其预测变体具有极佳的实际性能，但其理论解释尚不完整，尤其是不依赖于步长（stepsize invariance）的特性被认为是其成功的关键因素之一。现有的一阶方法需要仔细调参步长，而基于Blackwell可逼近性的遗憾最小化算法（如RM⁺）在单纯形上具有步长不变性，但尚未扩展到更复杂的序列形式多面体（treeplex）。
- **研究动机**：将Blackwell可逼近性框架扩展到整个treeplex，从而构建一类步长不变的遗憾最小化算法，并探索其在EFG求解中的性能，以解释CFR⁺成功的原因，同时追求理论上的快速收敛率。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用treeplex的结构性质（⟨x, a⟩ = 1，其中a = (1,0)），将决策集T的遗憾最小化转化为对其锥包C = cone(T)上的遗憾最小化。算法1（Blackwell approachability on the treeplex）维护一个累积向量Rₜ∈C，策略xₜ = Rₜ/⟨Rₜ, a⟩，并定义瞬时损失f(xₜ, ℓₜ) = ℓₜ − ⟨xₜ, ℓₜ⟩a，满足超平面强迫条件⟨Rₜ, f(xₜ, ℓₜ)⟩ = 0。该框架可与任何锥上的遗憾最小化器结合。
- **关键技术细节**：
  - **PTB⁺**（Algorithm 2）：将框架与锥上的预测性在线镜像下降（POMD）结合，使用投影Π_C。PTB⁺具有**Treeplex步长不变性**：迭代序列不受步长η影响。理论收敛率O(1/√T)。
  - **Smooth PTB⁺**（Algorithm 3）：为解决PTB⁺在接近锥边界时决策函数不稳定问题，引入稳定区域C≥ = {R∈cone(T) | ⟨R,a⟩ ≥ R₀}，投影到C≥。损失了步长不变性，但获得了Lipschitz连续性，结合RVU界得到**O(1/T)收敛率**，是首个基于Blackwell可逼近性达到该速率的EFG求解算法。
  - **AdaGradTB⁺和AdamTB⁺**：分别采用自适应步长（AdaGrad、Adam）更新，但步长衰减可能影响性能。
- **关键公式和算法流程**（文字描述）：
  - Algorithm 1：初始化R₁=0；每轮t：xₜ=Rₜ/⟨Rₜ,a⟩；观察损失ℓₜ；将损失f(xₜ,ℓₜ)反馈给cone(T)上的遗憾最小化器更新Rₜ₊₁。
  - PTB⁺：在Algorithm 1中采用POMD更新：Rₜ=Π_C(ˆRₜ−ηmₜ)，ˆRₜ₊₁=Π_C(ˆRₜ−ηf(xₜ,ℓₜ))，预测mₜ通常取上一轮损失。
  - Smooth PTB⁺：将投影改为Π_{C≥}，其余类似。

### 3. 实验设计：数据集/场景、benchmark、对比方法
- **数据集/场景**：五个标准EFG基准游戏：Kuhn扑克、Leduc扑克、Liar’s Dice、Goofspiel、Battleship。
- **Benchmark**：无特定外部基准，但对比了多种现有先进算法。
- **对比方法**：
  - CFR⁺（线性平均）、PCFR⁺（预测性CFR⁺）、SC-POMD（单次调用投影的乐观OMD，O(1/T)速率）。
  - 内部对比：TB⁺（无预测）、PTB⁺、Smooth PTB⁺、AdaGradTB⁺、AdamTB⁺。
  - 所有算法均测试了不同平均方案（均匀、线性、二次）和是否使用交替更新。

### 4. 资源与算力
- **文中未明确说明**使用的GPU型号、数量或训练时长。实验均为CPU可完成的博弈求解，迭代次数最多10³，未提及大规模并行计算。因此算力需求较低，一般工作站即可完成。

### 5. 实验数量与充分性
- **实验数量**：
  - 第一组实验（图4）：在5个游戏上比较内部算法（TB⁺、PTB⁺、Smooth PTB⁺、AdaGradTB⁺、AdamTB⁺），展示了二次平均和最后迭代的结果，共约5×5＝25条曲线。
  - 第二组实验（图2）：对比PTB⁺、CFR⁺、PCFR⁺、SC-POMD的**平均迭代**性能（各算法最佳参数设置下）。
  - 图3：展示**最后迭代**性能。
  - 附录K.4：对每个算法单独测试不同平均方案和交替与否，共约12个图，每个图含8条曲线，覆盖所有组合。
- **充分性**：实验设计全面，涵盖了常见的EFG基准，对比了当前最流行的基线（CFR⁺、PCFR⁺、SC-POMD），并探索了步长不变性对性能的影响。但缺乏统计显著性检验（如多次随机种子重复），因为博弈求解是确定性的，只需一次运行即可。
- **公平性**：对非步长不变算法（Smooth PTB⁺、SC-POMD）进行了步长调参（η∈{0.05,0.1,0.5,1,2,5}），选取最佳结果。对PTB⁺等步长不变算法不调参。这种处理公平，但未在文中展示非最优步长的性能波动。

### 6. 论文的主要结论与发现
- **主要结论**：
  - 提出了第一个treeplex上的Blackwell可逼近性框架，并证明可转化为锥上的遗憾最小化。
  - PTB⁺具有Treeplex步长不变性，且达到O(1/√T)收敛率；Smooth PTB⁺通过引入步长达到O(1/T)更快速率，但失去步长不变性。
  - 实验发现：PCFR⁺（结合CFR分解和预测性RM⁺）总体优于PTB⁺，尽管两者都基于Blackwell可逼近性且都为预测型。**关键区别**：CFR⁺/PCFR⁺具有**信息集级步长不变性**（不同信息集可使用不同步长而不影响迭代），而PTB⁺只有**整体treeplex级步长不变性**。这种“信息集局部步长不变性”可能是CFR⁺强大实际性能的关键因素，也是论文提出的新假说。
  - 对于最后迭代性能，无算法一致最优，仍需进一步研究。
- **结论表1**总结了各算法的收敛率与步长不变性等级。

### 7. 优点
- **方法论创新**：首次将Blackwell可逼近性扩展到treeplex，提供了模块化框架，可灵活搭配不同锥上遗憾最小化器。
- **理论贡献**：证明了Smooth PTB⁺达到O(1/T)收敛率，是此类算法首次；清晰区分了treeplex步长不变性与信息集步长不变性。
- **实验分析**：深入对比了多个算法，并通过实验结果提出了关于CFR⁺成功原因的新假说（信息集步长不变性），为领域提供了有价值的研究方向。
- **可复现性**：详细描述了投影计算复杂度（O(dn log(l+m))），并给出了稳定区域的简单表达，便于实现。

### 8. 不足与局限
- **实验覆盖**：仅在5个中等规模博弈上进行，未包含超大规模博弈（如德州扑克），可能无法完全体现算法在大规模实例下的性能差异。
- **步长调参**：对非步长不变算法进行了简单网格搜索，但可能未涵盖最优步长区域；且未研究步长随迭代自适应调整的潜力。
- **最后迭代性能**：未给出理论解释，且实验显示各算法不稳定，缺乏深入分析。
- **交替更新的影响**：文中仅简要提及交替可提升性能，但未理论分析其与步长不变性的交互。
- **局限性陈述**：论文在6. Conclusion中承认PTB⁺并不如预期优于CFR⁺，并指出未来方向包括更好理解最后迭代收敛性和交替的作用。

（完）
