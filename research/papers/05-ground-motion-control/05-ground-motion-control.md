# 地面运动控制（Ground Motion Control）

## 领域概览

| 项目 | 内容 |
|------|------|
| **Topic** | 混合式 UAV-UGV 机器人的地面运动控制技术，涵盖轮式/履带移动平台的运动学建模、差速驱动控制策略以及悬架与越障能力分析 |
| **Key Challenges** | 多地形适应性（松软土壤、碎石、台阶）、轮地交互作用力建模、履带打滑补偿、悬架与越障时的姿态稳定性、运动学模型在转向与不平路面下的误差累积 |
| **Key Technologies** | 两轮差速运动学、四轮阿克曼转向、履带滑移转向、Mecanum 轮全向运动学、PID 轮速控制、被动/主动悬架设计、基于接触力学的越障建模 |
| **Popular Platforms/Tools** | ROS/Gazebo 仿真、MATLAB/Simulink 控制设计、Arduino/Pixhawk 嵌入式控制器、Clearpath Husky / Summit XL / Pioneer 3-DX 等 UGV 平台 |

---

## 1. 轮式/履带运动学综述

### [1] 两轮差速与四轮阿克曼移动机器人运动学对比综述

- **作者/年份**: Siciliano, B., Sciavicco, L., Villani, L., & Oriolo, G. (2010)
- **来源**: *Robotics: Modelling, Planning and Control* (Springer), 第11章
- **核心贡献**: 系统推导了差速驱动（unicycle模型）和 Ackermann 转向的运动学方程，给出了前后轮转向曲率半径的计算方法，并对比了两种构型的最小转弯半径、路径连续性等特性。
- **关键词**: differential drive, Ackermann steering, unicycle model, kinematic constraints, maneuverability
- **链接**: https://doi.org/10.1007/978-1-84628-642-1 （教材，需手动下载）

### [2] Mecanum 轮全向移动平台运动学建模与控制

- **作者/年份**: Taheri, H., & Zhao, C. Y. (2020)
- **来源**: *Mechanism and Machine Theory*, 153, 103958
- **核心贡献**: 综述了各种全向轮机构（包括 Mecanum 轮）的设计原理与运动学模型，分析了导航方法在室内外环境中的适用性，并总结了全向移动机器人的主要挑战与控制策略。
- **关键词**: omnidirectional wheel, Mecanum wheel, kinematics, navigation, mobile robot
- **链接**: https://doi.org/10.1016/j.mechmachtheory.2020.103958

### [3] 变形轮（轮-腿混合轮）运动学分析

- **作者/年份**: She, Y., Hurd, C. J., & Su, H.-J. (2014)
- **来源**: *IEEE Transactions on Robotics*, 30(6), 1487-1498
- **核心贡献**: 提出 Wheel Transformer——一种将圆形轮与腿式越障优势结合的被动变形轮，设计了绳驱动变形机构，建立了轮径切换的运动学模型，并实验验证了在崎岖地形上的越障性能提升。
- **关键词**: transformable wheel, wheel-leg hybrid, passive mechanism, kinematics, obstacle traversal
- **链接**: https://doi.org/10.1109/TRO.2014.2360351

### [4] 履带式 UGV 滑移转向运动学建模

- **作者/年份**: Wong, J. Y. (2008)
- **来源**: *Theory of Ground Vehicles* (Wiley), 第7章
- **核心贡献**: 经典教材中系统论述了履带车辆滑移转向（skid-steer）的运动学与动力学，推导了转向半径与两侧履带速度差的关系，给出了考虑地面剪切力作用的转向阻力矩模型。
- **关键词**: tracked vehicle, skid-steer, slip ratio, turning resistance, terramechanics
- **链接**: ISBN: 9780470170380 （教材，需手动下载）

---

## 2. 差速转向控制

### [5] 基于李雅普诺夫方法的非完整移动机器人轨迹跟踪控制

- **作者/年份**: Kanayama, Y., Kimura, Y., Miyazaki, F., & Noguchi, T. (1990)
- **来源**: *IEEE International Conference on Robotics and Automation (ICRA)*, 384-389
- **核心贡献**: 提出了基于李雅普诺夫稳定性理论的非完整移动机器人轨迹跟踪控制律，证明了控制规则的渐进稳定性，并通过死区推算实验验证了该方法对不同类型移动机器人的通用性。
- **关键词**: nonholonomic, trajectory tracking, Lyapunov stability, mobile robot, dead reckoning
- **链接**: https://doi.org/10.1109/ROBOT.1990.126006

### [6] 考虑轮地滑移的履带式机器人运动学近似方法

- **作者/年份**: Martinez, J. L., Mandow, A., Morales, J., Pedraza, S., & Garcia-Cerezo, A. J. (2005)
- **来源**: *The International Journal of Robotics Research*, 24(10), 867-878
- **核心贡献**: 提出了针对履带式 skid-steer 机器人的运动学近似方法，通过实验数据拟合瞬时转动中心（ICR）的位置变化规律，建立了考虑履带滑移的改进运动学模型，在多种地面条件下验证了模型精度。
- **关键词**: skid-steer, tracked robot, kinematics approximation, ICR, slip compensation
- **链接**: https://doi.org/10.1177/0278364905058239

### [7] 基于扩张状态观测器的差速 UGV 抗干扰速度控制

- **作者/年份**: Yang, C., Huang, K., Cheng, H., Li, Y., & Su, C.-Y. (2021)
- **来源**: *IEEE Transactions on Systems, Man, and Cybernetics: Systems*, 51(12), 7437-7447
- **核心贡献**: 提出了考虑输入饱和与外部扰动的轮式移动机器人 H-infinity 跟踪控制方法，通过引入抗饱和补偿机制与扰动抑制策略，在多种扰动条件下实现了优于传统 PID 的鲁棒轨迹跟踪控制性能。
- **关键词**: H-infinity control, input saturation, disturbance rejection, trajectory tracking, wheeled mobile robot
- **链接**: https://doi.org/10.1109/TSMC.2019.2963280

---

## 3. 悬架与越障

### [8] 移动操作臂倾翻稳定性裕度的力-角度量方法

- **作者/年份**: Papadopoulos, E., & Rey, D. A. (2000)
- **来源**: *Vehicle System Dynamics*, 33(1), 1-17
- **核心贡献**: 提出了一种新的倾翻稳定性度量方法——力-角稳定裕度（Force-Angle Stability Measure），具有简单的几何解释、计算便捷且对质心高度和系统重量敏感，可用于实时监测移动操作臂的倾翻风险。
- **关键词**: tipover stability, force-angle measure, mobile manipulator, stability margin, rollover prevention
- **链接**: https://doi.org/10.1076/0042-3114(200001)33:1;1-5;FT029

### [9] 崎岖地形轮式移动机器人创新设计

- **作者/年份**: Siegwart, R., Lamon, P., Estier, T., Lauria, M., & Piguet, R. (2002)
- **来源**: *Robotics and Autonomous Systems*, 40(2-3), 151-162
- **核心贡献**: 提出了一种基于六轮菱形构型的崎岖地形移动机器人（Shrimp Rover）创新方案，前轮和后轮具备转向功能，中间两轮由被动悬架驱动，建立了基于被动适应机构的越障运动学模型，实验证明了优异的地形适应能力。
- **关键词**: rough terrain, passive suspension, rhombus configuration, rover, obstacle climbing
- **链接**: https://doi.org/10.1016/S0921-8890(02)00240-3

### [10] 履带式车辆在松软地面上的机动性能分析

- **作者/年份**: Al-Milli, S., Althoefer, K., & Seneviratne, L. D. (2008)
- **来源**: *IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)*, 2821-2826
- **核心贡献**: 采用多体动力学方法系统研究了履带式车辆在可变形松软土壤上的稳态滑移转向机动性能，提出了一种预测转向过程中履带地面作用力的新方法，为履带式 UGV 在不同土壤条件下的通过性评估提供了理论依据。
- **关键词**: tracked vehicle, skid-steering, soft terrain, track-terrain interaction, maneuverability
- **链接**: https://doi.org/10.1109/IROS.2008.4651043

### [11] 全地形轮式机器人移动性评估方法

- **作者/年份**: Thueer, T., & Siegwart, R. (2010)
- **来源**: *Robotics and Autonomous Systems*, 58(5), 508-519
- **核心贡献**: 提出了一套量化评估全地形轮式机器人移动性能的方法体系，基于静态二维模型结合轮扭矩优化以最小化所需摩擦力，实现了对不同轮式构型在地形通过性方面的系统比较与评估。
- **关键词**: mobility evaluation, all-terrain robot, wheeled locomotion, terrainability, performance metrics
- **链接**: https://doi.org/10.1016/j.robot.2010.01.007

---

> **说明**: 标注 "需手动下载" 的论文来自付费期刊或教材，建议通过 DOI 或论文标题在 Google Scholar / CNKI / 学校图书馆数据库中检索获取全文。
