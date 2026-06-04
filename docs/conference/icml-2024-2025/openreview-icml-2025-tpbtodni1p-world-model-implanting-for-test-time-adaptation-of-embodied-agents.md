---
title: World Model Implanting for Test-time Adaptation of Embodied Agents
title_zh: 世界模型植入：具身智能体测试时自适应
authors: "Minjong Yoo, Jinwoo Jang, Sihyung Yoon, Honguk Woo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tpbtodnI1p"
tags: ["query:player-ai"]
score: 5.0
evidence: 世界模型植入用于具身智能体适应，可迁移至游戏智能体
tldr: 针对具身智能体跨域适应困难，提出世界模型植入框架（WorMI），通过测试时组合LLM推理和独立学习的领域世界模型，实现高效的跨域适应，原型检索机制利用轨迹抽象匹配，实验显示在多种环境（包括模拟游戏环境）中适应能力显著提升。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 852, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1631, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 832, \"height\": 959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 832, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 829, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1590, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1748, \"height\": 299, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1520, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 694, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 677, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 832, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1109, \"height\": 586, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 967, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1001, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1195, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1029, \"height\": 1011, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 610, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 756, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 487, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 579, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 704, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 533, \"height\": 422, \"label\": \"Table\"}]"
motivation: 具身智能体在新领域需要大量数据重训练，缺乏适应性。
method: 提出WorMI，通过原型检索组合LLM和领域世界模型。
result: 在多个模拟环境（包括类似游戏的场景）中，WorMI实现快速适应。
conclusion: 为具身智能体跨域适应提供新思路，可推广至游戏场景。
---

## Abstract
In embodied AI, a persistent challenge is enabling agents to robustly adapt to novel domains without requiring extensive data collection or retraining. To address this, we present a world model implanting framework (WorMI) that combines the reasoning capabilities of large language models (LLMs) with independently learned, domain-specific world models through test-time composition. By allowing seamless implantation and removal of the world models, the embodied agent's policy achieves and maintains cross-domain adaptability. In the WorMI framework, we employ a prototype-based world model retrieval approach, utilizing efficient trajectory-based abstract representation matching, to incorporate relevant models into test-time composition. We also develop a world-wise compound attention method that not only integrates the knowledge from the retrieved world models but also aligns their intermediate representations with the reasoning model's representation within the agent's policy. This framework design effectively fuses domain-specific knowledge from multiple world models, ensuring robust adaptation to unseen domains. We evaluate our WorMI on the VirtualHome and ALFWorld benchmarks, demonstrating superior zero-shot and few-shot performance compared to several LLM-based approaches across a range of unseen domains. These results highlight the framework’s potential for scalable, real-world deployment in embodied agent scenarios where adaptability and data efficiency are essential.

---

## 论文详细总结（自动生成）

## 论文中文总结

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：具身智能体（embodied agents）在跨域任务中缺乏适应性，面对全新领域（unseen domains）时通常需要大量数据收集或重新训练，成本高且不灵活。
- **背景**：现有方法包括上下文适应（in-context learning）和模型集成（model integration），但前者检索开销大，后者缺乏知识扩展性。
- **目标**：提出一种测试时模型组合框架，使智能体能够动态融合领域特定知识，在不重训练的情况下实现零样本或小样本跨域适应。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：通过“世界模型植入”（World Model Implanting, WorMI）将多个预训练的领域世界模型（world models）与一个固定的大语言模型（LLM）推理模型在测试时动态组合，形成可插拔的策略结构。
- **关键技术细节**：
  - **原型检索（Prototype-based Retrieval）**：利用对象级状态嵌入和k-center聚类，为每个世界模型生成少量原型（prototype），在测试时计算当前观测嵌入集与原型的Wasserstein距离，选择Top-K最相关的世界模型。
    - 公式：\( \delta(\mathbf{p}_i, \mathbf{p}_j) \leq \delta(E_i, E_j) + 2\rho \)（证明原型距离可约束数据集距离）。
  - **世界级复合注意力（World-wise Compound Attention）**：
    - 线性投影：将各世界模型中间层表示投影到推理模型维度。
    - 世界级交叉注意力：以推理模型层输出为查询，各世界模型投影表示为键/值，生成融合表示。
    - 推理级交叉注意力：以推理模型为查询，融合表示为值，对齐到推理模型。
  - **元学习训练**：采用MAML式元学习，通过内循环（少量梯度步）和外循环（聚合参数）训练复合注意力模块，使其学会快速适应任意的世界模型组合。

### 3. 实验设计
- **数据集与环境**：
  - **VirtualHome**：3D家庭模拟环境，收集1023个episode，覆盖78个任务（16个seen, 62个unseen）和20个场景（6个seen, 14个unseen）。
  - **ALFWorld**：基于文本的家庭任务模拟，收集3554个episode，按CL-ALFRED设置分为4种场景（3 seen, 1 unseen）和6种任务（4 seen, 2 unseen）。
- **评价指标**：成功率（SR）和待定步数（PS，平均完成任务所需步数，越低越好）。
- **对比方法**：
  - ZSP（零样本直接使用预训练LLM）
  - LLM+FT（在有限领域数据上微调）
  - LLM-Planner（上下文学习+检索演示）
  - SayCanPay（集成可学习成本模型的SOTA方法）
- **实现细节**：推理模型统一使用Llama-3.2-3B（固定），世界模型和微调模型使用Llama-3.2-1B。

### 4. 资源与算力
- **文中未明确说明GPU型号、数量及训练总时长**，仅提及使用Llama-3.2-1B和3B模型、训练步数等超参数。
- 附录指出推理时使用K=3个世界模型（总N=6），内存约30-33GB，推理时间约385ms，表明计算需求相对可控。

### 5. 实验数量与充分性
- **实验多样性**：
  - 零样本实验（表1）：覆盖三种场景（seen tasks & seen scenes, seen tasks & unseen scenes, unseen tasks & unseen scenes）。
  - 少样本实验（表2）：1-shot、5-shot、10-shot设置。
  - 消融实验（表3）：原型检索（全量 vs 随机 vs 原型）、复合注意力（拼接 vs 求和 vs 注意力）。
  - LLM规模影响（表4）：1B、3B、11B。
  - 世界模型数量影响（表5）：1~6个。
  - 复杂指令实验（表6）：长时程任务、多指令任务。
  - 持续模型植入实验（图5）：增量添加和移除世界模型的影响。
- **充分性评估**：实验覆盖了不同适应场景、多种基线、关键组件消融及扩展性分析；所有结果均报告95%置信区间（5随机种子），设置公平、客观。

### 6. 主要结论与发现
- WorMI在所有设置下均显著优于基线，尤其在未见过域（unseen tasks & unseen scenes）：
  - VirtualHome零样本：SR比SayCanPay提升20.41%，PS减少3.87步；少样本平均SR提升26.58%，PS减少4.98步。
  - ALFWorld零样本：SR提升12.01%，PS减少3.68步；少样本平均SR提升19.16%，PS减少7.36步。
- 原型检索比随机或全量检索更有效；复合注意力比简单拼接/求和更好。
- 世界模型数量适中（2~4个）最佳，过多或过少都会导致性能下降；持续添加相关世界模型可逐步提升性能，移除则造成下降。
- 复合注意力可动态聚焦最相关的世界模型（如根据物体存在、位置、任务分解调整注意力权重）。

### 7. 优点
- **动态选择性**：原型检索只激活最相关的世界模型，减少无用计算。
- **复合注意力设计巧妙**：分层融合多个世界模型知识，并有效对齐推理模型。
- **元学习参数高效**：只训练轻量复合注意力模块，无需微调大模型，适应速度快。
- **支持持续适应**：可无缝添加/移除世界模型，具备可扩展性和知识遗忘能力。
- **对不同规模LLM鲁棒**：即使使用较小LLM（1B）仍能取得比基线更好的结果（说明主要增益来自世界模型融合而非LLM能力）。

### 8. 不足与局限
- **计算开销**：同时推理多个世界模型仍带来额外显存和延迟，在资源受限场景可能受限（附录显示显存约33GB）。
- **依赖LLM底座**：性能受LLM能力上限影响，若LLM推理错误，复合注意力可能无法完全修正。
- **领域模型假设**：需预先训练独立的领域世界模型，建立成本较高；若某些领域缺少数据则无法直接应用。
- **对抗模型风险**：实验表明当检索到的世界模型中混入了未训练的“对抗”模型且比例超过1/3时，性能显著下降（但原型检索和复合注意力可部分缓解）。
- **环境局限**：仅在模拟环境中验证（VirtualHome, ALFWorld），缺少真实机器人实验。

（完）
