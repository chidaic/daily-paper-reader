---
title: "SPC: Evolving Self-Play Critic via Adversarial Games for LLM Reasoning"
title_zh: SPC：通过对抗性博弈进化自博弈评论家以改进LLM推理
authors: "Jiaqi Chen, Bang Zhang, Ruotian Ma, Peisong Wang, Xiaodan Liang, Zhaopeng Tu, Xiaolong Li, Kwan-Yee K. Wong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=JddJvNSiHk"
tags: ["query:player-ai"]
score: 4.0
evidence: 利用对抗性自博弈进行LLM推理评估
tldr: 该论文针对LLM推理步骤评估缺乏人工标注的问题，提出了自博弈评论家方法。通过微调两个模型副本分别扮演狡猾生成器和评论家，在对抗性博弈中提升评论家识别错误推理步骤的能力。实验表明该方法无需人工标注即可有效评估推理步骤正确性，但其核心仍是评估而非直接游戏玩家建模，与要求属于间接相关。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jddjvnsihk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1224, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jddjvnsihk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jddjvnsihk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1387, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jddjvnsihk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1408, \"height\": 1412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jddjvnsihk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1418, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jddjvnsihk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1415, \"height\": 1188, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jddjvnsihk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1406, \"height\": 1607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jddjvnsihk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1416, \"height\": 746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jddjvnsihk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1418, \"height\": 715, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jddjvnsihk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1203, \"height\": 658, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jddjvnsihk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1404, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jddjvnsihk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 958, \"label\": \"Table\"}]"
motivation: LLM推理步骤评估依赖于昂贵的人工标注。
method: 通过自博弈训练生成器和评论家进行对抗性博弈。
result: 评论家能够有效检测生成器产生的推理错误。
conclusion: 自博弈框架可替代人工标注用于推理评估。
---

## Abstract
Evaluating the step-by-step reliability of large language model (LLM) reasoning, such as Chain-of-Thought, remains challenging due to the difficulty and cost of obtaining high-quality step-level supervision. In this paper, we introduce Self-Play Critic (SPC), a novel approach where a critic model evolves its ability to assess reasoning steps through adversarial self-play games, eliminating the need for manual step-level annotation. SPC involves fine-tuning two copies of a base model to play two roles, namely a "sneaky generator" that deliberately produces erroneous steps designed to be difficult to detect, and a "critic" that analyzes the correctness of reasoning steps. These two models engage in an adversarial game in which the generator aims to fool the critic, while the critic model seeks to identify the generator's errors. Using reinforcement learning based on the game outcomes, the models iteratively improve; the winner of each confrontation receives a positive reward and the loser receives a negative reward, driving continuous self-evolution. Experiments on three reasoning process benchmarks (ProcessBench, PRM800K, DeltaBench) demonstrate that our SPC progressively enhances its error detection capabilities (e.g., accuracy increases from 70.8% to 77.7% on ProcessBench) and surpasses strong baselines, including distilled R1 model. Furthermore, SPC can guide the test-time search of diverse LLMs and significantly improve their mathematical reasoning performance on MATH500 and AIME2024, surpassing those guided by state-of-the-art process reward models.

---

## 论文详细总结（自动生成）

# 论文总结：SPC: Evolving Self-Play Critic via Adversarial Games for LLM Reasoning

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：大规模语言模型（LLM）的逐步推理过程（如Chain-of-Thought）的可靠性评估十分困难，因为获取高质量、细粒度的步骤级标注既昂贵又耗时。
- **背景**：现有的过程验证模型（如过程奖励模型PRM）需要大量人工标注的步骤正确性数据；且LLM更新快，人工标注容易过时；此外，标注仅限于正确性评分，缺乏实质性的反馈（批评）。
- **目标**：提出一种无需人工步骤标注的自我进化方法，训练一个能识别推理步骤错误并提供文本批评的评论家模型，以提升LLM推理的可靠性和测试时搜索效果。

## 2. 方法论：核心思想、技术细节、算法流程
- **核心思想**：采用自博弈（Self-Play）框架，让两个角色——一个“狡猾生成器”（Sneaky Generator）和一个“步骤评论家”（Step Critic）——进行对抗性游戏，通过强化学习迭代提升评论家的错误检测能力。
- **关键角色**：
  - **狡猾生成器**：将正确的推理步骤转换为微妙的错误步骤，目标是既降低LLM解题成功率又欺骗评论家。
  - **步骤评论家**：基于部分推理路径，判断最后一个步骤的正确性，并输出文本批评和结论。
- **初始化**：
  - 生成器：使用PRM800K中正确-错误步骤对，借助GPT-4生成转换链（包括5种预定义错误类型），通过监督微调（SFT）初始化策略πθ。
  - 评论家：使用DeepSeek-R1-Distill-Qwen-7B生成初始长批评，再由GPT-4o精简为标准化批评，同样通过SFT初始化。
- **对抗性游戏**：每轮自博弈中，从不同LLM求解器生成的多条解答中随机选取正确步骤，由生成器转为错误步骤；若成功影响求解成功率（原始步骤成功率≥75%，错误步骤成功率=0%）则视为有效错误步骤，然后交给评论家判断。奖励设计：
  - 生成器：成功欺骗评论家得+1，被识破或未成功影响求解得-1。
  - 评论家：正确识别错误得+1，被欺骗得-1。
- **强化学习**（RL）：采用离线RL，目标函数包含重要性采样权重、优势估计（减去基线并使用KL惩罚），使用RLOO/GRPO风格的训练。迭代训练时采用不对称进化策略：当生成器弱于评论家时，使用较弱生成器与较弱评论家对抗（如Sneaky-1 vs Critic-0）以保持游戏平衡，防止过拟合。
- **测试时间搜索**：在LLM逐步生成解答时，每步后由SPC判断正确性；若错误则重新生成（最多5次），若正确继续，可结合自一致性（majority vote）。

## 3. 实验设计
- **数据集**：
  - 推理过程评估：ProcessBench（3400例，来自GSM8K、MATH、OlympiadBench、Omni-MATH）、PRM800K（1341对步骤）、DeltaBench（1542例，来自R1、QwQ长CoT）。
  - 数学推理增强：MATH500、AIME2024。
- **Benchmark**：步骤正确性预测的召回率（正确/错误步骤的召回率、算术平均、调和平均）以及最终解题准确率。
- **对比方法**：
  - 过程奖励模型（PRM）：Math-Shepherd-PRM-7B、Qwen2.5-Math-7B-PRM800K。
  - 提示LLM作为评论家：Llama-3.1-8B/70B-Instruct、Qwen2.5-7B/32B-Instruct、GPT-4o、DeepSeek-R1-Distill-Qwen-7B。
  - 自身消融：不同自博弈轮次、是否使用配对样本、是否平衡对抗等。

## 4. 资源与算力
- 论文**未明确说明**使用的GPU型号、数量、训练时长等算力细节。仅在附录C.3给出训练超参数：SFT阶段batch size=64，学习率5e-6，3个epoch；RL阶段batch size=64，学习率2e-6。未提及硬件配置。

## 5. 实验数量与充分性
- **实验数量**：主要包含三类实验：
  1. 步骤正确性预测：在ProcessBench（表1）、PRM800K和DeltaBench（表2）上比较多个指标。
  2. 指导测试时搜索：在MATH500和AIME2024上，对三个不同LLM求解器（Llama-3.1-8B、Qwen2.5-32B、DeepSeek-R1-Distill-Qwen-7B）评估，结合自一致性和其他verifier对比（表3）。
  3. 消融实验：图3展示了不同策略（是否用配对样本、是否平衡游戏）对评论家准确率的影响，以及生成器攻击成功率和胜率。
- **充分性**：实验覆盖了多个基准、多种基线和消融设置，结果清晰展示了SPC的进化趋势和优势。但测试时搜索部分只评估了数学推理，未扩展到其他领域。总体客观、公平，对比方法包含当前主流模型。

## 6. 主要结论与发现
- SPC在三个推理过程基准上逐步进化：ProcessBench平均准确率从70.8%升至77.7%，PRM800K从71.0%升至75.8%，DeltaBench从54.9%升至60.5%，均超越同等规模的蒸馏R1模型和所有PRM基线。
- SPC能有效指导LLM测试时搜索，在MATH500和AIME2024上显著提升三个不同类型LLM的解题性能，超越现有过程奖励模型。
- 自博弈中的平衡对抗策略（如Sneaky-1 vs Critic-0）对持续进化至关重要，不平衡会导致性能退化。
- 生成器从求解器和评论家双方获得奖励信号非常重要，否则攻击成功率大幅下降。

## 7. 优点
- **创新性**：首次将自博弈对抗学习应用于步骤级评论家训练，完全无需人工步骤标注，自动生成正负样本。
- **实用性**：评论家不仅输出正确性判断，还能生成文本批评，可提供更丰富的反馈；且能泛化到长CoT推理模型（如R1）。
- **有效性**：在多个基准上达到SOTA，且通过迭代不断改进，验证了自进化能力。
- **公平性**：实验设计考虑了多种基线（包括同规模PRM、不同大小LLM提示、蒸馏模型），并进行了充分的消融分析。

## 8. 不足与局限
- **领域限制**：当前实验仅集中在数学推理任务，尚未扩展到其他复杂推理领域（如代码、科学推理等），泛化性有待验证。
- **算力开销**：论文未报告具体GPU小时数，自博弈迭代需生成大量数据并多次训练，实际资源消耗可能较大，可重复性受限。
- **偏差风险**：生成器依赖预定义错误类型（5种），可能无法覆盖所有真实错误；评论家的初始化使用了GPT-4和DeepSeek-R1，可能存在标注偏差。
- **潜在负面社会影响**：狡猾生成器技术可能被滥用于产生误导性信息；虽然论文提及可加强安全审查，但未提供具体防护措施。
- **测试时搜索效率**：每步调用评论家，会增加推理延迟和计算成本，文中未讨论实际效率。

（完）
