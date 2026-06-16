---
title: An end-to-end platform for pose estimation and real-time edge-AI deployment
title_zh: 用于姿态估计与实时边缘AI部署的端到端平台
authors: "Haggerty, D. L., Darden, C. B., Lovinger, D. M."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.24.700912v2.full.pdf"
tags: ["query:mec-video"]
score: 8.0
evidence: 基于视频姿态估计的实时边缘AI部署
tldr: 现有姿态估计工具多针对离线工作流，依赖碎片化软件、工作站GPU或外部中间件，难以实时边缘部署。本文提出集成软硬件生态系统，包括覆盖数据创建、训练、离线分析的SqueakPose Studio，实时部署的SqueakView和模块化硬件箱MouseHouse。该系统在CPU、GPU、Apple Silicon及嵌入式设备上高效运行，无需工作站级硬件。该平台统一了离线与实时实验流程，为行为分析提供了端到端的可部署方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有工具依赖工作站级硬件和碎片化软件，无法在边缘设备上实时运行姿态估计。
method: 提出集成软硬件生态系统，包括SqueakPose Studio、SqueakView和MouseHouse，统一数据格式与定时架构。
result: 在嵌入式边缘设备上实现实时姿态估计，支持多种硬件平台，无需外部中间件。
conclusion: 该平台为离线分析和实时实验提供统一解决方案，降低对高端硬件的依赖。
---

## 摘要
精确的姿态估计是行为定量分析的基础，然而许多基于深度学习的追踪工具仍主要针对离线工作流程优化，这些流程依赖于碎片化的软件管线、工作站级GPU或外部中间件来实现实时部署。本文提出了一种用于姿态估计的软硬件集成生态系统，涵盖数据集创建、模型训练、离线分析以及在嵌入式边缘计算设备上的实时部署。SqueakPose Studio提供了一套用于基于深度学习的整帧姿态估计的软件套件，统一了数据集创建、手动和模型辅助标注、模型训练、验证以及大规模离线推理。该系统利用现代目标检测架构，无需基于块的采样或多阶段后处理即可实现高效的端到端训练和推理，并支持在CPU、GPU和Apple Silicon上执行。对于需要连续记录和同步数据采集的实验场景，SqueakView支持在嵌入式边缘计算硬件上进行实时模型部署、视频捕获和传感器日志记录，而MouseHouse则提供了一种专为基于家居笼实验设计的紧凑、模块化外壳，集成了嵌入式GPU计算、基于微控制器的定时和外围I/O。共享的数据格式和确定性定时架构确保了离线分析和实时部署之间的一致性。SqueakPose Studio、SqueakView和MouseHouse共同提供了一个统一的姿态估计平台，既支持传统的离线分析，也支持嵌入式实时实验，且无需依赖工作站级硬件或外部中间件。

## Abstract
Accurate pose estimation underpins quantitative analysis of behavior, yet many deep learning-based tracking tools remain optimized for offline workflows that rely on fragmented software pipelines, workstation-grade GPUs, or external middleware to enable real-time deployment. Here we present an integrated software-hardware ecosystem for pose estimation that spans dataset creation, model training, offline analysis, and real-time deployment on embedded edge-computing devices. SqueakPose Studio provides a software suite for whole-frame, deep learning-based pose estimation that unifies dataset creation, manual and model-assisted labeling, model training, validation, and large-scale offline inference. The system leverages modern object-detection architectures to enable efficient end-to-end training and inference without patch-based sampling or multi-stage postprocessing, and supports execution on CPUs, GPUs, and Apple Silicon. For experimental settings requiring continuous recording and synchronized data acquisition, SqueakView enables real-time model deployment, video capture, and sensor logging on embedded edge-computing hardware, while MouseHouse provides a compact, modular enclosure designed for home cage-based experiments that integrates embedded GPU compute, microcontroller-based timing, and peripheral I/O. A shared data format and deterministic timing architecture ensure consistency across offline analysis and real-time deployment. Together, SqueakPose Studio, SqueakView, and MouseHouse provide a unified platform for pose estimation that supports both conventional offline analysis and embedded, real-time experimentation, without reliance on workstation-grade hardware or external middleware.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与研究动机

- **背景**：深度学习的姿态估计工具（如 DeepLabCut、SLEAP、Lightning Pose）已能精准追踪无标记动物姿态，但大多数工具针对离线分析优化，依赖工作站级 GPU、碎片化软件管线以及外部中间件（如 Bonsai）才能实现实时部署。这种架构引入可变延迟，难以实现确定性同步，限制了在嵌入式或高通量实验中的应用。
- **核心问题**：如何构建一个**端到端的软硬件生态系统**，既能进行离线高精度分析，又能直接在嵌入式边缘设备上实时运行姿态估计，且无需依赖昂贵的工作站硬件或外部中间件。
- **整体意义**：为行为神经科学提供一套统一的、可扩展的、低成本的实验平台，使模型训练、推理、传感器同步及闭环控制在一个框架内完成，降低技术门槛并加速高吞吐量实验。

## 2. 方法论：核心思想与关键技术

- **核心思想**：采用现代单阶段目标检测架构（YOLOv11）替代传统两阶段（如 ResNet + patch 采样）姿态框架，实现**整帧推理**，无需裁剪和复杂后处理；同时将软件、硬件和控制统一起来，采用**共享数据格式和确定性定时架构**。
- **关键技术细节**：
  - **SqueakPose Studio**：基于 Python 3.12 和 PyQt6 的图形界面套件，集成数据集创建、手动/模型辅助标注、YOLO 训练、验证和离线推理。支持 bounding box 及 keypoint 标注，可直接导出 YOLO 格式。
  - **模型架构**：YOLOv11s-pose，采用 C2f-Darknet 骨干网络 + PAN-FPN++ 特征融合颈部 + 多任务检测/姿态/分割头。
  - **训练优化**：标准数据增强（旋转±15°、翻转、缩放、亮度/对比度抖动），150 epoch，batch size = 8。
  - **SqueakView**：运行在 Jetson Orin Nano Super 上的实时软件，通过 TensorRT 引擎部署模型（FP32/FP16/INT8），集成 DeepStream 管道进行实时视频捕获、推理和传感器日志。
  - **MouseHouse**：3D 打印的模块化行为箱，集成 Jetson Orin Nano Super 和 RP2040 微控制器（作为时序主控），支持 TTL 同步、电容式舔水检测、FED3 食物颗粒发放等外设。
  - **行为分析**：Jupyter Notebook 工具，自动计算距离、速度、加速度、朝向等运动特征；支持像素到真实世界单位校准（1-Euro 平滑）；使用 UMAP + HDBSCAN 进行半监督行为聚类。
  - **推理部署流程**：PyTorch → ONNX → TensorRT（支持 INT8 量化，使用内部标定数据）。

## 3. 实验设计

- **数据集**：15 个视频（每个 10 分钟，单小鼠在旷场中记录，带有双侧光遗传光纤线缆），手动标注 150 帧（bounding box + 6 个关键点：鼻子、头部、左耳、右耳、背部、尾根）。80/20 划分训练/验证。
- **基准（Benchmark）**：与 **DeepLabCut**（ResNet-50 骨干）进行对比，在**相同训练集和条件**下训练和推理。
- **对比方法**：仅对比了 YOLOv11s-pose 与 DeepLabCut（ResNet-50），未与其他工具（如 SLEAP、Lightning Pose）直接比较。
- **实验场景**：
  - 训练速度；推理速度（对完整 10 分钟视频进行全帧预测）；关键点定位精度（像素误差分布）。
  - 在 Jetson Orin Nano Super 上测试不同精度（FP32/FP16/INT8）的延迟。
  - 在样本旷场数据上展示行为分析（运动特征、ROI 分析、UMAP-HDBSCAN 聚类）。
- **消融实验**：未明确设计消融实验（如不同 backbone、数据量、模型尺寸等）。

## 4. 资源与算力

- **训练硬件**：
  - Apple M2 Pro Mac Mini (32 GB 统一内存) – 使用 MPS 加速。
  - 定制 Windows 工作站：Intel i7-8700K CPU, 32 GB RAM, **NVIDIA RTX 4060 Ti GPU (16 GB VRAM)**。
- **训练时长**：YOLOv11s-pose 训练平均时间比 DeepLabCut 快 **4.5 倍**（即减少 77.9% 的时间），但未报告绝对小时数。
- **推理硬件**：
  - 离线推理：同一 RTX 4060 Ti（对比 DeepLabCut 获得 35 FPS vs 4 FPS）。
  - 实时部署：**NVIDIA Jetson Orin Nano Super**（6 核 ARM CPU, 1024 个 Volta 架构 CUDA 核心, 32 个 Tensor Core, 8 GB LPDDR5, 67 INT8 TOPS）。
- **训练 batch size**：8；**epoch**：150。

## 5. 实验数量与充分性

- **实验数量**：相对有限。
  - 训练/推理对比：仅一个重复测试？未说明多次运行统计。
  - 精度对比：呈现了像素误差分布图，但未给出具体 RMSE 或 P95 数值对比，也未进行统计检验。
  - 实时延迟：在 Jetson 上测试了三种精度的帧延迟，但未说明载荷（同时执行多少个模型？传感器流？）。
  - 行为分析：仅在单个样例数据上展示了功能，未进行跨动物或跨实验室复现。
- **充分性与客观性**：
  - 对比条件较为公平（同一数据集、同一训练参数），但仅选择了 DeepLabCut 的 ResNet-50 变体，未对比更轻量或更现代的 backbone（如 EfficientNet、MobileNet 或 SLEAP 的 UNet 变体）。
  - 缺乏多动物场景、长时间记录、复杂行为范式的验证。
  - 没有进行消融实验（如不同 YOLO 版本、不同训练帧数的影响）。
  - 没有提供实际闭环控制实验（如利用实时检测触发光遗传刺激的延迟测量）。

## 6. 主要结论与发现

- SqueakPose Studio 在**同等精度**下，训练速度比 DeepLabCut 快 4.5 倍，离线推理速度提升 8.5 倍（35 FPS vs 4 FPS）。
- 基于 YOLO 的整帧推理消除了 patch 采样和后处理，显著简化了流程。
- 在 Jetson Orin Nano Super 上，INT8 精度下的帧延迟约 7–10 ms，足以支持实时闭环反馈。
- MouseHouse + SqueakView 提供了集成化的边缘计算平台，无需工作站级 GPU 或外部中间件就能进行同步视频、传感器记录和模型推理。
- 行为分析模块（UMAP + HDBSCAN）能从运动特征中自动识别行为聚类（如边缘探索、静止、中心探索），并可导出到下游工具（CEBRA、Keypoint-MoSeq）。

## 7. 优点与亮点

- **端到端集成**：从数据标注、训练、离线分析到实时部署，所有环节在一个框架内统一，数据格式完全兼容，降低了用户使用多工具拼接的复杂度。
- **高性能**：基于 YOLOv11 的整帧推理，在相同精度下实现数量级的速度提升，且在 CPU、Apple Silicon、CUDA GPU 和嵌入式 GPU 上均可运行。
- **实时边缘部署**：突破传统工具依赖工作站 GPU 的局限，利用 Jetson 系列实现低延迟推理，支持闭环控制（如根据行为触发刺激或奖励）。
- **低成本、模块化**：MouseHouse 使用 3D 打印和商用组件，总成本远低于商业系统，且每个单元独立运行，可批量扩展。
- **开源开放**：代码、CAD 文件、固件均在 GitHub 上公开，便于复现和改进。
- **跨物种兼容**：支持 COCO 人体姿态模型，可零样本迁移到人类姿态追踪。

## 8. 不足与局限

- **实验覆盖有限**：仅在单一旷场任务、单只小鼠上进行了精度和速度验证，缺乏：
  - 多动物交互场景。
  - 不同光照条件（红外/可见光切换）。
  - 不同复杂行为（如精细抓取、社交识别）。
  - 长时间连续记录（数小时）下的稳定性验证。
- **缺乏统计严谨性**：训练/推理时间未报告多次运行的标准差；关键点误差未提供数值摘要及显著性检验；未与其他主流工具（SLEAP、Lightning Pose）进行横向对比。
- **依赖 YOLO 特定版本**：当前基于 Ultralytics YOLOv8/v11，当 YOLO 架构快速迭代时可能需持续适配。未探讨其他单阶段模型的适用性。
- **实时控制验证不足**：虽然声称支持闭环，但没有具体实验案例展示利用实时检测触发硬件（如光遗传刺激）的实际延迟和效果。
- **数据集规模较小**：仅 150 帧标注，虽然符合迁移学习常规，但未探索更大标注量或更少帧量下的性能边界。
- **潜在偏差**：所有实验由同一个实验室在相同设备环境完成，未进行多中心验证；仅 C57BL/6J 小鼠，性别虽包括雄性和雌性但未单独分析。
- **应用限制**：系统依赖于 NVIDIA Jetson 生态（DeepStream、TensorRT），若用户不使用该硬件则无法获取相同的实时性能。Apple Silicon 支持仅用于训练，推理部署需额外适配。

（完）
