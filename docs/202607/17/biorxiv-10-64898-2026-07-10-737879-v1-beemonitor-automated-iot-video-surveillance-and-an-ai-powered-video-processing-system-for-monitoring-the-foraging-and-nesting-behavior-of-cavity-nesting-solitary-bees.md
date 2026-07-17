---
title: "BeeMonitor: Automated IoT video surveillance and an AI-powered video processing system for monitoring the foraging and nesting behavior of cavity-nesting solitary bees"
title_zh: "BeeMonitor: 用于监测穴居独居蜂觅食和筑巢行为的自动化物联网视频监控与AI视频处理系统"
authors: "Amoah, E. I., Sanjel, S., Boyle, N., Grozinger, C."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.10.737879v1.full.pdf"
tags: ["query:mec-video"]
score: 8.0
evidence: 基于IoT视频监控和边缘AI实时蜜蜂监测
tldr: "穴居独居蜂的觅食和筑巢行为对评估传粉服务至关重要，但人工观测效率低且难以连续。BeeMonitor集成低成本Raspberry Pi与AI视频处理流水线，结合YOLOv6目标检测、自定义多目标跟踪器BeeTrack和随机森林分类器，从连续视频中自动识别巢管进出事件。经29天野外测试，硬件可靠率达97.5%，事件检测精度91.3%、召回87.3%（F1=0.893），且检测的觅食次数与幼虫细胞数高度相关（R²=0.849）。该系统实现了高时空分辨率的实时行为监测，支持模块化扩展至其他物种。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737879-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1661, \"height\": 667, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737879-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1678, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737879-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1662, \"height\": 1028, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737879-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1707, \"height\": 981, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737879-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1670, \"height\": 1211, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737879-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1483, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737879-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1420, \"height\": 1036, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737879-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1659, \"height\": 943, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737879-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1677, \"height\": 1721, \"label\": \"Table\"}]"
motivation: 人工观测独居蜂行为耗时费力且无法连续，现有自动化系统需个体标记或无法分辨巢管级进出事件，亟需低成本、非侵入式的智能监控方案。
method: 采用树莓派进行太阳能供电的野外视频录制，结合YOLOv6检测蜜蜂、BeeTrack多目标跟踪及随机森林分类器，基于轨迹特征过滤伪检测，实现巢管进出事件识别。
result: "29天部署中硬件覆盖率达97.5%，事件检测F1=0.893；觅食次数与幼虫细胞数R²=0.849，随机森林模型（AUC=0.820）表明太阳辐射是主要驱动因素。"
conclusion: BeeMonitor证明基于计算机视觉的自动化系统可可靠提取生态相关行为数据，实现无法通过人工观测达到的时空分辨率实时监测，且设计模块化易于推广。
---

## 摘要
使用人工陷阱巢的独居蜂物种对农作物生产和栖息地质量指标具有重要意义。量化穴居独居蜂的觅食和筑巢行为对于实时分析种群数量和传粉活动，以及理解环境条件如何影响繁殖成功和种群动态至关重要。然而，人工观察劳动强度大、易受观察者偏差影响，且无法提供连续数据。现有的自动化系统要么需要对个体蜜蜂进行标记，要么只能检测存在性而无法解析巢管级别的进出事件。我们开发了BeeMonitor，这是一个集成的硬件和计算机视觉流水线，能够从连续视频中检测穴居独居蜂的巢穴进入和离开事件，以角额壁蜂（Osmia cornifrons）为模型系统。低成本树莓派负责太阳能供电的野外录制，而软件结合了目标检测（YOLOv26）、自定义多目标跟踪器（BeeTrack）以及基于轨迹特征训练的随机森林分类器，以区分真实事件与偶然检测。在29天的部署中，硬件可靠性平均覆盖率达到97.5%。该流水线实现了91.3%的精确率和87.3%的召回率（F1=0.893），在留一视频交叉验证中表现稳健（平均F1=0.904）。检测到的觅食行程与巢室数量高度相关（R²=0.849，p<0.001，n=19），随机森林模型（AUC=0.820）确定太阳辐射是觅食活动的主要驱动因素，其次是温度。BeeMonitor证明，自动化计算机视觉可以从连续视频中可靠地提取生态相关的行为数据，从而以人工观察无法达到的时间和空间分辨率实现传粉者行为和丰度的实时分析。其模块化设计支持适应其他物种和监测场景。

## Abstract
Solitary bee species that use artificial trap nests are important for agricultural crop production and as indicators of habitat quality. Quantifying cavity-nesting solitary bee foraging and nesting behavior is essential for real-time analysis of population numbers and pollination activity, as well as understanding how environmental conditions shape reproductive success and population dynamics. However, manual observation is labor-intensive, prone to observer bias, and unable to deliver continuous data. Existing automated systems either require individual bee marking or detect presence without resolving nest-tube-level entry and exit events. We developed BeeMonitor, an integrated hardware and computer-vision pipeline that detects nest entry and exit events in cavity-nesting solitary bees from continuous video, using Osmia cornifrons (the horn-faced mason bee) as a model system. A low-cost Raspberry Pi handles solar-powered field recording, while the software combines object detection (YOLOv26), a custom multiple-object tracker (BeeTrack), and a Random Forest classifier trained on trajectory-derived features to distinguish genuine events from incidental detections. Over a 29-day deployment, hardware reliability averaged 97.5% recording coverage. The pipeline achieved 91.3% precision and 87.3% recall (F1 = 0.893), generalizing robustly under leave-one-video-out cross-validation (mean F1 = 0.904). Detected foraging trips correlated strongly with brood cell counts (R2 = 0.849, p < 0.001, n = 19), and a Random Forest model (AUC = 0.820) identified solar radiation as the dominant driver of foraging activity, followed by temperature. BeeMonitor demonstrates that automated computer vision can reliably extract ecologically relevant behavioral data from continuous video, enabling real-time analysis of pollinator behavior and abundance at a temporal and spatial resolution unattainable through manual observation. Its modular design supports adaptation to other species and monitoring contexts.

---

## 论文详细总结（自动生成）

# BeeMonitor 论文详细总结

## 1. 核心问题与整体含义（研究动机与背景）
- **核心问题**：穴居独居蜂（如角额壁蜂 *Osmia cornifrons*）的觅食和筑巢行为是评估传粉服务、种群动态及环境响应的重要指标，但传统人工观测劳动强度大、存在观察者偏差，且无法实现连续、高时空分辨率的数据采集。现有自动化系统要么依赖个体标记（影响自然行为），要么仅检测蜜蜂存在而无法区分巢管级别的“进入/离开”事件。
- **研究意义**：开发一套低成本、非侵入式、能自动从连续视频中提取巢管级进出事件的软硬件一体化系统，对于实时监测传粉昆虫行为、理解环境驱动因素、支持生态研究和农业管理具有重要价值。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：集成物联网硬件与AI视频处理流水线，通过目标检测+多目标跟踪+轨迹分类，从持续录制的视频中自动识别独居蜂的巢管进出事件，无需个体标记。
- **技术细节**：
  - **硬件系统**：Raspberry Pi 4 + IMX477高分辨率摄像头 + Witty Pi 4电源管理模块，太阳能供电（100W光伏板+锂电池），支持野外持续录制（30fps，10分钟片段存储）。
  - **软件流水线**（三步）：
    1. **目标检测**：YOLOv26（单阶段检测器，无需NMS后处理）同时检测蜜蜂和巢管位置，为后续分配提供空间参考。
    2. **多目标跟踪（BeeTrack）**：基于SORT框架改进，关键创新——增大卡尔曼滤波的运动不确定性权重，使跟踪器对蜜蜂频繁的急转弯更鲁棒；匹配距离阈值根据自动估计的蜜蜂尺寸自适应缩放；保留短暂消失的轨迹（允许复活）以应对遮挡。
    3. **活动提取**：先基于几何规则提取候选进出事件（轨迹端点落于巢管范围内），再使用随机森林分类器（基于20个轨迹特征）区分真实事件与噪声，输出CSV格式的结构化数据。
- **算法流程文字说明**：输入视频帧 → YOLOv26检测蜜蜂与巢管 → BeeTrack关联检测生成轨迹 → 几何候选筛选 → 随机森林分类 → 最终事件列表。

## 3. 实验设计：数据集、场景、基准与对比方法
- **数据集与场景**：
  - 部署地点：美国宾州州立大学园艺研究农场（40.8106° N, -77.8600° W）。
  - 监测对象：约300头角额壁蜂（*Osmia cornifrons*）在木制蜂巢酒店中筑巢。
  - 监测时段：2024年4月16日至5月16日（29天），每日9:00-19:00连续录制。
  - 评估视频：从不同日期和时间段选取11段10分钟视频，共包含300个人工标注的进出事件（涵盖不同活动水平与环境条件）。
- **评估指标与基准**：
  - 硬件可靠性：录制覆盖率和存储保存率。
  - 软件性能：精确率（Precision）、召回率（Recall）、F1分数（±2秒匹配窗口）。
  - 生态验证：检测到的觅食总行程与巢管中幼虫细胞数的线性回归（R²）。
  - 环境驱动分析：随机森林分类器预测5分钟间隔内是否发生觅食（AUC），并计算特征重要性。
- **对比方法**：未直接对比其他系统在相同数据集上的结果，但文中比较了已有工作：Bee Tracker（需标记蜜蜂，精确率96%但无召回率报告）和Wittmann等（无标记，精确率78%）。BeeMonitor在无标记条件下达到91.3%/87.3%的P/R。

## 4. 资源与算力
- **文中未明确说明**训练YOLOv26或随机森林模型所使用的GPU型号、数量及训练时长。论文仅提及使用了Penn State Institute for Computational and Data Sciences（ICDS）的Roar Core Facility计算资源，但未给出具体算力细节。此外，硬件端Raspberry Pi 4用于推理（视频处理在离线或云端完成？需进一步确认），也未详述推理阶段的算力需求。

## 5. 实验数量与充分性
- **实验数量**：
  - 硬件评估：1次29天连续部署。
  - 软件评估：11段视频（共300个标注事件）的整体性能测试 + 11折留一视频交叉验证（LOVO）。
  - 生态分析：19个巢管的幼虫细胞计数与觅食次数回归；4859个5分钟时间间隔的随机森林模型（5折时间序列交叉验证）。
- **充分性分析**：
  - **优势**：LOVO交叉验证设计了11个不同日期、时间、活动水平的视频，涵盖约300个事件，验证了模型的泛化能力。环境驱动模型采用了时间序列交叉验证，避免了数据泄露。硬件覆盖率统计完整。
  - **不足**：仅单一站点、单一物种、单一季节，样本量（巢管n=19，事件n=300）相对有限；未进行跨年份、跨地点或跨物种的重复实验；缺乏与其他自动化系统在相同数据集上的直接对比（hard benchmark），而是引用文献中的不同数据集结果进行定性比较。

## 6. 主要结论与发现
1. **硬件可靠性高**：录制覆盖率达97.51%（存储保存率82.36%），主要损失源于存储空间不足（5月2-6日），系统本身运行稳定。
2. **检测性能优秀**：整体F1=0.893（P=91.3%, R=87.3%），入口事件（F1=0.928）优于出口事件（F1=0.857）。LOVO交叉验证平均F1=0.904，证明分类器泛化能力好。
3. **觅食活动与繁殖产出强相关**：每巢管觅食次数与幼虫细胞数呈线性正相关（R²=0.849, p<0.001），约14次觅食对应1个幼虫细胞。
4. **环境驱动因素明确**：太阳辐射（36.7%相对重要性）是主导因子，其次是温度（26.0%）、湿度（18.7%）、气压（12.2%），风速和降水影响微弱。随机森林预测AUC=0.820。
5. **系统实用性**：BeeMonitor可替代人工观察，提供连续、高分辨率的觅食行为数据，且模块化设计支持扩展到其他物种或场景。

## 7. 优点（亮点）
- **一体化软硬件方案**：从野外录制到事件输出全链路自动化，开源代码和3D打印文件可复现。
- **无标记、非侵入性**：避免人工标记对蜜蜂行为的影响。
- **算法创新**：针对蜜蜂运动特点改进SORT跟踪器（自适应运动不确定性、尺度自适应匹配、轨迹复活），相比标准SORT更鲁棒。
- **模块化设计**：检测、跟踪、分类三个模块可独立替换或重新训练，便于适配不同物种或摄像头设置。
- **生态验证充分**：将自动检测的觅食次数与幼虫细胞数关联，从生态学角度验证了系统的生物学有效性。
- **环境驱动因素分析**：结合高时间分辨率（5分钟）行为数据与气象数据，揭示了太阳辐射的主导作用，具有新洞见。

## 8. 不足与局限
- **实验覆盖面有限**：单站点、单季节、单物种（角额壁蜂），未测试其他穴居独居蜂或不同地理区域/气候条件。
- **硬件存储瓶颈**：存储空间不足导致约5天数据缺失（占总体18%），未实现云存储或实时上传。
- **检测性能失衡**：出口事件召回率（83.4%）低于入口事件（91.3%），可能低估实际觅食次数；可通过提高帧率或改进跟踪算法缓解。
- **算力需求未公开**：训练成本未知，且推理是否需要在本地Raspberry Pi上实时运行也未明确（论文提及离线处理？）。
- **缺乏端到端实时性测试**：从视频录制到事件输出是否有延迟未讨论。
- **仅依赖外部气象站**：未集成机载环境传感器，存在空间分辨率不匹配风险。
- **无个体识别**：无法区分不同蜜蜂个体，限制了社会性或个体水平分析（如归巢成功率、寿命等）。
- **对比不严格**：未在相同数据集上直接与现有系统（如Bee Tracker）公平对比，仅引用文献中不同条件的指标。

（完）
