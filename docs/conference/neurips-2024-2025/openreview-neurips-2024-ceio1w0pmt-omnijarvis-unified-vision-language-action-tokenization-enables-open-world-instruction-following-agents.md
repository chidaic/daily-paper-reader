---
title: "OmniJARVIS: Unified Vision-Language-Action Tokenization Enables Open-World Instruction Following Agents"
title_zh: OmniJARVIS：统一的视觉-语言-动作令牌化实现开放世界指令跟随代理
authors: "Zihao Wang, Shaofei Cai, Zhancun Mu, Haowei Lin, Ceyao Zhang, Xuejie Liu, Qing Li, Anji Liu, Xiaojian Ma, Yitao Liang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=ceIO1w0PmT"
tags: ["query:player-ai"]
score: 9.0
evidence: VLA模型用于Minecraft游戏中的指令跟随代理
tldr: 本文提出OmniJARVIS，一种新颖的视觉-语言-动作（VLA）模型，用于Minecraft中的开放世界指令跟随代理。通过将行为轨迹离散化为行为令牌并整合到预训练词汇中，该模型实现了强推理和高效决策的统一，优于先前将文本目标与控制器分离的方法。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-ceio1w0pmt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1301, \"height\": 806, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ceio1w0pmt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ceio1w0pmt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ceio1w0pmt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 440, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ceio1w0pmt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1370, \"height\": 209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ceio1w0pmt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1361, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ceio1w0pmt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1430, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ceio1w0pmt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1370, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ceio1w0pmt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 572, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ceio1w0pmt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 571, \"height\": 326, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-ceio1w0pmt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 719, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ceio1w0pmt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 663, \"height\": 92, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ceio1w0pmt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 677, \"height\": 86, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ceio1w0pmt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1415, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ceio1w0pmt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 937, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ceio1w0pmt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1370, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ceio1w0pmt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1429, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ceio1w0pmt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1444, \"height\": 515, \"label\": \"Table\"}]"
motivation: 现有方法要么输出文本目标，要么直接控制，缺乏统一推理与决策的机制。
method: 学习行为编码器将行为轨迹离散化为令牌，并扩充到预训练词汇中。
result: 在Minecraft中实现了高效的指令跟随和决策。
conclusion: 统一的令牌化方法能同时保证推理和决策能力。
---

## Abstract
This paper presents OmniJARVIS, a novel Vision-Language-Action (VLA) model for open-world instruction-following agents in Minecraft. Compared to prior works that either emit textual goals to separate controllers or produce the control command directly, OmniJARVIS seeks a different path to ensure both strong reasoning and efficient decision-making capabilities via unified tokenization of multimodal interaction data. First, we introduce a self-supervised approach to learn a behavior encoder that produces discretized tokens for behavior trajectories $\tau = \{o_0, a_0, \dots\}$ and an imitation learning policy decoder conditioned on these tokens. These additional behavior tokens will be augmented to the vocabulary of pretrained Multimodal Language Models. With this encoder, we then pack long-term multimodal interactions involving task instructions, memories, thoughts, observations, textual responses, behavior trajectories, etc into unified token sequences and model them with autoregressive transformers. Thanks to the semantically meaningful behavior tokens, the resulting VLA model, OmniJARVIS, can reason (by producing chain-of-thoughts), plan, answer questions, and act (by producing behavior tokens for the imitation learning policy decoder). OmniJARVIS demonstrates excellent performances on a comprehensive collection of atomic, programmatic, and open-ended tasks in open-world Minecraft. Our analysis further unveils the crucial design principles in interaction data formation, unified tokenization, and its scaling potentials. The dataset, models, and code will be released at https://craftjarvis.org/OmniJARVIS.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：构建能够在开放世界（如 Minecraft）中遵循指令、推理、规划并行动的自主智能体。现有 Vision-Language-Action（VLA）模型存在两大缺陷：
  - **文本-动作不匹配**：依赖文本目标与独立控制器通信的方法（如 DEPS、JARVIS-1）难以精确描述复杂具身任务，导致控制器执行失败。
  - **长时域任务效率低**：直接输出低级控制命令的方法（如 RT-2）在长时域任务中面临上下文长度、计算成本与推理效率问题。
- **整体含义**：提出一种通过**统一多模态交互数据令牌化**来同时实现强推理与高效决策的 VLA 模型 OmniJARVIS，使智能体能够像人类一样进行多轮心智、言语和物理交互。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：
  - 将多模态交互数据（视觉观测、语言指令/记忆/思考、行为轨迹）统一令牌化为序列，用自回归 Transformer 建模。
  - 通过自监督方式学习行为令牌（behavior tokens），将其扩充到预训练多模态语言模型（MLM）的词表中。
- **关键技术细节**：
  1. **行为令牌化（Behavior Tokenization）**：
     - 基于 VAE 框架，将 GROOT 中的连续高斯潜变量替换为**有限标量量化（FSQ, Finite Scalar Quantization）**，得到离散行为令牌。
     - 采用 FSQ 配置 `[8,8,8,6,5]`，产生长度为 5、码本大小为 15360 的离散代码。
     - 行为编码器（非因果 Transformer）将长度为 128 帧的行为轨迹编码为离散令牌；行为解码器（策略网络，因果 Transformer）根据行为令牌和观测产生动作。
     - 训练目标：最小化行为克隆损失（公式1）。
  2. **多模态交互数据构建**：
     - 使用 OpenAI Contractor Dataset（Minecraft 游戏视频）作为初始轨迹数据。
     - 通过 GPT-3.5 合成缺失的文本段：**指令**（利用元信息总结任务）、**记忆**（总结已完成的关键步骤）、**思考**（根据逆动力学模型推断决策原因）。
     - 形成标准交互序列：指令、记忆、观测、思考、行为轨迹（可重复多轮）。
  3. **OmniJARVIS 架构与训练**：
     - 基于预训练 MLM（默认 LLaVA-7B），在词表中增加 35 个行为令牌（对应 FSQ 各维度）。
     - 训练采用前缀语言建模：将指令、记忆、观测作为前缀，自回归预测思考和行为令牌（公式3）。
     - 训练数据：600k 轨迹（约 900M tokens）的指令跟随数据集 + 300k 对话（约 90M tokens）的 Minecraft 问答数据集，混合训练约 1T tokens。
  4. **推理**：
     - 输入任务指令、空记忆与初始观测。
     - 模型产生思考链，然后输出 5 个行为令牌，送入行为解码器生成动作。
     - 每 32 步重新用最新观测进行新一轮推理。

## 3. 实验设计
- **实验场景与数据集**：
  - **环境**：Minecraft（开放世界体素游戏）。
  - **训练数据**：OpenAI Contractor Dataset（6xx/7xx/10xx 段） + JARVIS-1 记录数据。
  - **用于评估的任务类型**：
    - **原子任务（Atomic Tasks）**：短时域技能，如砍树、挖土、采矿、收集小麦种子。
    - **程序化任务（Programmatic Tasks）**：长链条物品获取，分 5 组（木、食物、石、铁、钻石），共 30 个任务。
    - **开放式指令跟随（Open-ended Instruction Following）**：需至少 5 分钟人工游戏时间的创意任务。
    - **开放式具身问答（Open-ended Embodied QA）**：关于 Minecraft 世界的知识、规划、推理问题。
- **评估指标**：
  - 原子任务：平均奖励（10 runs）。
  - 程序化任务：成功率。
  - 开放式指令跟随：Frechet Sequence Distance (FSD)（使用 MineCLIP 视频编码器）。
  - 开放式问答：LLM-as-judge 打分（Vicuna-7B/13B, LLaMA2-70B, GPT-3.5 比较）。
- **对比方法**：
  - 原子任务：Text-conditioned VPT、STEVE-I、Video-instructed GROOT。
  - 程序化任务：STEVE-I、GROOT、GPT Zero-Shot Planner、ReAct、DEPS。
  - 开放式任务：VPT、STEVE-1、Voyager、DEPS。

## 4. 资源与算力
- **行为令牌化训练**：8 块 NVIDIA 3090 Ti GPU，batch size 2，学习率 4e-5，bf16 精度。
- **OmniJARVIS 训练**：8 块 A800 GPU，FSDP 分布式训练，batch size 2，梯度累积 4 步，bf16 精度，学习率 1.4e-5，cosine 调度，warm-up 0.03，训练 1 epoch（约 1T tokens 数据）。
- 文中未明确说明具体训练时长（小时/天），但提供了硬件配置和批次信息。

## 5. 实验数量与充分性
- **实验数量**：大量实验覆盖四个主要评估集合（原子任务、程序化任务、开放式指令跟随、开放式问答），每个任务多次运行并报告均值与标准差。
- **消融实验**：
  - 交互数据格式消融（指令、记忆、思考、标注的作用）。
  - 视觉令牌化方法消融（ImageCaptioner+LLaMA2、Fuyu-8B、LLaVA-7B）。
  - 行为令牌化方法消融（FSQ vs VQ-VAE vs 语言目标）。
  - 行为码本大小消融（不同 FSQ 配置）。
  - 扩展性实验：数据量增加与模型规模（2B、7B、13B）的验证损失曲线。
  - 泛化性实验：在 Montezuma's Revenge（Atari 游戏）上微调，获得 3600 分。
- **公平性与客观性**：各对比方法在相同任务和指标下评估，基线选择全面（包括已有 SOTA 方法），消融实验完整。报告了多次运行的标准差和置信区间。

## 6. 主要结论与发现
- **整体性能**：OmniJARVIS 在原子任务中达到接近最优的平均奖励；在程序化任务（30 个长链条任务）中平均成功率 0.59，显著优于所有基线（DEPS 0.43）；在开放式指令跟随和问答任务上也取得最佳（FSD 最低，QA 得分最高 8.40）。
- **关键设计原则**：
  - 行为令牌的**自监督离散化**（使用 FSQ）比语言目标描述更优，且无需额外语言标注。
  - 指令和思考对行为令牌预测最为关键。
  - LLaVA 架构的视觉令牌化效果最佳。
- **扩展性**：验证损失随数据和模型规模增大呈 log-linear 下降（符合 Scaling Law），且 7B→13B 收益递减，提示进一步扩展 VLM 可能需要更大数据量匹配。
- **泛化性**：成功迁移至 Montezuma's Revenge（Atari 游戏），得分 3600，表明方法的通用性。

## 7. 优点
- **方法创新性**：统一多模态令牌化方案，将行为轨迹离散为语义丰富的令牌，并将其无缝集成到 MLM 的词表中，实现了推理-规划-执行的一体化，无需额外语言中介。
- **实验全面性**：涵盖原子、程序化、开放式三种难度类型，同时评估指令跟随与问答能力，消融实验深入分析了数据格式、视觉/行为令牌化、码本大小等关键因素。
- **扩展性验证**：展示了数据和模型规模的正向 scaling，并测试了跨游戏（Atari）的泛化能力。
- **实用性**：自监督行为令牌化无需人工标注；推理时仅需输出 5 个令牌即可完成 128 步行为控制，效率高。
- **开源承诺**：数据集、模型和代码将在 /OmniJARVIS/ 发布，利于复现和后续研究。

## 8. 不足与局限
- **仅限 Minecraft 环境**：实验完全在 Minecraft 中进行，虽然泛化到 Atari 但仅有一个游戏，对更复杂的 3D 开放世界仍需验证。
- **数据合成依赖 LLM**：交互数据中的指令、记忆、思考完全依赖 GPT-3.5 合成，可能引入偏差或错误，且未讨论合成质量对最终性能的影响。
- **行为令牌长度固定**：每个行为轨迹固定为 128 帧，对于更长或更短的轨迹需分段处理，可能导致上下文信息丢失或冗余。
- **未报告训练成本**：虽然给出了 GPU 硬件配置，但未提供具体训练时间（GPU-hours），不利于直观比较资源消耗。
- **推理时强制再规划频率**：每 32 步重新推理是经验设定，未对该超参数进行消融分析。
- **安全隐患与伦理问题**：文中未讨论模型可能被用于生成有害内容或不当行为的风险，也未提及安全防护措施。
- **语言能力退化担忧**：作者指出 VLA 微调后语言能力可能退化，但未进行定量评估。
- **实验统计信息**：部分表格（如开放式指令跟随 FSD）未提供标准差或置信区间，影响结果可靠性。

（完）
