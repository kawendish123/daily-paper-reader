---
title: "Sample size dependence of Occam's razor in human decision-making"
title_zh: 人类决策中奥卡姆剃刀的样本量依赖性
authors: "Rinaldi, F. G., Piasini, E."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.25.701581v3.full.pdf"
tags: ["query:mec-video"]
score: 7.0
evidence: 人类决策中模型选择原理的研究
tldr: 人类在感知决策中倾向于简单解释，但规范模型（如BIC）要求样本量N增大时简化偏见应减弱。本研究通过视觉聚类任务发现，人类行为不遵循线性缩放，而是呈现亚线性缩放，且有两个不同缩放区间，与数量感知偏差一致。这表明人类借用低层感知启发式动态权衡证据与模型复杂性。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究人类在感知决策中是否像规范模型（AIC/BIC）一样，随着样本量增加而减弱对简单模型的偏好，以及背后的计算机制。
method: 预注册视觉任务，被试推断数据点背后的高斯源数量，系统改变样本量N；对比线性缩放、无缩放、亚线性缩放三种行为模型，并用高斯过程推断缩放形状。
result: 线性缩放模型拟合最差，亚线性缩放最强；亚线性缩放呈现两个不同区间，与数量感知偏差一致。
conclusion: 人类使用高效启发式，借用量化感知等低层机制替代规范计算，动态调整样本量的有效权重以简化决策。
---

## 摘要
为了理解嘈杂的世界，生物体不断面临对模糊感官数据的竞争性解释之间的决策。这一过程类似于统计模型选择，其中大多数框架（如赤池信息准则（AIC）和贝叶斯信息准则（BIC））基于模型拟合优度与复杂性之间的权衡，并倾向于选择更简单的模型（解释）。我们之前研究了这种对简单性的偏向如何在一个简单的感知任务中反映在人类行为中。然而，规范性框架的一个核心原则是，这种权衡应依赖于样本量（N）：随着更多数据变得可用，拟合优度的增长速度快于复杂模型的“成本”，从而削弱了对简单性的整体偏向。目前尚不清楚人类是否也遵循类似的比例缩放原则，如果是，这种行为是源于类似于导致规范性解决方案的内部计算，还是源于更简单的启发式方法。在这里，我们通过一个预注册的视觉任务研究这些问题，在该任务中，受试者推断产生数据点簇的潜在高斯源的数量，并且每次试验中呈现的点数（N）被系统地变化。我们考虑了三种对参与者行为的描述：一种源于感官证据权重在N中的线性缩放（如BIC和AIC中所示），一种无缩放，另一种受已知数量感知偏差启发的亚线性缩放。我们的结果表明，规范性的线性缩放描述对人类行为的解释最差。相反，我们发现了有效样本量亚线性缩放的强有力证据。通过使用高斯过程推断这种缩放的形状，我们揭示了不同N范围内的两种不同缩放模式，与数量感知偏差一致。我们的发现表明，在选择对感官数据的竞争性解释时，人类采用了一种高效的启发式方法，重新利用低层次的感知机制来动态权衡证据与模型复杂性。

## Abstract
To make sense of a noisy world, living beings constantly face decisions between competing interpretations for ambiguous sensory data. This process parallels statistical model selection, where most frameworks, like the Akaike Information Criterion (AIC) and the Bayesian Information Criterion (BIC), are based on a trade-off between a model's goodness-of-fit and its complexity and prescribe a bias towards simpler models (explanations). We previously studied how this same bias towards simplicity is reflected in human behavior for a simple perceptual task. However, a core tenet of normative frameworks is that the trade-off should depend on the sample size (N): as more data becomes available, the goodness-of-fit grows faster than the "cost" of complex models, weakening the overall bias towards simplicity. It is unknown whether humans also conform to an analogous scaling principle, and if so, whether this behavior arises from an internal computation similar to that leading to the normative solution or from a simpler heuristic. Here, we investigate these questions using a preregistered visual task where subjects inferred the number of latent Gaussian sources generating clusters of data-points, and where the number of points (N) presented on each trial is varied systematically. We consider three kinds of descriptions for participant behavior: one arising from a linear scaling of the weight of sensory evidence in N (as in BIC and AIC), one with no scaling, and one with sublinear scaling inspired by known biases in numerosity perception. Our results demonstrate that the normative, linear scaling description provides the worst account of human behavior. Instead, we find strong evidence for a sublinear scaling of effective sample size. By inferring the shape of this scaling with Gaussian Processes, we reveal two distinct scaling regimes for different ranges of N, consistent with numerosity perception biases. Our findings suggest that, when selecting between competing explanations for sensory data, humans employ an efficient heuristic that repurposes lower-level perceptual mechanisms to dynamically weight evidence against model complexity.