---
title: "Multi-agent KTO: Enhancing Strategic Interactions of Large Language Model in Language Game"
title_zh: 多智能体KTO：增强大型语言模型在语言游戏中的战略互动
authors: "Rong Ye, Yongxin Zhang, Yikai Zhang, Haoyu Kuang, peng sun, zhongyu wei"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=WPHpBnKvdq"
tags: ["query:player-ai"]
score: 9.0
evidence: LLM代理在狼人杀语言游戏中增强战略互动
tldr: 本文以狼人杀语言游戏为测试平台，提出了多智能体KTO（MaKTO）框架。通过让多种模型进行大量游戏，生成未配对的理想和非理想回应，然后利用KTO优化模型。该方法使语言代理能够在上下文中学习，而不是传统分离决策与表达的框架，从而增强战略互动和语言理解能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wphpbnkvdq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1139, \"height\": 713, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wphpbnkvdq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1421, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wphpbnkvdq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 632, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wphpbnkvdq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1051, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wphpbnkvdq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1162, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wphpbnkvdq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 330, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wphpbnkvdq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 719, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wphpbnkvdq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1450, \"height\": 405, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 616, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 882, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 666, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1301, \"height\": 519, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 836, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 727, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 727, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1439, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1432, \"height\": 1508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1379, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1444, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1322, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1035, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1040, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1040, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wphpbnkvdq/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1257, \"height\": 287, \"label\": \"Table\"}]"
motivation: 实现AGI需要智能代理不仅能做出战略决策，还能进行灵活有意义的交流。
method: 以狼人杀游戏为环境，提出MaKTO框架，通过游戏生成回应并用KTO优化。
result: 模型在战略互动和语言理解方面得到提升。
conclusion: 语言代理可以通过上下文互动学习，无需分离决策与表达。
---

## Abstract
Achieving Artificial General Intelligence (AGI) requires AI agents that can not only make strategic decisions but also engage in flexible and meaningful communication. Inspired by Wittgenstein's language game theory, we propose that language agents can learn through in-context interaction rather than traditional multi-stage frameworks that separate decision-making from language expression. Using Werewolf, a social deduction game that tests language understanding, strategic interaction, and adaptability, as a test bed, we develop the Multi-agent Kahneman-Tversky's Optimization (MaKTO). MaKTO engages diverse models in extensive gameplay to generate unpaired desirable and unacceptable responses, then employs KTO to refine the model's decision-making process. In 9-player Werewolf games, MaKTO achieves a 61% average win rate across various models, outperforming GPT-4o and two-stage RL agents by relative improvements of 23.0% and 10.9%, respectively. Notably, MaKTO also demonstrates human-like performance, winning 60% against expert players and showing only 48.9% detectability in Turing-style blind tests. Code and data are available at project page https://reneeye.github.io/MaKTO.html.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：实现通用人工智能（AGI）需要智能代理同时具备战略决策和灵活交流能力。传统方法将语言处理与决策分离，例如先由策略网络生成意图，再由语言模型生成表达，这种多阶段框架限制了跨环境迁移和泛化。
- **理论背景**：受维特根斯坦后期语言游戏理论（《哲学研究》）启发——意义产生于语言与非语言互动，而非语言到逻辑事实的简单映射。因此，语言代理应通过上下文互动学习，而非分阶段处理。
- **测试环境**：选择狼人杀（Werewolf）这类社交推理游戏，因其融合语言理解、战略互动和适应性，且具备可量化的完成率和胜率指标。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 核心思想
提出 **Multi-agent KTO (MaKTO)**，一种通过多智能体互动优化语言模型战略推理的方法。无需配对偏好数据，利用游戏规则和他人反馈收集理想/不可接受回应，再用KTO进行偏好优化。

### 2.2 关键技术细节（两阶段训练）

#### 阶段一：行为克隆（Behavior Cloning）
- **数据来源**：17位资深玩家（千场以上经验）标注的331场游戏记录，包含夜间行动、日间发言、投票及每步决策背后的思维链（Chain-of-Thought）。
- **指令数据集**：三类数据：
  - 基础游戏理解：术语和黑话解释（如“金水”）。
  - 高级技巧：来自玩家策略指南。
  - 真实游戏行为：结构化“先想后说”格式（行动前输出理由，发言前列出身份标签和投票意图等）。
- **辅助任务**：每天结束时预测所有玩家身份。

#### 阶段二：多智能体KTO
- **KTO算法**（Kahneman-Tversky Optimization）：
  - 损失函数：
    ```
    r_θ(x,y) = log(π_θ(y|x)/π_ref(y|x))
    z0 = E(x,y)~D[ KL(π_θ(y|x) || π_ref(y|x)) ]
    v(x,y) = { λ_D σ(β(r_θ - z0)) if y desirable; λ_U σ(β(z0 - r_θ)) if y undesirable }
    L(π_θ; D) = E[ λ_y - v(x,y) ]
    ```
  - 超参数：λ_D=0.7, λ_U=1.0。
- **多智能体玩游戏**：使用多样模型池（GPT-4o, Claude-3.5, SFT模型, Mix agent等）随机分配角色，生成交互数据，避免自玩导致的策略僵化。
- **逐步偏好数据选择**（非简单胜负）：
  - 启发式规则：如狼人首夜进攻特殊角色为理想，放弃进攻为不可接受；投票时村民集体投狼为理想。
  - 阶段性投票规则：根据投票结果评价发言质量（如被投出玩家发言差）。
  - 验证器规则：用GPT-4o等强LLM检查发言与事实一致性，减少幻觉。

## 3. 实验设计

### 3.1 数据集与环境
- **训练数据**：331场专家标注的狼人杀游戏（278场9人局，53场7人局），覆盖预言家、女巫、守卫、猎人等角色。总发言超54万token，行动2698次，投票3875次。
- **测试数据**：51场独立专家游戏用于离线评估（484个投票事件，5130个身份预测）。
- **默认环境**：9人标准局（3狼，6村民含预言家、女巫、守卫）。

### 3.2 对比方法（Benchmark）
- **API模型**：GPT-4o、GPT-4o-mini、Claude-3.5-Sonnet（带思维链提示）。
- **Mix agent**：采用Cicero-like方法，用AlphaStar式多智能体强化学习训练策略网络（结构化输入），再用LLM（GPT-4o）生成表达。
- **SFT模型**：基于Qwen2.5-14b-instruct和72b-instruct的监督微调模型。
- **推理模型**：DeepSeek-R1-Distill-Qwen-14B/70B。
- **消融变体**：自玩KTO、无玩游戏（仅从标注数据选偏好）、轨迹级选择、仅理想数据SFT等。

### 3.3 实验类型与数量
- **头对头锦标赛**：100场（每方各50场），完整胜率矩阵。
- **随机锦标赛**：260场，计算TrueSkill评分。
- **人类-AI比赛**：头对头20场、随机30场，共14位千场以上人类玩家参与。
- **Turing测试**：强制要求人类玩家判断每位参与者是否为AI。
- **行为分析**：50场细粒度指标对比（投票正确率、守卫保护神职率等）。
- **泛化测试**：
  - 新角色：猎人替代守卫（Seer-Witch-Hunter局）。
  - 更大规模：10人局（两种配置）、12人局。
- **消融实验**：自玩vs多智能体、逐步vs轨迹选择、各组件贡献、与推理模型对比、仅理想数据SFT对比。
- **统计检验**：Chi-square检验，p<0.05。

## 4. 资源与算力

- 论文在Appendix E中明确说明：
  - **SFT阶段**：使用DeepSpeed ZeRO-3，学习率1e-6，warm-up ratio 0.05，训练3 epochs。
  - **KTO阶段**：20k偏好数据（12k理想 + 8k不可接受），batch size 2 per device，150 warmup steps，训练20 epochs。
  - **硬件**：14B模型使用8张A100 GPU；72B模型使用32张A100 GPU。
  - **基座模型**：Qwen2.5-14b-instruct和Qwen2.5-72b-instruct（因中文语境更优）。

## 5. 实验数量与充分性

- **实验覆盖充分**：包括多种对抗形式（AI-AI、人类-AI）、多种评估维度（胜率、行为、可检测性、泛化、消融）。
- **控制变量严谨**：头对头比赛控制阵营；消融实验控制数据量（20k）、模型尺寸（14B）；使用统计显著性检验。
- **公平性考量**：
  - 对比了同尺寸推理模型（DeepSeek-R1-Distill）。
  - 对比了不同基座（Qwen vs Llama）。
  - 测试了未见过的游戏规模和角色，评估泛化而非过拟合。
- **结论可靠**：多次重复、统计检验、多维度验证支持主要结论。

## 6. 论文的主要结论与发现

- **核心结果**：MaKTO-72b在9人局平均胜率61%，相对GPT-4o提升23.0%，相对Mix agent（强RL基线）提升10.9%。
- **人类表现**：对人类专家胜率60%（Head-to-head）；Turing检测准确率仅48.9%（低于随机），成功模仿人类风格。
- **行为分析**：MaKTO在所有细粒度指标（如投票准确率、首夜施救率、正确毒杀率）上显著优于SFT。
- **泛化能力**：在未见过的猎人角色及10/12人局中仍保持最高胜率，显示学习到可迁移策略而非过拟合。
- **消融结论**：
  - 多智能体玩优于自玩（平均胜率高4%）。
  - 逐步偏好选择优于轨迹选择（平均胜率高8.7%）。
  - 行为克隆贡献30.6%提升，KTO额外贡献8.7%。
- **与推理模型对比**：MaKTO-14B对DeepSeek-R1-Distill-14B胜率74%，MaKTO-72B对R1-Distill-70B胜率84%，显示长思维链模型在社交推理游戏中表现不佳。

## 7. 优点

- **方法创新**：首次将KTO应用于多智能体语言游戏，利用其无需配对数据的特性适应“单次尝试”场景；通过多智能体模型池而非自玩提高策略多样性。
- **数据质量高**：收集了带有思维链的专家数据，使模型学到“先想后说”的推理过程，而非简单模仿。
- **偏好选择精细**：逐步选择（非整轨迹）更符合游戏特点（单个非理性行动不影响胜负）。
- **实验全面且具说服力**：
  - 包括人类真实对比和Turing测试，验证类人性。
  - 泛化测试证明方法学到的策略可迁移。
  - 消融实验清晰量化各组件贡献。
- **开源促进复现**：代码和数据集已公开。

## 8. 不足与局限

- **角色个性缺失**：为公平对比，未添加不同角色个性，模型仅给出理性决策而非个性化风格。
- **通信模式局限**：基于轮流发言，非自由交互环境，与真实人类自然对话有差距。
- **长文本不一致**：在长对话中可能出现行为不一致和幻觉，长上下文建模能力有待提升。
- **方法论上限**：论文指出在线多智能体RL理论上可能更优，但当前KTO作为便捷有效方案仍有改进空间。
- **环境局限**：虽可推广到其他社交推理游戏，但当前仅在狼人杀环境下验证。
- **算力成本**：72B模型需32块A100 GPU训练20 epochs，对资源要求较高。

（完）
