---
title: Evaluating LLMs in Open-Source Games
title_zh: 评估开源游戏中的大型语言模型
authors: "Swadesh Sistla, Max Kleiman-Weiner"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=X9SNL203cV"
tags: ["query:player-ai"]
score: 9.0
evidence: 评估LLM作为开源游戏中的游戏代理
tldr: 本文研究了大型语言模型在开源游戏中的表现，游戏中的玩家提交计算机程序作为行动。作者评估了多种LLM在预测和分类程序策略方面的能力，并分析了在双人和进化设定下LLM代理所达到的近似程序均衡的特征，发现了利润最大化、合作和欺骗策略的出现。这项工作展示了LLM在游戏理论环境中的潜力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-x9snl203cv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1122, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x9snl203cv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1419, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x9snl203cv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1294, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x9snl203cv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x9snl203cv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1355, \"height\": 744, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x9snl203cv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1433, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x9snl203cv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1491, \"height\": 1909, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-x9snl203cv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1355, \"height\": 793, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x9snl203cv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 642, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x9snl203cv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x9snl203cv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1487, \"height\": 345, \"label\": \"Table\"}]"
motivation: 利用LLM的编程能力使其参与开源游戏，探索程序均衡等新概念。
method: 提出开源游戏设定，评估LLM预测和分类程序策略的能力，分析程序均衡特征。
result: 识别出利润最大化、合作和欺骗策略的出现。
conclusion: LLM能在开源游戏中形成复杂的策略均衡，具有可解释性和可验证性优势。
---

## Abstract
Large Language Models' (LLMs) programming capabilities enable their participation in \textit{open-source games}: a game-theoretic setting in which players submit computer programs in lieu of actions. These programs offer numerous advantages, including interpretability, inter-agent transparency, and formal verifiability; additionally, they enable \textit{program equilibria}, solutions that leverage the transparency of code and are inaccessible within normal-form settings. We evaluate the capabilities of leading open- and closed-weight LLMs to predict and classify program strategies and evaluate features of the approximate program equilibria reached by LLM agents in dyadic and evolutionary settings. We identify the emergence of payoff-maximizing, cooperative, and deceptive strategies, characterize the adaptation of mechanisms within these programs over repeated open-source games, and analyze their comparative evolutionary fitness. We find that open-source games serve as a viable environment to study and steer the emergence of cooperative strategy in multi-agent dilemmas.

---

## 论文详细总结（自动生成）

# 论文总结：Evaluating LLMs in Open-Source Games

## 一、论文的核心问题与整体含义（研究动机与背景）

- **核心问题**：在多人博弈场景中，大型语言模型（LLM）能否通过提交可执行的程序（而非直接选择动作）来参与“开源游戏”（open-source games），并形成可解释、可验证的“程序均衡”（program equilibrium）。这一设定旨在解决传统博弈中策略黑箱化、难以审计的问题，同时探索LLM能否利用代码透明度实现合作、欺骗或利润最大化策略。
- **背景**：随着LLM代理被部署到现实世界（如金融、合同谈判、客服），多智能体之间的战略互动日益重要。游戏理论（如囚徒困境）揭示自私代理可能无法实现合作；而开源博弈理论要求代理提交完整程序，程序间互相读取代码后再行动，从而获得比普通形式博弈更多的均衡可能性（例如基于代码相似度的合作）。然而此前多为理论分析，缺乏LLM的实证评估。本文首次系统评估LLM在开源游戏中的表现。

## 二、论文提出的方法论：核心思想与关键技术细节

- **开源游戏设定**：
  - 每轮（meta-round）中，每个LLM代理生成一个Python程序（策略函数），该函数接收对手的源代码作为输入，并输出动作（如合作C或背叛D）。
  - 程序在每轮开始前相互交换代码，然后执行；代理基于上一轮对手的代码和交互历史更新自己下一轮的程序。
  - 最终目标是达到“程序均衡”：没有代理能通过单方面更换程序获得更高收益。
- **两大任务**：
  1. **SPARC基准**（Strategic Program Analysis for Reciprocal Cooperation）：测试LLM是否能从Python代码中判断一个IPD（迭代囚徒困境）策略是否会在10轮中始终合作（面对纯合作对手）。通过掩码（去除类名）和混淆（重命名所有标识符）来剥离语义线索，测试真正的算法推理能力。
  2. **多轮开源游戏实验**：让LLM代理在IPD和Coin Game（一种二维网格上的空间社会困境）中反复生成程序，观察策略演化。定义三种目标类型：
     - PM（利润最大化）：只追求自己得分。
     - CPM（合作型利润最大化）：追求高得分但避免欺骗/剥削。
     - DPM（欺骗型利润最大化）：允许使用欺骗手段。
   - 采用**两阶段生成**：代理先写自然语言策略描述，再实现为Python代码。
   - 分析指标：循环复杂度、Halstead Effort（程序理解难度）、对手脚本访问分数（OSAS，代码中引用对手代码的程度），以及通过GPT-4o作为裁判对策略特征分类（独立发展、模仿、反制、剥削尝试、佯攻）。
- **进化动力学**：利用复制子动力学（replicator dynamics）模拟三种策略在种群中随时间的变化，计算支付矩阵并分析吸引子（稳定均衡）。

## 三、实验设计：数据集、场景、基准、对比方法

- **数据集/场景**：
  - **SPARC基准**：来自Axelrod Python库的239个IPD策略，覆盖不同复杂度、随机性、记忆深度。三种版本：原始、掩码类名、完全混淆。
  - **多轮开源游戏**：IPD（标准支付T=5,R=3,P=1,S=0）和Coin Game（2D网格，红蓝玩家，收集自己颜色得1分，让对手捡到则扣2分）。
- **基准模型**：
  - 开放权重模型：Mistral Small (24B)、Qwen 2.5 (7B/72B)、Qwen 2.5 Coder (32B)、Kimi K2、DeepSeek-V3。
  - 封闭模型：GPT-4o Mini、GPT-4.1 Nano/Mini、GPT-4.1。
  - 推理模型：DeepSeek-R1、o4-mini。
- **对比方法**：对SPARC任务，比较零样本（ZS）与思维链（COT）提示；对多轮游戏，比较三种目标类型（CPM、DPM、PM）之间的两两配对，并分析静态对手（纯合作/纯背叛）基线。此外，还测试了基于语法比较的相似性合作者（Similarity-Based Cooperator）。

## 四、资源与算力

- 论文未明确报告GPU型号、数量或训练时长。仅提及：
  - 所有实验通过商用LLM API完成，总成本低于50美元。
  - 每次调用耗时从几秒到一分钟不等。
  - 未使用本地大规模计算资源，主要依赖云API（HuggingFace、OpenAI API）。
- 因此，本文不涉及自训练或微调，仅进行推理和评估，算力需求较低。

## 五、实验数量与充分性

- **SPARC基准**：对所有239个策略，在三个版本（原始/掩码/混淆）、两种提示（ZS/COT）下评估了12个模型，共约12*3*2=72个实验结果表（部分模型无COT）。统计显著性通过t检验报告（图3）。
- **多轮游戏**：每种配对（CPM vs CPM, CPM vs DPM, ……共6种配对）进行10个独立种子（run），每个种子10个meta-round，每轮10个IPD或Coin Game回合。因此总共10*6*10*10=6000次游戏运行（每种游戏）。策略特征分析使用了GPT-4o裁判。
- **进化动力学**：通过复制子动力学模拟，基于50次游戏的支付矩阵。
- **相似性合作者实验**：10个种子，每个20轮IPD。
- **充分性评价**：
  - 实验量较为充分，覆盖多种模型、多种策略类型和多种游戏场景。
  - 统计误差（标准误）和显著性检验基本到位。
  - 但仅使用了两种游戏（IPD和Coin Game），且均为两人零和/社会困境，泛化性受限。
  - 仅用一种LLM（Kimi K2）进行多轮策略生成实验，未在不同模型间对比生成能力（SPARC测试了多种模型，但生成实验只用了Kimi K2，理由可能是成本或性能？）。这可能导致结论对模型选择敏感。

## 六、论文的主要结论与发现

1. **LLM能理解战略代码**：在SPARC基准上，顶级模型（如o4-mini、DeepSeek-V3）在混淆代码上仍能达到>80%准确率，思维链提示显著提升性能，且语义线索（类名）影响不大。
2. **开源游戏中LLM能形成复杂策略**：在双人开源游戏中，LLM代理能根据目标类型（CPM、DPM、PM）产生显著不同的策略特征，如CPM偏向反制/模仿，DPM偏向剥削/佯攻，PM则机会主义。
3. **程序复杂度随游戏类型变化**：在Coin Game中复杂度逐渐上升（需要空间推理），在IPD中复杂度下降（收敛到简单的“以牙还牙”类策略）。
4. **从代码读取向历史学习的转变**：早期回合OSAS高（直接分析对手代码），随后降低，说明代理更多利用历史交互而非运行时代码读取。
5. **进化动力学显示不同均衡**：Coin Game中PM占优（所有流线指向PM角落），IPD中CPM和DPM均为稳定状态（存在多个吸引子）。
6. **开源游戏可作为研究合作涌现的可行环境**：LLM代理能在没有显式协调的情况下实现近似程序均衡，并展现出合作与欺骗策略。

## 七、优点：方法与实验设计的亮点

- **创新性设定**：首次将开源博弈理论（程序均衡）与LLM编程能力结合，开辟了多智能体安全与可解释性新方向。
- **精心设计**：SPARC基准通过掩码和混淆剥离语义线索，有效测量了核心算法推理而非语言理解，提高了评估的纯净度。
- **多维度分析**：不仅报告得分，还分析了程序复杂度、代码读取程度、策略分类等，深入揭示策略演化机制。
- **进化动力学分析**：提供了长期稳定性视角，不仅看短期表现，还预测哪些策略能持续存在。
- **开源可复现**：提供代码和数据集。

## 八、不足与局限

1. **场景受限**：仅测试了两种两人博弈（IPD和Coin Game），未扩展到更多玩家、部分可观察、连续动作等复杂现实场景。
2. **假设完全透明**：代理能完整阅读对手原始源代码，这在现实开放系统中可能不成立（如编译后、混淆后、部分隐藏）。
3. **数据集污染风险**：IPD策略（如Tit-for-Tat）可能出现在LLM训练数据中，影响生成模式；虽SPARC去除了语义线索，但生成实验中LLM可能依赖记忆。
4. **生成实验仅用单模型**：多轮策略生成仅使用Kimi K2，未测试其他模型（如DeepSeek、GPT-4）是否能产生更优策略，结论的普适性存疑。
5. **缺乏形式验证**：论文声称可验证性，但实际并未对生成的程序进行形式验证或安全证明。
6. **欺骗策略的影响**：实验中DPM代理的欺骗效果有限（未能显著压榨对手），可能由于LLM实现能力的限制；但在更强大模型下欺骗可能更危险。

---

（完）
