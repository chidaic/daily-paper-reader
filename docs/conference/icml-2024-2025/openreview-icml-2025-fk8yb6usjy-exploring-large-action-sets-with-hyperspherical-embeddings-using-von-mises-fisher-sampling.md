---
title: Exploring Large Action Sets with Hyperspherical Embeddings using von Mises-Fisher Sampling
title_zh: 利用von Mises-Fisher采样探索超球面嵌入的大动作集
authors: "Walid Bendada, Guillaume Salha-Galvan, Romain Hennequin, Théo Bontempelli, Thomas Bouabça, Tristan Cazenave"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Fk8yB6uSJy"
tags: ["query:player-ai"]
score: 5.0
evidence: 针对RL中大动作集的可扩展探索方法
tldr: 本文提出von Mises-Fisher探索（vMF-exp），一种用于强化学习大规模动作集的可扩展探索方法。该方法将动作表示为超球面嵌入，通过采样状态嵌入并搜索最近邻来探索动作，可扩展到任意数量候选动作。理论上，vMF-exp渐近地保持与Boltzmann探索相同的概率，但避免了计算softmax的瓶颈。该方法可应用于游戏AI等需要大动作空间的场景。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-fk8yb6usjy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1784, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk8yb6usjy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1780, \"height\": 1061, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk8yb6usjy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1772, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk8yb6usjy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 768, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk8yb6usjy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 771, \"height\": 956, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk8yb6usjy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 770, \"height\": 806, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk8yb6usjy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 2103, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk8yb6usjy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1779, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk8yb6usjy/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1762, \"height\": 1130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk8yb6usjy/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1772, \"height\": 462, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-fk8yb6usjy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1588, \"height\": 175, \"label\": \"Table\"}]"
motivation: Boltzmann探索在大动作集上计算softmax不可扩展。
method: 采用von Mises-Fisher分布采样状态嵌入，再搜索最近邻动作。
result: 渐近保持与Boltzmann探索相同的探索概率，且可扩展。
conclusion: vMF-exp提供了一种高效探索大动作集的方法。
---

## Abstract
This paper introduces von Mises-Fisher exploration (vMF-exp), a scalable method for exploring large action sets in reinforcement learning problems where hyperspherical embedding vectors represent these actions. vMF-exp involves initially sampling a state embedding representation using a von Mises-Fisher distribution, then exploring this representation's nearest neighbors, which scales to virtually unlimited numbers of candidate actions.
We show that, under theoretical assumptions, vMF-exp asymptotically maintains the same probability of exploring each action as Boltzmann Exploration (B-exp), a popular alternative that, nonetheless, suffers from scalability issues as it requires computing softmax values for each action.
Consequently, vMF-exp serves as a scalable alternative to B-exp for exploring large action sets with hyperspherical embeddings. 
Experiments on simulated data, real-world public data, and the successful large-scale deployment of vMF-exp on the recommender system of a global music streaming service empirically validate the key properties of the proposed method.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：传统强化学习（RL）中，当动作集规模极大（如音乐推荐服务中数百万首歌曲）时，常用的探索策略如 **Boltzmann探索（B-exp）** 因需对每个动作计算 softmax 而无法扩展到大规模场景；而 **ε-greedy** 随机探索无法利用嵌入相似度，导致推荐质量下降；截断 Boltzmann（TB-exp）虽可扩展但人为限制探索半径，可能遗漏潜在相关动作。
- **核心问题**：设计一种同时满足 **可扩展性（P1）**、**无半径限制（P2）** 和 **顺序保持（P3）**（即采样概率与嵌入内积严格正相关）的探索策略。
- **整体含义**：提出 **von Mises-Fisher探索（vMF-exp）**，通过采样连续超球面向量并检索最近邻动作，实现对大规模超球面嵌入动作集的高效探索，并理论上证明其渐近等价于 B-exp，替代后者成为可扩展方案。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用 von Mises-Fisher（vMF）分布从当前状态嵌入向量 V 出发采样一个连续向量 \tilde{V}，然后返回 \tilde{V} 在动作嵌入集合中的最近邻（ANN）作为探索的动作。vMF-exp 的实现仅需常数时间采样（与动作数 n 无关），随后通过 ANN 引擎在亚线性时间内找到最近邻。
- **关键技术细节**：
  - 动作嵌入为 d 维单位超球面上的点（\|X_i\|=1）。
  - vMF 分布的 PDF：\( f_{\text{vMF}}(\tilde{V} \mid \kappa, V, d) = C_d(\kappa) e^{\kappa \langle V, \tilde{V} \rangle} \)，其中 κ 控制集中程度。
  - 采样概率：动作 i 被选中的概率为 \( P_{\text{vMF-exp}}(i \mid V, X_n, \kappa) = \int_{\tilde{V} \in \text{Voronoi}(X_i \mid X_n)} f_{\text{vMF}}(\tilde{V} \mid \kappa, V, d) d\tilde{V} \)，始终为正（满足 P2）。
- **理论结果**：
  - 假设嵌入向量独立同分布于超球面上的均匀分布，证明 vMF-exp 与 B-exp 在 n 很大时渐近等价：\(\lim_{n\to\infty} P_{\text{B-exp}}(a)/P_{\text{vMF-exp}}(a)=1\)。
  - 给出两种方法各自的一阶近似公式（P0），并指出在高维情况下 vMF-exp 的探索范围略大于 B-exp（P1 近似）。

## 3. 实验设计：使用了哪些数据集/场景，benchmark 是什么，对比了哪些方法

- **模拟数据**：在合成数据上验证理论渐近性，使用蒙特卡洛模拟（每次实验 800 万次重复）。
- **真实公开数据**：GloVe-25 数据集（100 万词嵌入，维度 25），用于验证 P1、P2、P3 及近似公式的准确性。
- **工业场景**：全球音乐流媒体服务 Deezer 的“Mixes inspired by”推荐系统，涉及数百万用户、数百万歌曲。对比方法：
  - **vMF-exp**：本文方法。
  - **参考基线**：直接检索初始歌曲的 500 个最近邻后随机打乱推荐。
  - **TB-exp**（截断 Boltzmann）：仅对 500 个最近邻计算 softmax。
- **Benchmark**：Deezer 上的在线 A/B 测试（百万用户规模），评估指标为每日用户“喜欢”的推荐歌曲数的相对提升以及推荐多样性（Jaccard 相似度）。

## 4. 资源与算力

- **文中未明确说明使用的 GPU/TPU 型号、数量或训练时长**。但提及：
  - 模拟实验使用 Python vMF 采样器（Pinzón & Jung, 2023）和 800 万次重复。
  - 生产部署中，vMF-exp 抽样延迟仅为几毫秒，与 TB-exp 相当。
  - 使用 Faiss 库进行近似最近邻搜索，其吞吐量（QPS）高达数万（详见 Table 1）。

## 5. 实验数量与充分性

- **实验数量**：
  - 模拟实验：多个 (d, κ, ⟨V,A⟩) 组合（d=4,8,16,32,64,128；κ=1,2；⟨V,A⟩=0.5,0.9,-0.3,-0.9 等），覆盖多种参数。
  - GloVe-25 实验：确定采样概率并对比近似公式，重复 3000 万次。
  - 在线 A/B 测试：百万用户规模、统计显著（p<0.01），持续数月。
- **充分性与公平性**：
  - 实验设计较充分，覆盖合成数据、公开数据和生产环境。
  - 对比方法包括朴素基线、TB-exp 等主流实践。
  - 但作者指出，理论假设（嵌入 i.i.d. 均匀分布）在真实数据（如 GloVe）上不完全成立，导致高 |⟨V,A⟩| 时近似精度下降，但整体趋势仍支持结论。

## 6. 论文的主要结论与发现

- vMF-exp 同时满足 **可扩展性**（常数时间采样 + 亚线性 ANN）、**无半径限制**（所有动作概率为正）、**顺序保持**（概率随内积单调增加）。
- 理论上，在大动作集且嵌入均匀独立分布条件下，vMF-exp 渐近等价于 B-exp，可作为其可扩展替代。
- 在 GloVe-25 数据上验证了 P1、P2、P3 及近似公式的有效性（P0 近似对 B-exp 极其精确）。
- 在 Deezer 的在线 A/B 测试中，vMF-exp 与 TB-exp 相比，推荐歌曲的“喜欢”率提升 11%（p<0.01），且推荐多样性（Jaccard 相似度）低 35%（p<0.01），表明更充分的探索。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：将连续 vMF 分布采样引入离散动作探索，巧妙利用 Voronoi 单元概率积分，避免离散 softmax 计算。
- **理论严谨**：给出渐近等价、一阶/二阶近似等严格证明，并分析高维情况下的修正项。
- **实验覆盖全面**：从合成数据到公开数据再到工业在线测试，验证理论同时证明实用性。
- **可重复性**：公开了 GitHub 代码库 (deezer/vMF-exploration)，便于复现。
- **实际影响力**：成功部署于 Deezer 生产环境（数百万用户），实现了高效低延迟的探索。

## 8. 不足与局限

- **理论假设较强**：主要结论依赖于嵌入向量 i.i.d. 均匀分布在超球面上，真实数据（如 GloVe）不满足，导致高相似度时近似误差增大。
- **未考虑 ANN 误差**：理论分析假定最近邻检索精确，但实际中 ANN 存在近似误差，可能引入微小偏移。
- **维度与 κ 的交互影响**：高维或大 κ 下 vMF-exp 与 B-exp 的差异需进一步研究二阶项。
- **实验部分未报告计算资源消耗**（如 GPU 型号/数量），不利于复现代码的实际需求评估。
- **应用场景局限**：仅针对超球面嵌入的动作集，不适用于其他嵌入空间或非向量化动作。

（完）
