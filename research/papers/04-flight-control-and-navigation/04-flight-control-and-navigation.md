# 飞控与导航方向 — 调研索引

## 方向概览

| 项目 | 内容 |
|------|------|
| **Topic** | 陆空两栖机器人（Hybrid UAV-UGV）的飞行控制与自主导航技术 |
| **Key Challenges** | 变形飞行器的重心/惯量突变导致控制失稳；空地模态切换过渡控制；GPS拒止环境下的精确定位；多传感器融合的实时性与鲁棒性 |
| **Key Technologies** | 自适应/增量式控制（INDI、自适应PID）；GPS/INS松耦合/紧耦合；视觉惯性里程计（VIO）；光流定位；卡尔曼滤波（EKF/UKF/CKF） |
| **Popular Platforms/Tools** | ArduPilot、PX4、ROS、MAVLink、VINS-Mono、VINS-Fusion、ORB-SLAM3 |

---

## 一、多模态飞控综述

### 1 变形无人机自适应控制（变形后重心/惯量变化导致传统PID失效）

- **作者/年份:** Zhao J. 等, 2025
- **来源:** Drones (MDPI), Vol. 9, No. 9, 663
- **核心贡献:** 综述了当前变形四旋翼平台的机构设计、驱动方式和自适应控制框架，识别了变形导致重心/惯量变化后传统PID控制器的失效模式，并比较了各自适应方案的收敛速度和鲁棒性。
- **关键词:** morphing quadrotor; adaptive control; centroid variation; flight control
- **链接:** https://www.mdpi.com/2504-446X/9/9/663

### 2 鲁棒约束跟随控制用于变形四旋翼UAV

- **作者/年份:** Liu F. 等, 2024
- **来源:** Journal of the Franklin Institute, Vol. 361, 106703
- **核心贡献:** 提出分段建模法获取变形条件下的四旋翼模型，设计自适应鲁棒约束跟随控制器以处理系统不确定性，显著提升了变形过程中的飞行稳定性。
- **关键词:** morphing quadrotor; segmented modeling; adaptive robust control; uncertainty
- **链接:** https://www.sciencedirect.com/science/article/pii/S0016003224000991

### 3 A Hybrid Quadrotor With a Passively Reconfigurable Wheeled Leg Capable of Robust Terrestrial Maneuvers

- **作者/年份:** Yu S., Pu B., Dong K., Bai S., Chirarattananon P., 2025
- **来源:** IEEE Robotics and Automation Letters, Vol. 10, No. 4, pp. 3486-3493
- **核心贡献:** 提出一种带有被动可重构单轮腿的陆空两栖四旋翼，实现了飞行与两种地面模式（稳定站姿、动态巡航）之间的平滑过渡。巡航模式离心加速度达 0.55g，展示了鲁棒的陆面机动能力。
- **关键词:** hybrid aerial-ground robot; reconfigurable leg; quadrotor; terrestrial maneuver
- **链接:** https://doi.org/10.1109/LRA.2025.3544078 [需手动下载]

### 4 ATOM: Design and Development of a Novel Two-Actuator Hybrid Land-Air Robot

- **作者/年份:** Bhardwaj R., Win S. K., 2025
- **来源:** The International Journal of Robotics Research (SAGE)
- **核心贡献:** 提出一种仅使用两个执行器的新型空地两栖机器人，支持旋转飞行与地面运动两种模式切换，探索了极简驱动下的多模态控制策略。
- **关键词:** hybrid robot; dual-mode locomotion; two-actuator; aerial-ground
- **链接:** https://journals.sagepub.com/doi/10.1177/02783649251344968 [需手动下载]

---

## 二、姿态估计与控制

### 5 A Comparative Study for Control of Quadrotor UAVs

- **作者/年份:** Rinaldi M., Primatesta S., Guglieri G., 2023
- **来源:** Applied Sciences (MDPI), Vol. 13, No. 6, 3464
- **核心贡献:** 对四旋翼UAV多种控制方法进行了广泛的定量对比，包括PID、LQR、滑模控制、反步法等，在多种扰动条件下评估了各控制器的跟踪性能和鲁棒性。
- **关键词:** quadrotor; comparative control; PID; LQR; sliding mode; backstepping
- **链接:** https://www.mdpi.com/2076-3417/13/6/3464

### 6 Active Disturbance Rejection Control of a Quadrotor: A Comparative Study

- **作者/年份:** Ahsan M. A., Khan H. Z. I., Rajput J., Riaz J., 2022
- **来源:** 2022 19th International Bhurban Conference on Applied Sciences and Technology (IBCAST), pp. 545-553
- **核心贡献:** 对比了PID、线性ADRC和非线性ADRC在四旋翼上的性能，基于鲁棒性、抗扰能力和计算开销进行全面评估，验证了ADRC在强扰动下的优势。
- **关键词:** ADRC; PID; quadrotor; disturbance rejection; comparison
- **链接:** https://ieeexplore.ieee.org/document/9990161 [需手动下载]

### 7 Comparative Analysis of Attitude Control of Quadrotor UAVs: PID, ADRC, and NMPC Algorithms

- **作者/年份:** Zhang T., Ng J. Y., Tai V. C., 2024
- **来源:** 2024 9th International Conference on Electronic Technology and Information Science (ICETIS)
- **核心贡献:** 针对四旋翼UAV姿态控制，对比PID、ADRC和NMPC三种控制器的跟踪精度与抗扰能力。实验表明PID在简易工况下表现良好但大干扰下振荡明显，NMPC虽计算量大但响应最优。
- **关键词:** attitude control; PID; ADRC; LQR; quadrotor UAV
- **链接:** https://ieeexplore.ieee.org/abstract/document/10593686 [需手动下载]

### 8 Incremental Nonlinear Dynamic Inversion Control for Quadrotor UAV With an Angular Accelerometer

- **作者/年份:** Zhang Q., Fu M., Zhai C., Wang S., Ning K., Wang M., 2023
- **来源:** 2023 42nd Chinese Control Conference (CCC), pp. 1-6
- **核心贡献:** 将增量式非线性动态逆（INDI）方法应用于四旋翼UAV控制，通过引入角加速度计直接测量角加速度而非微分获取，避免了对全模型精确建模的需求，实现了对模型不确定性和外部扰动的强鲁棒性。
- **关键词:** INDI; incremental control; quadrotor; disturbance rejection; nonlinear control
- **链接:** https://ieeexplore.ieee.org/document/10240476 [需手动下载]

### 9 PID Control of Quadrotor UAVs: A Survey

- **作者/年份:** López-Sánchez I., Moreno-Valenzuela J., 2023
- **来源:** Annual Reviews in Control, Elsevier, Vol. 56, 100912
- **核心贡献:** 系统综述了四旋翼UAV中PID控制结构的各种变体，涵盖线性、非线性、不连续、分数阶、智能和自适应PID方案，为四旋翼控制器选型提供了全面的参考框架。
- **关键词:** PID control; quadrotor; survey; adaptive; fractional-order
- **链接:** https://www.sciencedirect.com/science/article/pii/S1367578823000640

---

## 三、GPS/INS组合导航

### 10 A GNSS/INS Integrated Navigation Algorithm Based on Kalman Filter

- **作者/年份:** Wang G., Han Y., Chen J., Wang S., Zhang Z., Du N., Zheng Y., 2018
- **来源:** IFAC-PapersOnLine, Vol. 51, Issue 17, pp. 232-237
- **核心贡献:** 在多传感器信息融合的GNSS/INS组合导航系统中，提出集中式卡尔曼滤波方法在松耦合条件下融合GPS和INS数据，验证了位置和速度估计精度的提升。
- **关键词:** GNSS/INS; Kalman filter; loose coupling; sensor fusion
- **链接:** https://www.sciencedirect.com/science/article/pii/S2405896318312692

### 11 Distributionally Robust Kalman Filtering for INS/GPS Tightly Coupled Integration With Model Uncertainty and Measurement Outlier

- **作者/年份:** Si K., Li P., Yuan Z., Qiao K., Wang B., He X., 2023
- **来源:** IEEE Transactions on Instrumentation and Measurement, Vol. 72, pp. 1-13
- **核心贡献:** 提出一种分布式鲁棒卡尔曼滤波方法用于INS/GPS紧耦合系统，有效处理了不确定性条件下的离群值和模型误差，显著提升了复杂环境下的定位精度与鲁棒性。
- **关键词:** robust Kalman filter; INS/GPS; tightly coupled; uncertainty; outliers
- **链接:** https://ieeexplore.ieee.org/document/10177214 [需手动下载]

### 12 Comparative Analysis of Kalman Filtering Methods in Tightly-Coupled GNSS/INS for UAVs

- **作者/年份:** Wang Y., Jin Z., Sui S., Hao Y., Huang H., Ji S., Zheng S., 2025
- **来源:** International Conference on Signal Processing, Communication and Control Systems (SPCCS 2025) / SPIE Proceedings, Vol. 13705
- **核心贡献:** 全面对比了在紧耦合GNSS-INS集成导航中三种卡尔曼滤波方法（EKF、UKF、CKF）的性能，评估了非线性滤波在无人机机动环境下的收敛速度与精度。
- **关键词:** EKF; UKF; CKF; GNSS/INS; tightly coupled; UAV navigation
- **链接:** https://www.spiedigitallibrary.org/conference-proceedings-of-spie/13705/137051X/Comparative-analysis-of-Kalman-filtering-methods-in-tightly-coupled-GNSS/10.1117/12.3070672.full [需手动下载]

### 13 Analysis of a Robust Kalman Filter in Loosely Coupled GPS/INS Navigation System

- **作者/年份:** Zhao L., Qiu H., Feng Y., 2016
- **来源:** Measurement, Elsevier, Vol. 80, pp. 138-147
- **核心贡献:** 基于最优控制与滤波的对偶性，分析了鲁棒卡尔曼滤波器在松耦合GPS/INS集成中的应用，在GPS信号异常时通过鲁棒化处理抑制发散，保持了定位精度。
- **关键词:** robust Kalman filter; GPS/INS; loose coupling; outlier rejection
- **链接:** https://www.sciencedirect.com/science/article/pii/S0263224115005941

---

## 四、视觉导航与光流定位

### 14 UAV Navigation With Monocular Visual Inertial Odometry Under GNSS-Denied Environment

- **作者/年份:** Luo Y., Li Y., 2023
- **来源:** IEEE Transactions on Geoscience and Remote Sensing, Vol. 61, Article 5623519
- **核心贡献:** 在GNSS拒止环境中，提出基于单目视觉惯性里程计（VIO）的无人机导航方案，通过IMU与视觉特征的紧耦合融合，实现了无GPS环境下的稳定定位和航迹跟踪。
- **关键词:** VIO; GNSS-denied; monocular; UAV navigation; sensor fusion
- **链接:** https://ieeexplore.ieee.org/document/10275007 [需手动下载]

### 15 Event-Based Visual/Inertial Odometry for UAV Indoor Navigation

- **作者/年份:** Elamin A., El-Rabbany A., Jacob S., 2025
- **来源:** Sensors (MDPI), Vol. 25, No. 1, 61
- **核心贡献:** 提出基于事件相机的视觉惯性里程计方法，采用自适应事件累积和选择性关键帧更新降低计算开销，在室内弱纹理和高速运动场景中展示了对传统帧式相机的优势。
- **关键词:** event camera; visual-inertial odometry; indoor navigation; UAV
- **链接:** https://www.mdpi.com/1424-8220/25/1/61

### 16 VINS-Mono: A Robust and Versatile Monocular Visual-Inertial State Estimator

- **作者/年份:** Qin T., Li P., Shen S., 2018
- **来源:** IEEE Transactions on Robotics, Vol. 34, No. 4, pp. 1004-1020
- **核心贡献:** 提出VINS-Mono，一个鲁棒的单目视觉惯性状态估计器，支持滑动窗口优化与闭环检测，成为无人机视觉导航的基准开源系统。后继VINS-Fusion支持多传感器融合扩展。
- **关键词:** VINS-Mono; visual-inertial; state estimation; SLAM; loop closure
- **链接:** https://github.com/HKUST-Aerial-Robotics/VINS-Mono (开源代码) / DOI: 10.1109/TRO.2018.2853729 [需手动下载]

### 17 A UAV Positioning Strategy Based on Optical Flow Sensor and Inertial Navigation

- **作者/年份:** Qi J., Nikitin Yu. N., Lu X., 2017
- **来源:** 2017 IEEE International Conference on Unmanned Systems (ICUS), pp. 81-87
- **核心贡献:** 研究了基于光流传感器与惯性导航信息融合的小型无人机定位技术，通过光流修正IMU漂移，实现了无GPS环境下的速度估计和定点悬停。
- **关键词:** optical flow; INS; UAV localization; sensor fusion; GPS-denied
- **链接:** https://ieeexplore.ieee.org/document/8278322 [需手动下载]

### 18 Improving Optical Flow Sensor Using a Gimbal for Quadrotor Navigation in GPS-Denied Environment

- **作者/年份:** Flores J., Gonzalez-Hernandez I., Salazar S., Lozano R., Reyes C., 2024
- **来源:** Sensors (MDPI), Vol. 24, No. 7, 2183
- **核心贡献:** 提出使用云台改进光流传感器，解决光流传感器在四旋翼倾斜状态下精度下降的问题。云台保持光流传感器水平，使无人机在无GPS环境中获得更稳定的速度和位置估计。
- **关键词:** optical flow; gimbal stabilization; quadrotor; GPS-denied
- **链接:** https://www.mdpi.com/1424-8220/24/7/2183

---

## 五、开源飞控平台架构参考

### 19 PX4 Autopilot Flight Control Architecture

- **作者/年份:** PX4开发团队, 持续更新
- **来源:** 开源项目文档
- **核心贡献:** PX4采用模块化架构，支持多旋翼、固定翼、VTOL等多种机型。其飞行栈包含位置/姿态控制器层级（外环P/内环PID）、EKF2传感器融合引擎，以及灵活的混控器输出机制，是学术界和工业界广泛使用的飞控参考平台。
- **关键词:** PX4; flight stack; EKF2; multicopter control; open source
- **链接:** https://docs.px4.io/main/en/flight_stack/controller_diagrams

### 20 Efficient Development of Model-Based Controllers in PX4 Firmware: A Template-Based Customization Approach

- **作者/年份:** D'Angelo S., Pagano F., Longobardi F., Ruggiero F., Lippiello V., 2024
- **来源:** 2024 International Conference on Unmanned Aircraft Systems (ICUAS), pp. 1-8
- **核心贡献:** 提出一种基于模板的定制方法，帮助开发者在PX4固件中高效集成自定义控制算法，降低了PX4二次开发的门槛，适用于快速原型验证。
- **关键词:** PX4; model-based control; template customization; embedded control
- **链接:** https://www.researchgate.net/publication/380604433_Efficient_Development_of_Model-Based_Controllers_in_PX4_Firmware_A_Template-Based_Customization_Approach [需手动下载]

---

> **说明:** 标有 `[需手动下载]` 的条目受付费墙限制，建议通过机构订阅或Sci-Hub获取全文。
