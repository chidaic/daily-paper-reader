---
title: "Large Language Models Play StarCraft II:Benchmarks and A Chain of Summarization Approach"
title_zh: 大型语言模型玩星海争霸II：基准与一种链式摘要方法
authors: "Weiyu Ma, Qirui Mi, Yongcheng Zeng, Xue Yan, Runji Lin, Yuqiao Wu, Jun Wang, Haifeng Zhang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=kEPpD7yETM"
tags: ["query:player-ai"]
score: 9.0
evidence: 大型语言模型玩星海争霸II；直接针对实时策略游戏中AI智能体的基准
tldr: 本文构建了TextStarCraft II环境，用于评估大语言模型在实时战略决策中的能力。针对传统链式思维方法的不足，提出了链式摘要（CoS）方法，增强LLM在快速决策中的有效性。实验表明CoS在星海争霸II场景中显著提升了智能体的表现，为游戏AI研究提供了新基准和方法。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 800, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1415, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 649, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 677, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 671, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 683, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1177, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 646, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 670, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 672, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 670, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 669, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 681, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 680, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 680, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 678, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 682, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 679, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 681, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 680, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 679, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1473, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 631, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 628, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 629, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 630, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 626, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 629, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 630, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 632, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1428, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1448, \"height\": 817, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1393, \"height\": 829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1445, \"height\": 816, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1408, \"height\": 828, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1445, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1410, \"height\": 825, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-keppd7yetm/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1445, \"height\": 821, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-keppd7yetm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 555, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-keppd7yetm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1060, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-keppd7yetm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 923, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-keppd7yetm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1072, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-keppd7yetm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1296, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-keppd7yetm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1175, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-keppd7yetm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1044, \"height\": 344, \"label\": \"Table\"}]"
motivation: 现有基准缺乏对实时战略决策场景的评估，大语言模型在该领域的能力尚未明确。
method: 设计TextStarCraft II环境，并提出链式摘要（CoS）方法，改进LLM的推理与决策流程。
result: 实验证明CoS方法提升了LLM在星海争霸II中的决策效果。
conclusion: 为LLM在实时策略游戏中的应用提供了基准框架和有效方法。
---

## Abstract
With the continued advancement of Large Language Models (LLMs) Agents in reasoning, planning, and decision-making, benchmarks have become crucial in evaluating these skills. However, there is a notable gap in benchmarks for real-time strategic decision-making. StarCraft II (SC2), with its complex and dynamic nature, serves as an ideal setting for such evaluations. To this end, we have developed TextStarCraft II, a specialized environment for assessing LLMs in real-time strategic scenarios within SC2. Addressing the limitations of traditional Chain of Thought (CoT) methods, we introduce the Chain of Summarization (CoS) method, enhancing LLMs' capabilities in rapid and effective decision-making. Our key experiments included:
1. LLM Evaluation: Tested 10 LLMs in TextStarCraft II, most of them defeating LV5 build-in AI, showcasing effective strategy skills.
2. Commercial Model Knowledge: Evaluated four commercial  models on SC2 knowledge; GPT-4 ranked highest by Grandmaster-level experts.
3. Human-AI Matches: Experimental results showed that fine-tuned LLMs performed on par with Gold-level players in real-time matches, demonstrating comparable strategic abilities.

All code and data from this
study have been made pulicly available at https://github.com/histmeisah/Large-Language-Models-play-StarCraftII

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：大语言模型（LLM）在推理、规划和决策方面取得了显著进展，但现有基准（如AGENTBENCH）主要关注多轮对话或开放世界任务，缺乏专门针对**实时战略决策**和**长期规划**能力的评估环境。实时战略游戏（如《星际争霸II》，简称SC2）因其动态、复杂和分秒必争的特性，是评估LLM在这些能力上的理想测试床。
- **核心问题**：如何构建一个适合LLM的SC2交互环境，并设计一种方法克服传统思维链（Chain-of-Thought, CoT）在快速、实时决策中的局限性（高计算成本、推理慢）。
- **整体意义**：填补了LLM在实时策略游戏中评估和应用的空白，为研究LLM在复杂动态场景下的决策、规划与自适应能力提供了新的基准和方法。

## 2. 论文提出的方法论：核心思想、关键技术细节与算法流程

- **核心思想**：提出了**链式摘要（Chain of Summarization, CoS）** 方法，灵感来源于计算机硬件中的缓存机制和强化学习中的帧跳过技术。CoS旨在通过**信息压缩**、**推理加速**和**全局理解**来增强LLM的实时决策能力，是对传统CoT的改进和插件化扩展。
- **关键技术细节**：
  - **TextStarCraft II环境**：基于python-sc2框架，将复杂的游戏状态（资源、单位、建筑、敌方信息等）转换为文本形式的观察（Observation-to-Text），并通过文本命令执行宏观行动（Text-to-Action）；微观行动由预定义的规则脚本控制（类似OpenAI Five方式）。
  - **单帧摘要（Single-Frame Summarization）**：对每一帧原始游戏观察（密集文本）进行压缩和关键信息提取，可使用基于规则的方法（快速）或基于LLM的few-shot方法（更精准）。
  - **多帧摘要（Multi-Frame Summarization）**：将连续K帧的单一摘要聚合为一个周期摘要σ，使LLM能够分析时间序列趋势，避免每帧都调用LLM，从而大幅降低延迟。
  - **动作提取与动作队列**：LLM基于多帧摘要进行CoT推理，输出分析、建议和决策；通过正则表达式和相似度搜索从输出中提取K个具体动作（文字命令），放入动作队列，由环境依次执行（每帧一个动作）。
- **算法流程**（文字描述）：
  1. 初始化环境，获取初始观察o0，并初始化观察队列Qobs和动作队列Qaction。
  2. 将o0重复K次填入Qobs（填充队列）。
  3. 当游戏未结束时循环：
     - 如果Qobs长度达到K，则对队列中每个观察执行单帧摘要（SSF），得到单帧摘要队列QSF。
     - 对QSF执行多帧摘要（SMF），生成周期摘要σ。
     - 对σ应用CoT推理，得到输出υ。
     - 从υ中提取K个动作（a1, a2, ..., aK）并填入Qaction。
     - 从Qaction取出下一个动作at，执行并获取奖励rt和下一观察ot+1。
     - 将ot+1加入Qobs，更新总奖励R。
  4. 循环直到游戏终止。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **环境与基准**：**TextStarCraft II** 作为测试环境，对手为游戏内置AI（10个难度级别，LV1~LV10），主要评估在LV5（Harder）上的表现。地图为Altitude LE和Ancient Cistern LE（2023赛季1v1天梯地图）。
- **评估指标**（共5个）：
  - 胜率（Win Rate）
  - 人口阻塞率（Population Block Ratio, PBR）
  - 资源利用率（Resource Utilization Ratio, RUR）
  - 平均人口利用率（Average Population Utilization, APU）
  - 科技率（Technology Rate, TR）
- **对比方法**：
  - 闭源LLM：GPT-3.5-turbo-16k、GPT-4-turbo、Gemini-Pro、GLM4、Claude 2.1（使用完整CoS）
  - 开源微调模型：Fine-tune-ChatGLM3-6B、Fine-tune-Qwen1.8B、Fine-tune-Qwen7B、Fine-tune-LLaMA2-7B（使用CoS without CoT，因算力限制）
  - 未微调的LLaMA2-70B：无法理解任务，不产生有效命令
- **辅助实验**：
  - **SC2知识问答评估**：从热门论坛收集5类问题（基础知识、种族机制、典型策略、标准建造顺序、经典策略与反制），由4个商业模型（ChatGPT、GPT-4、Claude2、Bard）回答，由大师级别人类专家和GPT-4进行双盲评分。
  - **人机对战**：将微调的Qwen1.8B模型（仅需4GB显存）与亚洲服务器上的不同等级人类玩家（职业选手、大师、黄金、新手）对战，每人对战10局。
  - **数据质量消融实验**：使用GPT-3.5-Turbo-16k的游戏记录数据，分别用全数据集、仅胜局数据集、按APU分层的胜局子集（前25%、25-50%、50-75%、后25%）对开源模型进行微调，对比胜率。
  - **提示词影响实验**：对比简单提示（Prompt1）和复杂多阶段提示（Prompt2）下GPT-3.5-Turbo-16k在不同难度AI下的胜率。

## 4. 资源与算力

- **训练阶段**：使用2块NVIDIA A100 40GB GPU，微调开源LLM，总耗时约70小时。
- **测试阶段**：
  - 微调模型推理：使用2块NVIDIA A100 40GB GPU（训练/评估环境）。
  - 游戏环境运行：NVIDIA GeForce RTX 3060 GPU + 13代Intel i5-13400F CPU（2.50 GHz）。
- **各模型延迟（每步）**：
  - 微调Qwen2-1.8B：64ms
  - 微调Qwen2-7B：98ms
  - 微调LLaMA2-7B：102ms
  - GPT-3.5：1.2s（基于闭源API，含网络传输）
  - GPT-4：2.3s
  - Gemini-Pro：0.3s

## 5. 实验数量与充分性

- **主要LLM对比（表1）**：每个模型在LV5 AI下进行20场比赛（如GPT-3.5 11/20胜），共测试9个模型（含闭源和微调），共约180局。
- **数据质量消融（表2）**：每个数据集子集进行100场比赛（如全数据集28/100，前25% APU数据集54/100），共5×100=500局。
- **提示词影响（表4）**：对比两种提示词，分别在LV1~LV6各进行若干局（具体局数未逐级列出，但显示百分比），覆盖了6个难度级别。
- **人机对战（表3）**：1个模型（微调Qwen1.8B）与4个不同水平人类玩家，各10局，共40局。
- **知识评估（图2）**：4个商业模型，5个问题，由人类专家和GPT-4双盲评分。
- **消融方式**：还包括CoS with vs without CoT的比较（表1中下半部分即为无CoT的微调模型）；不同Prompt的对比；不同数据质量（APU分层）的对比。
- **充分性与公平性**：
  - 比赛设置公平：统一使用Protoss对Zerg，地图固定，温度参数固定为0.1，覆盖多个游戏补丁（5.0.11~5.0.13）。
  - 指标设计客观：除胜率外，还有反映宏观管理的PBR、RUR、APU、TR。
  - 知识评估采用双盲，减少主观偏差。
  - 但部分实验（如提示词影响）的样本量未明确给出具体局数，仅以百分比呈现，略欠透明。

## 6. 论文的主要结论与发现

- **CoS方法有效**：使用完整CoS的闭源LLM（如GPT-3.5、GPT-4）均能击败LV5内置AI，胜率分别达55%（11/20）和60%（12/20），显着优于简单CoT。
- **微调开源模型潜力大**：微调后的Qwen-7B和Qwen-1.8B在LV5上分别取得45%（9/20）和40%（8/20）胜率，表现优于同参数量的未微调模型。人机对战中，微调Qwen1.8B实力相当于黄金级玩家（面对黄金级玩家5胜5负）。
- **数据质量至关重要**：仅使用胜局中APU排名前25%的数据进行微调，胜率最高（54%）；使用全数据（含败局）反而降低至28%，说明高质量数据胜过大数据。
- **LLM决策可解释性强**：相比AlphaStar的“黑箱”策略，LLM agent能够结构化分析局势、预测对手策略并给出合理决策（如提前建造光子炮台、针对敌方部队转型），展示了类人推理。
- **闭源模型知识水平**：GPT-4在SC2知识问答中得分最高（人类和GPT-4双重评估），其次为ChatGPT、Claude2、Bard；但所有模型对复杂建造顺序和技术树理解仍有不足。

## 7. 优点

- **创新方法**：CoS方法有效缓解了LLM在实时环境下的响应延迟问题，兼顾推理深度与速度，可作为插件集成。
- **环境构建出色**：TextStarCraft II将复杂RTS游戏转化为文本界面，支持LLM与内置AI、其他LLM及人类玩家的对战，并开放全部代码与数据。
- **评估全面**：包含多种LLM对比、微调消融、提示词分析、知识问答（专家+GPT-4双盲）、人机实战，覆盖多个维度。
- **可解释性贡献**：展示了LLM决策过程的透明性，为AI安全性、人机协作提供了新视角。
- **实用性强**：微调小模型（1.8B）仅需4GB显存即可在普通PC上运行，具备落地潜力。

## 8. 不足与局限

- **环境简化**：依赖规则脚本处理微操（如单位集火、走位），LLM只负责宏观决策；不支持原生视觉输入（仅文本），可能损失部分战略信息（如地形、阵型）。
- **种族覆盖不全**：实验仅用Protoss对Zerg，未测试其他种族或种族内战的泛化能力。
- **算力限制**：未微调大模型（如LLaMA2-70B）无法运行；部分微调模型移除了CoT组件（CoS without CoT），导致策略多样性下降（如只出追猎者）；大型闭源模型延迟较高（>1s/步），难以完全实时。
- **实验鲁棒性**：人机对战样本量较小（每对手10局），且仅1个模型参与；提示词影响实验的局数未详细列出；未进行交叉验证或统计显著性检验（除表6的知识评估外）。
- **缺乏与强化学习方法的直接比较**：未与AlphaStar、ROA-Star等经典RL智能体进行同条件对比，难以量化LLM方法的相对优势。
- **泛化性存疑**：方法和环境高度特化于SC2，是否可迁移至其他RTS或实时决策任务尚不明确。

（完）
