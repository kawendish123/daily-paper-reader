---
title: A Web-based software toolkit for accessible and best-practice machine learning analyses in biomedical research
title_zh: 一个基于Web的软件工具包，用于生物医学研究中可访问且最佳实践的机器学习分析
authors: "Morais Lyra Junior, P. C., Qiu, J., Van Dang, K., Pybus, A., Narvaez-Bandera, I., Singh, M. A., Gu, Q., Sargent, L., Creason, A. L., Goecks, J."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730487v1.full.pdf"
tags: ["query:mec-video"]
score: 7.0
evidence: 工具包含模型选择功能
tldr: 生物医学研究中，利用机器学习进行预测分析日益关键，但高效、规范地使用需要大量计算专业知识和操作经验，这常成为障碍。GLEAM作为Galaxy上的Web工具套件，提供无需编程的图形界面，标准化了从数据划分到模型报告的全流程，自动追踪所有步骤，确保可重复性和最佳实践。在免疫治疗反应、皮肤病变和癌症复发三个预测任务中，GLEAM均产生了高精度模型，且分析完全透明，便于审查和复现。GLEAM支持表格、图像和多模态数据，大幅降低了机器学习使用门槛，使无编程背景的研究者也能严格进行分析，提升研究整体质量和可信度。
source: biorxiv
selection_source: fresh_fetch
motivation: 机器学习在生物医学研究中日益重要，但高效使用需要大量计算专业知识和操作经验，现有工具门槛高且不够规范。
method: GLEAM运行在Galaxy上，提供无代码Web界面，标准化从数据划分到模型报告的全流程，自动追踪步骤，确保可重复性和最佳实践。
result: 在免疫治疗反应、皮肤病变分类和癌症复发三个预测任务中，GLEAM均生成高精度模型，且分析过程透明可复现。
conclusion: GLEAM显著降低了机器学习使用门槛，使无编程背景的研究者也能规范分析，提升研究可访问性和可重复性。
---

## 摘要
机器学习在生物医学研究中日益重要，但有效使用机器学习通常需要大量的计算专业知识和严谨的方法学才能产生高质量的结果。为了使生物医学研究人员更容易使用机器学习工具，同时支持最佳实践方法，我们开发了Galaxy学习与建模（GLEAM）软件工具包。GLEAM通过一组基于Web、无需编程的软件工具，支持对表格、图像和多模态生物医学数据集进行监督式机器学习分析。GLEAM标准化了数据划分、模型选择、训练、评估和报告流程，帮助研究人员以更高的严谨性和一致性应用机器学习。GLEAM运行在Galaxy计算工作台上，并利用Galaxy的核心功能使所有分析都可访问、可重复和可扩展。我们在三个生物医学任务上验证了GLEAM：预测患者对免疫疗法的反应、皮肤病变分类和癌症复发预测。在这些任务中，GLEAM生成了高精度的预测模型，并提高了透明度、可重复性和严谨性。

## Abstract
Machine learning is increasingly central to biomedical research, but using machine learning well often requires substantial computational expertise and methodological care to produce high-quality results. To make machinelearning tools more accessible to biomedical researchers while supporting best-practice approaches, we developed the Galaxy Learning and Modeling (GLEAM) software toolkit. GLEAM enables researchers to performsupervised machine learning analyses through a set of web-based, code-free software tools for tabular, image, and multimodal biomedical datasets. GLEAM standardizes data partitioning, model selection, training, evaluation,and reporting, helping researchers apply machine learning with greater rigor and consistency. GLEAM runs on the Galaxy computational workbench and uses Galaxy's core features to make all analyses accessible,reproducible, and scalable. We validated GLEAM on three biomedical tasks: predicting patient response to immunotherapy, skin lesion classification, and cancer recurrence prediction. Across these tasks, GLEAM producedhighly accurate predictive models and improved transparency, reproducibility, and rigor.