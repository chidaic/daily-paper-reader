---
title: "Securing Equal Share: A Principled Approach for Learning Multiplayer Symmetric Games"
title_zh: 确保均分收益：多人对称博弈学习的原则性方法
authors: "Jiawei Ge, Yuanhao Wang, Wenzhe Li, Chi Jin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=rCxB0tVHp1"
tags: ["query:player-ai"]
score: 8.0
evidence: 面向AI智能体的多人对称博弈学习
tldr: 该论文针对多人博弈中均衡非唯一且可被利用的问题，提出以“均分收益”为目标的学习算法，为麻将、扑克等游戏的AI智能体提供了有理论保证的均衡选择方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-rcxb0tvhp1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rcxb0tvhp1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 863, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rcxb0tvhp1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 172, \"label\": \"Table\"}]"
motivation: 多人博弈中均衡不唯一且不可利用，缺乏合理的训练目标。
method: 以均分收益为目标，设计算法在多人博弈中学习稳健策略。
result: 在多人博弈中训练的智能体能获得接近理论均分的收益。
conclusion: 均分目标为多人博弈AI训练提供了理论依据和实用方法。
---

## Abstract
This paper examines multiplayer symmetric constant-sum games with more than two players in a competitive setting, such as Mahjong, Poker, and various board and video games. In contrast to two-player zero-sum games, equilibria in multiplayer games are neither unique nor non-exploitable, failing to provide meaningful guarantees when competing against opponents who play different equilibria or non-equilibrium strategies. This gives rise to a series of long-lasting fundamental questions in multiplayer games regarding suitable objectives, solution concepts, and principled algorithms. This paper takes an initial step towards addressing these challenges by focusing on the natural objective of *equal share*—securing an expected payoff of $C/n$ in an $n$-player symmetric game with a total payoff of $C$. We rigorously identify the theoretical conditions under which achieving an equal share is tractable and design a series of efficient algorithms, inspired by no-regret learning, that *provably* attain approximate equal share across various settings. Furthermore, we provide complementary lower bounds that justify the sharpness of our theoretical results. Our experimental results highlight worst-case scenarios where meta-algorithms from prior state-of-the-art systems for multiplayer games fail to secure an equal share, while our algorithm succeeds, demonstrating the effectiveness of our approach.

---

## 论文详细总结（自动生成）

# 论文总结：《Securing Equal Share: A Principled Approach for Learning Multiplayer Symmetric Games》

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：多人对称常和博弈（如麻将、扑克、外交等）中，纳什均衡等传统解概念存在**非唯一性**和**可被利用性**，导致无法为学习主体提供有意义的收益保障。玩家面对不同均衡或非均衡对手时，无法确保获得公平份额（equal share，即总收益为C时获得C/n的期望 payoff）。
- **研究背景**：现有超人类AI系统（如Suphx、Pluribus、Cicero）大多依赖自对弈（self-play）或行为克隆等元算法，但缺乏理论支撑，且可能在最坏情况下无法保证均分收益。该文旨在系统性地回答两个问题：
  - 多人博弈中**合适的解概念**是什么？
  - 什么样的**原则性算法**能保证学习均分收益？
- **整体含义**：该文首次从“确保均分收益”这一自然目标出发，识别了实现该目标所需的结构条件（对手使用相同策略、有限适应性），并设计了基于无遗憾学习的高效算法，为多人博弈的AI训练提供了理论保证和实用工具。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：
  - 放弃传统Nash/CCE/CE，转向 **min_x max_x1 U1(x1, x^{\otimes n-1})** 这一解概念，对应条件：所有对手使用相同元策略（meta-strategy），且对手适应性有限，学习者需建模对手。
  - 利用无遗憾（no-regret）和无动态遗憾（no-dynamic-regret）学习工具，在不同对手设定下逼近均分收益。
- **关键技术细节**：
  - **固定对手**：使用Hedge算法，保证平均收益至少为 `0 - O(√(log(A/δ)/T))`。
  - **缓慢适应对手**：假设总变差预算 VT，使用强自适应在线学习器（Strongly Adaptive Online Learner with Hedge，SAOL_H），保证动态遗憾界 `O(V_T^{1/3} T^{-1/3} (√(log(A/δ)) + log T))`。
  - **中等速率适应对手**：行为克隆（Behavior Cloning），直接模仿上一轮对手的动作，保证平均收益至少为 `-O(V_T/T)`。
  - 补充了匹配的下界（Theorem 5.4, 5.5），证明上述算法在 worst-case 下是最优的（除对数因子）。
- **算法流程简述**：
  - **Hedge**：每轮根据观察到的对手动作更新策略权重，指数梯度上升。
  - **SAOL_H**：在多个时间区间上并行运行Hedge，自适应地选择区间并调整权值。
  - **行为克隆**：第一轮随机行动，此后重复对手的上一个动作。

## 3. 实验设计

- **使用的游戏场景**：
  - **Majority Vote (MV)**：3人多数投票游戏，动作{0,1}，多数得正收益，少数得负，全体一致得0。固定对手元策略 `ymeta = [0.49, 0.51]`。
  - **Switch Dominance Game (SDG)**：n=30人，动作{A,B,C}，根据选择A的人数切换支配关系（B≻A≻C 或 C≻B≻A），收益设计保证对称零和。固定对手元策略 `ymeta = [0.399, 0.6, 0.001]`。
- **Benchmark / 对比方法**：
  - **自对弈从头训练（SP scratch）**：Brown & Sandholm (2019) 风格。
  - **自对弈+行为克隆初始化（SP BC）**：Li et al. (2020) 风格。
  - **自对弈+行为克隆初始化+正则化（SP BC reg）**：Jacob et al. (2022) 风格。
  - **本文原则性算法（Hedge）**：直接对抗元策略运行Hedge。
- **评价指标**：
  - **Utility**：学习者收敛策略对固定元策略的期望收益（Monte Carlo评估，3×10^5局，10次运行，报告均值和标准差）。
  - **Exploitability**：最佳剥削者（100次内寻找最优反策略）下学习者的收益。

## 4. 资源与算力

- 论文中**未明确说明**训练所使用的具体GPU型号、数量或训练时长。仅在附录D提到实验在一台具有256个CPU的服务器上进行，每个实验可在几分钟内完成。因此，算力消耗较小，属于轻量级验证。

## 5. 实验数量与充分性

- **实验数量**：
  - 两个游戏（MV和SDG）各对比四种算法（SP scratch, SP BC, SP BC reg, Hedge）。
  - 对每种算法，报告了收敛策略的分布（MV中6种不同正则化强度的SP BC reg + Hedge；SDG中未展示分布但说所有自对弈变体收敛到同一策略）。
  - 最终给出了utility和exploitability的两张表格（表1、表2）。
- **充分性评价**：
  - 实验覆盖了固定对手这一最简单设定，验证了理论中识别的“自对弈失败模式”（多均衡吸引、单均衡负收益）。
  - 但缺少对**自适应对手**场景的模拟实验，也未涉及大规模动作空间或扩展式博弈。
  - 整体上实验设计简洁，针对性强，但广度有限。公平性方面，所有算法使用相同的Hedge优化器，超参数按理论最优选择，对比较为客观。

## 6. 主要结论与发现

- **理论结论**：
  - 若对手策略不同或对抗性变化，学习者无法保证均分收益（Proposition 4.1, 4.2）。
  - 在对手相同且有限适应（变差预算）下，无动态遗憾算法可逼近均分收益，行为克隆在中速适应区间最优。
  - 给出了匹配下界，表明算法几乎最优。
- **实验结论**：
  - 所有自对弈元算法（SP scratch, SP BC, SP BC reg）在worst-case下均会收敛到负收益策略，无法保证均分收益。
  - 本文的Hedge算法始终获得正收益（在MV中约1.03×10^{-2}，在SDG中约1.00），显著优于自对弈方法。
  - 所有学习策略均可被对手利用（exploitability均为负值），符合理论预测。
- **总体发现**：均分收益是多人对称博弈中一种可行的、有理论保证的目标，原则性算法比现有自对弈元算法更可靠。

## 7. 优点

- **理论创新**：首次对多人博弈中的“均分收益”目标进行系统性理论分析，识别了必要且充分的结构条件，并给出了算法和匹配下界。
- **原则性方法**：脱离了经验性的自对弈框架，提供了基于无遗憾学习的简单可证明算法。
- **实验设计清晰**：针对识别的失败模式设计了两个简单但具有代表性的游戏，有效地展示了自对弈的不足和本算法的优势。
- **连接实践**：论证了所提条件（对手相同、有限适应）在大型玩家群平台中自然成立，增强了方法的实用性。
- **消融与对比公平**：使用统一的Hedge优化器，并控制初始化（理想化行为克隆），避免了工程实现偏差。

## 8. 不足与局限

- **实验覆盖不足**：
  - 仅测试了固定对手场景（stationary opponents），未验证自适应对手（VT>0）下的算法性能。
  - 仅使用两个简单的小动作空间游戏（2或3个动作），缺乏对大规模动作空间或扩展式博弈（如真正麻将、扑克）的验证。
  - 未进行消融实验（如不同学习率、正则化强度的影响）。
- **偏差风险**：
  - 实验假设学习者已经完美知道对手的元策略（理想化行为克隆），这在实际系统中不现实，可能高估了本算法的相对优势。
  - 自对弈方法使用相同的学习率和优化器，可能未针对其最佳性能调优，导致对比偏向性。
- **应用限制**：
  - 对手必须使用相同元策略的假设在真实多玩家环境中不一定成立（尽管用大玩家数论证近似）。
  - 算法的收敛速度（O(1/√T) 或 O(V_T^{1/3} T^{-1/3})）对于长期训练可行，但短期内可能仍无法保证优势。
  - 未考虑部分可观测或信息不对称的博弈（如不完全信息扩展式博弈）。
- **理论方面**：算法基于无遗憾学习，但实际中需要完全已知收益函数U1，且只能从对手动作中获取梯度信息，在复杂游戏中手动构造特征可能困难。

（完）
