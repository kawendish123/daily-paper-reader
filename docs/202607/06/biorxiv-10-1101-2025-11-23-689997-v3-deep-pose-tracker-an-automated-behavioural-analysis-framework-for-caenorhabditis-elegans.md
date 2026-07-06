---
title: "Deep-Pose-Tracker: an automated behavioural analysis framework for Caenorhabditis elegans"
title_zh: Deep-Pose-Tracker：一种用于秀丽隐杆线虫的自动化行为分析框架
authors: "Saha, D., Chaudhary, S., Vyas, D., Ghosh-Roy, A., Sharma, R."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.23.689997v3.full.pdf"
tags: ["query:mec-video"]
score: 6.0
evidence: 动物行为自动化视频分析
tldr: 秀丽隐杆线虫的行为分析在神经科学和发育生物学中至关重要，但手动追踪耗时费力。Deep-Pose-Tracker基于YOLO模型实现了自动姿态检测，并集成了运动速度、方向、转向、欧米伽转弯等下游分析算法及特征蠕虫分解。在验证和测试数据集上表现出高推理速度和稳定性。该框架为不同实验刺激下的线虫行为量化提供了高效易用的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 减少手动追踪线虫行为的耗时与误差，实现自动化的行为分析。
method: 基于YOLO的自动姿态检测模型，结合下游行为量化算法。
result: 在验证和测试数据集上检测可靠，推理速度快。
conclusion: 提供了用户友好的自动化行为量化工具，适用于多种实验条件。
---

## 摘要
追踪和分析动物行为是神经科学和发育生物学等领域的关键步骤。例如，对秀丽隐杆线虫的行为研究有助于理解有机体如何响应外部线索，以及特定的生理反应如何与瞬时或习得行为相关联。尽管通过运动模式及姿态动力学来追踪行为已是常规操作，但人工手动执行时变得繁琐且耗时。因此，实现这一过程的自动化对于准确快速地进行检测和分析至关重要。为此，我们报告了Deep-Pose-Tracker（DPT），一个基于YOLO（You Only Look Once）的模型，用于从视频和图像中自动检测线虫的姿态。该模块进一步应用于多个下游分析算法，以量化基本行为特征，包括运动速度、朝向、向前或向后运动，以及诸如omega转弯等复杂身体弯曲。此外，它还包含特征蠕虫分解，以在低维空间中表示复杂的姿态动力学。该模型在验证和测试数据集上表现出可靠的性能，推理速度快，同时用户友好。因此，DPT可以成为在不同实验刺激下自动量化秀丽隐杆线虫行为的有价值工具包。

## Abstract
Tracking and analyzing animal behaviour is a crucial step in fields such as neuroscience and developmental biology. Behavioural studies in the nematode C. elegans, for example, help in understanding how organisms respond to external cues and how the specific physiological responses link to either instantaneous or learned behaviours. Although tracking behaviour through locomotion patterns and postural dynamics is routine, it becomes laborious and time-consuming when performed manually. Automation of this process is therefore crucial for accurate and fast detection and analysis. To this end, we report Deep-Pose-Tracker (DPT), a YOLO (You Only Look Once)-based model for automated pose detection of C. elegans from videos and images. The module is further utilized for several downstream analysis algorithms to quantify essential behavioural features, including locomotion speed, orientation, forward or reverse locomotion, and complex body bends such as omega turns. In addition, it includes eigenworms decomposition to represent complex posture dynamics in a low-dimensional space. The model shows reliable performance on the validation and test datasets, with high inference speed, while being user-friendly. DPT, therefore, can be a valuable toolkit for automated behavioural quantification of C. elegans under varying experimental stimuli.