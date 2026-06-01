---
title: "DLC2Action: A Multimodal Deep Learning-based Toolbox for Automated Behavior Segmentation"
title_zh: DLC2Action：基于多模态深度学习的自动行为分割工具箱
authors: "Kozlova, E., Bonnetto, A., Mathis, A."
date: 2026-05-30
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.27.678941v2.full.pdf"
tags: ["query:mec-video"]
score: 8.0
evidence: 自动视频行为标注与模型选择
tldr: 行为分析是神经科学的基础，但手动标注动作耗时且限制可重复性。DLC2Action工具箱整合多个深度学习架构，支持多模态输入（视频、音频、姿态）和自监督学习，在标注数据稀缺时也能提升性能。在9个涵盖啮齿动物、人类和野生动物的公开数据集上取得优秀结果，并发现Atari游戏中玩家眼球运动可预测按键。该工具箱开源且带有图形界面，支持模块化扩展，为行为自动化分析提供了易用且强大的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 手动行为标注不可扩展且可重复性差，亟需自动化的多模态行为分割工具。
method: 集成多种深度学习架构，支持自监督学习，从视频、音频和2D/3D姿态数据中自动分割行为。
result: 在9个多样化数据集上表现强劲，并成功应用于Atari游戏，揭示眼球运动与按键的一致性。
conclusion: 提供开源、模块化、带GUI的行为分析工具箱，显著提升行为研究的效率和可重复性。
---

## 摘要
行为分析是神经科学的基础，然而动作的手动标注仍然是制约实验规模和可重复性的瓶颈。本文介绍DLC2Action，一个开源的Python工具箱，能够从视频、音频以及估计的2D/3D姿态追踪数据中自动标注行为。DLC2Action集成了多种针对动作分割优化的最新深度学习架构，并支持自监督学习（SSL）以应对标注稀缺问题，在有限标注数据集上提升性能。为了便于模型比较，我们为九个不同数据集建立了固定的训练/测试划分，涵盖啮齿动物实验、人类烹饪研究和野生动物观察。DLC2Action在这些基准测试中均表现出色。为进一步展示该工具的通用性，我们将其应用于Atari游戏数据，发现在某些游戏中，玩家的眼球运动能跨被试一致地预测其按键操作。由于DLC2Action具有直观的图形用户界面（GUI），用户可以简化行为标注流程、执行主动学习并评估模型预测。支持多种姿态、视频和标注格式。最后，DLC2Action采用模块化设计，易于扩展，允许用户集成新模型、数据集特征和方法。代码和基准测试数据见：https://github.com/amathislab/DLC2action

## Abstract
Behavioral analysis is fundamental to neuroscience, yet the manual annotation of actions remains a bottleneck that constrains both the scale and the reproducibility of experiment. Here, we present DLC2Action, an open-source Python toolbox that enables automatic behavior annotation from video, audio and estimated 2D/3D pose tracking data. DLC2Action integrates multiple state-of-the-art deep learning architectures optimized for action segmentation and supports self-supervised learning (SSL) to address annotation scarcity, boosting performance with limited labeled datasets. To enable model comparison, we establish fixed train/test partitions for nine diverse datasets comprising rodent experiments, human cooking studies, and wildlife observation. DLC2Action reached strong performance across those benchmarks. To further showcase the tool's versatility, we applied it to Atari gameplay data and found that, in certain games, the players' eye movements consistently predict their button presses across subjects. Because DLC2Action features an intuitive graphical user interface (GUI), users can streamline behavior annotation, perform active learning, and assess of model predictions. Diverse pose, video, and annotation formats are supported. Lastly, DLC2Action is modular and thus designed for extensibility, allowing users to integrate new models, dataset features, and methods. The code and benchmarks are available at: https://github.com/amathislab/DLC2action