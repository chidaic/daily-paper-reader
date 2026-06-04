---
title: "CEDAR: A Counter-Example Driven Agent with Regular Restriction"
title_zh: CEDAR：基于反例驱动与正则约束的Agent框架
authors: "Lekai Chen, Alvaro Velasquez, Ashutosh Trivedi"
date: 2025-05-11
pdf: "https://openreview.net/pdf?id=IyMoawG676"
tags: ["query:player-ai"]
score: 8.0
evidence: 在Minecraft中通过DFA学习和LLM驱动Agent完成任务
tldr: 本文提出CEDAR方法，让Agent在Minecraft环境中通过大语言模型和人类提供的反例学习确定性有限自动机（DFA）表示的非正式规范，进而习得所需技能。该方法同时支持目标完成和终身学习，实验表明Cedar能有效将语言描述转化为可执行技能，为开放世界游戏中的AI Agent训练提供新途径。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-iymoawg676/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iymoawg676/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1320, \"height\": 1075, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iymoawg676/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iymoawg676/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1450, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iymoawg676/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iymoawg676/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 985, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iymoawg676/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1461, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iymoawg676/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1399, \"height\": 871, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-iymoawg676/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iymoawg676/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iymoawg676/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1209, \"height\": 109, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iymoawg676/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 748, \"height\": 734, \"label\": \"Table\"}]"
motivation: 在开放环境如Minecraft中，Agent需要从非正式规范中学习技能。
method: 利用LLM和人类反例构建DFA表示规范，并通过被动/主动学习算法习得技能。
result: CEDAR成功在Minecraft中完成多种目标并实现终身学习。
conclusion: 为游戏环境中Agent规范学习提供了一种有效框架。
---

## Abstract
We introduce CEDAR, a Counter-Example Driven Agent with Regular Restrictions in Minecraft, which learns and encodes informal specifications and skills as regular languages.
Our formalizer constructs deterministic finite automata (DFAs) to represent informal specifications by utilizing membership query responses from a Large Language Model (LLM) and counterexamples provided by a human. 
The DFA alphabet is derived from a global set of environmental events, with words in the language representing expected event sequences. 
These learned DFAs are then used by CEDAR's skill learner to acquire the necessary skills to fulfill the specifications. 
CEDAR supports both goal completion and lifelong learning by leveraging passive and active DFA learning algorithms, respectively. 
The DFAs for skills are refined through counterexamples generated from DFA simulations in the real environment. 
Skills acquired by CEDAR can be adapted to new scenarios by modifying the alphabet and can be logically verified to ensure they meet expected properties. 
Empirical evaluations demonstrate that CEDAR surpasses state-of-the-art methods in controllability, robustness, and extensibility.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在开放世界环境（如 Minecraft）中，基于大语言模型（LLM）的Agent在控制与规划方面取得了显著成功，但现有方法难以确保LLM生成的执行策略完全理解并遵循人类的非正式规范（如自然语言指令），可能导致意外甚至有害的结果。如何将人类规范与Agent行为对齐，并实现可逻辑验证的技能学习，是本文的核心问题。
- **背景**：当前LLM Agent（如Voyager）在复杂任务中依赖提示词和反馈，但缺乏对规范的形式化表示与验证机制。自动机学习（特别是DFA学习）为从示例中学习正则语言提供了理论基础，而LLM可以作为自然语言到形式语言的桥梁。本文结合两者，提出一种基于反例驱动的Agent框架CEDAR。

## 2. 方法论

### 核心思想
- 将人类非正式规范（自然语言）和目标技能表示为确定性有限自动机（DFA），通过LLM和人类提供的反例进行迭代学习与验证。技能DFA作为Agent的策略，通过模拟环境中的反例进行优化。
- 支持目标完成（被动学习）和终身学习（主动学习）两种模式。

### 关键技术细节
- **字母表定义**：全局字母表由控制原语、游戏对象和事件组成。通过RAG（检索增强生成）系统从全局字母表中检索与任务最相关的符号，构建子字母表。
- **DFA学习者**：
  - **被动学习（RPNI-EDSM）**：用于目标完成，LLM提供正负例，被动构建DFA，然后在包装环境中模拟，收集反例并迭代优化。
  - **主动学习（LAPR算法）**：用于终身学习，LLM作为成员查询（MQ） oracle，环境作为等价查询（EQ） oracle，通过交互不断细化DFA。
- **技能管理器**：技能存储为元组 `<A, v, n, E, D>`，其中A是DFA，v是动词，n是对象，E是事件集，D是示例集。可通过修改字母表实现技能泛化（替换名词对应的符号）。
- **验证器**：将自然语言规范通过主动学习（LLM做MQ，人类做EQ）形式化为DFA，然后与技能DFA进行交集或串联操作，检查一致性并生成新技能。交集操作用于确保技能符合规范，串联操作用于组合技能。

### 算法流程（文字说明）
1. 给定自然语言规范，通过RAG得到子字母表。
2. 利用LLM和人类反例学习规范DFA（主动学习）。
3. 对每个技能任务，使用LLM生成正负例，通过被动或主动学习构建技能DFA。
4. 在真实环境中模拟技能DFA，若未达成目标或违反规范则获取反例，重新学习DFA。
5. 技能经检验后存入管理器，可泛化到新任务（修改字母表）。
6. 验证器检查技能DFA与规范DFA是否一致，若不一致则交集合并或提供反例。

## 3. 实验设计

- **场景**：Minecraft游戏环境（Mineflayer API）。
- **Benchmark**：主要对比Voyager（当前最先进的Minecraft LLM Agent）。
- **对比方法**：
  - Voyager（有/无技能库）
  - CEDAR（有/无技能库）
- **实验类型**：
  1. **人类规范遵循实验**：如“晚上睡觉”、“只在夜间采矿”、“限定在windswept_forest生物群系”等，测量动作计数、健康值、物品收集分布。
  2. **目标完成性能**：木镐、铁镐、钻石镐、岩浆桶、指南针等物品的合成任务，记录提示迭代次数和成功率。
  3. **终身学习效率**：比较技能学习迭代次数。
  4. **技能泛化测试**：将已学技能通过修改字母表用于新任务。
  5. **RAG性能评估**：在44个技能DFA上测试字母表检索的准确性（绝对准确率、重叠系数、余弦相似度）。
  6. **反例发现成功率**：随机注入错误后模拟，统计反例收集概率。

## 4. 资源与算力

- **未明确说明使用的GPU型号、数量或训练时长**。文中提到所有LLM交互通过OpenAI API完成（gpt-4o用于任务分解和成员查询，gpt-4o-mini用于JSON翻译，text-embedding-3-large用于文本嵌入），因此无需本地GPU资源。作者指出受限于API调用成本，未能进行更多次实验。

## 5. 实验数量与充分性

- **实验数量**：
  - 人类规范遵循实验：每种指令重复5次，每次持续3天（游戏内时间）。
  - 目标完成性能：每个任务重复5次，统计成功率。
  - RAG性能评估：在44个技能DFA上测试。
  - 反例成功率：每个物品模拟110次实验。
- **充分性评价**：
  - 实验设计覆盖了主要声称的优势（可控性、鲁棒性、可扩展性），但样本量较小（5次重复），在Minecraft随机世界生成下具有一定说服力，但统计显著性有限。
  - 消融实验不足：未单独验证RAG、被动/主动学习、验证器各模块的贡献，也未对LLM版本或超参数进行系统分析。
  - 对比方法单一（仅Voyager），缺乏与其他基于DFA或形式化方法的对比。
  - 总体而言，实验初步验证了方法的有效性，但充分性和泛化性有待加强。

## 6. 主要结论与发现

- CEDAR在遵循人类规范（如晚上睡觉、限定时间段采矿、限定生物群系）方面显著优于Voyager，能保持更高健康值、更有效的资源收集。
- 在目标完成任务中，CEDAR在使用已学技能时效率高（仅需一次LLM查询），但对于新任务，由于需要环境反例迭代，提示次数略多于Voyager无技能库的情况。
- CEDAR的技能泛化能力强，通过修改字母表可快速适应新对象。
- RAG系统在字母表检索上表现良好（绝对准确率0.9372，重叠系数0.9208）。
- 反例发现成功率平均0.9358，且大部分反例长度较短，易于收集。

## 7. 优点

- **形式化保证**：将规范表示为DFA，可进行逻辑验证和交集/串联操作，确保Agent行为与人类意图对齐，提升了可解释性和可靠性。
- **反例驱动迭代**：利用真实环境和人类反馈获取反例，不断优化DFA，避免LLM幻觉积累。
- **终身学习与泛化**：主动学习支持持续改进，通过修改字母表实现技能迁移，无需从头学习。
- **LLM与自动机学习结合**：充分利用LLM的自然语言理解能力作为oracle，同时利用自动机学习的结构优势，降低了对完美LLM的依赖。
- **人机协作**：人类仅需提供反例（简单可行），无需参与复杂的成员查询，降低了标注负担。

## 8. 不足与局限

- **自然语言歧义问题**：假设人类能正确判断反例，但在语义模糊时可能出错。
- **LLM残余幻觉**：即使采用噪声容忍算法，当人类与LLM共同误解时，规范DFA可能仍不正确。
- **实验规模有限**：每组实验仅5次重复，统计稳定性不足；未在更多不同环境或任务上验证。
- **缺乏消融实验**：未分析各模块（RAG、主动/被动学习、验证器）的独立贡献。
- **计算代价**：需要多次LLM查询和环境模拟，成本较高；未讨论时间效率或扩展性。
- **应用限制**：目前仅针对Minecraft环境，字母表定义依赖游戏API，迁移到其他开放世界需重新设计。

（完）
