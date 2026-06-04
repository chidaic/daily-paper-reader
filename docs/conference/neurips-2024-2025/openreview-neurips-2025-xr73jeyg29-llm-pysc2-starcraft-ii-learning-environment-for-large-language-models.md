---
title: "LLM-PySC2: Starcraft II learning environment for Large Language Models"
title_zh: "LLM-PySC2: 面向大型语言模型的星际争霸II学习环境"
authors: "Zongyuan Li, Yanan Ni, Runnan Qi, Chang Lu, Lumin Jiang, Xu Xiaojie, Xiangbei Liu, Pengfei Li, Yunzheng Guo, Zhe Ma, Huanyu Li, wu hui, Guo Xian, Kuihua Huang, Xuebo Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Xr73jEYG29"
tags: ["query:player-ai"]
score: 9.0
evidence: 面向LLM的星际争霸II训练环境，支持AI agent训练
tldr: 星际争霸II平台尚未提供对大型语言模型（LLM）的原生支持。该论文提出LLM-PySC2环境，首次为LLM提供完整的pysc2动作空间和多模态接口，支持多智能体协作。该环境使得LLM能够直接参与星际争霸II游戏，为基于语言模型的游戏AI训练奠定了基础设施。实验表明LLM代理能在该环境中学习基本策略。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1288, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1278, \"height\": 952, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1282, \"height\": 701, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1292, \"height\": 888, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1375, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1377, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1333, \"height\": 1878, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1325, \"height\": 1893, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1346, \"height\": 1608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1303, \"height\": 1890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1325, \"height\": 1883, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1269, \"height\": 1975, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 662, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 659, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 659, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 662, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 658, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 663, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1326, \"height\": 1870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1284, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 664, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 666, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 661, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 661, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 661, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 661, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 608, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 604, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 610, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 608, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 611, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 612, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 618, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 605, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1368, \"height\": 912, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xr73jeyg29/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1366, \"height\": 918, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1462, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1431, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1450, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1431, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1554, \"height\": 606, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1548, \"height\": 1019, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1548, \"height\": 929, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1553, \"height\": 756, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1501, \"height\": 760, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1558, \"height\": 903, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1547, \"height\": 1163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1545, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1597, \"height\": 1741, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1596, \"height\": 1890, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1420, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1383, \"height\": 1420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1398, \"height\": 524, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1437, \"height\": 803, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1392, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xr73jeyg29/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1535, \"height\": 1894, \"label\": \"Table\"}]"
motivation: 现有游戏环境（如pysc2）不支持LLM的直接接口，限制了语言模型在复杂游戏中的应用。
method: 构建LLM-PySC2环境，封装pysc2的动作空间，并提供文本和视觉多模态输入，使LLM能驱动游戏代理。
result: 实验证明LLM代理能够在此环境中执行游戏动作并学习基本策略。
conclusion: 该工作填补了LLM与复杂游戏环境之间的桥梁，促进LLM在游戏AI领域的研究。
---

## Abstract
The tremendous potential has been demonstrated by large language models (LLMs) in intelligent decision-making problems, with unprecedented capabilities shown across diverse applications ranging from gaming AI systems to complex strategic planning frameworks. However, the StarCraft II platform, which has been widely adopted for validating decision-making algorithms in the past decade, has not yet provided substantial support for this emerging domain. To address issues that LLMs cannot interface with the hundreds of actions of the pysc2 backend and the lack of native support for multi-agent (MA) collaboration, we propose the LLM-PySC2 environment. This is the first environment that offers LLMs the complete pysc2 action space with sufficient multi-modal information and game Wiki knowledge. With an asynchronous query architecture, the environment efficiently interacts with LLMs that maintain a constant latency regardless of the scale of the agents' population. In the experiments, we evaluated LLMs' decision-making performance in both the macro-decision and micro-operation scenarios, with traditional StarCraft II Multi-Agent Challenge (SMAC) tasks and a series of new proposed. Results indicate that LLMs possess the potential to achieve victories in complex scenarios but cannot constantly generate correct decisions, especially in the recovered pysc2 action space and MA settings. Without task-relevant instructions, the pre-trained models suffer from issues such as hallucinations and inefficient collaboration. 
Our findings suggest that StarCraft II still challenges in the era of large models, revealing that there is a lot to do to develop an advanced LLM decision-making system, and the proposed LLM-PySC2 environment will support future development of LLM-based decision-making solutions.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：大型语言模型（LLM）在智能决策领域展现出巨大潜力，但星际争霸II（StarCraft II）这一经典决策验证平台却缺乏对LLM的原生支持。现有LLM星际环境（如Swarm Brain、TextStarCraft II）严重限制了动作空间（仅离散文本），丢失了pysc2后端数百种连续动作和多智能体协作能力，阻碍了LLM在复杂决策场景中的深入研究。
- **整体含义**：为了填补这一空白，论文提出了LLM-PySC2——首个为LLM提供完整pysc2动作空间、多模态观测和游戏Wiki知识的环境，并原生支持多智能体协作与异步查询架构，旨在推动LLM决策系统的发展，同时揭示当前LLM在复杂策略游戏中面临的挑战（如幻觉、知识缺乏、协作低效）。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将LLM作为决策智能体，通过文本接口与环境交互，使用完整的pysc2动作空间（而非离散化动作），并为每个智能体提供多模态观测（文本+图像+结构化的Wiki知识）。
- **关键技术细节**：
  - **动作接口**：定义`<ActionName(args)>`形式的文本动作，通过桥接对象（Bridge Object）将文本映射为pysc2函数序列，支持单元控制、技能、建造、研究等500+原始动作。
  - **多模态观测**：文本观测包括游戏信息、队伍单位、有效动作、上次行动、任务描述、相关Wiki知识；图像观测包括RGB屏幕、小地图、特征图，并附加辅助线和标注以辅助LLM理解坐标。
  - **多智能体系统**：支持集中式/分布式决策，智能体通过自然语言通信（`<MessageTo>`动作）协作。定义了指挥官（宏观决策）、开发者（经济/科技）、建造者（微观建造）、战斗组（微观操作）等角色。
  - **异步查询架构**：每个智能体独立线程查询LLM服务器，保证延迟不随智能体数量增长。
  - **两种简易模式**：Easy Build（简化建造）和Easy Control（简化控制），允许研究者聚焦于特定方面。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **实验场景**：
  - **宏观决策**：完整星际争霸II游戏（Simple64地图），包括三种模式：ECEB（Easy Control + Easy Build）、SCEB（Standard Control + Easy Build）、ECSB（Easy Control + Standard Build）。
  - **微观操作**：LLM-SMAC任务（传统SMAC场景，如2s3z、3s5z等）以及8个新设计的LLM-PySC2任务（要求使用单位技能，如2个幽灵渗透、3个凤凰骚扰、拦截空投、大型混合部队战斗等），每个任务分三个难度等级。
- **Benchmark**：以Kill/Death (KD)比率和胜率（Winning Rate, WR）作为评估指标。Vunit = minerals(unit) + 2×gas(unit)，KD = 总击杀价值/总阵亡价值。
- **对比方法**：
  - **宏观决策**：测试GPT-4o-mini在三种模式下的表现。
  - **微观操作**：对比了GPT-3.5-turbo、GPT-4o-mini、glm-4-plus、claude3-haiku、llama3.1-8b、llama3.1-70b、llama3.1-405b、gpt-4o、gpt-o1-mini共9个模型。
  - **附加对比**：在GPT-3.5-turbo上测试了三个难度级别，作为未来基线。

### 4. 资源与算力

- **硬件配置**：论文在附录D.1中给出了推荐和最低系统要求：推荐Windows 10/11、i9-14900 CPU（24核）、GeForce RTX 4090 24G、64GB RAM + 2TB SSD；最低要求Windows 10/11、8核CPU、GeForce GTX 1080、8GB RAM + 100GB SSD。
- **具体算力细节**：未明确说明训练时长或总的GPU小时数。实验使用远程LLM API（如GPT-4o-mini等），本地仅需运行环境代码，无需大规模训练。作者提到每个macro决策实验重复30次，micro实验重复20或50次，但未报告总计算成本或消耗的token数。

### 5. 实验数量与充分性

- **实验数量**：
  - 宏观决策：30次重复实验，涵盖7个难度级别，3种模式。但只使用了GPT-4o-mini一种模型。
  - 微观操作：LLM-SMAC任务每种模型20次（GPT-3.5-turbo为50次）；LLM-PySC2任务每种模型20次；难度级别测试仅使用GPT-3.5-turbo，每个级别20次。
- **充分性评估**：
  - **客观性**：使用Wilson Score置信区间评估胜率统计显著性（90% CI），处理了有限样本量的不确定性，较为严谨。
  - **公平性**：对比了多个主流模型（闭源和开源），涵盖不同大小（8B到405B）和不同公司，较为公平。
  - **不足**：宏观决策仅测试GPT-4o-mini，缺乏其他模型对比；微观任务中，部分模型（如gpt-o1-mini）在某些任务未完成全部测试（表格中显示“–”）。此外，实验较少涉及超参数调优或多次运行的平均方差报告（KD比率采用总和计算而非逐局平均）。总体而言，数量适中，但覆盖的模型和任务组合尚不够全面。

### 6. 论文的主要结论与发现

- **宏观决策**：在完整游戏中，ECEB模式下LLM最高在Level-5有约30%胜率，Level-6及以上几乎全败；SCEB和ECSB模式因动作空间恢复和多智能体协作要求，性能更差（ECSB在Level-4后胜率骤降）。表明LLM尚不能有效处理复杂游戏。
- **微观操作**：
  - LLM-SMAC任务中，所有模型表现糟糕（胜率极低），常见错误包括不移动远程单位、逃离战场等。
  - LLM-PySC2任务中，模型在简单任务（如任务3拦截空投）能达到100%胜率，但复杂任务（如任务4 Blink-Stalker战斗）胜率为0%。
  - **推理模型（如o1-mini）未显著提升决策能力**；**缩放定律在决策问题上不显著**（405B模型未明显优于70B模型）。
- **主要问题**：1) 缺乏领域知识（如不理解护盾回复、供给限制）；2) 幻觉（将友军误判为敌军、混淆坐标系统）；3) 协作低效（信息冗余、盲目信任队友）。
- **结论**：当前LLM虽具备零样本决策潜力，但无法持续做出有效决策；在复杂环境中学习必要的领域知识仍是未解决的问题。

### 7. 优点

- **环境设计创新**：第一个为LLM提供完整pysc2动作空间的环境，保留游戏原有的复杂性（500+动作、连续空间），避免过度简化。
- **多模态与知识融合**：同时提供文本、图像和结构化的游戏Wiki知识，有助于LLM利用先验知识。
- **原生多智能体支持**：内置自然语言通信机制和异步查询架构，支持集中式/分布式协作，且延迟不随智能体数量增长。
- **全面的评估体系**：包含宏观决策（完整游戏）和微观操作（传统SMAC+新任务），难度分档，并提供90% Wilson置信区间，统计严谨。
- **开源与复现**：代码已在匿名GitHub仓库公开，提供完整文档和快速启动脚本，有利于后续研究。

### 8. 不足与局限

- **实验局限性**：
  - 宏观决策仅测试了GPT-4o-mini，缺少其他模型对比，无法评估模型间差异。
  - 微观任务中部分模型（如o1-mini）未完成全部任务，导致结果不完整。
  - 未深入测试高级战术（如多线操作、隐形单位骚扰），由于LLM能力限制，环境对这些场景的鲁棒性验证不足。
  - 当前仅支持Protoss种族，Terran和Zerg尚未实现。
- **方法局限性**：
  - LLM的决策延迟较高（约5-6秒/查询），虽然环境侧延迟低，但整体实用性受限于LLM推理速度。
  - 未提出任何针对LLM的微调或强化学习训练方法，仅作为测评平台，未解决LLM的学习问题。
  - 多智能体通信中的幻觉和无效信息问题未提出解决方案。
- **偏差风险**：
  - 仅基于特定游戏环境（星际争霸II），结论推广到其他复杂决策任务时需谨慎。
  - 实验使用商业API模型，结果可能受版本更新、随机性影响，且无法完全复现。
  - 评估指标（KD、WR）未能反映决策质量（如战略合理性、资源效率等深层指标）。
- **应用限制**：环境依赖PySC2和StarCraft II客户端，部署复杂；LLM API费用较高，大规模实验成本大。

（完）
