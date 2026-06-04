---
title: "Craftium: Bridging Flexibility and Efficiency for Rich 3D Single- and Multi-Agent Environments"
title_zh: Craftium：桥接灵活性与效率，构建丰富的3D单代理和多代理环境
authors: "Mikel Malagón, Josu Ceberio, Jose A. Lozano"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=htP5YRXcS9"
tags: ["query:player-ai"]
score: 8.0
evidence: 可定制的3D游戏环境构建平台，用于代理训练
tldr: 现有2D环境无法满足3D空间推理需求，而复杂3D环境计算昂贵且缺乏可定制性。本文提出Craftium，一个高度可定制、易用的平台，用于构建丰富3D单/多智能体环境。其支持多种复杂度的环境，从单智能体导航到多智能体协作，为强化学习和智能体训练提供了高效灵活的测试床。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 723, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1511, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 319, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1096, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 754, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 406, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1637, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1749, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 835, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1715, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1804, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1681, \"height\": 1392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1776, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1778, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 549, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 814, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1402, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1708, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1250, \"height\": 1221, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1820, \"height\": 68, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1439, \"height\": 1075, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1796, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1776, \"height\": 1052, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1808, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 530, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1806, \"height\": 1181, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1522, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1254, \"height\": 707, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1399, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 498, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1649, \"height\": 1066, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1005, \"height\": 403, \"label\": \"Table\"}]"
motivation: 缺乏灵活高效且支持多智能体的3D环境平台，限制代理训练。
method: 开发Craftium平台，提供基于体素的3D环境构建和灵活定制接口。
result: 展示了多种复杂度和类型的3D环境，支持单/多智能体任务。
conclusion: Craftium为3D智能体研究提供了高效灵活的基础设施。
---

## Abstract
Advances in large models, reinforcement learning, and open-endedness have accelerated progress toward autonomous agents that can learn and interact in the real world. To achieve this, flexible tools are needed to create rich, yet computationally efficient, environments. While scalable 2D environments fail to address key real-world challenges like 3D navigation and spatial reasoning, more complex 3D environments are computationally expensive and lack features like customizability and multi-agent support. This paper introduces Craftium, a highly customizable and easy-to-use platform for building rich 3D single- and multi-agent environments. We showcase environments of different complexity and nature: from single- and multi-agent tasks to vast worlds with many creatures and biomes, and customizable procedural task generators. Benchmarking shows that Craftium significantly reduces the computational cost of alternatives of similar richness, achieving +2K steps per second more than Minecraft-based frameworks.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：当前强化学习（RL）与具身智能体研究依赖环境进行训练与评估，但现有环境存在严重权衡：**2D环境**（如ALE、MiniGrid）虽然高效但无法提供3D导航、空间推理等真实世界挑战；**3D环境**（如MineDojo、Habitat）虽然丰富但计算昂贵、缺乏可定制性，且大多不支持多智能体场景。此外，闭源游戏（如Minecraft）限制了修改权限，而基于领域特定语言（DSL）的平台（如VizDoom）开发困难且缺乏3D特性。这些问题特别影响计算密集型领域（如连续RL、无监督环境设计、多智能体RL）。
- **整体含义**：需要一种**灵活、高效、易用**的平台，能够创建丰富的3D单/多智能体环境，同时支持自定义和开源扩展，以加速自主智能体研究。

### 2. 方法论
- **核心思想**：基于开源体素游戏引擎**Luanti**（原名Minetest），通过修改其源码，使其支持RL/MARL所需功能，并提供Python接口（Gymnasium / PettingZoo）。用户通过Lua脚本（而不是DSL）定义环境逻辑，利用Luanti强大的Modding API实现高度定制。
- **关键技术细节**：
  - **架构**：Luanti服务器运行环境逻辑（由世界数据库和Lua mod定义），每个智能体对应一个客户端，客户端负责渲染并通过通信通道与Python库交互。Python库作为桥梁，发送动作、接收观察和奖励。
  - **观察**：RGB图像（可定制尺寸、通道数），支持帧跳过、帧堆叠。
  - **动作**：默认包含21个键盘动作（二进制）和鼠标移动（Δx,Δy ∈ [-1,1]²）。提供**BinaryActionWrapper**和**DiscreteActionWrapper**简化动作空间。
  - **奖励与终止**：通过扩展Luanti API（新增函数如`set_reward`, `set_termination`, `set_reward_once`等），在Lua脚本中定义奖励和终止条件。
  - **多智能体支持**：通过修改引擎支持多个客户端（每个智能体一个），并实现同步/异步更新机制，确保环境一致性。支持软重置避免频繁重启。
  - **环境创建**：两步走：①生成世界（可使用预设或自定义地图生成器）；②编写Lua mod定义行为（如挖树得奖励、死亡终止）。
  - **算法流程示例**：调用`gym.make("Craftium/Room-v0")`，循环`obs, r, tm, tc, inf = env.step(action)`，检查`tm`或`tc`后重置。

### 3. 实验设计
- **数据集/场景**：论文未使用外部数据集，而是**自建多种环境**展示平台能力：
  - **单智能体RL**：5个任务（ChopTree, SmallRoom, Room, Speleo, SpidersAttack），使用64×64 RGB图像观察，离散动作空间。
  - **多智能体RL**：1v1格斗环境（MultiAgentCombat），采用自对弈训练。
  - **开放世界**：基于VoxeLibre（Luanti社区游戏）的64K×64K×64K块世界，包含生物、怪物、技能树（工具、狩猎、防御三条分支），用于评估具身智能。
  - **程序化环境生成**：用于连续RL（CRL），自动生成10个难度递增的地牢环境，智能体需导航、击败敌人、收集钻石。
- **基准（Benchmark）**：
  - **性能对比**：与VizDoom和MineDojo比较每秒步数（steps/s）。在单NVIDIA A5000 GPU + Intel Xeon Silver 4309Y CPU上，Craftium平均2746步/秒，VizDoom 2091步/秒，MineDojo仅71.87步/秒（Craftium快约38倍）。
  - 还对比了并行环境（Craftium可达12K步/秒）、不同分辨率、世界复杂度、智能体数量对性能的影响。
- **对比方法**：
  - 单智能体RL任务：仅使用PPO（来自CleanRL）作为示例，未与其他算法对比（目的是展示环境可用性）。
  - 开放世界任务：对比PPO+LSTM与LLaVA-Agent（零样本），结果显示LLaVA能解锁更多技能。
  - CRL：对比从头训练（FS）与L2正则化微调（FT-L2），FT-L2在部分任务上表现更好。

### 4. 资源与算力
- **硬件**：单块NVIDIA A5000 GPU（24GB）和Intel Xeon Silver 4309Y CPU（16核）。未说明训练时长或GPU的具体使用模式（如是否用于渲染或仅用于训练）。
- **训练时长**：单智能体RL任务每个训练1M步（未说明实际时间），开放世界PPO+LSTM训练1M步，LLaVA-Agent约7000次迭代（1小时限制）。CRL中每个任务训练1M步。
- **未明确说明**：总GPU小时数、能源消耗、训练成本等细节未给出。

### 5. 实验数量与充分性
- **实验数量**：
  - 单智能体RL：5个环境，每个5次独立运行（seed不同），共25次训练。
  - 多智能体RL：1个环境，5次运行。
  - 开放世界：2种方法（PPO+LSTM和LLaVA-Agent），各10次运行。
  - CRL：2种方法（FS和FT-L2），在10个环境上各5次运行（？文中图19展示了多个环境但未说明重复次数）。
  - 性能基准：每个框架3个环境×5次重复，共45次测量。
  - 额外基准（并行、分辨率、复杂度、智能体数量等）：每种设置5次重复。
- **充分性**：
  - 性能对比充分，多次重复并报告均值和标准差，确保统计可靠性。
  - 功能展示覆盖多种使用场景（RL、MARL、CRL、具身AI），体现平台通用性。
  - **不足**：没有与类似框架（如MiniWorld、AI2-THOR）直接对比；没有在不同算法间进行系统比较（仅用PPO作为实例）；CRL实验仅对比了两种简单基线，且任务序列人工设计，未使用自动难度调整。

### 6. 主要结论与发现
- Craftium是一个**高效、灵活、易用**的3D环境构建平台，相比Minecraft-based框架（MineDojo）快38倍以上，与2.5D的VizDoom性能相当。
- 通过Lua Modding API，用户能快速创建各种复杂度的单/多智能体环境，代码量少（小于160行）。
- 支持并行环境（超过12K步/秒），内存占用低（660MB vs MineDojo 1.7GB）。
- 多智能体扩展对性能影响极小（<4%损失）。
- 通过示例展示了平台在RL、MARL、CRL、大语言模型具身体等领域的研究潜力。

### 7. 优点
- **性能卓越**：基于C++优化，远超Minecraft类框架，接近2.5D框架。
- **高度灵活**：使用通用编程语言Lua（而非DSL）定义环境，可访问引擎内部状态，支持实时修改任意实体、生物群落、物理参数。
- **开源友好**：完全开源，基于Luanti社区丰富资产（游戏、模组），降低开发成本。
- **标准化接口**：使用Gymnasium和PettingZoo，兼容Stable-Baselines3、CleanRL等主流库。
- **多智能体支持**：首个支持多智能体的开放式3D体素环境框架。
- **文档完善**：提供详细在线文档、教程、代码示例。

### 8. 不足与局限
- **实验覆盖有限**：仅使用PPO作为RL算法示例，未评估其他算法（如DQN、SAC）；与类似平台（如MiniWorld、Habitat）缺乏直接对比。
- **CRL实验简单**：任务序列固定，难度递增方式缺乏理论保证；仅对比了两种简单方法，未与先进CRL算法（如EWC、MAS）比较。
- **资源细节缺失**：未报告训练具体耗时、能源消耗、硬件配置细节（如CPU频率、内存大小），影响可复现性。
- **多智能体扩展性**：当前最多支持与CPU核心数相同的智能体（16个），对于大规模MARL有限制。
- **现实依赖**：平台基于体素渲染，不支持高保真物理仿真或照片级真实感，适用于认知型任务而非精细机器人操控。
- **评估偏差风险**：多数实验由作者完成，可能引入选择偏差（如使用较简单的MineDojo环境进行对比）；社区参与推广后还需进一步独立验证。

（完）
