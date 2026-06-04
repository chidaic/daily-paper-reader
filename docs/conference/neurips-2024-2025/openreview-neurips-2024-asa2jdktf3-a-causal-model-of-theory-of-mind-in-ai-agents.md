---
title: A Causal Model of Theory-of-Mind in AI Agents
title_zh: AI代理心智理论的因果模型
authors: "Jack Foxabbott, Rohan Subramani, James Fox, Francis Rhys Ward"
date: 2024-05-15
pdf: "https://openreview.net/pdf?id=ASA2jdKtf3"
tags: ["query:player-ai"]
score: 4.0
evidence: 提出AI代理心智理论的因果模型，可应用于游戏互动
tldr: 本文扩展了多智能体影响图框架，显式捕获AI代理的心智理论推理，即推理他人信念和意图的能力。提出的II-MAIDs框架与不完全信息动态游戏有理论联系，为理解代理在复杂交互中的行为提供了因果模型。
source: NeurIPS-2024-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-asa2jdktf3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1176, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-asa2jdktf3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1621, \"height\": 602, \"label\": \"Figure\"}]"
motivation: 代理在与其他代理和人类互动时需要心智理论推理。
method: 扩展多智能体影响图，引入不完全信息（II-MAIDs）来建模心智理论。
result: II-MAIDs与不完全信息动态游戏有强理论联系。
conclusion: 提供了一个因果框架来理解代理的复杂推理。
---

## Abstract
Agency is a vital concept for understanding and predicting the behaviour of future AI systems. There has been much focus on the goal-directed nature of agency, i.e., the fact that AI agents may capably pursue goals. However, the dynamics of agency become significantly more complex when autonomous agents interact with other agents and humans, necessitating engagement in theory-of-mind, the ability to reason about the beliefs and intentions of others. In this paper, we extend the framework of multi-agent influence diagrams (MAIDs) to explicitly capture this complex form of reasoning. We also show that our extended framework, MAIDs with incomplete information (II-MAIDs), has a strong theoretical connection to dynamic games with incomplete information with no common prior over types. We prove the existence of important equilibria concepts in these frameworks, and illustrate the applicability of II-MAIDs using an example from the AI safety literature.

---

## 论文详细总结（自动生成）

# AI代理心智理论的因果模型（II-MAIDs）中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：人工智能代理的“代理性”（agency）是理解和预测其行为的关键概念。现有研究主要关注单代理环境中的目标导向性，但实际场景中自主代理需要与其他代理和人类交互，这要求代理具备“心智理论”（Theory-of-Mind, ToM）——即推理他人信念和意图的能力。AI安全、多代理协同等领域的现实问题往往涉及代理间不一致、甚至错误的信念，而现有框架如多智能体影响图（MAIDs）假设所有代理共享相同的正确信念，无法建模这种复杂情况。
- **核心问题**：如何扩展MAIDs，使其能够显式建模代理的主观信念、高阶信念（信念关于信念），从而刻画更真实的多代理交互，特别是涉及欺骗、误解等理论心智场景。
- **整体含义**：本文提出的不完全信息多智能体影响图（II-MAIDs）框架为建模代理间复杂的信念层次结构提供了严格的数学基础，并与动态不完全信息博弈（无共同先验）建立了理论等价性，为未来研究AI代理在不确定环境中的行为提供了工具。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将MAIDs推广到不完全信息设置，允许代理拥有不同且可能不一致的信念，并包含任意深度的信念层次。通过引入“主观MAID”集合，每个主观MAID包含一个基础MAID以及每个代理在该主观MAID下的先验分布（即代理对该集合中其他主观MAID的概率赋值）。客观模型是集合中的一个特殊元素。
- **关键技术细节**：
  - **II-MAID定义**：形式化为四元组 \( S = (N, S^*, S) \)，其中 \( N \) 是代理集合，\( S^* \) 是客观模型（正确的世界），\( S \) 是主观MAID集合。每个主观 MAID \( S = (M_S, (P^i_S)_{i \in N}) \)，\( P^i_S \) 是代理 \( i \) 在 \( S \) 下的先验，且需满足**一致性条件**（coherency condition）：代理 \( i \) 知道自己的先验，因此只赋予与自己先验一致的主观MAID概率1。
  - **信息集与策略**：代理在决策时基于观察到的父节点值域和动作集构成信息集。策略定义在每个信息集上，指定动作的条件概率分布。期望效用的计算考虑代理自己的先验对所有可能主观MAID的加权平均。
  - **与不完全信息扩展式博弈（II-EFG）的联系**：定义了**元信息集**（meta-information sets），结合了动作集、观察以及代理的信念（类型）。证明了在完美回忆和有限假设下，II-EFG存在纳什均衡（定理16）和贝叶斯均衡（定理18）。通过构造转换函数 `maid2efgII` 和 `efg2maidII`，证明了II-MAID与II-EFG在中间阶段等价（定理20），从而II-MAID同样存在纳什均衡（定理21）。

## 3. 实验设计

- **本文为纯理论工作，未进行任何实验**。文中明确说明：“We did not run any experiments.”（见论文实验可重复性部分）。因此没有使用数据集、基准方法或对比实验。
- **示例说明**：文中使用了一个AI安全情景作为运行示例：人类评估AI的诚实性（图1a）或危险能力（图1b），而AI可能错误地认为自己在接受另一种评估。该示例用于直观展示II-MAID如何建模不一致信念。

## 4. 资源与算力

- **未涉及**：论文未提及任何计算资源、GPU型号、训练时长等信息。由于没有实验，算力消耗不适用。

## 5. 实验数量与充分性

- **无实验**：因此无法评估实验数量或充分性。论文所有结论均基于数学证明和理论推导。

## 6. 论文的主要结论与发现

- II-MAIDs框架能够显式建模代理的主观信念和高阶信念（如信念关于信念），且不要求共同先验，比传统MAIDs更适用于现实中的错误信念场景。
- II-MAIDs与动态不完全信息博弈（II-EFGs）在中间阶段是等价的，通过构造变换可相互转化，且保持策略和期望效用。
- 在完美回忆、有限状态集和有限动作集的假设下，II-MAIDs存在纳什均衡（行为策略）。
- 然而，纳什均衡在II-MAID中可能不是合理的解概念，因为代理基于错误信念行动，可能实际无法发现均衡。文中指出需要更合适的解概念（如考虑每个信念层次上的最优反应）。
- 局限性：缺乏有用的解概念；纳什均衡存在但代理通常无法识别。

## 7. 优点

- **理论创新**：首次将MAIDs扩展到不完全信息且无共同先验的设置，填补了现有因果博弈框架在建模心智理论方面的空白。
- **严格的数学基础**：定义了主观MAID集合、一致性条件、信息集、元信息集等概念，并证明了与II-EFG的等价性，保证了框架的理论牢固性。
- **紧凑表示**：基于MAIDs（比EFGs更紧凑）构建，便于表示因果依赖关系，尤其适用于AI安全中模拟欺骗、误解等场景。
- **开放性问题明确**：诚实地指出了目前缺乏可用解概念这一局限，为未来工作指明了方向。

## 8. 不足与局限

- **缺乏实验验证**：纯理论工作，未在具体任务或环境中测试框架的有效性或可操作性。
- **解概念不完善**：纳什均衡存在但无法被代理理性地发现，需要进一步定义符合心智理论直觉的解概念（如涉及代理对其他代理策略的信念）。
- **假设条件**：定理推导依赖完美回忆、有限状态集和有限动作集等假设，可能限制在连续或大规模场景中的应用。
- **未提供算法实现**：尽管定义了策略映射，但未给出求解或近似求解II-MAID的方法。
- **示例简单**：仅用双代理、二值变量的情景说明，未展示扩展到更多代理或更复杂信念层次时的计算复杂性或表征能力。

（完）
