---
title: Can Large Language Models Master Complex Card Games?
title_zh: 大型语言模型能掌握复杂纸牌游戏吗？
authors: "Wei Wang, Fuqing Bie, Junzhe Chen, Dan Zhang, Shiyu Huang, Evgeny Kharlamov, Jie Tang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cmN8Wbvanr"
tags: ["query:player-ai"]
score: 10.0
evidence: 大型语言模型作为AI代理玩复杂纸牌游戏
tldr: 该论文探索了大型语言模型在掌握复杂纸牌游戏方面的潜力。通过在八个不同纸牌游戏上系统评估微调效果，发现LLMs经过高质量游戏数据微调后能够掌握多种游戏，但保留通用能力方面存在挑战。这项工作验证了LLMs作为游戏AI代理的可行性，并为后续研究提供了基准。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cmn8wbvanr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 727, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cmn8wbvanr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cmn8wbvanr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cmn8wbvanr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 644, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cmn8wbvanr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 700, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cmn8wbvanr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 697, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cmn8wbvanr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 698, \"height\": 467, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cmn8wbvanr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cmn8wbvanr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 681, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cmn8wbvanr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 656, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cmn8wbvanr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1428, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cmn8wbvanr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1424, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cmn8wbvanr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1423, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cmn8wbvanr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cmn8wbvanr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 245, \"label\": \"Table\"}]"
motivation: 检验大型语言模型在复杂游戏领域是否能达到类似AlphaGo的成功。
method: 在八个纸牌游戏上微调LLMs并评估其游戏能力和通用能力保留。
result: LLMs经过微调能掌握纸牌游戏，但通用能力有所下降。
conclusion: LLMs有潜力成为游戏代理，但需要平衡专业化与泛化。
---

## Abstract
Complex games have long been an important benchmark for testing the progress of artificial intelligence algorithms. AlphaGo, AlphaZero, and MuZero have defeated top human players in Go and Chess, garnering widespread societal attention towards artificial intelligence. Concurrently, large language models (LLMs) have exhibited remarkable capabilities across various tasks, raising the question of whether LLMs can achieve similar success in complex games. In this paper, we explore the potential of LLMs in mastering complex card games. We systematically assess the learning capabilities of LLMs across eight diverse card games, evaluating the impact of fine-tuning on high-quality gameplay data, and examining the models' ability to retain general capabilities while mastering these games. Our findings indicate that: (1) LLMs can approach the performance of strong game AIs through supervised fine-tuning on high-quality data, (2) LLMs can achieve a certain level of proficiency in multiple complex card games simultaneously, with performance augmentation for games with similar rules and conflicts for dissimilar ones, and (3) LLMs experience a decline in general capabilities when mastering complex games, but this decline can be mitigated by integrating a certain amount of general instruction data. The evaluation results demonstrate strong learning ability and versatility of LLMs. The code is available at 
https://github.com/THUDM/LLM4CardGame

---

## 论文详细总结（自动生成）

# 论文《Can Large Language Models Master Complex Card Games?》中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：复杂游戏（如围棋、国际象棋）长期作为AI算法能力的试金石。AlphaGo、AlphaZero、MuZero等专用AI已达到超人类水平。但大型语言模型（LLMs）在通用任务（知识问答、数学、编码）上表现卓越，其是否能在复杂游戏中同样取得类似成功，成为自然的研究问题。
- **本文目的**：系统评估LLMs在**八个高复杂度纸牌游戏**上通过**监督微调**掌握游戏的能力，并考察其对多游戏的同时学习、以及通用能力的保留情况。
- **核心贡献**：首次提出在多个高复杂度游戏上全面评估LLMs的学习能力；通过强AI生成高质量轨迹数据避免从头探索的高成本；实验表明LLMs可以同时掌握多个复杂游戏，且通用能力下降可通过混合通用数据缓解。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用现有强游戏AI（教师模型）生成高质量的游戏交互轨迹（observation-action pairs），通过**监督微调**让LLM学习这些“成功经验”，从而掌握游戏。对比AlphaGo等需要从环境探索的方法，该方法更高效。
- **技术细节**：
  - **八个游戏**：DouDizhu（斗地主）、GuanDan（掼蛋）、Riichi Mahjong（日本麻将）、Uno、Gin Rummy、Leduc Hold’em、Limit Texas Hold’em、No-limit Texas Hold’em。
  - **数据生成**：使用教师模型（DouZero、DanZero、专家数据、DQN、规则模型等）与对手对战，仅保留**获胜方**的步数，且过滤掉合法动作数≤1的样本。每个样本为一个observation-action pair。
  - **指令微调格式**：为每个游戏设计包含游戏规则、当前状态、历史动作、合法动作等信息的提示模板，输出要求为JSON格式的动作。
  - **微调方法**：使用LoRA（秩8，alpha 16）进行参数高效微调，学习率1e-4，余弦调度，batch size 128，训练1 epoch。
- **无需修改模型架构**：LLMs通用架构可直接应用于不同游戏，仅需更换提示模板，对比传统强化学习方法需为每个游戏专门设计网络结构。

## 3. 实验设计：数据集 / 场景、基准、对比方法

- **数据集**：
  - 每个游戏生成大量轨迹数据，过滤后训练规模：斗地主、掼蛋、麻将各100万条；其他游戏各40万条。
  - 混合训练集：共310万条，各游戏数量按复杂度经验分配（如掼蛋95万，斗地主70万等）。
- **场景**：
  - **RQ1**：在单个游戏上微调，评估随数据量变化的性能变化。
  - **RQ2**：在所有游戏混合数据上微调，评估多任务学习。同时分析**游戏间相互影响**（相似规则促进，不同规则冲突）。
  - **RQ3**：在通用基准（MMLU-Pro、Math-500、HumanEval）上评估通用能力下降，并尝试用通用数据恢复。
- **基准**：
  - **游戏内性能**：斗地主用胜率；掼蛋用回合胜率；其余用奖励分数（平均排名或RLCard框架分数）。
  - **对比方法**：
    - **API模型**：GPT-4o-mini, GPT-4o, GLM-4-air, GLM-4-plus, DeepSeek-V3, DeepSeek-R1。
    - **未微调的基座模型**：Qwen2.5-7B-Instruct, Llama3.1-8B-Instruct, GLM4-9B-Chat。
    - **教师模型**：DouZero, DanZero, Mortal AI等作为性能上界。
  - **模型类型与大小**：Qwen2.5 (0.5B~14B), Llama3.1-8B, GLM4-9B。
- **评估方式**：LLM与固定对手（规则模型或随机）对战，每游戏对战不同局数（斗地主1000局，掼蛋20局等）。

## 4. 资源与算力

- **训练硬件**：8块 H100 GPU（80GB）的服务器；CPU为Intel Xeon Platinum 8476C。
- **训练时长**（以1百万样本为例，单个模型）：
  - 斗地主：11-14小时（因模型而异）。
  - 掼蛋：21-29小时。
- **对比**（附录A.1）：
  - DouZero：2 CPU + 4×1080Ti，训练30天，数据量未公开。
  - DanZero：4 CPU + 1×RTX 3070，训练30天，数据量未公开。
  - 本文方法在算力相当或更优的情况下，训练时间显著缩短（数小时 vs 30天），但需注意数据已由教师AI生成，并非从头探索。

## 5. 实验数量与充分性

- **实验数量**：覆盖8个游戏、3类模型（Qwen/Llama/GLM）、5个参数量级（0.5B~14B）、3个通用基准。每组实验均记录随数据量变化的学习曲线。
- **消融分析**：
  - 不同游戏间的相互影响（单游戏微调模型在其他游戏上的表现，表4-6）。
  - 通用能力恢复实验（混合通用数据后的游戏性能变化）。
  - 角色不平衡分析（斗地主农民角色因数据过滤导致性能差）。
- **主观评价**：实验设计系统，覆盖三方面研究问题，对比充分（API模型、基座模型、教师模型）。但未进行多次重复（如不同随机种子）的统计误差棒，可能受单次运行影响；游戏内评估对局数有限（如掼蛋20局），统计效力稍弱。

## 6. 论文的主要结论与发现

1. **LLMs能掌握复杂纸牌游戏**：通过监督微调高质量数据，性能可接近甚至达到强AI（如斗地主胜率接近DouZero；麻将平均排名优于Mortal AI）。数据量增加，性能持续提升。
2. **多游戏同时学习可行**：混合模型在所有游戏上表现均优于API和基座模型，尤其在复杂游戏（斗地主、掼蛋、麻将）提升显著。相似规则游戏（斗地主与掼蛋；三种德州扑克）之间存在正向迁移，不同规则游戏间则存在冲突。
3. **通用能力下降但可恢复**：微调后MMLU-Pro、Math-500、HumanEval得分均下降。通过在混合训练中加入少量通用数据（知识、数学、编码各2万条），可在基本保持游戏性能的同时恢复大部分通用能力。

## 7. 优点：方法或实验设计上的亮点

- **高质量数据驱动**：利用强AI生成轨迹并过滤获胜方，避免LLMs从零探索的高成本，且保证数据质量。
- **多维度评估**：不仅评估单一游戏，还研究多任务学习、任务间迁移、通用能力退化，结论全面，具有实际指导意义。
- **通用性展示**：LLM无需修改架构即可处理八个不同复杂度的游戏，对比传统RL方法需为每个游戏设计独立网络，体现了LLM作为通用学习器的优势。
- **角色平衡分析**：发现斗地主中数据过滤导致农民角色低质量数据，影响模型均衡学习，这个发现对数据构建有重要启示。

## 8. 不足与局限

- **推理速度慢**：LLM参数量大（7B/8B/9B），游戏内平均决策时间远超专用AI（如DouZero），不适合实时对战。
- **数据偏差**：仅保留获胜方数据可能引入偏差（如斗地主农民角色被动胜利的低质量样本），导致角色性能不均衡。
- **实验覆盖有限**：
  - 仅评估8个纸牌游戏，未覆盖棋类、电子游戏等更复杂领域。
  - 通用基准仅三类（知识、数学、编码），未全面评估指令遵循、推理等能力。
  - 未报告多次实验的误差棒或统计显著性，单次结果可能不稳定。
- **计算开销**：虽然训练时间短，但数据生成依赖已有的强AI（需计算资源提前生成），且教师模型本身需专门训练。论文未定量比较总计算量（生成数据+微调 vs 从头训练）。
- **未探讨强化学习与LLM的混合方法**：仅采用监督微调，未尝试利用LLM进行探索与自我博弈，可能限制了性能上限。

（完）
