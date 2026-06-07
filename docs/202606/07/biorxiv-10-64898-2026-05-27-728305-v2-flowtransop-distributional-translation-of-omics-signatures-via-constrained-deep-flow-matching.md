---
title: "FlowTransOP: Distributional Translation of Omics Signatures via Constrained Deep Flow Matching"
title_zh: "FlowTransOP: 通过约束深度流匹配实现组学特征的分布翻译"
authors: "Meimetis, N., Hoang, T. N., Magliacane, S., Lauffenburger, D. A."
date: 2026-05-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728305v2.full.pdf"
tags: ["query:mec-video"]
score: 6.0
evidence: 提供跨翻译体制的模型选择指南
tldr: 临床前模型与人类患者间的生物观测跨域转化常因特征不重叠和缺乏配对数据而失败。FlowTransOP通过深度流匹配在预对齐潜在空间中对齐域分布，并引入结构正则化保持相似条件邻近。在配对样本少于35或特征相关性≤0.58时，其性能优于需配对样本的金标准方法。该模型基于ARCHS4训练的小鼠-人类转录组基础图谱，成功应用于肝病预测，实现了无直接对应关系下的可靠治疗推断。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法无法处理特征非重叠、无配对样本的跨域转化，导致临床前模型难以泛化到人类，阻碍可靠治疗推断。
method: FlowTransOP使用约束深度流匹配，在预对齐潜在空间中对齐完整域分布，并通过结构正则化使相似条件在变换后保持邻近。
result: 在配对样本少于35或特征相关性≤0.58时，FlowTransOP优于黄金标准方法；基于ARCHS4的小鼠-人类图谱成功预测肝脏疾病。
conclusion: FlowTransOP能在无需直接对应关系下翻译临床前模型与患者的生物扰动，为可靠的治疗推断提供新途径。
---

## 摘要
来自临床前模型的观察结果很少能推广到人类患者，导致临床试验中许多失败。大多数现有方法无法处理特征不重叠且无配对样本的领域。在这里，我们开发了FlowTransOP，用于跨此类领域翻译生物观察结果，无需一对一的特征映射和配对数据，同时为跨四种翻译模式的模型选择提供了指南。我们使用流匹配在一个预对齐的潜在空间中对齐完整的域分布，并通过结构正则化项保持转换后相似条件的接近性。FlowTransOP与需要配对样本的金标准方法相比保持竞争力，但在配对样本稀缺（<35对）或跨域特征仅中等相关（r<=0.58）时表现更优。总之，当直接对应关系不可用时，FlowTransOP可以在临床前模型和患者之间翻译扰动，从而实现可靠的治疗推断。作为概念验证，我们在ARCHS4上训练了一个基础的小鼠-人类转录组图谱，并将其应用于肝脏疾病预测。

## Abstract
Observations from pre-clinical models rarely generalize to human patients, leading to many failures in clinical trials. Most existing methods cannot handle domains with non-overlapping features and no paired samples. Here, we developed FlowTransOP to translate biological observations across such domains without requiring 1-to-1 feature mappings and paired data, while providing a guideline for model selection across four translational regimes. We use flow matching to align full domain distributions in a pre-aligned latent space, with a structural regularization term that keeps similar conditions proximate after transformation. FlowTransOP remains competitive with gold-standard approaches requiring paired samples, but outperforms them when pairs become scarce (<35 pairs) or when cross-domain features are only moderately correlated (r<=0.58). Overall, FlowTransOP can translate perturbations between pre-clinical models and patients when direct correspondences are unavailable, enabling reliable therapeutic inference. As a proof-of-concept, we trained a foundational mouse-human transcriptomic map on ARCHS4 and applied it to liver disease predictions.