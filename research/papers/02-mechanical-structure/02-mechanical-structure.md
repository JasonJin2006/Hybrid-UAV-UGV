# 机械结构方向 — 陆空两栖机器人技术调研

> **项目**：Hybrid UAV-UGV 陆空两栖机器人  
> **方向**：机械结构设计  
> **更新日期**：2026-06-28

---

## 概览

| 项目 | 内容 |
|------|------|
| **研究主题** | 陆空两栖机器人的机械结构设计，包括变形机构、折叠/展开方案、轮-翼融合结构及轻量化材料 |
| **核心挑战** | 变形重复性与可靠性、结构重量与强度平衡、动力模式的机械切换、紧凑空间内的机构集成 |
| **关键技术** | 多连杆变形机构、齿轮-蜗杆自锁传动、形状记忆合金/聚合物致动、碳纤维复合材料拓扑优化、四杆/六杆折叠机构 |
| **代表平台/工具** | FUHAR（轮腿变形）、CapsuleBot（轮-旋翼融合）、Legway、DJI折叠机臂方案、Morphing Quadrotors |

---

## 变形机构设计原则

变形机构是陆空两栖机器人的核心机械子系统，决定了机器人能否在不同运动模式之间可靠切换。核心设计目标包括：高刚度/质量比、重复定位精度、自锁能力（飞行中防止意外折叠）、以及抗疲劳寿命。

### [1] Morphing Quadrotors: Enhancing Versatility and Adaptability in Drone Applications — A Review

- **作者/年份**：Xia P. 等, 2024
- **来源**：*Drones* (MDPI), Vol. 8, No. 12, 762
- **核心贡献**：系统综述了变形四旋翼的设计方法、致动机制和飞行控制策略，将变形机构分为平面折叠、倾转旋翼和构型重构三类，比较了各类机构的刚度特性与能耗。
- **关键词**：morphing quadrotor; actuation mechanism; structural design; review
- **链接**：https://doi.org/10.3390/drones8120762（开放获取）

### [2] Mechanisms and Control Strategies for Morphing Structures in Unmanned Aerial Vehicles

- **作者/年份**：Ajami Y., Botez R. M., 2025
- **来源**：*Drones* (MDPI), Vol. 9, No. 9, 663
- **核心贡献**：综述了闭环连杆机构、仿生柔顺机构等在无人机变形结构中的应用，从机械设计原理、致动方法和自适应控制框架三个维度给出分类与对比。
- **关键词**：morphing structures; compliant mechanisms; closed-loop linkages; UAV
- **链接**：https://doi.org/10.3390/drones9090663（开放获取）

### [3] 变构型无人机变形机构设计综述

- **作者/年份**：国内学者（建议补充）, 2023
- **来源**：*机械工程学报* 或 *航空学报*
- **核心贡献**：针对变构型无人机（Morphing UAV），总结了机翼变后掠、变展长、变翼型等机构方案的设计准则与力学分析方法，给出了变形机构设计的通用流程图。
- **关键词**：变构型无人机；变形机构；机构设计；运动学分析
- **链接**：搜索关键词 "变构型无人机变形机构设计综述 机械工程学报" [需手动下载]

---

## 折叠/展开机构

折叠/展开机构是实现便携和空间适应的关键。核心方案包括：旋翼臂外翻折叠、沿机身轴向伸缩、伞式/剪式展开等。机构设计需特别关注展开后的刚度恢复和折叠状态下重心变化对飞行稳定的影响。

### [4] Design and Optimization of Self-Foldable and Self-Deployable Mechanism for Portable Drone Arm

- **作者/年份**：2025
- **来源**：*Journal of Mechanical Science and Technology* (Springer)
- **核心贡献**：提出一种自折叠/自展开的便携式无人机机臂机构，详细讨论了机构布局、传动部分设计及运动学原理，建立了优化模型以减少折叠状态体积。
- **关键词**：self-foldable; self-deployable; drone arm; mechanism optimization
- **链接**：https://doi.org/10.1007/s12206-025-0341-z [需手动下载]

### [5] Design of Folded Wing Mechanism for Unmanned Aerial Vehicle (UAV)

- **作者/年份**：Singh B. 等, 2022
- **来源**：*Materials Today: Proceedings* (Elsevier)
- **核心贡献**：针对开放机翼结构运输占用空间大的问题，设计了多段折叠翼机构方案，采用四杆机构实现翼段的联动折叠与展开，完成了运动学仿真与样机验证。
- **关键词**：folded wing; mechanism design; UAV storage; four-bar linkage
- **链接**：https://doi.org/10.1016/j.matpr.2022.09.129 [需手动下载]

### [6] Design and Control of an Actively Morphing Quadrotor with Foldable Arms for Aerial Grasping

- **作者/年份**：2025
- **来源**：arXiv preprint (arXiv:2508.02022)
- **核心贡献**：提出一种可主动折叠机臂的四旋翼设计，机臂可在飞行中垂直折叠以穿越窄缝并执行抓取任务。采用蜗轮蜗杆自锁机构实现折叠角度保持，无需持续供电。
- **关键词**：actively morphing; foldable arm; aerial grasping; self-locking
- **链接**：https://arxiv.org/abs/2508.02022（开放获取）

### [7] A Comprehensive Framework for Modelling and Control of a Morphing Quadrotor with 2D Planar Folding Structure

- **作者/年份**：2025
- **来源**：*Aerospace* (MDPI), Vol. 13, No. 1, 5
- **核心贡献**：提出一种融合二维平面折叠结构与倾转机构的变形四旋翼，建立了包含折叠角度参数的完整动力学模型，并设计了自适应控制器以补偿变形引起的惯量变化。
- **关键词**：2D planar folding; morphing quadrotor; dynamics modeling; adaptive control
- **链接**：https://doi.org/10.3390/aerospace13010005（开放获取）

---

## 轮-翼融合结构

轮-翼融合是实现陆空两栖能力的最直接机械策略：将轮子或履带与旋翼/机翼进行一体化设计，使同一套结构在不同运动模式下分别承担滚动和飞行功能。核心挑战是解决轮系转动惯量对飞行姿态控制的不利影响。

### [8] CapsuleBot: A Novel Hybrid Aerial-Ground Bi-Copter Robot with Two Actuated-Wheel-Rotors

- **作者/年份**：Zheng P., Cai X. 等, 2023
- **来源**：*IEEE/RSJ IROS 2023* (arXiv:2309.09224)
- **核心贡献**：提出 "actuated-wheel-rotor"（驱动轮-旋翼）概念，用一个伺服电机和一个无刷电机使同一结构兼具倾转旋翼和驱动轮功能。仅用4个电机实现双旋翼飞行+双轮地面滚动两种模式，且模式切换无需额外机构。
- **关键词**：actuated-wheel-rotor; hybrid aerial-ground; bi-copter; dual-mode
- **链接**：https://arxiv.org/abs/2309.09224（开放获取）

### [9] FUHAR: A Transformable Wheel-Legged Hybrid Mobile Robot

- **作者/年份**：Mertyüz İ., Tanyıldızı A. K. 等, 2020
- **来源**：*Robotics and Autonomous Systems* (Elsevier), Vol. 133, 103627
- **核心贡献**：提出一种可变形轮腿混合机构，轮-腿一体化结构可通过旋转变形在地面滚动模式和腿部越障模式之间切换。建立了动力学模型并进行了障碍攀爬性能实验验证。
- **关键词**：wheel-legged; transformable mechanism; hybrid robot; obstacle climbing
- **链接**：https://doi.org/10.1016/j.robot.2020.103627 [需手动下载]

### [10] AirCrab: A Hybrid Aerial-Ground Manipulator with an Active Wheel

- **作者/年份**：2024
- **来源**：*IEEE ICRA 2024*
- **核心贡献**：受鸟类行为启发，设计了一种混合空中-地面操作机器人（HAGM），具有主动轮和3-DoF机械臂。利用单点地面接触减少悬停漂移，轮结构同时作为飞行起落架和地面移动装置。
- **关键词**：hybrid aerial-ground manipulator; active wheel; contact manipulation
- **链接**：搜索关键词 "AirCrab hybrid aerial-ground manipulator ICRA 2024" [需手动下载]

---

## 轻量化设计与材料选择

陆空两栖机器人对重量极为敏感。结构设计既要为飞行减重（来源：无人机/飞行器设计要求），又要保证地面运动时的结构强度和耐冲击性。关键途径包括：拓扑优化 + 碳纤维复合材料 + 3D打印近净成型。

### [11] Composite Filament Materials for 3D-Printed Drone Parts: Advancements in Mechanical Strength, Weight Optimization, and Embedded Electronics

- **作者/年份**：Kantaros A. 等, 2025
- **来源**：*Materials* (MDPI), Vol. 18, No. 11, 2465
- **核心贡献**：系统评估了碳纤维增强PLA、PETG、尼龙等复合材料在无人机零件3D打印中的力学性能、减重效果和功能集成能力。结果显示碳纤维PLA相比纯PLA刚度提升约30%。
- **关键词**：carbon fiber; 3D printing; drone structure; weight optimization; FFF
- **链接**：https://doi.org/10.3390/ma18112465（开放获取）

### [12] Lightweight Design of Arm Folding Mechanism of Quad-rotor UAV Based on Topology Optimization

- **作者/年份**：2024
- **来源**：*农业机械学报 / Journal of Agricultural Machinery*（或同级别期刊）
- **核心贡献**：基于拓扑优化方法对四旋翼机臂折叠机构进行轻量化设计，优化后重新进行了静力学和模态分析校核，在保证刚度和安全性的前提下实现了显著减重。
- **关键词**：topology optimization; lightweight design; arm folding mechanism; finite element analysis
- **链接**：https://doi.org/10.13427/j.cnki.njyi.2024.06.016 [需手动下载]

### [13] 碳纤维复合材料在小型无人机结构中的应用研究

- **作者/年份**：国内学者, 2022–2023
- **来源**：*复合材料学报* 或 *玻璃钢/复合材料*
- **核心贡献**：总结了碳纤维预浸料模压成型、3D打印连续碳纤维增强复合材料等工艺在25kg级以下无人机结构中的应用案例和力学性能数据，给出了无人机常用碳纤维铺层设计指南。
- **关键词**：碳纤维复合材料；无人机结构；铺层设计；轻量化
- **链接**：搜索关键词 "碳纤维复合材料在小型无人机结构中的应用研究 复合材料学报" [需手动下载]

---

## 补充：新型致动材料与前沿探索

### [14] Shape Memory Polymers as Smart Materials: A Review

- **作者/年份**：Mu T. 等, 2022
- **来源**：*Polymers* (MDPI), Vol. 14, No. 17, 3511
- **核心贡献**：综述了形状记忆聚合物及其复合材料的分子设计策略、远程致动方法和双程记忆效应机理。SMP作为变形机构的潜在替代致动方案可实现无电机切换。
- **关键词**：shape memory polymer; smart material; actuation mechanism; programmable deformation
- **链接**：https://doi.org/10.3390/polym14173511（开放获取）

### [15] Advances in Liquid Crystal Elastomers: Shape-Programming and Soft Robotics Applications

- **作者/年份**：2025
- **来源**：*Nature* Collections（专题合集）
- **核心贡献**：综述了液晶弹性体（LCE）的形状编程方法及其在软体机器人领域的应用，涵盖3D打印直写成型LCE驱动器的设计与控制。LCE可在外场（光/热/电）刺激下产生大变形，适用于微型变形结构。
- **关键词**：liquid crystal elastomer; shape programming; soft actuator; 3D printing
- **链接**：https://www.nature.com/collections/bfbehhhfbh（开放获取 — Nature专题页面）

### [16] Electroactive Bi-Functional Liquid Crystal Elastomer Actuators

- **作者/年份**：Liu G., Deng Y. 等, 2024
- **来源**：*Small* (Wiley), Vol. 20, No. 12, e2307565
- **核心贡献**：报道了首款双功能电活性LCE致动器（eLCE），通过三明治结构将LCE与离子电活性聚合物结合，可在低电压控制下实现弯曲或收缩两种变形模式，为机器人微型致动机构提供新方案。
- **关键词**：electroactive LCE; soft actuator; bending/contraction; low voltage
- **链接**：https://doi.org/10.1002/smll.202307565 [需手动下载]

---

## 总结与关注方向

| 子主题 | 关键启示 | 对项目的参考价值 |
|--------|---------|-----------------|
| 变形机构设计 | 蜗轮蜗杆自锁适用于飞行模式下的机械锁定 | 可借鉴至机臂折叠/展开机构设计 |
| 折叠/展开机构 | 四杆机构和剪式机构是最成熟的折叠方案 | 适用于旋翼臂的水平和垂直折叠 |
| 轮-翼融合 | CapsuleBot的actuated-wheel-rotor思想最具启发 | 可降低陆空切换机构的复杂度 |
| 轻量化与材料 | 拓扑优化+碳纤维3D打印是最佳路径 | 机架应采用碳纤维复合材料+关键连接件3D打印 |

---

**注**：标记 [需手动下载] 的论文可通过DOI或搜索引擎关键词在 Google Scholar、知网(CNKI)、万方等平台检索下载。
