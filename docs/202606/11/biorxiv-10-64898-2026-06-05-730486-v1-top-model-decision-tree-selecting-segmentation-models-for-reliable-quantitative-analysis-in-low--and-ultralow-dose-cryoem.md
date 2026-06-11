---
title: "Top Model Decision Tree: Selecting Segmentation Models for Reliable Quantitative Analysis in Low- and Ultralow-Dose CryoEM"
title_zh: 顶层模型决策树：为低剂量和超低剂量冷冻电镜中的可靠定量分析选择分割模型
authors: "Massenburg, L. N., Madugula, S. S., Brown, S. R., Bible, A. N., Harris, C. R., Zhang, L. X., Parker, K., Retterer, S. T., Morrell-Falvey, J. L., Vasudevan, R. K., Williams, A. N."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730486v1.full.pdf"
tags: ["query:mec-video"]
score: 6.0
evidence: 基于分割模型的模型选择工作流
tldr: 低剂量冷冻电镜图像中，深度学习分割模型性能受成像条件影响，导致下游定量分析不可靠。为此，提出系统评估工作流，以细菌包膜厚度测量为例，比较YOLOv11、U-Net等架构。结果表明，YOLOv11保真度最高，SAM3在超低剂量下鲁棒性更强，但高F1模型可能因拥挤或伪影产生偏差。该工作强调模型选择应基于实验需求而非单一指标，为AI驱动的冷冻电镜分析提供实践指导。
source: biorxiv
selection_source: fresh_fetch
motivation: 深度学习模型在低剂量冷冻电镜分割中表现不一，需要系统性筛选以保证下游定量分析的可靠性。
method: 构建结构化评估流程，以细菌包膜厚度为测试用例，比较YOLOv11、U-Net等模型在不同剂量下的性能、速度和鲁棒性。
result: YOLOv11提供最高保真度的膜分割，SAM3在超低剂量下鲁棒性更优，而高F1模型可能因拥挤或插值伪影产生测量偏差。
conclusion: 模型选择应权衡性能、速度与成像条件，优先考虑下游定量分析需求，而非仅依赖分割指标。
---

## 摘要
深度学习神经网络为分割低对比度冷冻电子显微镜（cryoEM）图像提供了一种强大的方法。然而，模型性能在不同成像条件下可能有显著差异，并可能阻碍下游定量分析。在此，我们提出一个结构化评估工作流程，基于性能、推理速度、跨成像条件的鲁棒性以及下游定量测量的可靠性，系统筛选分割模型。以细菌细胞包膜厚度工具（BCET）为测试案例，我们在低剂量和超低剂量cryoEM条件下评估了多种架构（YOLOv11、YOLOv26、U-Net、Detectron2和SAM3）。虽然多个模型取得了高指标，但模型选择强烈影响下游包膜厚度的测量。针对高F1分数优化的模型可能因物体拥挤、插值伪影或成像条件而产生不可靠的分割掩膜。我们的结果揭示了模型在性能、速度和鲁棒性之间的不同权衡。YOLOv11为定量测量提供了最高保真度的膜分割，而基于Meta的模型SAM3在超低剂量条件下提供了改进的鲁棒性，且推理性能具有竞争力。这项工作为cryoEM工作流程中的模型选择提供了实用指导，强调最优选择取决于实验优先级和下游分析需求，而不仅仅是指标。随着基于AI的分析扩展到生物科学之外，这些发现与cryoEM工作流程广泛相关。

## Abstract
Deep learning neural networks provide a powerful approach for segmenting low-contrast cryogenic electron microscopy (cryoEM) images. However, model performance can vary significantly across imaging conditions and may hinder downstream quantitative analyses. Here, we present a structured evaluation workflow to systematically screen segmentation models based on performance, inference speed, robustness across imaging conditions, and reliability of downstream quantitative measurements. Using the Bacterial Cell Envelope Thickness Tool (BCET) as a test case, we evaluate multiple architectures (YOLOv11, YOLO26, U-Net, Detectron2, and SAM3) under low-dose and ultralow-dose cryoEM conditions. While several models achieve high metrics, model choice strongly influences downstream measurements of envelope thickness. Models optimized for high F1-scores may produce unreliable segmentation masks from object crowding, interpolation artifacts or imaging conditions. Our results reveal distinct trade-offs between performance, speed, and robustness amongst models. YOLOv11 provides the highest fidelity membrane segmentation for quantitative measurements and the Meta-based model SAM3 offers improved robustness under ultralow-dose conditions with competitive inference performance. This work provides practical guidance for model selection in cryoEM workflows, emphasizing that optimal choice depends on experimental priorities and downstream analysis requirements rather than metrics alone. These findings are broadly relevant to cryoEM workflows as AI-based analysis expands beyond the biological sciences.

Graphical Abstract

O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=142 SRC="FIGDIR/small/730486v1_ufig1.gif" ALT="Figure 1">
View larger version (33K):
org.highwire.dtl.DTLVardef@f29df4org.highwire.dtl.DTLVardef@601d6eorg.highwire.dtl.DTLVardef@2c5023org.highwire.dtl.DTLVardef@1413f76_HPS_FORMAT_FIGEXP  M_FIG C_FIG