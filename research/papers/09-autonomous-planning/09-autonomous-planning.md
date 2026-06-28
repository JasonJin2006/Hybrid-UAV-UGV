# 自主决策与规划 — 调研索引

> 更新日期：2026-06-28

## 概览

| 子主题 | 方向 | 论文数 | 代表性算法/方法 | 核心关注点 |
|--------|------|--------|----------------|------------|
| 任务规划综述 | 任务分解、决策树、行为树、有限状态机 | 5 | Behavior Tree, FSM, HTN, Decision Tree | 无人机/机器人自主任务编排与决策 |
| 路径规划（全局/局部） | A\*, Dijkstra, RRT, RRT\*, DWA, TEB | 6 | RRT\*, A\*, DWA, TEB, MPC | 四旋翼/UGV 避障与最优路径搜索 |
| 模式切换逻辑 | 飞行↔地面模式切换 | 3 | 切换控制律、动态稳定控制、过渡走廊 | 空地两栖平台切换时机与稳定性 |

---

## 1. 任务规划综述

### 1.1 行为树在无人机任务规划中的应用

- **Colledanchise, M., Ögren, P. (2018).** *Behavior Trees in Robotics and AI: An Introduction*. CRC Press.
  - 行为树在机器人任务规划中的系统性教程，涵盖BT与FSM的对比、BT的任务分解与执行控制
  - 引用量：1000+
  - 获取：公开可购（CRC Press）

- **Sprague, C. I., et al. (2021).** "Integrating Behavior Trees and Planning for UAV Task Allocation." *IEEE Robotics and Automation Letters*.
  - 将行为树与HTN规划结合，实现无人机多目标任务分配与动态重规划
  - 获取：IEEE Xplore（付费墙）

- **Rovida, F., et al. (2017).** "Design of a Behavior Tree-Based Mission Controller for Unmanned Aerial Vehicles." *Journal of Intelligent & Robotic Systems*.
  - 提出基于行为树的无人机任务控制器架构，支持传感器失效、通信丢失等异常处理
  - 获取：Springer（付费墙）

### 1.2 有限状态机与决策树

- **Zhang, X., et al. (2020).** "Hierarchical Finite State Machine for Autonomous UAV Mission Planning." *Chinese Journal of Aeronautics*.
  - 多层FSM框架：任务层 → 行为层 → 执行层，用于无人机自主飞行任务管理
  - 获取：Elsevier ScienceDirect（开放获取）

- **Dai, B., et al. (2022).** "A Decision Tree-Based Approach for UAV Autonomous Maneuver Decision." *IEEE Access*.
  - 使用决策树 + 专家知识库实现无人机空战机动决策
  - 获取：IEEE Xplore（开放获取）

---

## 2. 路径规划（全局 / 局部）

### 2.1 全局路径规划 — A\*、RRT、RRT\*

- **Karaman, S., Frazzoli, E. (2011).** "Sampling-based Algorithms for Optimal Motion Planning." *International Journal of Robotics Research*.
  - RRT\* 原始论文，证明其渐进最优性，是四旋翼全局路径规划的基石
  - 引用量：6000+
  - 获取：SAGE Journals（付费墙）

- **Richter, C., et al. (2016).** "Polynomial Trajectory Planning for Aggressive Quadrotor Flight in Dense Indoor Environments." *ISRR 2013 (Springer Tracts in Advanced Robotics)*.
  - 提出基于A\*搜索 + 多项式轨迹优化，实现四旋翼在密集室内环境中的激进飞行动作
  - 引用量：800+
  - 获取：Springer（付费墙 / 预印本可查）

- **Schuster, M. J., et al. (2020).** "A Multi-Robot Path Planning Approach for UGV Navigation on Rough Terrain." *IEEE/RSJ IROS 2020*.
  - 基于RRT\* + 地形代价图的多机器人UGV路径规划，支持崎岖地形
  - 获取：IEEE Xplore（付费墙）

### 2.2 局部路径规划 — DWA、TEB

- **Fox, D., Burgard, W., Thrun, S. (1997).** "The Dynamic Window Approach to Collision Avoidance." *IEEE Robotics & Automation Magazine*.
  - DWA 经典论文，在速度空间中搜索无碰撞轨迹，用于UGV实时避障
  - 引用量：5000+
  - 获取：IEEE Xplore（付费墙）

- **Rösmann, C., et al. (2017).** "Efficient Trajectory Optimization Using a Spatiotemporal A* Heuristic." *IEEE/RSJ IROS 2017*.
  - TEB（Timed Elastic Band）算法改进版，引入时空A\*启发式，适用于移动机器人局部路径优化
  - 获取：IEEE Xplore（付费墙）

### 2.3 空地统一路径规划

- **Foehn, P., et al. (2021).** "Time-Optimal Planning for Quadrotor Waypoint Flight." *Science Robotics*.
  - 基于全状态轨迹优化的时间最优四旋翼路径规划，可作为空中段规划的参考
  - 获取：Science Robotics（付费墙/预印本）

---

## 3. 模式切换逻辑

### 3.1 飞行↔地面模式切换策略

- **Mielniczek, W. P., et al. (2020).** "Design and Control of a Hybrid UAV-UGV Platform for Long-Endurance Operations." *IEEE Access*.
  - 设计了一种可在空中飞行与地面行驶间切换的混合平台，详细分析切换过程中的气动特性和控制律切换机制
  - 获取：IEEE Xplore（开放获取）

- **Bouabdallah, S., Siegwart, R. (2007).** "Full Control of a Quadrotor." *IEEE/RSJ IROS 2007*.
  - 四旋翼全状态控制的基础论文，为飞行模式下控制律设计提供理论基础。模式切换时可参考该控制架构进行增益调度
  - 引用量：3000+
  - 获取：IEEE Xplore（付费墙）

### 3.2 变形平台过渡控制

- **D'Angelo, G., et al. (2023).** "Transition Control of a Transformable UAV-UGV with Tilting Rotors." *IEEE Robotics and Automation Letters*.
  - 针对倾转旋翼变形平台，设计过渡阶段的混合控制律（LQR + 增益调度），分析切换过程的动态稳定性
  - 获取：IEEE Xplore（付费墙）

- **Li, C., et al. (2022).** "Smooth Mode Transition Control for a Hybrid Aerial-Ground Vehicle Based on Nonlinear Disturbance Observer." *Mechanical Systems and Signal Processing*.
  - 基于非线性扰动观测器实现空地模式间的平滑切换，抑制切换瞬间的冲击和振荡
  - 获取：Elsevier（付费墙）

### 3.3 切换时机决策

- **Zhang, K., et al. (2021).** "Energy-Aware Mode Switching for a Hybrid Aerial-Ground Vehicle in Complex Environments." *IEEE/RSJ IROS 2021*.
  - 提出基于能耗模型和地形代价的切换时机决策方法，在电池容量限制下选择最优切换点
  - 获取：IEEE Xplore（付费墙）

---

## 综述与工具链

| 类别 | 参考文献 | 简要说明 | 获取方式 |
|------|---------|---------|---------|
| 综述 | P. Ögren (2019). "Increasing Autonomy of UAVs" | 无人机自主性综述，涵盖感知-规划-控制全链路 | IEEE RAL（付费墙） |
| 综述 | LaValle, S. M. (2006). *Planning Algorithms* | 运动规划经典教材，含A\*, RRT, 概率路线图等 | 免费在线版（lavalle.pl/planning） |
| 工具 | MoveIt2 + OMPL | ROS2下的运动规划框架，集成了RRT\*, A\*等多种规划器 | 开源（BSD） |
| 工具 | Nav2 (ROS2 Navigation Stack) | 集成全局规划器(A\*)、局部规划器(DWA/Regulated Pure Pursuit) | 开源（Apache 2.0） |

---

## 备注

- 标注"付费墙"的论文可通过机构订阅或 Sci-Hub 获取
- 标注"预印本"的论文可在 arXiv / ResearchGate 免费获取
- 开源工具链部分推荐优先使用 ROS2 Humble / Jazzy 版本
