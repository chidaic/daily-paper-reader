---
title: Ad-Hoc Human-AI Coordination Challenge
title_zh: 即席人机协调挑战
authors: "Tin Dizdarević, Ravi Hammond, Tobias Gessler, Anisoara Calinescu, Jonathan Cook, Matteo Gallici, Andrei Lupu, Jakob Nicolaus Foerster"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=FuGps5Zyia"
tags: ["query:player-ai"]
score: 9.0
evidence: 在Hanabi纸牌游戏中的人机协调
tldr: 该论文针对人机协调评估成本高、难以复现的问题，提出Ad-Hoc人机协调挑战(AH2AC2)，在Hanabi游戏中基于大规模人类数据集训练代理智能体作为评估伙伴。该基准为发展可泛化的人机协调AI提供了标准化测试平台。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-fugps5zyia/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1340, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fugps5zyia/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 815, \"height\": 942, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fugps5zyia/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1516, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fugps5zyia/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1519, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fugps5zyia/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 821, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fugps5zyia/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 826, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fugps5zyia/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1228, \"height\": 941, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fugps5zyia/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1229, \"height\": 936, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1540, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1244, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 772, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 881, \"height\": 938, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 932, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 933, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1126, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1138, \"height\": 1456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1098, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 912, \"height\": 528, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 800, \"height\": 1541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 575, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 885, \"height\": 486, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 991, \"height\": 1497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 991, \"height\": 1497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fugps5zyia/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 988, \"height\": 1013, \"label\": \"Table\"}]"
motivation: 在Hanabi等游戏中评估人机协调面临人类实验成本高、结果不可复现的挑战。
method: 构建AH2AC2基准，利用大规模人类数据训练人类代理作为评估伙伴。
result: 提供了可复现且低成本的人机协调评估方法。
conclusion: 人类代理能有效替代真实人类进行协调评估，促进人机协调研究。
---

## Abstract
Achieving seamless coordination between AI agents and humans is crucial for real-world applications, yet it remains a significant open challenge. Hanabi is a cooperative card game featuring imperfect information, constrained communication, theory of mind requirements, and coordinated action -- making it an ideal testbed for human-AI coordination. However, its use for human-AI interaction has been limited by the challenges of human evaluation. In this work, we introduce the Ad-Hoc Human-AI Coordination Challenge (AH2AC2) to overcome the constraints of costly and difficult-to-reproduce human evaluations. We develop \textit{human proxy agents} on a large-scale human dataset that serve as robust, cheap, and reproducible human-like evaluation partners in AH2AC2. To encourage the development of data-efficient methods, we open-source a dataset of 3,079 games, deliberately limiting the amount of available human gameplay data. We present baseline results for both two- and three- player Hanabi scenarios. To ensure fair evaluation, we host the proxy agents through a controlled evaluation system rather than releasing them publicly. The code is available at \href{https://github.com/FLAIROx/ah2ac2}{https://github.com/FLAIROx/ah2ac2}.

---

## 论文详细总结（自动生成）

好的，作为资深学术论文分析助手，现根据您提供的论文内容，对《即席人机协调挑战》一文进行结构化、深入且客观的总结。

### 论文总结：Ad-Hoc Human-AI Coordination Challenge (AH2AC2)

#### 1. 论文的核心问题与整体含义

- **研究动机与背景**：随着AI在医疗、自动驾驶、机器人等领域的广泛应用，实现AI与人类之间无缝、有效的协调变得越来越重要。然而，传统的自对弈(Self-Play)训练方法容易导致AI代理过度拟合特定策略，难以与未经共同训练的人类或其他AI泛化协作。现有的人机协调评估方法依赖昂贵、耗时且难以复现的人类实验，严重阻碍了该领域的发展。
- **核心问题**：为克服人机协调研究中，因依赖人类评估而导致的高成本、低可复现性及缺乏标准化基准的瓶颈。
- **整体含义**：论文旨在构建一个标准化的、低成本、可复现的评估框架，用以衡量AI代理在复杂、部分可观察的协作场景（如经典纸牌游戏Hanabi）中与人类伙伴进行即席协调(Ad-Hoc Teamplay)的能力。这项工作为研究数据高效的人机协作算法提供了关键平台。

#### 2. 论文提出的方法论

- **核心思想**：开发“人类代理”(Human Proxy Agents)作为替代昂贵人类实验的评估伙伴。这些代理通过结合行为克隆(BC)和正则化强化学习(RL)进行训练，使其既具备人类风格的策略，又比纯粹的模仿学习更加稳健。论文围绕此思想提出了“即席人机协调挑战”(AH2AC2)基准。
- **关键技术细节**：
    1.  **数据收集与限制**：从`hanab.live`平台收集了大规模的人类游戏数据（101,096场双人, 46,525场三人游戏），但仅开放小部分(3,079场)给参赛者，以鼓励开发数据高效的方法。
    2.  **人类代理训练 (Human-Data-Regularised IPPO, HDR-IPPO)**：
        - **第一步：行为克隆(BC)**：首先在一个LSTM网络上，通过监督学习最小化预测动作与真实人类动作的交叉熵损失，训练一个初始的BC策略`π^BC_θ`。
        - **第二步：正则化强化学习**：以BC策略的权重初始化后续策略`π^HP_θ`。然后使用独立近端策略优化(IPPO)算法进行强化学习微调，同时在目标函数中加入一个KL散度正则化项，以确保微调后的策略不会过度偏离人类风格。公式表达为：`L_HDR-IPPO(θ) = (1-λ) · L_IPPO(θ) + λ · DKL(π^BC_θ'(.|τ) || π^HP_θ(.|τ))`。其中，`λ`是平衡强化学习性能和人类相似度的权重。
- **算法流程**：该流程可简述为：收集人类数据 → 训练BC模型 → 使用BC模型参数初始化IPPO网络 → 在Hanabi环境中进行IPPO自对弈训练 → 每一步训练时，添加KL散度作为惩罚项，约束当前策略不要远离BC策略 → 最终得到人类代理。
- **评估系统**：论文通过一个受控的API托管这些人类代理，参赛者需预先注册实验，这使得评估过程一致且可复现，并防止参赛者针对代理行为进行“调优”。

#### 3. 实验设计

- **数据集与场景**：
    - **大型私有数据集**：101,096场双人游戏和46,525场三人游戏，用于训练论文提供的人类代理。
    - **开放数据集**：3,079场游戏（1,858场双人, 1,221场三人），供参赛者开发自己的AI代理。
    - **评估场景**：Hanabi游戏的双人(2P)和三人(3P)模式。
- **Benchmark**：AH2AC2包含两个评估部分：
    1.  **协调能力评估**：参赛者的AI代理与论文提供的人类代理进行1,000场游戏，以**平均分**和**中位数分数**作为主要指标。
    2.  **动作预测挑战(可选)**：在未公开的人类游戏数据集上，评估AI代理预测人类动作的能力，使用**交叉熵损失**作为指标。
- **对比方法**：论文对比了多种基线方法：
    - **IPPO**：纯自对弈训练。
    - **BC**：仅在开放数据集上训练的模仿学习。
    - **HDR-IPPO**：仅在开放数据集上使用论文方法训练。
    - **BR-BC**：对BC策略的最佳响应。
    - **OBL**：强大的零样本协调方法，不使用人类数据。
    - **OP**：其他-游戏方法，用于零样本协调。
    - **FCP**：虚构共玩方法，一种基于种群的方法。
    - **DeepSeek-R1**：大型语言模型，提供基础能力基准。

#### 4. 资源与算力

- **文中明确指出**：训练人类代理使用的总时间步为5e9（50亿）。用于训练和评估的环境数量为1,024个训练环境和512个评估环境。
- **未明确说明**：文中未明确报告所使用的GPU型号、数量以及具体的训练总时长。关于参考基线（如FCP）的计算量，论文提到“由于计算需求巨大，我们仅用一个种子训练FCP代理”，暗示其成本较高。总体而言，论文提供了关于训练迭代次数的信息，但未提供硬件层面的具体细节。

#### 5. 实验数量与充分性

- **实验数量**：实验数量非常丰富。
    - **人类代理验证**：进行了跨游戏测试（各配置15,000场）、动作预测性能评估（对比BC和人类代理）、行为指标分析（基于50,000场生成数据和大型数据集）。
    - **消融实验**：对HDR-IPPO中的KL正则化权重`λ`进行了详细的消融分析，比较了8个不同`λ`值（0.00-0.70）下的自对弈得分、跨游戏性能、测试集准确率等。
    - **基线对比**：在标准化测试中，每种基线方法（BC， HDR-IPPO, BR-BC）都使用了3个不同随机种子进行训练，IPPO、FCP等至少使用1个种子。结果通过1,000场游戏进行评估。DeepSeek-R1因资源限制仅评估了100场。
- **充分性与公平性**：
    - **充分性**：实验设计覆盖了对人类代理有效性（协调性与相似性）的全方位验证，以及对不同基线方法的广泛比较，实验量充足。
    - **客观与公平**：实验设置较为客观。采用1,000场游戏评估来降低随机性；对不同方法进行对比；评估系统采用预注册和受控API，防止作弊。不过，某些基线的对比可能不完全公平，例如OBL在整体性能上优于HDR-IPPO，但OBL使用了更大的训练数据和计算资源。而HDR-IPPO方法在资源受限且追求数据效率的场景下进行评估，其排名较低是符合预期的。

#### 6. 论文的主要结论与发现

- **人类代理的有效性**：通过HDR-IPPO训练的人类代理在自对弈中显著优于纯BC代理，且在与BC代理的跨游戏中保持了良好的一致性，验证了其既是“高玩”也是“像人类”的特性。
- **当前方法的局限性**：
    - **零样本协调方法领先**：无需人类数据的OBL方法在双人场景中取得了最高的平均分（21.04），超过了所有依赖有限人类数据的方法（如HDR-IPPO，得分为12.76）。
    - **数据利用效率待提升**：当前方法无法有效利用有限的人类数据进行协调，依赖人类数据的方法（如BR-BC, HDR-IPPO）表现不如OBL，这表明存在研究空白。
    - **基于种群的FCP方法在Hanabi中表现不佳**，表明其在高复杂度的部分可观察环境中存在局限。
    - **大模型(DeepSeek-R1)虽有一定基础能力，但仍远未达标**，即使在知晓H-约定后，其表现仍远不如OBL。
- **AH2AC2的挑战性**：该基准成功地展示了人机协调在当前AI技术下的巨大挑战，为未来的研究提供了清晰方向。

#### 7. 优点

1.  **开创性基准**：首次提出了一个标准化、可复现的人机协调评估框架和开放的Hamabi人机游戏数据集，填补了该领域的空白。
2.  **高质量评估伙伴**：训练的人类代理经过多维度验证，证明其兼具人类风格和高超技艺，是替代难以获取的真实人类进行大规模评估的理想选择。
3.  **促进数据效率研究**：通过故意提供有限的数据，激励研究社区开发对少量人类数据高效利用的方法。
4.  **实验设计全面严谨**：对代理的自身性能、人类相似性、行为特征等做了详尽的量化分析，并提供了全面的消融实验。
5.  **评估机制完善**：通过API托管和预注册制度，确保了评估的公平性和结果的可比性。

#### 8. 不足与局限

1.  **正则化权重λ的敏感性**：HDR-IPPO的性能高度依赖于`λ`的选择，需要针对不同环境和数据进行调参。论文的消融实验本身也证明了这一点。
2.  **代理的现实替代性不完美**：尽管代理与人类行为相似，但论文指出其最终验证仍需通过真实人类实验（直接人-AI对弈），这并未在当前工作中完成。
3.  **基准覆盖范围有限**：当前基准仅涵盖2人和3人标准Hanabi任务。游戏变种（如彩虹卡）以及更多玩家的场景未被覆盖，限制了其泛化性评估。
4.  **基线计算量不透明**：OBL等强大的基线方法（如OBL）的训练算力和数据量未在论文中详述，可能让不同方法的对比存在不公平因素。
5.  **LLM评估不充分**：对DeepSeek-R1的评估仅进行了100场游戏（远低于标准的1,000场），且未进行动作预测挑战。该部分实验的充分性和显著性有待提升。
6.  **潜在的分布偏差**：训练数据仅来自使用H-组约定的玩家社区。尽管认为其包含多种玩法，但AI代理仍可能对此特定社区风格过拟合，在面对非此约定体系的人类时表现可能不佳。

（完）
