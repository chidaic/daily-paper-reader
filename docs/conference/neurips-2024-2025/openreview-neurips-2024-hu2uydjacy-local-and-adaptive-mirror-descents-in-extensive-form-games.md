---
title: Local and Adaptive Mirror Descents in Extensive-Form Games
title_zh: 广泛形式博弈中的局部自适应镜像下降
authors: "Côme Fiegel, Pierre Menard, Tadashi Kozuno, Remi Munos, Vianney Perchet, Michal Valko"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=HU2uyDjAcy"
tags: ["query:player-ai"]
score: 8.0
evidence: 用于不完全信息博弈中epsilon最优策略的局部自适应OMD
tldr: 该论文针对不完全信息博弈中的策略学习问题，提出了一种基于固定采样的局部自适应在线镜像下降算法（OMD）。该方法通过在每个信息集应用独立的递减学习率和正则化损失，有效降低了重要性采样带来的高方差。理论分析证明了算法收敛到epsilon最优策略。该工作为博弈中的智能体学习提供了高效且稳定的优化方法。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-hu2uydjacy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1302, \"height\": 996, \"label\": \"Figure\"}]"
motivation: 现有不完全信息博弈策略学习方法因重要性采样导致高方差，需要更稳定的优化技术。
method: 提出局部自适应在线镜像下降算法，每个信息集使用独立学习率和正则化损失，结合固定采样策略。
result: 理论证明算法能在轨迹反馈下收敛到epsilon最优策略，有效降低方差。
conclusion: 该工作为博弈中的在线学习提供了低方差的新框架，适用于广泛形式博弈。
---

## Abstract
We study how to learn $\epsilon$-optimal strategies in zero-sum imperfect information games (IIG) with *trajectory feedback*. In this setting, players update their policies sequentially, based on their observations over a fixed number of episodes denoted by $T$. Most existing procedures suffer from high variance due to the use of importance sampling over sequences of actions. To reduce this variance, we consider a *fixed sampling* approach, where players still update their policies over time, but with observations obtained through a given fixed sampling policy. Our approach is based on an adaptive Online Mirror Descent (OMD) algorithm that applies OMD locally to each information set, using individually decreasing learning rates and a *regularized loss*. We show that this approach guarantees a convergence rate of $\tilde{\mathcal{O}}(T^{-1/2})$ with high probability and has a near-optimal dependence on the game parameters when applied with the best theoretical choices of learning rates and sampling policies. To achieve these results, we generalize the notion of OMD stabilization, allowing for time-varying regularization with convex increments.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在零和不完全信息博弈（IIG）中，通过自对弈学习 $\epsilon$-最优策略时，现有的基于轨迹反馈的方法（如基于重要性采样的 OMD 或 CFR）存在高方差问题，主要源于两个方面：一是同一策略同时用于最小化遗憾和收集数据，导致探索与利用的冲突；二是对动作序列进行重要性采样，在大规模游戏中轨迹概率极小，导致重要性权重巨大，方差膨胀。
- **整体含义**：高方差会阻碍算法在大型游戏中的实际应用，尤其当结合函数近似（如神经网络）时，噪声可能导致不稳定的训练。作者旨在设计一种无需对动作序列进行全局重要性采样、且能降低方差的方法，以实现高效的策略学习。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：提出 **LocalOMD** 算法，采用 **固定采样策略框架**（fixed sampling policy framework）来解耦观测策略与更新策略：在每个回合，一位玩家使用固定的采样策略（如 $\mu_s$）进行观测，另一位玩家使用当前更新的策略进行交互，交替更新。这样，损失估计仅需对当前动作进行重要性采样（而非整条轨迹），从而大幅降低方差。
- **关键技术细节**：
    - **局部 OMD**：在树博弈中，将在线镜像下降（OMD）应用于每个信息集（information set）局部，每个信息集拥有独立递减的学习率 $\eta_t(x)$ 和正则化损失 $\tilde{\ell}_t(x,a)$。
    - **正则化损失**：$\tilde{\ell}_t(x,a) = \frac{I\{x=x_t^h, a=a_t^h\}}{\mu_s^{1:}(x)} (\ell_t^h + q_t^{h+1})$，其中 $q_t^{h+1}$ 是子树的递归最小值，仅需对当前动作做重要性采样（分母为 $\mu_s^{1:}(x)$），避免了轨迹级重要性采样。
    - **时间变化正则化**：推广了双稳（dual-stabilization）技术，允许正则化参数随时间变化，只要增量函数是凸的（如非增学习率序列）。这使得可以使用自适应学习率，例如 $\eta_t(x) = \eta / \sqrt{\sum_{k=1}^t I\{x=x_k^h\}}$。
    - **算法流程**（Algorithm 2）：
        1. 输入固定采样策略 $\mu_s$ 和初始策略 $\mu_1$，以及每个信息集的学习率序列。
        2. 每回合 $t$：使用 $\mu_s$ 收集一条轨迹；从叶子到根递归计算局部更新：
            - $\mu_{t+1}(\cdot|x) \leftarrow \arg\min_{\mu\in\Delta\mathcal{A}(x)} h_t^x(\mu)$，其中 $h_t^x$ 包含局部损失、Bregman散度项和稳定项。
            - 更新未访问的信息集保持原策略。
        3. 输出时间平均策略 $\bar{\mu}$。
- **公式支撑**：理论证明了估计遗憾（estimated regret）的有界性，并通过 Bernstein 型不等式转化为真实遗憾的界，得到 $\tilde{\mathcal{O}}(T^{-1/2})$ 的收敛率。

### 3. 实验设计：数据集/场景、基准、对比方法

- **实验场景**：三个标准博弈基准：
    - **Kuhn poker**（小型，$A_X=B_Y=12$）
    - **Leduc poker**（中型，$A_X=B_Y=1092$）
    - **Liars dice**（大型，$A_X=B_Y=24570$）
- **使用框架**：OpenSpiel v1.4。
- **对比方法**：
    - **BalancedCFR**（Bai et al., 2022）：理论上最优的固定采样 CFR 算法。
    - **BalancedFTRL**（Fiegel et al., 2023）：基于 FTRL 的算法（非固定采样，但作为基线）。
    - **LocalOMD Optimal**：使用定理 4.2 的固定学习率（$\eta_t(x)=\eta/\kappa(\mu_s|x)$）。
    - **LocalOMD Adaptive**：使用定理 4.1 的自适应学习率（如 $\eta_t(x)=\eta/\sqrt{\sum I\{x=x_k^h\}}$）。
- **评估指标**：**可开发性差距（exploitability gap）** 和 **损失估计的经验方差**。

### 4. 资源与算力

- 文中未明确提及使用的 GPU 型号、数量或训练时长。实验规模（最大动作数约 2.5 万）较小，推测在常规 CPU/个人电脑上即可完成。作者仅提到“experiments were run on a personal computer as they do not require heavy computations”。

### 5. 实验数量与充分性

- **实验数量**：每个游戏进行了 **5 次独立模拟**（5 simulations），图中显示了方差。
- **充分性与公平性**：
    - 所有算法的学习率（及 IX 参数）均通过网格搜索独立优化，确保公平对比。
    - 固定采样算法（LocalOMD, BalancedCFR）在总回合数上劣势，因为每轮需要两个回合（一个观测，一个交互），但论文仍按总回合数（episodes）展示，这种做法技术上对固定采样算法不利，但作者公开了这一比较方式。
    - 对比了不同游戏规模（小、中、大），覆盖了典型博弈场景。
- **客观性**：实验展示了方差曲线，验证了 LocalOMD 在损失估计方差上确实低于 BalancedFTRL（非固定采样）和 BalancedCFR（固定采样但需多层采样）。但缺乏与大模型或最新 Deep RL 方法的对比，仅限于传统表格型算法。

### 6. 论文的主要结论与发现

- **主要结论**：
    1. LocalOMD 在固定采样框架下可达到 $\tilde{\mathcal{O}}(T^{-1/2})$ 的高概率收敛率，且具有近最优的样本复杂度 $\tilde{\mathcal{O}}(H^3(A_X + B_Y)/\epsilon^2)$（当使用平衡采样策略时）。
    2. 局部 OMD 结合固定采样有效降低了损失估计的方差，使得算法对大规模游戏更具鲁棒性。
    3. 理论分析推广了 OMD 的双稳技术，支持时间变化正则化（如自适应学习率）。
- **实验发现**：
    - LocalOMD 的两种版本在 exploitability 上始终优于 BalancedCFR，主要因为 BalancedCFR 每层需要独立样本，导致需要更多回合。
    - 与 BalancedFTRL 相比，LocalOMD 在 Leduc poker 上更好，在 liars dice 上稍差，但总体表现相当。
    - 方差图表明固定采样算法的损失估计方差远小于 BalancedFTRL，而 LocalOMD 又优于 BalancedCFR（因为 BalancedCFR 每 H 回合才估计一层损失，方差增大）。

### 7. 优点：方法或实验设计上的亮点

- **方法创新**：
    - 将固定采样与局部 OMD 结合，避免了轨迹级重要性采样，仅需动作级重要性采样，显著降低方差，有利于扩展到函数近似（如神经网络）。
    - 支持自适应学习率，无需预先调参，适用于未知游戏结构。
    - 理论提供了与问题相关的复杂度 $\kappa(\mu_s)$，并证明了平衡策略能最小化该量。
- **实验设计**：
    - 清晰比较了两种 LocalOMD 版本与现有最优算法的性能，并专门绘制了损失估计方差，直观展示方法优势。
    - 在三个不同规模的标准博弈上验证，体现了可扩展性。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制

- **实验覆盖不足**：
    - 仅测试了三个小型到中型游戏（最大动作数约 2.5 万），未在超大规模博弈（如德州扑克全规模）上评估，实际方差优势在更大游戏中可能更明显，但未验证。
    - 未实验函数近似（如神经网络）场景，论文虽声称适用于此类扩展，但缺乏实证。
- **偏差风险**：
    - 固定采样策略需要预先定义，若选择不佳（如非平衡策略），复杂度 $\kappa(\mu_s)$ 会很大，可能抵消优势。论文虽讨论了平衡策略，但未探索如何在线自适应选择采样策略。
    - 对比方法 BalancedCFR 在实现上可能因层独立采样而处于劣势，但这是其算法固有特性。
- **应用限制**：
    - 固定采样框架需要两倍的回合数（观测+交互），样本效率可能低于单回合算法（如 BalancedFTRL），尽管方差降低。
    - 算法假设完美回忆（perfect recall），不适用于部分可观测但无记忆的设定。
    - 理论结果依赖于对数项 $ \log(A_X/\delta) $ 等，常数可能较大，实际中可能需要更多样本。

（完）
