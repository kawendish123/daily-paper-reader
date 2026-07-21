---
title: Edge-First Ground Reaction Force Estimation with Consumer Smartwatches
authors: "Ghaffarzadeh, P., Chakraborty, D., Aslansefat, K., Dostan, A., Papadopoulos, Y."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.18.739307v1.full.pdf"
tags: ["query:mec-video"]
score: 6.0
evidence: 边缘优先的可穿戴系统用于地面反作用力估计，在手表和iPhone上进行本地推理，无需云端
tldr: 在实验室外长期监测地面反作用力困难。本文提出边缘优先的可穿戴系统，利用消费级智能手表采集惯性数据，在iPhone上本地运行GRFNet-MultiScale模型进行推理，无需云端。在10名受试者上达到平均皮尔逊相关系数0.798，证明了边缘计算的可行性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-18-739307-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 1624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-18-739307-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1868, \"height\": 1365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-18-739307-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 176, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-18-739307-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 277, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-18-739307-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 276, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-18-739307-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 279, \"height\": 192, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-18-739307-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 250, \"height\": 345, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-18-739307-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 959, \"height\": 373, \"label\": \"Table\"}]"
motivation: 边缘优先的可穿戴系统用于地面反作用力估计，在手表和iPhone上进行本地推理，无需云端。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## Abstract
Ground reaction force (GRF) measurement remains largely confined to instrumented laboratories, limiting longitudinal monitoring in daily life. This article presents an edge-first wearable system for estimating vertical GRF from consumer smartwatches. Two Apple Watch Series 6 devices worn at the wrist and waist stream 12-channel inertial data at 100 Hz to an iPhone, where preprocessing, storage, and inference occur locally without cloud dependence. The proposed GRFNet-MultiScale model is a compact temporal convolutional network with four dilated residual blocks and a global context branch. Under leave-one-subject-out evaluation on 539 stance windows from 10 healthy participants, the dual-sensor system achieved a mean Pearson correlation of 0.798 with an RMSE of 257 N, while a wrist-only configuration retained 82.5% of dual-sensor correlation. Temporal attribution remained stable across validation folds and identified early-stance wrist acceleration as the dominant reproducible signal. The system is strongest for cyclic locomotion.