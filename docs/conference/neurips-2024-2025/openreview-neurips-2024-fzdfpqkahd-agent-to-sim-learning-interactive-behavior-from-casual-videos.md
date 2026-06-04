---
title: "Agent-to-Sim: Learning Interactive Behavior from Casual Videos"
title_zh: "Agent-to-Sim: 从随意视频学习交互行为"
authors: "Gengshan Yang, Andrea Bajcsy, Angjoo Kanazawa, Shunsuke Saito"
date: 2024-05-10
pdf: "https://openreview.net/pdf?id=fzdFPqkAHD"
tags: ["query:player-ai"]
score: 8.0
evidence: 从视频学习智能体行为模拟，可用于游戏
tldr: 手动构建智能体行为模拟器需要大量人工。该论文提出Agent-to-Sim框架，从单目视频中学习可模拟的3D智能体。通过将观测融合到规范空间进行4D时空重建，支持从普通视频学习复杂交互行为。该方法避免了对多相机等专业设备的依赖，可扩展至游戏和VR场景。实验显示生成了逼真的交互行为。
source: NeurIPS-2024-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzdfpqkahd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 430, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzdfpqkahd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzdfpqkahd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1239, \"height\": 1531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzdfpqkahd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1430, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzdfpqkahd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1423, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzdfpqkahd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1437, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzdfpqkahd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1285, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzdfpqkahd/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 778, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzdfpqkahd/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1367, \"height\": 870, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzdfpqkahd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzdfpqkahd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 310, \"label\": \"Table\"}]"
motivation: 传统行为模拟需要手工设计决策和运动模式，且依赖专业传感器，难以扩展。
method: 从单目视频重建3D智能体，在规范空间中融合观测，生成4D时空表示。
result: 方法能生成逼真的3D交互行为模拟，支持游戏和VR应用。
conclusion: 为可扩展的智能体行为仿真提供了基于视觉学习的有效途径。
---

## Abstract
Agent behavior simulation empowers robotics, gaming, movies, and VR applications, but building such simulators often requires laborious effort of manually crafting the agent's decision process and motion patterns. Recent advance in visual tracking and motion capture enables learning of agent behavior from real-world data, but these methods are limited to a few scenarios due to the dependence on specialized sensors (e.g., synchronized multi-camera systems). Towards better scalability, we present a framework, Agent-to-Sim, that learns simulatable 3D agents in a 3D environment from monocular videos. To deal with partial views, our framework fuses observations in a canonical space for both the agent and the scene, resulting in a dense 4D spatiotemporal reconstruction. We then learn an interactive behavior generator by querying paired data of agents' perception and actions from the 4D reconstruction. Agent-to-Sim enables real-to-sim transfer of agents in their familiar environments given longitudinal video recordings captured with a smartphone over a month. We show results on pets (e.g., cat, dog, bunny) and a person, and analyse how the observer's motion and 3D scene affect an agent's behavior.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：行为模拟在机器人、游戏、电影和VR中至关重要，但传统方法要么依赖手工设计的决策逻辑（如路径规划算法或游戏引擎中的脚本），要么依赖专业传感器（如多相机同步系统、IMU）进行动作捕捉，成本高、扩展性差，且无法真实反映智能体在自然环境中的行为。
- **核心问题**：如何从轻松拍摄的单目视频（如用智能手机长时间记录同一智能体在相同环境中的活动）中，学习可交互的、真实的3D智能体行为模型，使其能够对环境（包括观察者的运动）做出合理反应。
- **整体含义**：提出名为 **Agent-to-Sim (ATS)** 的框架，实现了从“随意视频”到“可模拟智能体”的端到端管线，为大规模、低成本的现实行为仿真开辟新路径。

## 2. 论文提出的方法论

### 核心思想
- 将多个单目视频中的观测融合到一个规范（canonical）3D空间，构建包含智能体、场景和观察者（相机）的密集4D时空重建（3D + 时间）。
- 从重建中提取智能体的感知-动作配对数据，训练一个基于扩散模型的分层交互行为生成器。

### 关键技术细节
1. **4D表征：智能体、场景和观察者**
   - **静态部分**：场景场（MLP_scene）和智能体场（MLP_agent）分别定义规范空间中的密度、颜色和语义特征。场景场引入每视频延迟编码β以拟合视频特有细节。
   - **时变部分**：观察者相机位姿ξ∈SE(3)；智能体运动由25个“骨骼”（刚性体）的混合蒙皮变形描述：`X_t = G_a X = (Σ_b W_b G_t^b) X`，其中W为蒙皮权重。
   - **渲染**：通过光线投射将4D表示渲染为图像，并与观测值比较进行优化。

2. **多视频配准优化**
   - **粗到细配准**：先使用**神经定位器**（基于DINOv2特征和ResNet-18）将每帧相机全局对齐到规范空间（通过监督式训练拟合预建场景地图），再联合优化场景结构并微调相机。
   - **特征度量对齐**：在光度损失之外加入特征度量损失（DINOv2特征），增强对光照和外观变化的鲁棒性。
   - **场景退火**：训练时随机交换不同视频的β编码，并逐渐降低交换概率，促进跨视频结构共享同时保留细节。

3. **交互行为生成**
   - **分层模型**：将身体运动G（6B×T*）分解为**目标Z∈R³** → **路径P∈R³×T*** → **身体运动G**，允许低延迟目标预测。
   - **扩散模型**：每个层级用条件扩散模型（得分函数）表示多模态分布。目标得分用MLP；路径和身体运动用ControlUNet（类似ControlNet结构），分别以目标Z和路径P作为控制条件。
   - **自我感知编码**：将世界（场景T和观察者ξ）转换到智能体自我中心坐标系，通过3D卷积网络（场景）和MLP（观察者运动、历史）提取感知编码ω，用于生成条件。

### 算法流程
1. 用iPhone拍摄多段RGBD视频（含一段全景扫描视频用于定位器训练）。
2. 对每段视频提取帧，用预训练模型获得分割、光流、DINOv2特征。
3. 先训练神经定位器，再用特征度量损失优化环境30k步，然后联合优化环境和智能体30k步。
4. 从重建轨迹中提取6.4秒窗口的训练样本（约12k），训练分层扩散模型（目标、路径、身体运动及感知编码器）120k步。

## 3. 实验设计

### 数据集
- **自建数据集**：用iPhone采集4种智能体的RGBD视频：猫（26段）、狗（3段）、兔子（2段）、人（2段）。时间跨度1天至1个月，每段30秒至2分钟，包含行走、躺卧、进食、跟随相机、坐沙发等多样行为。
- **评测子集**：用猫的22段视频训练，4段验证（代表三种主要行为模式：与观察者互动、探索空间、忽视观察者）。

### Benchmark与对比方法
- **4D重建**：与现有单视频方法TotalRecon对比（多视频输入情况），进行消融实验：去掉神经定位器、去掉特征度量对齐、去掉场景退火。
- **行为预测**：
  - 目标预测基线：**Location prior**（统计位置偏好直方图）。
  - 路径/身体预测基线：**FaF**（Fast-and-Furious，数据驱动回归模型，重新训练以适配动物行为）。
  - 消融：去除观察者条件、场景条件、自我中心坐标（改为世界坐标）。

### 评估指标
- 目标：位移误差（DE）和最小位移误差（minDE），使用K=64个样本。
- 路径和身体：平均位移误差（ADE）和最小平均位移误差（minADE），分别给定真值目标和真值路径。

## 4. 资源与算力

- **4D重建阶段**：
  - 猫数据集（26段视频）：使用**8块A100 GPU**，优化约**24小时**。
  - 狗、兔子、人（2-3段视频）：使用**1块A100 GPU**。
- **行为模型训练**：
  - 使用**1块A100 GPU**，训练**10小时**（120k步，batch size 1024）。
- **推理速度**：
  - 目标去噪每步2ms，路径/身体去噪每步9ms（GeForce RTX 3090）。

## 5. 实验数量与充分性

- **4D重建实验**：在猫、狗、兔子、人四个数据集上进行，有消融实验（4种变体），并与TotalRecon定性比较（含补充中的单视频对比）。
- **行为预测实验**：仅猫数据集上有定量结果（训练集22视频，验证集4视频），包括3种基线（Location prior、FaF、完整ATS）和4种消融（去掉ωo、ωs、自我中心、无条件）。此外有定性分析（改变观察者轨迹生成不同行为）。
- **评估充分性**：
  - 消融设计合理，验证了各组件贡献。
  - 仅一个物种（猫）有定量结果，其他为定性；验证集较小（4段视频），可能无法完全代表多样性。
  - 没有与其他同类方法（如人类运动预测方法）在同一数据集上直接比较，原因是动物尚无标准benchmark。
- **公平性**：FaF基线重新训练，使用相同输入，对比公平；Location prior可认为最简基线。

## 6. 论文的主要结论与发现

- ATS能从手机拍摄的随意视频中实现完整的4D场景-智能体重建，并学习到可交互的行为模型。
- 多视频配准显著提升场景和智能体重建质量；神经定位器和特征度量对齐对配准成功至关重要；场景退火有助于结构共享。
- 分层扩散模型能有效捕获目标、路径和身体运动的多模态分布，优于确定性回归模型（FaF）。
- **环境交互性**：观察者运动条件和场景条件对目标预测有明显影响；去除它们会导致预测目标发散或不可行（如穿透地面）。
- 自我中心坐标比世界坐标更有效，能避免过拟合特定位置。

## 7. 优点

- **数据源简单**：仅需单个智能手机的RGBD视频，无需多相机阵列或IMU，极大降低了数据采集门槛。
- **端到端管线**：从视频到可交互模拟智能体的全自动流水线，包含重建、配准和行为学习。
- **方法通用性强**：不依赖智能体类别特定的先验模型（如SMPL人体模型），适用于猫、狗、兔子等多种动物。
- **交互性显式建模**：通过自我感知编码将观察者轨迹和场景结构融入行为生成，使智能体能对用户动作（如靠近或远离）做出符合现实的反应。
- **分层生成控制**：目标—路径—身体的分级结构允许低延迟目标预测，并支持逐步精细控制。

## 8. 不足与局限

- **普适性不足**：定量评测仅针对猫一个物种，且验证集仅4段视频，样本量小；狗、兔子、人仅有定性演示，无法完全证明方法的跨物种泛化能力。
- **时间尺度有限**：模型训练的时间窗口为6.4秒，只能学习中期行为（如移动到某地、停留、走动），无法模拟长期复杂行为模式（如日常作息）。
- **物理合理性欠缺**：生成的运动可能不满足物理约束（如穿透地面、脚部滑动），论文未引入物理引擎优化。
- **场景重建局限**：对随时间变化的瞬态结构（如可移动的垫子）重建效果不佳，且缺少针对这些动态物体的专门处理。
- **安全性与覆盖度**：在测试集上目标预测误差仍较大（minDE=0.395m），且可能遗漏真实目标，不适合直接用于安全关键场景（如自动驾驶行人预测）。
- **多智能体缺失**：当前仅支持单智能体行为模拟，未扩展到多智能体交互场景。
- **计算成本偏高**：4D重建需8块A100 GPU训练24小时，不利于大规模推广。
- **缺乏标准benchmark**：没有公开数据集和标准化评估协议，可复现性和可比性受限。

（完）
