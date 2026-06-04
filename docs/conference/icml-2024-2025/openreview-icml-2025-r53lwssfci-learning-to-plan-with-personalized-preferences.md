---
title: Learning to Plan with Personalized Preferences
title_zh: 学习规划个性化偏好
authors: "Manjie Xu, Xinyi Yang, Wei Liang, Chi Zhang, Yixin Zhu"
date: 2025-01-21
pdf: "https://openreview.net/pdf?id=r53lwSSfcI"
tags: ["query:player-ai"]
score: 4.0
evidence: AI代理在规划任务中学习个性化偏好
tldr: 该论文针对现有具身智能体忽视个人偏好的问题，提出从少量演示中学习用户偏好并自适应调整规划策略的方法。通过引入PbP基准测试在具身环境中验证了偏好泛化能力。该方法为游戏中玩家行为建模提供了可迁移的偏好学习框架。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-r53lwssfci/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r53lwssfci/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r53lwssfci/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r53lwssfci/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1601, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r53lwssfci/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 853, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r53lwssfci/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1599, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r53lwssfci/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 849, \"height\": 367, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-r53lwssfci/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r53lwssfci/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1390, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r53lwssfci/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 882, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r53lwssfci/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 928, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r53lwssfci/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1174, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r53lwssfci/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1488, \"height\": 1175, \"label\": \"Table\"}]"
motivation: 现有具身智能体采用通用规划方法，忽视了个体偏好差异，限制了人机协作效果。
method: 提出从少量演示中隐式学习用户偏好，并基于偏好自适应调整规划策略。
result: 在PbP基准测试中验证了偏好跨场景迁移的有效性。
conclusion: 隐式偏好学习可显著提升智能体在多样化规划场景中的个性化适应能力。
---

## Abstract
Effective integration of AI agents into daily life requires them to understand and adapt to individual human preferences, particularly in collaborative roles. Although recent studies on embodied intelligence have advanced significantly, they typically adopt generalized approaches that overlook personal **preferences in planning**. We address this limitation by developing agents that not only learn preferences from few demonstrations but also learn to adapt their planning strategies based on these preferences. Our research leverages the observation that preferences, though implicitly expressed through minimal demonstrations, can generalize across diverse planning scenarios. To systematically evaluate this hypothesis, we introduce PbP benchmark, an embodied benchmark featuring hundreds of diverse preferences spanning from atomic actions to complex sequences. Our evaluation of SOTA methods reveals that while symbol-based approaches show promise in scalability, significant challenges remain in learning to generate and execute plans that satisfy personalized preferences. We further demonstrate that incorporating learned preferences as intermediate representations in planning significantly improves the agent's ability to construct personalized plans. These findings establish preferences as a valuable abstraction layer for adaptive planning, opening new directions for research in preference-guided plan generation and execution.

---

## 论文详细总结（自动生成）

# 论文总结：《Learning to Plan with Personalized Preferences》

## 1. 核心问题与整体含义

- **研究动机**：现有具身智能体（embodied AI agents）在规划任务中通常采用通用化方法，忽略个体用户的个性化偏好。当人类下达模糊指令（如“准备食物”）时，智能体无法自动推断用户的隐含偏好（如洗苹果、切法、放置位置等），需要繁琐的逐项确认，降低了协作效率。
- **整体含义**：本文旨在开发能够从少量人类行为演示中学习用户偏好，并基于所学偏好自适应调整规划策略的智能体，使AI助手能提供个性化、高效的辅助服务，无需用户显式逐一指示每一步细节。

## 2. 方法论

### 核心思想
- 偏好虽隐含在少量演示中，但可以跨多样化的规划场景泛化。
- 提出两阶段框架：
  1. **偏好学习阶段**：从用户的前几个演示（egocentric视频+动作序列）中推断出偏好表示（显式偏好标签或隐式特征）。
  2. **规划阶段**：利用所学偏好作为中间表示，指导智能体在新场景中生成符合偏好的动作序列。

### 关键公式与流程
- **偏好学习**：  
  \( p = f(O; \theta_f) \)  
  其中 \( O = \{(S_i, A_i, M)\} \) 是演示观测（状态、动作、可选地图图），\( p \) 为偏好表示。
- **规划优化**：  
  \( L = \sum_{i} \ell(g(s_i, f(O;\theta_f); \theta_g), a_i) \)  
  其中 \( g(\cdot) \) 是规划函数，将当前状态和偏好表示映射到下一动作。

### 技术细节
- 偏好分为三级：**动作级**（如洗苹果的方式）、**选项级**（如水果放在冰箱还是桌上）、**序列级**（如先洗后切还是切后洗）。
- 构建了基于NVIDIA Omniverse和OmniGibson的**PbP基准**，包含50个场景、290种偏好、5000个测试实例。
- 演示包含第一人称视图、鸟瞰地图和逐帧动作注释（含Omniverse对象ID）。

## 3. 实验设计

### 数据集/场景
- 使用自行构建的**PbP基准测试集**（基于仿真环境），包括三个偏好层级，共5000个测试点，来自15000个演示记录。

### 对比方法
- **视频输入模型**：ViViT、LLaVA-NeXT、EILEV、GPT-4V
- **符号输入模型**：DAG-Opt、Llama3-8B、GPT-4（输入为动作序列文本）
- **设置**：包括端到端生成（直接根据演示+当前状态输出动作序列）和两阶段（先预测偏好标签，再基于标签规划）。并引入“Second-stage (gt)”使用真实偏好标签作为上限。

### 评估指标
- **规划任务**：Levenshtein距离（生成序列与真实序列的差异，动作视为token）
- **偏好预测**：分类准确率

### 额外实验
- **泛化实验**：比较演示和测试场景相同（direct）vs 不同场景/物体（generalization）下的偏好预测准确率。
- **演示数量消融**：1、2、3、5个演示，观察对偏好学习和规划的影响。

## 4. 资源与算力

- 文中明确说明：所有实验在一台配备**8块NVIDIA A100 GPU**的机器上运行。
- **训练时长**：未具体给出ViViT等可训练模型的收敛时间或推理耗时，因此无法量化总体计算成本。

## 5. 实验数量与充分性

- **实验数量**：包括端到端（6种模型×3个偏好层级）、两阶段偏好预测（6种模型×3层级）、两阶段规划（结合预测/真实偏好）、泛化实验（4种模型×2条件）、演示消融（4种模型×2层级×4种数量），总计数十组比较。
- **充分性与公平性**：
  - 覆盖了当前主流的多模态和符号模型，对比全面。
  - 控制了输入格式（视频统一512×512, 8fps; 符号输入同等文本化），解码参数一致（温度0.05, top-k=1等）。
  - 消融实验考虑了演示数量、场景变化等因素，分析了泛化能力。
- **综合评价**：实验设计系统，能够支撑论文结论，但主要基于合成数据，未涉及真实世界的人机交互验证。

## 6. 主要结论与发现

1. **端到端学习效果差**：所有模型在直接生成动作序列时Levenshtein距离接近平均序列长度，说明无法从演示中提取偏好。
2. **两阶段策略显著提升性能**：在偏好预测阶段后，再基于预测偏好规划，Levenshtein距离大幅下降；若使用真实偏好标签，GPT-4和GPT-4V能接近完美规划。
3. **符号模型优于视频模型**：GPT-4（符号输入）在偏好预测准确率和规划距离上均为最优；视频模型（如LLaVA-NeXT）在偏好推断上较弱，但在偏好已知时规划能力尚可。
4. **偏好作为抽象层有效**：显式偏好标签作为中间表示能桥接高层目标和底层动作，增强规划适应性。
5. **泛化挑战**：视频模型对新场景/物体的泛化能力差，容易过拟合到视觉特征；符号模型则不受场景变化影响。
6. **演示数量影响**：增加演示一般提升表现，但过多（如5个）在部分模型中会降低偏好预测准确率，表明存在最优演示数。

## 7. 优点

- **基准创新**：首次构建大规模、多层次偏好的具身规划基准PbP，涵盖从原子动作到复杂序列的290种偏好，可重用可扩展。
- **框架清晰**：将偏好学习与规划解耦为两阶段，系统性地分析了不同模态模型的优劣势，揭示了偏好作为中间表示的价值。
- **实验全面**：不仅评估了多个SOTA模型，还细致测试了泛化能力、演示数量影响，并进行了消融分析，结论可信。
- **动机明确**：针对真实人机协作中偏好隐含、少样本的现实问题，具有应用前景。

## 8. 不足与局限

- **依赖合成数据**：所有演示和测试均基于Omnibuson仿真环境，无法完全复制真实世界的多样性、感知噪声和人类行为的自然变化。
- **偏好标签人为预设**：290种偏好由研究人员定义，可能无法涵盖所有细微的个性化差异，真实偏好可能更复杂或具有重叠。
- **视频模型性能弱**：当前视觉模型在偏好推断上准确率偏低，尤其在高层次序列偏好和泛化场景中，限制了偏好学习的实际可行性。
- **未进行真实机器人实验**：论文仅停留在仿真层面，未在真实机器人平台上验证，限制了方法的实用性。
- **计算资源依赖**：模型（尤其是GPT-4V、GPT-4）依赖商用API，可重复性和成本可能成为障碍。

（完）
