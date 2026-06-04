---
title: "SimWorld: An Open-ended Simulator for Agents in Physical and Social Worlds"
title_zh: SimWorld：用于物理和社交世界中代理的开放模拟器
authors: "Xiaokang Ye, Jiawei Ren, Yan Zhuang, Xuhong He, Yiming Liang, Yiqing Yang, Mrinaal Dogra, Xianrui Zhong, Eric Liu, Kevin Benavente, Rajiv Mandya Nagaraju, Dhruv Vivek Sharma, Ziqiao Ma, Tianmin Shu, Zhiting Hu, Lianhui Qin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FxCy8TvQHO"
tags: ["query:player-ai"]
score: 8.0
evidence: 开放模拟器用于在真实环境中开发和评估LLM/VLM代理
tldr: 本文介绍SimWorld，一个基于虚幻引擎5构建的开放模拟器，专门用于开发和评估LLM/VLM代理在复杂物理和社会环境中的表现。与现有简化的游戏模拟器不同，SimWorld提供丰富的真实世界场景，支持大规模交互、推理和训练，为游戏AI代理训练提供了有力工具。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1160, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 662, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 800, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 594, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 580, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1412, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1391, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1447, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1451, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1372, \"height\": 798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1388, \"height\": 1064, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1446, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1450, \"height\": 250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1428, \"height\": 1909, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1443, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1441, \"height\": 1301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 452, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 455, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 451, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 449, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1442, \"height\": 1138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1415, \"height\": 1110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1441, \"height\": 1309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1451, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1326, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1438, \"height\": 1389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1444, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fxcy8tvqho/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1443, \"height\": 939, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fxcy8tvqho/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fxcy8tvqho/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1346, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fxcy8tvqho/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fxcy8tvqho/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1356, \"height\": 924, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fxcy8tvqho/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 994, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fxcy8tvqho/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 934, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fxcy8tvqho/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 439, \"label\": \"Table\"}]"
motivation: 现有模拟器环境有限，缺乏对LLM/VLM代理的原生支持。
method: 基于Unreal Engine 5构建SimWorld，支持丰富的真实世界场景和LLM/VLM代理。
result: 提供了一个可用于开发和评估代理的通用平台。
conclusion: SimWorld能促进代理在复杂现实场景中的进步。
---

## Abstract
While LLM/VLM-powered AI agents have advanced rapidly in math, coding, and computer use, their applications in complex physical and social environments remain challenging. Building agents that can survive and thrive in the real world (e.g., by autonomously earning income) requires massive-scale interaction, reasoning, training, and evaluation across diverse scenarios. However, existing world simulators for such development fall short: they often rely on limited hand-crafted environments, simulate simplified game-like physics and social rules, and lack native support for LLM/VLM agents. We introduce SimWorld, a new simulator built on Unreal Engine 5, designed for developing and evaluating LLM/VLM agents in rich, real-world-like settings. SimWorld offers three core capabilities: (1) realistic, open-ended world simulation, including accurate physical and social dynamics and language-driven procedural environment generation; (2) rich interface for LLM/VLM agents, with multi-modal world inputs/feedback and open-vocabulary action outputs at varying levels of abstraction; and (3) diverse physical and social reasoning scenarios that are easily customizable by users. We demonstrate SimWorld by deploying frontier LLM agents (e.g., Gemini-2.5-Flash, Claude-3.5, GPT-4o, and DeepSeek-Prover-V2) on both short-horizon navigation tasks requiring grounded re-planning, and long-horizon multi-agent food delivery tasks involving strategic cooperation and competition. The results reveal distinct reasoning patterns and limitations across models. We open-source SimWorld and hope it becomes a foundational platform for advancing real-world agent intelligence across disciplines. Please refer to the project website for the most up-to-date information: http://simworld.org/.

---

## 论文详细总结（自动生成）

# SimWorld: 开放物理与社交世界智能体模拟器——论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：当前LLM/VLM驱动的智能体在数学、编程、网页操作等结构化任务上表现优异，但在复杂、动态、真实的物理与社交环境（如城市导航、多智能体经济协作）中仍面临巨大挑战。现有模拟器（如Minecraft、CARLA、AI2-THOR等）存在三大局限：场景手工程度有限、物理/社交规则过于简化、缺乏对LLM/VLM智能体的原生支持。
- **研究动机**：构建能“在真实世界中生存与繁荣”（如自主赚钱）的智能体，需要大规模、多样化的交互、推理、训练与评估平台。为此，论文提出并实现了**SimWorld**——一个基于Unreal Engine 5构建的、面向LLM/VLM智能体的开放、逼真、可扩展的模拟器。
- **整体含义**：SimWorld旨在成为智能体在真实世界物理与社交互动中发展的基础平台，填补现有模拟器与真实世界需求之间的鸿沟，推动AI智能体从“数字工具使用者”向“真实世界参与者”迈进。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：SimWorld采用**双层架构**：底层为Unreal Engine 5提供逼真的3D渲染、实时物理引擎（重力、动量、碰撞等）及动态环境（灯光、天气、行人流）；上层为Python层，提供丰富的接口与工具，包括：
  - **开放世界生成**：通过**过程化生成**（四叉树+道路/建筑/细节三级管线）创建几乎无限的城市环境；支持**自然语言驱动的场景编辑**（LLM解析指令→检索资产库→如无匹配则调用Text-to-3D生成新物体并整合），实现实时、语言可控的世界构建。
  - **真实物理与社交模拟**：物理层面模拟重力、惯性、坡度滑行等真实力学；社交层面模拟交通信号、人行道规则、个人空间等社会化行为；车辆与行人遵循实时交通系统。
  - **丰富智能体接口**：
    - **输入**：多模态感知（RGB图、深度图、分割图、语义场景图、碰撞反馈等）。
    - **输出**：支持**开放词汇自然语言高层动作**（如“go to the nearest chair and sit down”），由内置的**局部动作规划器**（rule-based或VLM-based）分解为低层可执行动作序列（如导航、抓取、坐下）。
    - **航点系统**：提供粗粒度与细粒度的路标网络，便于智能体进行高层路径规划与低层避障。
  - **物理与社交推理场景**：模块化任务定义、角色、奖励与评估指标，支持用户自定义场景。
- **关键技术细节**：
  - 场景生成：使用四叉树管理层次化场景图，支持快速空间检索。
  - LLM场景编辑：通过检索增强生成（RAG）+CLIP匹配实现语义锚定；若资产缺失则调用Hunyuan3D等生成模型。
  - 局部动作规划器：解析器接收高层计划，执行器分为规则式（基于Dijkstra最短路径）和视觉式（VLM根据视觉反馈实时决策）。
  - 多智能体通信：通过Python与UE之间的TCP通信（基于UnrealCV扩展）实现异步控制。

## 3. 实验设计：数据集/场景、基准、对比方法
- **实验场景**：
  - **案例1**：单智能体**视觉导航任务**（物理推理）。智能体需从起点到达目标，规避静态（树木、长椅）和动态（行人）障碍，遵守交通规则。分为**Easy**（单段直行）、**Medium**（单次转弯）、**Hard**（多个转弯跨四段）和**Dynamic**（有行人干扰）四种难度。每条任务由过程化生成的城市中随机采样，共40个任务（每难度10个）。
  - **案例2**：多智能体**食品配送任务**（社交与战略推理）。多个智能体（20个相同模型控制的代理）在同一个城市环境中竞争与合作，管理能量、资金，可竞标订单、共享订单、购买车辆、调整速度等，目标最大化总利润。实验运行5000个模拟步，每步2次API调用。
- **基准方法**：
  - 案例1比较了**规则基线**（严格遵循航点）与多个前沿VLM：GPT-4o-mini、GPT-4o、Claude-3.7-Sonnet、Gemini-2.5-Pro。另外做了**无局部动作规划器**的消融实验。
  - 案例2比较了：Claude-3.5-Sonnet、DeepSeek-V3、GPT-4o、Gemini-2.5-Flash、Gemini-2.0-Flash、Qwen3-32B、DeepSeek-Prover-V2、QwQ、GPT-4o-mini等。此外还进行了**模型竞争**（12个模型各控2个智能体，1000轮）、**环境配置**（总订单数、初始资金）和**人格特质**（大五人格）的消融实验。

## 4. 资源与算力
- **论文未明确说明具体GPU型号、数量或训练时长。** 所有实验均基于闭源或部分开源的LLM/VLM API（如OpenAI、Claude、Gemini等），无需本地训练。每个实验涉及多次API调用（案例2每步约7000tokens）。作者在附录中强调可通过并行多智能体提高效率，但未提供详细的算力计费或硬件配置。

## 5. 实验数量与充分性
- **实验数量**：案例1在4个难度上各测试了4-5个模型，每个模型重复多次（具体未明确，但结合标准差不难推测至少3次）。案例2主实验对9个模型进行了3轮5000步模拟。消融实验包括：无局部规划器（3个模型）、模型竞争（12个模型×1000轮×3种子）、环境配置（总订单数5个水平、初始资金5个水平）、人格特质（大五人格×每个模型2个代理×20个代理）。
- **充分性评估**：实验设计较为全面，覆盖了物理导航、多智能体协作竞争、人格影响、资源配置等多个维度，并提供了均值与标准差。但案例1中动态障碍实验仅使用单一动态场景（行人），环境多样性有限；案例2仅在一个地图上进行；缺乏在更多随机地图或真实数据集上的泛化验证。此外，论文未报告API调用的温度、top-k等超参数设置，可能影响可复现性。总体而言实验数量充分，但客观性受限于闭源模型的黑箱性质。

## 6. 论文的主要结论与发现
- **物理推理方面**：
  - GPT-4o、Claude-3.7-Sonnet、Gemini-2.5-Pro在静态障碍导航中成功率均高于90%（Hard难度），但存在普遍问题：**忽视红绿灯**（即使给出全景图，模型不主动调整视角观察信号，红灯时仍通行）。
  - 动态障碍下，GPT-4o和Claude-3.7-Sonnet成功率更高（86.7%、93.3%），但Gemini-2.5-Pro碰撞更少，却因频繁重新选点而卡住。
  - 无局部规划器设置下，Gemini-2.5-Pro成功率最高（60%），而GPT-4o完全失败（0%）；Claude-3.7-Sonnet在决策效率与安全间平衡。
- **多智能体社交推理方面**：
  - DeepSeek-V3和Claude-3.5-Sonnet平均利润最高（约69美元），但标准差大（±16~20），表现不稳定；Gemini-2.5-Flash利润中等（42美元）但稳定（±3.1）。
  - 竞标策略差异显著：灵活出价的模型（Claude-3.7-Sonnet、Gemini-2.5-Flash）更容易赢得订单；激进低价策略（DeepSeek-Prover-V2、Qwen3-32B）胜率高但利润低；GPT-4o-mini完全不参与（利润为0）。
  - **资源影响**：订单越多，智能体倾向消极等待（按兵不动）；资金越多，更愿意投资（买自行车）而非激烈竞价。
  - **人格影响**：尽责性高的智能体更专注任务完成；开放性高的智能体探索性强但容易亏损；宜人性高则不易无所事事。
- **总体发现**：当前最强LLM/VLM在物理与社交推理中表现出“有潜力但有明显缺陷”——物理感知与行动脱节，规则遵守差，策略一致性不足。SimWorld揭示了这些差距，为改进提供了精确的评估维度。

## 7. 优点：方法或实验设计上的亮点
- **逼真与开放性的结合**：基于UE5提供照片级真实感和真实物理模拟，同时通过过程化生成和语言编辑实现几乎无限的环境多样性，远超以往模拟器。
- **原生LLM/VLM接口**：支持自然语言高层动作和多模态输入，配套局部动作规划器，使得LLM可专注于高层推理，而低层执行由模拟器负责，极大降低了部署门槛。
- **多维度、分层次的评估体系**：案例1从成功率、碰撞数（成功/失败）、红绿灯违规率、卡死率、决策效率等多个角度衡量；案例2设计了高（总利润）、中（订单成功率、能源效率、共享/投资次数）、低（动作合规性）三层次指标，系统全面。
- **丰富的消融实验**：深入到局部规划器作用、模型竞争、环境资源、人格特质等影响因素，提供了对智能体行为模式的深刻洞察。
- **社区贡献**：开源全部代码、场景、任务集和评估脚本，便于复现与扩展。

## 8. 不足与局限
- **实验环境有限**：物理导航仅在两个城市、四种场景下测试；多智能体任务仅在一个地图运行。虽然过程化生成支持多样性，但论文未在随机生成的大量地图上进行大规模验证。
- **闭源模型黑箱**：所有LLM/VLM均为API访问，算法细节和超参数不可控，导致部分结论可能受模型版本、温度等影响，可复现性受限。
- **物理交互深度不足**：当前案例仅涉及“行走、避障、坐下”等有限动作，未涉及复杂的操作（如推、拉、开门等），缺乏如机器人操控类的精细评估。
- **社交模拟的简化**：多智能体任务中，顾客和商店由规则管理，社交行为仅通过订单共享和竞价体现，尚未模拟真实的人类交流、谈判、情感等高级社交现象。
- **规模化训练支持待优化**：论文提到SimWorld可用于RL训练，但未展示大规模并行训练的效率；当前通信基于TCP，可能存在多智能体高并发下的延迟瓶颈。
- **计算成本未说明**：缺少总API调用次数、预算或时间成本，不利于其他团队复现类似实验规模。

（完）
