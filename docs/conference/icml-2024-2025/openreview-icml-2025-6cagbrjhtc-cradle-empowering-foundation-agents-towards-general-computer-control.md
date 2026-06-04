---
title: "Cradle: Empowering Foundation Agents towards General Computer Control"
title_zh: Cradle：赋能基础智能体实现通用计算机控制
authors: "Weihao Tan, Wentao Zhang, Xinrun Xu, Haochong Xia, Ziluo Ding, Boyu Li, Bohan Zhou, Junpeng Yue, Jiechuan Jiang, Yewen Li, Ruyi An, Molei Qin, Chuqiao Zong, Longtao Zheng, YuJie Wu, Xiaoqiang Chai, Yifei Bi, Tianbao Xie, Pengjie Gu, Xiyun Li, Ceyao Zhang, Long Tian, Chaojie Wang, Xinrun Wang, Börje F. Karlsson, Bo An, Shuicheng YAN, Zongqing Lu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6CAgbrjHTc"
tags: ["query:player-ai"]
score: 7.0
evidence: 面向通用计算机控制的基础智能体，可应用于游戏
tldr: 该工作针对基础智能体在不同虚拟场景泛化差的问题，提出通用计算机控制框架Cradle，以截图输入和键盘鼠标输出为统一接口，通过六个模块实现任务推理和计划，为游戏等虚拟环境中的AI代理训练提供了通用方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1588, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1586, \"height\": 695, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1742, \"height\": 793, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1602, \"height\": 799, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1594, \"height\": 625, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1587, \"height\": 1306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1701, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1729, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1590, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 721, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1684, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1775, \"height\": 1146, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1727, \"height\": 770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1725, \"height\": 1152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1771, \"height\": 964, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1430, \"height\": 2121, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1775, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1724, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 689, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 686, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 438, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 686, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 686, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 439, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 647, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 644, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 413, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 646, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 67, \"height\": 64, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 640, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 411, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1753, \"height\": 1103, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1757, \"height\": 830, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1544, \"height\": 1418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1769, \"height\": 1104, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1727, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 725, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 724, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 719, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 718, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 724, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 721, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-043.webp\", \"caption\": \"\", \"page\": 0, \"index\": 43, \"width\": 719, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-044.webp\", \"caption\": \"\", \"page\": 0, \"index\": 44, \"width\": 718, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-045.webp\", \"caption\": \"\", \"page\": 0, \"index\": 45, \"width\": 1619, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-046.webp\", \"caption\": \"\", \"page\": 0, \"index\": 46, \"width\": 1617, \"height\": 312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-047.webp\", \"caption\": \"\", \"page\": 0, \"index\": 47, \"width\": 1079, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-048.webp\", \"caption\": \"\", \"page\": 0, \"index\": 48, \"width\": 545, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-049.webp\", \"caption\": \"\", \"page\": 0, \"index\": 49, \"width\": 542, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-050.webp\", \"caption\": \"\", \"page\": 0, \"index\": 50, \"width\": 874, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-051.webp\", \"caption\": \"\", \"page\": 0, \"index\": 51, \"width\": 875, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-052.webp\", \"caption\": \"\", \"page\": 0, \"index\": 52, \"width\": 1411, \"height\": 96, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-053.webp\", \"caption\": \"\", \"page\": 0, \"index\": 53, \"width\": 1401, \"height\": 171, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-054.webp\", \"caption\": \"\", \"page\": 0, \"index\": 54, \"width\": 875, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-055.webp\", \"caption\": \"\", \"page\": 0, \"index\": 55, \"width\": 877, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-056.webp\", \"caption\": \"\", \"page\": 0, \"index\": 56, \"width\": 874, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-057.webp\", \"caption\": \"\", \"page\": 0, \"index\": 57, \"width\": 874, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-058.webp\", \"caption\": \"\", \"page\": 0, \"index\": 58, \"width\": 1729, \"height\": 763, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-059.webp\", \"caption\": \"\", \"page\": 0, \"index\": 59, \"width\": 1458, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-060.webp\", \"caption\": \"\", \"page\": 0, \"index\": 60, \"width\": 1457, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-061.webp\", \"caption\": \"\", \"page\": 0, \"index\": 61, \"width\": 1458, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-062.webp\", \"caption\": \"\", \"page\": 0, \"index\": 62, \"width\": 1459, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-063.webp\", \"caption\": \"\", \"page\": 0, \"index\": 63, \"width\": 1459, \"height\": 283, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-064.webp\", \"caption\": \"\", \"page\": 0, \"index\": 64, \"width\": 1460, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-065.webp\", \"caption\": \"\", \"page\": 0, \"index\": 65, \"width\": 1733, \"height\": 770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-066.webp\", \"caption\": \"\", \"page\": 0, \"index\": 66, \"width\": 1727, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-067.webp\", \"caption\": \"\", \"page\": 0, \"index\": 67, \"width\": 1723, \"height\": 767, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-068.webp\", \"caption\": \"\", \"page\": 0, \"index\": 68, \"width\": 1731, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-069.webp\", \"caption\": \"\", \"page\": 0, \"index\": 69, \"width\": 1727, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-070.webp\", \"caption\": \"\", \"page\": 0, \"index\": 70, \"width\": 1760, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-071.webp\", \"caption\": \"\", \"page\": 0, \"index\": 71, \"width\": 810, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-072.webp\", \"caption\": \"\", \"page\": 0, \"index\": 72, \"width\": 1768, \"height\": 1125, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-073.webp\", \"caption\": \"\", \"page\": 0, \"index\": 73, \"width\": 1766, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-074.webp\", \"caption\": \"\", \"page\": 0, \"index\": 74, \"width\": 1756, \"height\": 858, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-075.webp\", \"caption\": \"\", \"page\": 0, \"index\": 75, \"width\": 807, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-076.webp\", \"caption\": \"\", \"page\": 0, \"index\": 76, \"width\": 1744, \"height\": 1453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-077.webp\", \"caption\": \"\", \"page\": 0, \"index\": 77, \"width\": 1721, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-078.webp\", \"caption\": \"\", \"page\": 0, \"index\": 78, \"width\": 1750, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-079.webp\", \"caption\": \"\", \"page\": 0, \"index\": 79, \"width\": 1043, \"height\": 1047, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-080.webp\", \"caption\": \"\", \"page\": 0, \"index\": 80, \"width\": 1783, \"height\": 1121, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-081.webp\", \"caption\": \"\", \"page\": 0, \"index\": 81, \"width\": 1777, \"height\": 1016, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-082.webp\", \"caption\": \"\", \"page\": 0, \"index\": 82, \"width\": 1772, \"height\": 1006, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-083.webp\", \"caption\": \"\", \"page\": 0, \"index\": 83, \"width\": 1772, \"height\": 1007, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cagbrjhtc/fig-084.webp\", \"caption\": \"\", \"page\": 0, \"index\": 84, \"width\": 1776, \"height\": 1010, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 897, \"height\": 895, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1344, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1423, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1114, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1392, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1135, \"height\": 1183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1786, \"height\": 1313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1589, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1412, \"height\": 475, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1392, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 480, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1782, \"height\": 1362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1782, \"height\": 721, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1344, \"height\": 1567, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cagbrjhtc/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1514, \"height\": 245, \"label\": \"Table\"}]"
motivation: 现有基础智能体因环境接口各异而难以泛化到多样虚拟场景。
method: 提出GCC设置，以统一界面（截图、键盘鼠标）构建Cradle框架，含信息收集、自省等模块。
result: 在多个计算机任务中展示了泛化控制能力，包括游戏类场景。
conclusion: 统一界面范式能有效提升智能体在虚拟环境中的通用性。
---

## Abstract
Despite their success in specific scenarios, existing foundation agents still struggle to generalize across various virtual scenarios, mainly due to the dramatically different encapsulations of environments with manually designed observation and action spaces. To handle this issue, we propose the General Computer Control (GCC) setting to restrict foundation agents to interact with software through the most unified and standardized interface, i.e., using screenshots as input and keyboard and mouse actions as output. We introduce Cradle, a modular and flexible LMM-powered framework, as a preliminary attempt towards GCC. Enhanced by six key modules, Information Gathering, Self-Reflection, Task Inference, Skill Curation, Action Planning, and Memory, Cradle is able to understand input screenshots and output executable code for low-level keyboard and mouse control after high-level planning and information retrieval, so that Cradle can interact with any software and complete long-horizon complex tasks without relying on any built-in APIs. Experimental results show that Cradle exhibits remarkable generalizability and impressive performance across four previously unexplored commercial video games (Red Dead Redemption 2, Cities:Skylines, Stardew Valley and Dealer's Life 2), five software applications (Chrome, Outlook, Feishu, Meitu and CapCut), and a comprehensive benchmark, OSWorld. With a unified interface to interact with any software, Cradle greatly extends the reach of foundation agents thus paving the way for generalist agents.

---

## 论文详细总结（自动生成）

# 论文《Cradle: Empowering Foundation Agents towards General Computer Control》详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有基础智能体（foundation agents）虽然在特定场景下取得成功，但由于不同虚拟环境封装了人为设计的观察和动作空间，导致智能体难以跨场景泛化。
- **整体含义**：为突破这一瓶颈，论文提出**通用计算机控制（General Computer Control, GCC）** 设置，要求智能体通过最统一、标准化的界面与软件交互——以**截图作为输入**、**键盘鼠标操作作为输出**，从而摆脱对内置API的依赖，向通用智能体迈进。

## 2. 方法论

### 2.1 核心思想
- 构建一个模块化、由大型多模态模型（LMM）驱动的框架 **Cradle**，通过六大模块协同工作，实现“反思过去、总结现在、规划未来”的高层推理与精确执行。

### 2.2 关键技术细节
- **六个关键模块**：
  1. **Information Gathering**：从视频观测中提取视觉与文本信息（OCR、布局、UI元素、图标等），并利用Grounding DINO、SAM等工具增强定位。
  2. **Self-Reflection**：评估上一动作是否成功、任务是否完成，并分析失败原因，为后续决策提供反馈。
  3. **Task Inference**：根据当前状态推断最高优先级的子任务，决定何时结束当前任务、开启新任务。
  4. **Skill Curation**：生成、更新、检索代码形式的技能（skill），技能可基于游戏教程、手册或自我探索自动生成，并存储在过程记忆中。
  5. **Action Planning**：从技能集中选择合适技能，实例化参数（如坐标、时长），生成可执行动作序列。
  6. **Memory**：分为**情景记忆**（存储关键截图、推理输出、摘要）和**过程记忆**（存储技能代码及其嵌入，通过余弦相似度检索）。

- **骨干模型**：使用 GPT-4o（gpt-4o-2024-05-13）作为LMM骨干，温度设为0以降低生成方差。
- **动作空间**：包含所有键盘/鼠标操作（key_press, mouse_move, wheel_scroll等），通过Python代码封装为 `io_env` 类。
- **技能生成示例**：根据游戏屏幕上的指令提示（如“Hold [TAB] to show Weapon Wheel”）直接生成对应代码函数。

## 3. 实验设计

### 3.1 数据集/场景与基准
- **视频游戏**（4款）：Red Dead Redemption 2（主线第1、2章共13个任务）、Cities: Skylines（建设城市）、Stardew Valley（清理农场、种植、购物）、Dealer's Life 2（一周店铺管理）。
- **软件应用**（5款）：Chrome、Outlook、CapCut、Meitu、Feishu，每款设计5个领域任务，共25个任务。
- **综合基准**：OSWorld（包含369个真实计算机任务，自动评估脚本）。

### 3.2 对比方法
- 基线方法：**React-like**（仅信息收集、技能策划、动作规划、过程记忆）、**Reflexion-like**（增加自我反思和情景记忆）、**Voyager-like**（将图像转为文本描述输入）。
- 骨干模型对比：GPT-4o vs. Claude 3 Opus。
- 消融实验：系统移除 Cradle 各模块（信息收集、自我反思、任务推断、情景记忆）在 RDR2 的6个连续子任务上测试。

### 3.3 实验设置
- 除OSWorld外，每个任务运行5次；人类玩家（5名新手）作为对比基准。
- 最大步数限制：RDR2子任务500步，Stardew Valley 100步，Cities: Skylines 1000步等。
- OSWorld使用官方评估脚本，其他任务采用人工评估（类似SIMA）。

## 4. 资源与算力

论文在附录C中明确说明了计算成本：

- **硬件**：
  - RDR2：需要 NVIDIA RTX 4090 GPU 的 Windows 10 机器。
  - 其他软件和游戏：普通 Windows 10 机器即可。
- **运行时长**（单次运行所有任务）：
  - RDR2：约 240 小时
  - Cities: Skylines：约 60 小时
  - Stardew Valley：约 30 小时
  - Dealer's Life 2：约 20 小时
  - 软件应用：约 50 小时
  - OSWorld：约 240 小时
  - **总计**：约 640 小时
- **API费用**（以 gpt-4o-2024-05-13 计）：
  - 总输入 Token 约 880M，输出约 35M
  - 总成本约 **5410 美元**（含实验4.1部分，基线对比和消融未计入）
- 作者指出，使用更新的模型（如 gpt-4o-2024-08-06）成本可减半，未来几年有望降低一至两个数量级。

## 5. 实验数量与充分性

- **数量**：
  - 游戏 + 软件：共约 14+1+3+1+25 = 44 个任务，每个 5 次运行 → 约 220 组实验。
  - OSWorld：369 个任务各 1 次运行。
  - 基线对比：在 RDR2 的 5 个代表性任务 + Stardew Valley 的 1 个任务上进行。
  - 消融实验：在 RDR2 的 6 个子任务上比较 4 种变体（移除不同模块），每个 5 次运行 → 约 120 组。
- **充分性与公平性**：
  - 使用相同的骨架模型（GPT-4o）进行公平对比，并控制温度等超参数。
  - 人类评估作为基准，但人类玩家仅执行一次（非多次取平均），且人类玩家是新手，可能影响公平性。
  - 实验覆盖了多种复杂度和领域的任务，但每次运行次数有限（5次），且部分任务成功率波动较大（如 RDR2 的 Protect Dutch 仅 1/5 成功）。
  - 消融实验设计合理，验证了各模块的必要性。

**总体评价**：实验规模较大，场景多样，对比方法合理，但受限于成本和推理速度，重复次数偏少，统计显著性有待加强。

## 6. 主要结论与发现

- Cradle 首次使 LMM 驱动的智能体能够在复杂 AAA 游戏（RDR2）中完成长达一小时的主线任务（约 8000 步，98 分钟游戏内时间），达到人类玩家水平的近似表现（人类平均 67 分钟）。
- 在 Stardew Valley 中，智能体能够完成大多数种植任务（4/5 成功），但在像素级定位和物体交互方面仍弱于人类。
- 在 Dealer's Life 2 中，Cradle 通过谨慎的谈判策略取得了比人类玩家更高的总利润率（+39.6% vs. +17.3%），成功交易率 93.6%。
- 在 Cities: Skylines 中，Cradle 能规划基本城市布局（平均人口 450），但因视觉理解不足导致水管连接错误，影响人口增长。
- 在软件应用和 OSWorld 上，Cradle 表现优于大多数基线，特别是在需要视觉理解和错误修复的专业领域。
- 消融实验表明，**信息收集模块**对性能影响最大，其次是自我反思和任务推断。

## 7. 优点

- **统一接口**：以截图输入、键盘鼠标输出，无需任何内部 API，极大扩展了智能体可交互的虚拟场景范围。
- **模块化设计**：六大模块职责清晰，可独立改进或替换，易于适配新环境。
- **技能自动生成**：通过游戏内引导或自我探索自动生成可复用的代码技能，无需人工预定义大部分技能。
- **首次探索 GCC**：为将任意软件（尤其是复杂游戏）转化为智能体测试床和数据收集平台提供了可行范式。
- **实验覆盖全面**：涵盖 AAA 游戏、2D 像素游戏、模拟经营游戏、办公软件、视频编辑软件等多个领域，展示了较强的泛化性。

## 8. 不足与局限

- **LMM 能力瓶颈**：当前 GPT-4o 在非写实风格游戏（如 Stardew Valley）的图标识别、空间定位、精细控制方面表现不佳，限制了任务成功率。
- **推理延迟**：每次调用 LMM 需数十秒，导致游戏内需要频繁暂停，影响时间敏感任务（如战斗）的表现。
- **缺少音频输入**：屏幕截图未包含音频信息，而许多游戏和软件依赖声音反馈。
- **成本高昂**：单次完整实验费用超过 5400 美元，阻碍了大规模重复验证和社区复现。
- **实验覆盖有限**：每任务仅 5 次运行，部分任务成功率低，统计可靠性不足；人类玩家也仅各执行一次，对比不够严谨。
- **环境适应性**：虽然框架理论通用，但目前仍需针对每个环境进行提示工程和少量预定义技能，未完全实现零迁移。
- **未涉及训练**：目前仅使用预训练 LMM 进行推理，未结合强化学习或行为克隆进行自我提升。

（完）
