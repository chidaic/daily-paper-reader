---
title: Behavior Generation with Latent Actions
title_zh: 基于潜在动作的行为生成
authors: "Seungjae Lee, Yibin Wang, Haritheja Etukuru, H. Jin Kim, Nur Muhammad Mahi Shafiullah, Lerrel Pinto"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=hoVwecMqV5"
tags: ["query:player-ai"]
score: 8.0
evidence: 利用向量量化的潜在动作行为生成
tldr: 本文提出VQ-BeT，一种基于向量量化的行为变换器，用于生成复杂行为序列。该方法将连续动作量化到离散代码本，克服了k-means聚类在缩放和梯度方面的缺陷。在多模态行为生成任务中，VQ-BeT在长期动作序列建模上显著优于行为变换器（BeT）。该模型可应用于游戏玩家行为模拟和智能体动作生成。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1625, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1741, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 851, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1746, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1767, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1723, \"height\": 763, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1768, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1775, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hovwecmqv5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1016, \"height\": 529, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 869, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 872, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 869, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1780, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 859, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1263, \"height\": 686, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 1082, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1551, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1767, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1781, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1562, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hovwecmqv5/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1772, \"height\": 617, \"label\": \"Table\"}]"
motivation: 现有行为变换器使用k-means离散化动作，扩展性差且缺乏梯度信息。
method: 采用向量量化将连续动作转换为离散token，并基于Transformer生成行为。
result: 在长期动作序列建模上优于BeT。
conclusion: VQ-BeT提供更高效的行为生成模型。
---

## Abstract
Generative modeling of complex behaviors from labeled datasets has been a longstanding problem in decision-making. Unlike language or image generation, decision-making requires modeling actions – continuous-valued vectors that are multimodal in their distribution, potentially drawn from uncurated sources, where generation errors can compound in sequential prediction. A recent class of models called Behavior Transformers (BeT) addresses this by discretizing actions using k-means clustering to capture different modes. However, k-means struggles to scale for high-dimensional action spaces or long sequences, and lacks gradient information, and thus BeT suffers in modeling long-range actions. In this work, we present Vector-Quantized Behavior Transformer (VQ-BeT), a versatile model for behavior generation that handles multimodal action prediction, conditional generation, and partial observations. VQ-BeT augments BeT by tokenizing continuous actions with a hierarchical vector quantization module. Across seven environments including simulated manipulation, autonomous driving, and robotics, VQ-BeT improves on state-of-the-art models such as BeT and Diffusion Policies. Importantly, we demonstrate VQ-BeT’s improved ability to capture behavior modes while accelerating inference speed 5× over Diffusion Policies. Videos can be found https://sjlee.cc/vq-bet/

---

## 论文详细总结（自动生成）

# 论文总结：VQ-BeT（Vector-Quantized Behavior Transformer）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：行为生成（behavior generation）需要从标签数据中建模复杂的连续动作序列。与语言或图像生成不同，动作是连续值向量，分布高度多模态，且生成误差会在序列预测中累积，导致灾难性失败。
- **现有局限**：行为变换器（BeT）使用k-means聚类离散化动作以捕捉多模态，但k-means难以扩展至高维动作空间或长序列，缺乏梯度信息，因此BeT在长程动作建模上表现不佳。扩散策略虽然性能好，但推理速度慢（需多步去噪）。
- **本文目标**：提出VQ-BeT，结合Transformer的长程建模能力与向量量化（VQ）的表达力，实现高效、高质量的多模态行为生成，同时支持条件生成和部分观测。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 将连续动作（或动作片段）通过**残差向量量化（Residual VQ-VAE）**转化为离散代码，然后用Transformer预测这些代码，最后解码为连续动作。
- 同时预测一个**偏移量（offset）**以保持动作的完整精度，解决离散化带来的信息损失。

### 关键技术细节
1. **动作离散化（Stage 1）**  
   - 使用Residual VQ-VAE，包含N_q层（实验中N_q=2）。  
   - 编码器ϕ将动作序列a_{t:t+n}映射为潜在向量x，然后通过最近邻查找逐层量化，最终表示为各层代码之和：\( z_q(x) = \sum_{i=1}^{N_q} z_q^i \)。  
   - 损失函数：重建L1损失 + VQ损失（停止梯度），并使用移动平均更新代码本。

2. **VQ-BeT学习（Stage 2）**  
   - 基于GPT-like Transformer，输入观测序列（可选项含目标序列），预测两个头：  
     - **代码预测头**：层次化预测主码（primary code）和次码（secondary code），使用Focal loss，并加权（主码权重β，次码权重1，实验中β=0.1~0.6）。  
     - **偏移头**：预测连续残差以保持精度，使用L1损失。  
   - 最终动作由解码器ψ对预测的代码组合加偏移得到。

3. **条件与非条件任务统一框架**  
   - 无条件：π: O^h → A^n  
   - 条件：π: O^h × O^g → A^n，其中O^g为目标观测序列。

## 3. 实验设计：数据集/场景、基准、对比方法

### 环境与数据集（8个模拟+1个真实）
- **模拟环境**：  
  - 操作任务：PushT（状态/图像）、Franka Kitchen（状态/图像）、BlockPush、UR3 BlockPush  
  - 运动任务：Multimodal Ant  
  - 自动驾驶：nuScenes（684个场景）  
- **真实机器人**：Hello Robot Stretch，厨房环境（单相/多相/长程任务共12个任务）

### 对比方法
- **无条件生成**：MLP-BC、BeT、DiffusionPolicy（卷积/Transformer变体）  
- **条件生成**：GCBC、C-BeT、C-BESO、CFG-BESO

### 评价指标
- **任务完成质量**：最终IoU、完成目标数、成功率  
- **多模态捕获**：行为熵（behavior entropy）  
- **推理速度**：单步/多步推理时间

## 4. 资源与算力

论文未明确说明使用的GPU型号、数量及具体训练时长。仅在附录中给出一系列超参数（如训练轮数1000~2000，学习率等），但未披露硬件配置。因此无法直接总结算力。

## 5. 实验数量与充分性

- **实验数量充足**：在8个模拟环境（含状态和图像变体）上进行了条件与非条件实验，并报告了熵、推理时间等；在真实机器人上完成了12个任务（5单相+3两相+4长程）。
- **消融实验充分**：在三个代表性环境（Kitchen、Ant、nuScenes）上消融了5个关键设计：残差VQ vs 普通VQ、偏移头、动作分块、自回归代码预测、代码加权β=1。结果验证了残差VQ、偏移和加权的重要性。
- **公平性**：对比方法使用官方或合理复现，对扩散策略进行了改进（如闭环控制以避免开放循环失败），并在相同设置下比较。实验结果客观展示性能提升。

## 6. 论文的主要结论与发现

1. **性能领先**：VQ-BeT在7/7条件任务中优于或匹配所有基线（除BlockPush持平），在5/7无条件任务中最优。
2. **多模态捕获强**：行为熵普遍高于基线，可视化显示VQ-BeT能生成覆盖所有模式的平滑轨迹。
3. **推理速度优势**：单步前向推理，比扩散策略快5倍（模拟）至25倍（真实机器人闭环推理）。
4. **自动驾驶应用**：在nuScenes上，VQ-BeT以部分观测信息（无车道线）达到与全信息SOTA相当或更低的L2误差。
5. **真实世界有效**：在长程任务上比扩散策略相对提升73%，且代码对代码本大小不敏感（鲁棒）。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：将残差VQ引入行为生成，解决了k-means无梯度、难扩展的问题，同时保留离散化的多模态表达能力。
- **实验设计全面**：覆盖模拟、真实机器人、自动驾驶三大领域，包含状态和图像观测，条件与无条件，且对消融、模式多样性、推理效率均有分析。
- **实际部署友好**：单步推理、内存占用低，适合低成本机器人（如Hello Robot Stretch）的实时控制。

## 8. 不足与局限

- **实验覆盖**：未在更复杂的高维动作空间（如灵巧手、双手操作）上验证；自动驾驶部分仅用nuScenes一个数据集。
- **潜在偏差**：在BlockPush等简单任务上优势不明显，说明方法在极小维度动作空间中提升有限。
- **应用限制**：代码本大小虽鲁棒，但极端情况下（如条件Kitchen）扩大代码本反而略降性能；未探索与强化学习结合或利用反馈。
- **算力信息缺失**：未公开训练所需GPU型号和时长，可复现性稍弱。

（完）
