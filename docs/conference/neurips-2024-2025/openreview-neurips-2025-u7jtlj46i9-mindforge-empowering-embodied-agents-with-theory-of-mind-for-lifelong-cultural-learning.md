---
title: "MindForge: Empowering Embodied Agents with Theory of Mind for Lifelong Cultural Learning"
title_zh: "MindForge: 赋予具身代理心智理论以实现终身文化学习"
authors: "Mircea Tudor Lică, Ojas Shirekar, Baptiste Colle, Chirag Raman"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=u7jtLj46i9"
tags: ["query:player-ai"]
score: 9.0
evidence: 在Minecraft中AI代理玩游戏
tldr: 该论文针对大型语言模型驱动的具身代理在Minecraft等开放世界中执行基本任务能力不足的问题，提出了MindForge框架。该框架通过结构化心智理论表示、智能体间自然通信和多组件记忆系统，使代理能够进行终身文化学习。实验表明，在指令性和协作性场景中，该框架显著提升了代理的任务完成能力，为游戏人工智能中的玩家行为建模提供了新的方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-u7jtlj46i9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1427, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-u7jtlj46i9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-u7jtlj46i9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 952, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-u7jtlj46i9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-u7jtlj46i9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 564, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-u7jtlj46i9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1431, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-u7jtlj46i9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1129, \"height\": 530, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-u7jtlj46i9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u7jtlj46i9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u7jtlj46i9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 640, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u7jtlj46i9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u7jtlj46i9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1454, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u7jtlj46i9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1369, \"height\": 482, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u7jtlj46i9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 937, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u7jtlj46i9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1088, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u7jtlj46i9/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1453, \"height\": 255, \"label\": \"Table\"}]"
motivation: 现有LLM驱动的具身代理在开放世界游戏中对基本任务仍然表现不佳。
method: 提出MindForge生成式代理框架，包含结构化心智理论表示、自然通信和多组件记忆系统。
result: 在Minecraft环境中，MindForge在指令性和协作性任务上均提升了代理的性能。
conclusion: 通过显式视角采样，代理可以在游戏环境中实现高效的文化学习。
---

## Abstract
Embodied agents powered by large language models (LLMs), such as Voyager, promise open-ended competence in worlds such as Minecraft. However, when powered by open-weight LLMs they still falter on elementary tasks after domain-specific fine-tuning. We propose MindForge, a generative-agent framework for cultural lifelong learning through explicit perspective taking. We introduce three key innovations: (1) a structured theory of mind representation linking percepts, beliefs, desires, and actions; (2) natural inter-agent communication; and (3) a multi-component memory system. Following the cultural learning framework, we test MindForge in both instructive and collaborative settings within Minecraft. In an instructive setting with GPT-4, MindForge agents powered by open-weight LLMs significantly outperform their Voyager counterparts in basic tasks yielding $3\times$ more tech-tree milestones and collecting $2.3\times$ more unique items than the Voyager baseline. Furthermore, in fully collaborative settings, we find that the performance of two underachieving agents improves with more communication rounds, echoing the Condorcet Jury Theorem. MindForge agents demonstrate sophisticated behaviors, including expert-novice knowledge transfer, collaborative problem solving, and adaptation to out-of-distribution tasks through accumulated cultural experiences.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有由大型语言模型（LLM）驱动的具身代理（如 Voyager）在 Minecraft 等开放世界中展示了无限学习潜力，但高度依赖闭源模型（如 GPT-4）。当替换为开放权重 LLM（如 Mistral-7B、Llama-3.1-8B）时，即使经过领域微调，仍然无法完成挖一个泥土块或木头块这样的基础任务。论文指出，这些代理的另一个核心局限是孤立学习，缺乏人类社会学习中的文化和心智理论（Theory of Mind, ToM）能力。
- **整体含义**：提出 MindForge 框架，使开放权重 LLM 代理能够通过显式的视角采样（perspective taking）和与其他代理的交互进行文化式终身学习。实验表明，这种方法能显著缩小开放权重模型与 GPT-4 之间的性能差距，体现了社会交互作为一种“测试时计算”（test-time compute）替代大规模模型扩展的可能性，符合绿色 AI 理念。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：基于文化学习框架（Tomasello），让代理通过结构化 ToM 表示进行视角采样，利用自然语言通信和记忆系统实现跨代理的知识共享与能力提升。
- **关键技术细节**：
  1. **结构化心智状态表示**：基于 BigToM 因果模板，将自身的感知（percepts）、信念（beliefs）、欲望（desires）、行动（actions）显式建模。信念细分为四类：感知信念、任务信念、交互信念、伙伴信念，每类由独立 LLM 调用生成。
  2. **心智理论 (ToM)**：每个代理维护一个关于对话伙伴的 BigToM 因果图，持续根据对话内容更新伙伴信念，从而推理对方的心理状态，实现视角采样。
  3. **通信媒介**：利用 Minecraft 内置聊天系统，在代理任务失败后自动发起通信。通过专用 LLM 实例将对话内容解析为结构化的 ToM 表示（交互信念和伙伴信念）。
  4. **多组件记忆系统**：
     - **情景记忆**：存储过去失败的经历（包括上下文、代码、批评），采用 RAG 检索相关失败案例并摘要后融入代码生成。
     - **语义记忆**：存储关于任务和世界的抽象知识（如“挖泥土不需要工具”），可通过通信修正错误信念。
     - **程序记忆**：等价于 Voyager 的技能库，存储可复用的成功代码片段。
- **算法流程**（文字说明）：代理通过自动课程生成下一个任务 → 从情景记忆和语义记忆中检索相关信息 → 基于当前感知和信念生成代码 → 执行过程中若失败则进入通信模块 → 借助伙伴模型（ToM）生成针对性帮助请求或解答 → 更新信念和记忆 → 重试直到成功或达到轮次上限。

### 3. 实验设计：使用的数据集/场景、Benchmark、对比方法

- **场景与环境**：Minecraft（基于 MineDojo 和 Mineflayer），与原 Voyager 相同。
- **基准任务**：
  - 原子任务：收集 1 个泥土块、1 个木头块。
  - 复杂任务：挖一个铁块、合成一把木镐。
  - 终身学习任务：Minecraft 科技树（木工具→石工具→铁工具）。
- **对比方法**：
  - Voyager（原始 GPT-4 版本 + 开放权重版本），以及 ReAct、Reflexion、AutoGPT（仅 GPT-4）。
  - 开放权重 LLM：Mistral-7B, Mixtral-8×7B, Llama-3.1-8B/70B.
  - MindForge 变体：无协作、有协作（指令/协作）、不同通信轮次、有无 ToM、结构化/非结构化 ToM、有无情景记忆、灵活通信协议。
- **评估指标**：任务完成率（24 次独立试验）、科技树里程碑达成次数和所需迭代数（3 次平均）、独特物品数量。
- **附加实验**：人类专家（Wizard-of-Oz）协作、后协作及 OOD 泛化、弱-弱协作（Condorcet 效应）。

### 4. 资源与算力

- 论文附录 G 指出，所有 LLM 调用除微调模型外均通过 API 完成：Llama-3.1-8B 使用 Lambda Inference API，GPT-4 使用 OpenAI API，Mixtral 和 Llama-3.1-70B 使用 Together AI API。
- 微调使用 LoRA（参数高效微调），在本地执行，但未说明 GPU 型号、数量或训练时长。
- **总结**：论文未明确披露完整的计算资源（如 GPU 卡时、训练时间），仅提及 API 调用和本地 LoRA 微调，因此算力细节不透明。

### 5. 实验数量与充分性

- **实验数量**：
  - 基本任务：表 1、表 2 各 24 次试验，涵盖了多个模型和设置。
  - 科技树：表 3 每个条件 3 次取平均，带标准差。
  - 消融实验：表 7-9（视角采样、记忆）、表 4（复杂任务协作）、表 5（后协作/OOD）、表 6（协议变体）。
  - 通信轮次影响：图 5、图 7 呈现了 0-10 轮多种模型表现。
- **充分性**：实验设计较为全面，涵盖了原子任务、复合任务和终身学习场景；消融覆盖了各个核心模块；统计使用多次重复，给出误差棒。但不足在于：
  - 所有实验仅在 Minecraft 一个环境进行，缺乏跨环境验证。
  - 与 Voyager 的对比可能存在基线过弱（开放权重 Voyager 几乎失败）导致提升幅度看似巨大的问题。
  - 缺少与其他多代理框架（如 CoELA、COMBO）的定量对比。

### 6. 论文的主要结论与发现

- MindForge 使开放权重 LLM 代理在基础任务上比 Voyager 提升超过 40%，在科技树里程碑上达到 3 倍，独特物品收集量达到 2.3 倍。
- 识别出开放权重 Voyager 的两大失败模式：**错误信念**（如认为挖泥土需要工具）和**代码生成错误**，MindForge 通过通信和视角采样有效修正。
- 在指令学习（强-弱）中，随着通信轮次增加，任务完成率显著上升。
- 在协作学习（弱-弱）中，经过一轮 GPT-4 引导后，代理间多轮对话使群体成功率从 62% 上升至 79%，体现了 Condorcet 陪审团定理的“多脑”效应。
- 协作后的代理能在 OOD 任务上泛化（平均提升 8.78%）。
- 结构化 ToM 表示优于非结构化变体，情景记忆提升性能。

### 7. 优点

- **创新性**：将文化学习理论和 ToM 首次系统性地嵌入 LLM 代理框架，将知识蒸馏转变为测试时的社会交互过程，避免了梯度微调。
- **模块化架构**：三大创新（结构化 ToM、自然通信、多组件记忆）可独立消融，设计清晰。
- **丰富的消融和对比**：包括人类专家实验、多种 LLM、多种通信策略，增强了结论的可靠性。
- **绿色 AI 潜力**：展示了开放权重模型通过协作即可接近 GPT-4 水平，减少对大规模模型和微调的依赖。
- **启发性**：“测试时计算”视角和 Condorcet 效应为多代理协作提供了新的理论联系。

### 8. 不足与局限

- **环境单一**：所有实验仅在 Minecraft 中完成，未在 Habitat、ALFRED 等更广泛的具身环境中验证，通用性存疑。
- **计算成本未透明**：虽避免了大规模训练，但多轮通信和多次 LLM 调用增加了推理开销；论文未分析总 token 消耗或延迟。
- **基线弱势**：开放权重 Voyager 几乎失败，使 MindForge 的提升显得极为显著，但对比 GPT-4 Voyager 时差异依然存在（需更多协作轮次才能接近）。
- **初期专家引导的必要性**：弱-弱协作若无专家种子（单轮 GPT-4 引导）则性能止步不前，限制了完全自举的应用场景。
- **缺乏与其他多代理框架的定量比较**：没有与 CoELA、COMBO 等现有系统在同一条件下比较，无法判断相对优劣。
- **未涉及安全与偏见**：未讨论代理可能学习有害行为或产生偏见。

（完）
