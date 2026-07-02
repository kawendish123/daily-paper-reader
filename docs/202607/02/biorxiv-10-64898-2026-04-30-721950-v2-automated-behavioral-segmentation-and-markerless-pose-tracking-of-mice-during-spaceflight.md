---
title: Automated behavioral segmentation and markerless pose tracking of mice during spaceflight
title_zh: 太空飞行中老鼠的自动化行为分割与无标记姿态追踪
authors: "Kiffer, F. C., Scott, R. T., Martens, M. T., Mayo, A., Li, Y., Mendoza, M., Gautam, S., Huang, J., Bathwal, M., Jaikumar, S., Mahajan, A., Sanders, L. M., Eisch, A. J., Pereira, T. D."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721950v2.full.pdf"
tags: ["query:mec-video"]
score: 6.0
evidence: 自动视频行为分析
tldr: 太空舱内啮齿动物行为分析依赖人工标注，效率低下。本研究首次将深度学习姿态估计（SLEAP）和行为分割（DeepEthogram）应用于国际空间站存档视频，在镜头污染、网格遮挡等复杂条件下实现自动分析。姿态追踪精度接近人工标注者间一致性，8类行为分类准确率达0.86-0.90，并揭示了微重力下的渐进行为适应。该工作为太空飞行动物行为监测建立了自动化基准。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有太空舱内啮齿动物行为分析依赖人工标注，缺乏在复杂成像条件下自动化工具的验证。
method: "应用SLEAP进行姿态估计、DeepEthogram进行行为分割，由9名标注员标注3249个姿态和3名行为学家标注411,194帧视频。"
result: 姿态追踪精度接近人工变异，行为分类准确率0.86-0.90，发现微重力下行为适应，重建圆圈运动时向心加速度周期接近1g。
conclusion: 首次证明深度学习可自动化太空飞行中啮齿动物行为分析，为未来轨道监测系统建立基准。
---

## 摘要
国际空间站上的NASA啮齿动物栖息地使得能够对太空飞行的行为反应进行长期研究，但基于视频的行为分析依赖于费力的手动标注。尚无研究测试深度学习工具是否能在轨道动物饲养室的苛刻成像条件下自动化这一分析。我们将姿态估计（SLEAP）和行为分割（DeepEthogram）应用于啮齿动物研究-1任务的存档视频。九名标注员在2063帧中标注了3249个姿态标签，三名行为学家在66个视频中标注了411,194帧。尽管存在渐进式镜头污损、网格遮挡和球面像差，姿态追踪精度接近人工标注者间变异性。八个类别的行为分类准确率达到0.86-0.90，并提示对微重力的渐进行为适应。盘旋的运动学重建估计向心加速度周期性地接近1g。这是深度学习姿态估计和行为分割首次应用于太空飞行中的啮齿动物，为未来的监测系统建立了基准。

## Abstract
The NASA Rodent Habitat aboard the International Space Station enabled long-duration studies of behavioral responses to spaceflight, but video-based behavioral analysis has relied on laborious manual annotation. No study has tested whether deep learning tools can automate this analysis under the demanding imaging conditions of orbital vivaria. We applied pose estimation (SLEAP) and behavioral segmentation (DeepEthogram) to archival footage from the Rodent Research-1 mission. Nine labelers annotated 3,249 pose labels across 2,063 frames, and three behaviorists labeled 411,194 frames across 66 videos. Pose tracking accuracy approximated human inter-annotator variability despite progressive lens soiling, grid occlusions, and spherical aberration. Behavioral classification across eight categories achieved accuracy of 0.86-0.90 and suggests progressive behavioral adaptations to microgravity. Kinematic reconstruction of circling estimated centripetal accelerations periodically approaching 1g. This is the first application of deep learning-based pose estimation and behavioral segmentation to rodents in spaceflight, establishing benchmarks for future monitoring systems.