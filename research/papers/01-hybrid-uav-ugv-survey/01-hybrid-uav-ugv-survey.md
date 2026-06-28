# 陆空两栖机器人（Hybrid UAV-UGV）技术调研索引

## 领域概览

| 项目 | 内容 |
|------|------|
| **Topic（研究主题）** | 陆空两栖多模态机器人（Hybrid UAV-UGV / Terrestrial-Aerial Multimodal Robots） |
| **Key Challenges（关键挑战）** | 构型设计与运动解耦、模式切换的机构疲劳与耐久性、UAV-UGV分离对接的精确控制、轻量化与载荷能力的平衡、跨模态运动规划与控制 |
| **Key Technologies（关键技术）** | 形态变构机构设计（折展/变形）、轮-腿-桨复合驱动、多模态控制器（切换/混合）、UAV自主起降与对接、协同SLAM与通信 |
| **Popular Platforms/Tools（典型系统）** | FUHAR、Legway、Janus、CapsuleBot、DoubleBee、Roller-Quadrotor、ATOM、LCE+SMP微型机器人 |

**核心价值**：结合地面机器人的稳定性与载荷能力，以及空中系统的视野、速度和灵活性。UGV可作为无人机的移动基站，有效扩展飞行续航；UAV则为UGV提供大范围环境感知支持。

**主流构型分类**：
1. **结构叠加式**：轮式底盘 + 旋翼模块简单堆叠，设计简单但运动耦合强、控制精度低
2. **形态变构式**：机翼/机体变形实现功能复用，但折展机构存在疲劳和耐久性问题
3. **组合分离式**：UAV与UGV可分离独立工作，灵活但对接复杂

---

## 综述类

### 1 Configurations and Applications of Multi-Agent Hybrid Drone/Unmanned Ground Vehicle for Underground Environments: A Review

- **作者/年份**：R. R. S. de J. et al., 2023
- **来源**：MDPI Drones, Vol. 7(2), 136
- **核心贡献**：系统综述UAV-UGV协同系统的分类、架构和应用，涵盖多Agent混合编队、地下环境部署等场景
- **关键词**：UAV-UGV collaboration, multi-agent system, underground environment
- **链接**：DOI: [10.3390/drones7020136](https://www.mdpi.com/2504-446X/7/2/136)（开放获取）

### 2 陆空多模态机器人技术综述

- **作者/年份**：自动化学报, 2026
- **来源**：自动化学报（Acta Automatica Sinica）
- **核心贡献**：提出三分类体系（结构叠加式/形态变构式/组合分离式），系统梳理国内外陆空多模态驱动机理与控制策略
- **关键词**：陆空多模态、构型分类、驱动模式
- **链接**：DOI: [10.16383/j.aas.c250681](https://www.aas.net.cn/cn/article/doi/10.16383/j.aas.c250681)[需手动下载]

### 3 UGV-UAV Integration Advancements for Coordinated Missions: A Review

- **作者/年份**：2025
- **来源**：Springer, Journal of Intelligent & Robotic Systems
- **核心贡献**：UAV-UGV自主协同的系统性分析，提出安全、互操作、智能多Agent系统的路线图
- **关键词**：UAV-UGV integration, autonomous coordination, multi-agent
- **链接**：DOI: [10.1007/s10846-025-02273-w](https://link.springer.com/article/10.1007/s10846-025-02273-w)（开放获取）

### 4 Morphing Quadrotors: Enhancing Versatility and Adaptability in Drone Applications—A Review

- **作者/年份**：2024
- **来源**：MDPI Drones, Vol. 8(12), 762
- **核心贡献**：变形无人机的机构设计分类与控制挑战综述，分析折展/变构型机构的失效模式
- **关键词**：morphing quadrotor, reconfigurable mechanism, control
- **链接**：DOI: [10.3390/drones8120762](https://www.mdpi.com/2504-446X/8/12/762)（开放获取）

### 5 陆空两栖多模态可变形机器人

- **作者/年份**：机器人学报, 2025
- **来源**：《机器人》（Robot）, Vol. 47, No. 3
- **核心贡献**：抵近侦察场景，噪声对比（空中70dB vs 地面52dB），航程比>6
- **关键词**：抵近侦察、形态变构、低噪声
- **链接**：DOI: [10.13973/j.cnki.robot.240334](https://robot.sia.cn/cn/article/doi/10.13973/j.cnki.robot.240334)[需手动下载]

---

## 典型原型（结构叠加式）

### 6 FUHAR: A Transformable Wheel-Leg Hybrid Robot

- **作者/年份**：2020
- **来源**：Robotics and Autonomous Systems (RAS)
- **核心贡献**：轮腿模式切换，运动中越障时身体摆动小，六瓣式轮腿变形机构
- **关键词**：wheel-leg hybrid, transformable mechanism, obstacle crossing
- **链接**：DOI: [10.1016/j.robot.2020.103673](https://www.sciencedirect.com/science/article/pii/S092188902030467X)[需手动下载]

### 7 Legway: Design and Development of a Transformable Wheel-Leg Hybrid Robot

- **作者/年份**：Namgung et al., 2023
- **来源**：IEEE-RAS International Conference on Humanoid Robots (Humanoids)
- **核心贡献**：五杆连杆实现零额外驱动器的轮/腿/驻三模式切换，机构复用设计精巧
- **关键词**：leg mechanism, multi-mode, zero extra actuator, transformable wheel-leg
- **链接**：IEEE: [10.1109/Humanoids57100.2023.10375169](https://ieeexplore.ieee.org/document/10375169)[需手动下载]

### 8 Roller-Quadrotor: A Novel Hybrid Terrestrial/Aerial Quadrotor

- **作者/年份**：Zheng Wang et al., 2023
- **来源**：IEEE/RSJ IROS 2023
- **核心贡献**：首个将四旋翼与独轮车结合的陆空两栖设计，旋翼辅助转向实现地面高效机动
- **关键词**：roller-quadrotor, unicycle-driven, rotor-assisted turning
- **链接**：arXiv: [2303.00668](https://arxiv.org/abs/2303.00668)（开放获取）

### 9 DoubleBee: A Hybrid Aerial-Ground Robot with Two Active Wheels

- **作者/年份**：2023
- **来源**：IEEE/RSJ IROS 2023
- **核心贡献**：双桨+双主动轮混合推进，倾转伺服实现空地模式切换，完整动力学建模和控制
- **关键词**：hybrid aerial-ground, tilting propeller, active wheel
- **链接**：IEEE: [10.1109/IROS55552.2023.10341984](https://ieeexplore.ieee.org/document/10341984)[需手动下载] / arXiv: [2303.05075](https://arxiv.org/abs/2303.05075)（开放获取）

### 10 CapsuleBot: A Novel Compact Hybrid Aerial-Ground Robot

- **作者/年份**：Zheng Cai et al., 2023
- **来源**：IEEE Robotics and Automation Letters (RA-L)
- **核心贡献**：仅用4个电机实现双旋翼飞行和地面滚动的紧凑设计，轮-桨一体化结构，适用于长期隐蔽侦察
- **关键词**：capsule robot, actuated wheel-rotor, covert reconnaissance, compact
- **链接**：arXiv: [2309.09224](https://arxiv.org/abs/2309.09224)（开放获取）

---

## 典型原型（形态变构式）

### 11 FUHAR（已列于#6，见上）

### 12 Janus: A Morphing Quadrotor-Blimp With Balloon Failure Detection and Recovery Capability

- **作者/年份**：2024
- **来源**：IEEE Robotics and Automation Letters (RA-L)
- **核心贡献**：0.36秒内完成飞艇-四旋翼模式切换，整机仅159g，超轻量可变形飞行器
- **关键词**：airship-quadrotor, morphing, lightweight, rapid transition
- **链接**：IEEE: [10.1109/LRA.2024.3398230](https://ieeexplore.ieee.org/document/10511569)[需手动下载]

### 13 Transforming Machines Capable of Continuous 3D Shape Morphing

- **作者/年份**：Sun et al., 2025
- **来源**：Nature Machine Intelligence
- **核心贡献**：25g微型机器人，液晶弹性体+形状记忆聚合物协同致动实现陆空双模态，软体材料驱动
- **关键词**：LCE, SMP, micro robot, soft actuator, dual-modal
- **链接**：DOI: [10.1038/s42256-025-01028-4](https://www.nature.com/articles/s42256-025-01028-4)[需手动下载]

### 14 ATOM: Two-Actuator Hybrid Land-Air Robot

- **作者/年份**：Bhardwaj et al., 2025
- **来源**：The International Journal of Robotics Research (IJRR)
- **核心贡献**：仅用2个致动器实现旋转飞行和地面移动，极简驱动机陆空两栖设计
- **关键词**：two-actuator, minimal actuation, rotary flight, ground locomotion
- **链接**：DOI: [10.1177/02783649251344968](https://journals.sagepub.com/doi/10.1177/02783649251344968)[需手动下载]

---

## 组合分离式与协同系统

### 15 Vision-Based Autonomous Landing for Unmanned Aerial and Ground Vehicles Cooperative Systems

- **作者/年份**：Niu G. et al., 2022
- **来源**：IEEE Robotics and Automation Letters (RA-L), Vol. 7(3), pp. 6234-6241
- **核心贡献**：视觉引导的UAV在UGV移动平台上自主着陆与充电，扩展UAV任务续航
- **关键词**：autonomous landing, battery charging, visual servoing, UAV-UGV cooperation
- **链接**：IEEE: [10.1109/LRA.2021.3101882](https://ieeexplore.ieee.org/document/9507289)[需手动下载]

### 16 Design of Air-Ground Cooperative Landing Platform and Autonomous Landing Strategy

- **作者/年份**：Song et al., 2024
- **来源**：Proceedings of the Institution of Mechanical Engineers, Part I: Journal of Systems and Control Engineering (SAGE)
- **核心贡献**：UGV搭载自调平着陆平台，研究UAV自主着陆策略与对接机构设计
- **关键词**：self-leveling platform, autonomous landing, docking mechanism
- **链接**：DOI: [10.1177/09596518241237568](https://journals.sagepub.com/doi/10.1177/09596518241237568)[需手动下载]

### 17 Optimizing UAV-UGV Coalition Operations: A Hybrid Approach

- **作者/年份**：2024
- **来源**：Ad Hoc Networks, Elsevier
- **核心贡献**：提出改进mean-shift聚类的UAV-UGV编队优化算法（MEANCRFT），变数量车队协同
- **关键词**：UAV-UGV coalition, clustering algorithm, mission planning
- **链接**：DOI: [10.1016/j.adhoc.2024.103566](https://www.sciencedirect.com/science/article/pii/S1570870524001306)[需手动下载]

### 18 A Comprehensive Review of UAV-UGV Collaboration

- **作者/年份**：2024
- **来源**：MDPI, Robotics, Vol. 13(6), 81
- **核心贡献**：综述多UAV-多UGV系统，覆盖空地协同通信、协调机制与任务规划
- **关键词**：UAV-UGV collaboration, multi-agent, communication, coordination
- **链接**：DOI: [10.3390/robotics13060081](https://www.mdpi.com/2224-2708/13/6/81)（开放获取）

---

## 补充论文

### 19 Design, Modeling and Simulation of a Reconfigurable Land-Air Amphibious Robot (RLAR)

- **作者/年份**：2021
- **来源**：IEEE International Conference on Real-time Computing and Robotics (RCAR)
- **核心贡献**：提出可重构陆空两栖机器人（RLAR），兼具空中飞行与地面行驶能力
- **关键词**：reconfigurable, land-air amphibious, design, simulation
- **链接**：IEEE: [10.1109/RCAR52367.2021.9588166](https://ieeexplore.ieee.org/document/9588166)[需手动下载]

### 20 The Development of a Novel Terrestrial/Aerial Robot: Autonomous Quadrotor Tilting Hybrid Robot (AQT-HR)

- **作者/年份**：Zhang et al., 2024
- **来源**：Robotica (Cambridge University Press)
- **核心贡献**：自主四旋翼倾转混合机器人，实现陆空双模态并验证高能效
- **关键词**：quadrotor tilting, dual-modal, energy efficiency, autonomous transition
- **链接**：DOI: [10.1017/S0263574724000335](https://www.cambridge.org/core/journals/robotica/article/development-of-a-novel-terrestrialaerial-robot-autonomous-quadrotor-tilting-hybrid-robot/4F91F682179A5D2E0A0038D3A1580099)[需手动下载]

### 21 A Hybrid Quadrotor With a Passively Reconfigurable Wheeled Leg

- **作者/年份**：Yu et al., 2025
- **来源**：IEEE Robotics and Automation Letters (RA-L)
- **核心贡献**：被动可重构单轮腿实现飞行与两种地面模式（稳定站立/动态巡航）无缝切换
- **关键词**：passive reconfigurable, wheeled leg, quadrotor, terrestrial maneuvers
- **链接**：IEEE: [10.1109/LRA.2025.3536314](https://ieeexplore.ieee.org/document/10892640)[需手动下载]

### 22 A Morphing Land–Air Robot with Adaptive Capabilities for Confined Environments

- **作者/年份**：2026
- **来源**：MDPI Drones, Vol. 10(1), 45
- **核心贡献**：变体轮式陆空机器人（MW-LAR），将地面轮式运动和四旋翼飞行集成于同一平台
- **关键词**：morphing wheel, land-air robot, adaptive capability
- **链接**：DOI: [10.3390/drones10010045](https://www.mdpi.com/2504-446X/10/1/45)（开放获取）

### 23 Metamorphic Aerial Robot Capable of Mid-Air Shape Morphing

- **作者/年份**：2023
- **来源**：Nature Scientific Reports
- **核心贡献**：仿鸟类变形空中机器人，可在空中改变形态以着陆或栖息，生物启发式设计
- **关键词**：metamorphic, bio-inspired, mid-air morphing, perching
- **链接**：DOI: [10.1038/s41598-022-26066-5](https://www.nature.com/articles/s41598-022-26066-5)（开放获取）

---

**说明**：本文档为Hybrid UAV-UGV领域的技术调研索引，涵盖综述类论文5篇、典型原型7篇、组合分离式与协同系统4篇、补充论文5篇（2020-2026年），共21篇文献。链接标注说明：
- **开放获取**：可免费在线阅读和下载
- **[需手动下载]**：需通过机构订阅或个人付费获取
- **arXiv前缀**：为预印本，开放获取
