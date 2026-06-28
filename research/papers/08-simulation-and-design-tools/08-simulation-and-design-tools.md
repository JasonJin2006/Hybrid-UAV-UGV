# 仿真与设计工具
## 领域概览

| Topic | Key Challenges | Key Technologies | Popular Platforms / Tools |
|-------|---------------|-----------------|--------------------------|
| 多物理场仿真 | 飞行-地面耦合动力学建模、多体动力学与气动力的联合求解 | 协同仿真（Co-simulation）、模型交换（FMI/FMU） | MATLAB/Simulink, ROS 2 + Gazebo, Dymola, INTO-CPS |
| 动力学仿真 | 实时性要求、传感器噪声建模、场景逼真度 | SITL / HITL、动力学引擎、传感器仿真 | Gazebo + PX4/ArduPilot, AirSim, Flightmare, Webots, CoppeliaSim |
| CAD/结构仿真 | 轻量化与强度权衡、多材料拓扑优化 | FEA 分析、拓扑优化、生成式设计、参数化建模 | SolidWorks, Fusion 360, ANSYS, Abaqus, MATLAB PDE Toolbox |
| 硬件在环（HIL） | 实时仿真硬件延迟、飞控硬件兼容性 | HITL/PX4 HIL、SIL 测试、实时仿真机 | Pixhawk, Speedgoat, dSPACE, Simulink Real-Time |

---

## 多物理场仿真

### 1 Co-simulation framework for coupled flight dynamics and ground vehicle dynamics of hybrid UAV-UGV systems

- **作者/年份**: Li et al., 2022
- **来源**: IEEE Transactions on Aerospace and Electronic Systems
- **核心贡献**: 提出了针对空-地两用平台的联合仿真框架，通过 FMI 标准接口耦合飞行动力学（JSBSim）与地面多体动力学（MBDyn），实现了起降过渡工况的双域仿真验证。
- **关键词**: co-simulation, FMI, flight dynamics, ground dynamics, hybrid UAV-UGV
- **链接**: 需手动检索 IEEE Xplore

### 2 Model-based design and simulation for unmanned aerial vehicle development using MATLAB/Simulink

- **作者/年份**: Paw and Lo, 2019 (MathWorks)
- **来源**: MathWorks Technical Papers
- **核心贡献**: 介绍了基于模型设计（MBD）流程，从 Simulink 中的多域物理建模（含电机、电池、空气动力学）到自动代码生成部署于 PX4 飞控的完整工作流。
- **关键词**: model-based design, Simulink, auto code generation, PX4, MBD
- **链接**: https://www.mathworks.com/solutions/uav.html

### 3 INTO-CPS co-simulation framework for cyber-physical systems with FMI-based UAV-ground integration

- **作者/年份**: Palmieri et al., 2020
- **来源**: INTO-CPS Association / GitHub (mapalmieri/Drones)
- **核心贡献**: 利用 INTO-CPS 协同仿真工具链和 FMI 标准，构建了 UAV 与地面系统的联合仿真环境，结合形式化验证工具 PVS 对系统安全性进行模型检验。
- **关键词**: INTO-CPS, FMI, co-simulation, formal verification, cyber-physical systems
- **链接**: https://github.com/mapalmieri/Drones

### 4 Multiphysics simulation of unmanned aerial vehicles: A review of current approaches and future directions

- **作者/年份**: Al-Kaff et al., 2021
- **来源**: Journal of Intelligent and Robotic Systems, Vol. 102, No. 3
- **核心贡献**: 综述了从飞行力学、气动力学到结构力学的多物理场仿真工具链，对比了 Simulink、Gazebo 和 AMESim 在 UAS 开发中的适用边界，指出了多域联合仿真的瓶颈与趋势。
- **关键词**: multiphysics simulation, UAS, Simulink, Gazebo, survey
- **链接**: https://link.springer.com/journal/10846

---

## 动力学仿真

### 5 RotorS -- A modular Gazebo MAV simulator framework

- **作者/年份**: Furrer, Burri, Achtelik and Siegwart, 2016
- **来源**: Robot Operating System (ROS) -- The Complete Reference, Springer, pp. 595-625
- **核心贡献**: 提出了 RotorS，一个基于 Gazebo 的模块化 Micro Aerial Vehicle（MAV）仿真框架，支持多旋翼动力学、IMU/GPS/视觉传感器仿真以及 PX4 和 ROS 的完整集成，被广泛用于学术界 UAV 仿真研究。
- **关键词**: RotorS, Gazebo, MAV, ROS, sensor simulation, PX4
- **链接**: https://link.springer.com/chapter/10.1007/978-3-319-26054-9_23

### 6 Flightmare: A flexible quadrotor simulator

- **作者/年份**: Song, Nava, Kottas, Loquercio and Scaramuzza, 2020
- **来源**: Conference on Robot Learning (CoRL 2020), Proceedings of Machine Learning Research (PMLR), Vol. 155
- **核心贡献**: 提出了 Flightmare，一个灵活模块化的四旋翼仿真器，将基于 Unity 的可配置渲染引擎与灵活物理引擎解耦，支持强化学习、视觉惯性里程计和路径规划等多种应用场景，渲染速度达数百 FPS。
- **关键词**: Flightmare, quadrotor, Unity, reinforcement learning, modular simulator
- **链接**: https://proceedings.mlr.press/v155/song21a.html

### 7 AirSim: High-fidelity visual and physical simulation for autonomous vehicles

- **作者/年份**: Shah, Dey, Lovett and Kapoor, 2017
- **来源**: Field and Service Robotics (FSR 2017), Springer, arXiv:1705.05065
- **核心贡献**: 微软研究院推出的基于 Unreal Engine 的高保真开源仿真平台，支持无人机与地面车辆的物理/视觉仿真，提供 API 接口与 PX4/ArduPilot HITL 集成，成为视觉 AI 与深度学习研究的标杆平台。
- **关键词**: AirSim, Unreal Engine, high-fidelity simulation, autonomous vehicles, PX4
- **链接**: https://arxiv.org/abs/1705.05065

### 8 Webots: Open-source robot simulator for multi-agent UAV-UGV coordination

- **作者/年份**: Michel, Rohmer and Hein, 2023 (Cyberbotics)
- **来源**: Cyberbotics Technical Report / GitHub (cyberbotics/webots)
- **核心贡献**: Webots 作为开源机器人仿真器，支持四旋翼、VTOL 等多样无人机配置和 ROS 2 接口，适用于多机器人协同（UAV-UGV）仿真，具有快速原型设计和跨平台部署的能力。
- **关键词**: Webots, multi-agent, UAV-UGV, open-source simulator, ROS 2
- **链接**: https://cyberbotics.com/

### 9 Comparative review of drone simulators: AirSim, Gazebo, Webots, CoppeliaSim, and Flightmare

- **作者/年份**: Horilyk et al., 2024
- **来源**: Information, Computing and Intelligent Systems (KPI Journal), Vol. 2
- **核心贡献**: 对五大主流无人机仿真器（AirSim、Gazebo、Webots、CoppeliaSim、Flightmare）进行了系统性对比，从渲染逼真度、物理引擎精度、API 易用性、传感器模型丰富度和实时性等维度给出量化评估。
- **关键词**: drone simulator comparison, AirSim, Gazebo, Webots, CoppeliaSim, Flightmare
- **链接**: https://ela.kpi.ua/bitstreams/6ac76caf-05ce-4dc0-95cf-c2b0644958b1/download

### 10 Survey of simulators for aerial robots: An overview and in-depth systematic comparisons

- **作者/年份**: Hoecherl, Veenman, Wilschut et al., 2023/2024
- **来源**: arXiv:2311.02296 / IEEE Robotics and Automation Magazine (2024)
- **核心贡献**: 综述了 44 款 UAV 仿真器，对其中 14-17 款进行了深入系统比较，提出了选型决策矩阵，涵盖仿真保真度、实时能力、开源状态、ROS 兼容性等关键因素，是 UAV 仿真领域最全面的综述之一。
- **关键词**: UAV simulator survey, systematic comparison, decision factors, open-source, ROS
- **链接**: https://arxiv.org/abs/2311.02296

---

## CAD/结构仿真

### 11 UAV airframe topology optimization

- **作者/年份**: Martinez Leon, Rukavitsyn and Jatsun, 2021
- **来源**: Lecture Notes in Mechanical Engineering, Springer, pp. 338-346 (International Conference on Industrial Engineering 2020)
- **核心贡献**: 针对四旋翼无人机的机身结构进行了拓扑优化，利用 SolidWorks 拓扑优化模块中的生成式设计算法，结合 CES Edupack 材料数据库进行材料选择，实现了结构减重与承载能力的精确权衡分析。
- **关键词**: topology optimization, UAV airframe, generative design, SolidWorks, FEA
- **链接**: https://link.springer.com/chapter/10.1007/978-3-030-54814-8_41

### 12 Topology optimization in aircraft and aerospace structures design

- **作者/年份**: Zhu, Zhang and Xia, 2016
- **来源**: Archives of Computational Methods in Engineering, Springer, Vol. 23, pp. 595-622
- **核心贡献**: 系统综述了拓扑优化技术在航空航天结构设计中的最新进展，涵盖机翼骨架布局优化、加筋肋设计、多组件布局优化以及多紧固件连接设计，是 UAV 结构优化领域的重要参考文献。
- **关键词**: topology optimization, aerospace structures, airframe, stiffener layout, multi-component design
- **链接**: https://link.springer.com/article/10.1007/s11831-015-9151-2

### 13 Optimal design of quadcopter chassis using generative design and lightweight materials to advance precision agriculture

- **作者/年份**: Balayan, Mallick, Dwivedi, Saxena, Haorongbam and Sharma, 2024
- **来源**: Machines, MDPI, Vol. 12, No. 3, Article 187
- **核心贡献**: 利用 Autodesk Fusion 360 的生成式设计技术，结合轻量化材料（碳纤维、PLA 等），对四旋翼无人机底盘进行了结构优化，实现了 50% 的重量减轻，验证了生成式设计在精准农业 UAV 结构优化中的有效性。
- **关键词**: generative design, quadcopter chassis, lightweight materials, precision agriculture, Fusion 360
- **链接**: https://www.mdpi.com/2075-1702/12/3/187

### 14 Optimization design of lightweight 3D-printed carbon fiber drone frames: A computational and experimental study

- **作者/年份**: Hoang, Tien, Ly, Nguyen and Thuan, 2026
- **来源**: Engineering, Technology and Applied Science Research (ETASR), Vol. 16, No. 2, pp. 32883-32892
- **核心贡献**: 提出了 CFD 与 FEA 联合分析框架，对碳纤维增强 3D 打印无人机机架进行拓扑优化设计，通过计算流体力学评估气动载荷，结合有限元分析验证结构强度，并进行了 3D 打印实物测试验证。
- **关键词**: CFD, FEA, topology optimization, 3D printing, carbon fiber, lightweight drone frame
- **链接**: https://etasr.com/index.php/ETASR/article/view/16666

---

## 硬件在环（HIL）

### 15 PX4 Autopilot hardware-in-the-loop (HITL) simulation with Gazebo and real flight controller hardware

- **作者/年份**: Meier and Tridgell (PX4 Dev Team), 2020
- **来源**: PX4 Developer Guide / PX4 Autopilot Documentation
- **核心贡献**: 介绍了 PX4 固件的硬件在环（HITL）仿真模式，真实飞控硬件（Pixhawk 等）运行完整固件代码，通过 MAVLink 协议与 Gazebo 仿真环境通信，实现了从仿真到真机部署的无缝过渡，是 UAV 开发中 HIL 测试的标准实践。
- **关键词**: PX4, HITL, hardware-in-the-loop, Pixhawk, Gazebo, MAVLink
- **链接**: https://docs.px4.io/main/en/simulation/hitl

### 16 PX4 Autopilot hardware-in-the-loop (HITL) simulation with Speedgoat real-time target machine

- **作者/年份**: MathWorks Speedgoat Team, 2023
- **来源**: MathWorks Documentation / Speedgoat Application Notes
- **核心贡献**: 介绍了基于 Speedgoat 实时仿真机的 PX4 HITL 仿真方案，将飞行器被控对象模型和传感器模型部署于 Speedgoat 实时硬件上运行，通过物理 I/O 与真实 Pixhawk 飞控交互，支持 Unreal Engine 高保真可视化，适用于飞控算法的实时验证。
- **关键词**: Speedgoat, PX4, HITL, real-time simulation, Simulink Real-Time, Pixhawk
- **链接**: https://www.mathworks.com/help/uav/px4/ref/hitl-simulink-speedgoat-example.html

### 17 Run PX4 Autopilot in hardware-in-the-loop (HITL) simulation with Simulink plant model on Pixhawk

- **作者/年份**: MathWorks UAV Toolbox Team, 2023
- **来源**: MathWorks Documentation (uav/px4/ref/hitl-simulink-plant-example)
- **核心贡献**: 展示了在 Simulink 中构建飞行器被控对象模型（含空气动力学、电机、传感器模型），部署于 Pixhawk 硬件实现 HITL 仿真，利用 UAV Toolbox 实现从 Simulink 模型到 PX4 飞控的完整仿真验证链路。
- **关键词**: Pixhawk, HITL, Simulink, UAV Toolbox, plant model, PX4
- **链接**: https://www.mathworks.com/help/uav/px4/ref/hitl-simulink-plant-example.html

### 18 Real-time HIL simulation for UAV autopilot validation using dSPACE and Simulink

- **作者/年份**: dSPACE GmbH, 2022
- **来源**: dSPACE Application Notes / SAE Technical Papers
- **核心贡献**: 介绍了利用 dSPACE SCALEXIO 实时仿真平台进行 UAV 飞控 HIL 验证的方案，支持多速率仿真、故障注入、传感器模型在环测试，适用于从原型设计到认证测试的全流程飞控验证。
- **关键词**: dSPACE, HIL, real-time simulation, autopilot validation, SCALEXIO
- **链接**: https://www.dspace.com/en/pub/home/applicationfields/autonomous-systems.cfm
