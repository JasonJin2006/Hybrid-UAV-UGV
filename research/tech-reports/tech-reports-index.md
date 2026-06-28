# 开源项目与技术报告 — 索引

> 更新日期：2026-06-28

## 概览

| 类别 | 项目/报告 | 数量 | 核心技术 | 与本项目关系 |
|------|----------|------|---------|-------------|
| 飞控系统 | ArduPilot, PX4, Betaflight, ROSflight | 4 | 姿态估计、控制律、EKF融合 | 飞控核心参考 |
| 机器人框架 | ROS / ROS2 | 1 | 通信、SLAM、导航、规划 | 软件架构基础 |
| 通信协议 | MAVSDK, MAVLink | 2 | 无人机地面站通信、SDK | 控制链路参考 |
| 相关话题项目 | hybrid-uav, transformable-drone, uav-ugv-collaboration | 14+ | 变形机构、协同控制 | 直接竞品/参考 |
| 技术博客/报告 | 协同控制、DIY四旋翼、四旋翼建模仿真 | 6+ | 实操经验、理论教程 | 学习与复现参考 |

---

## 一、飞控系统（开源）

### 1.1 ArduPilot

| 项目 | 链接 | 说明 | 状态 |
|------|------|------|------|
| ArduPilot | https://ardupilot.org | 最成熟的开源自动驾驶仪，支持多旋翼、固定翼、车、船、潜艇。C++编写。支持传统直升机和VTOL | 活跃维护 |
| GitHub 仓库 | https://github.com/ArduPilot/ardupilot | 主仓库，~11k stars，~33k forks | 活跃 |
| 模式支持 | 支持 Plane / Copter / Rover / Sub / Blimp | 地面模式(Rover)与空中模式(Copter)均原生支持 | 可直接参考其Rover控制与Copter控制的模式切换逻辑 |
| 地面控制站 | Mission Planner / MAVProxy | 开源GCS，支持MAVLink标准通信 | 可用作混合平台的调试工具 |

> 关注点：ArduPilot的Rover模式与Copter模式分别适配了UGV和UAV，但其不支持在同一固件实例中混合两种模式。如需在单个飞行控制器上实现空地切换，需自行修改或构固件逻辑。

### 1.2 PX4 Autopilot

| 项目 | 链接 | 说明 | 状态 |
|------|------|------|------|
| PX4 Autopilot | https://px4.io | 专业级开源飞控，支持多旋翼、固定翼、VTOL、UGV。BSD 3-Clause许可 | 活跃维护 |
| GitHub 仓库 | https://github.com/PX4/PX4-Autopilot | 主仓库，~8k stars，~14k forks | 活跃 |
| VTOL模式 | 支持标准VTOL（倾转旋翼/尾座式）的飞行模式切换 | 其VTOL模式切换逻辑（transition logic）可直接参考用于空地模式切换 | 提供transition timeout、airspeed-based switching等机制 |
| UGV模式 | 实验性Rover支持（fw_rover） | 地面行驶控制，差速/阿克曼转向 | 较ArduPilot的Rover支持薄弱 |
| 仿真 | Gazebo SITL / jMAVSim | 完整的SITL仿真环境，支持多机仿真 | 可用于混合平台控制算法验证 |

> 关注点：PX4的VTOL transitions是学习飞行模式切换的最佳参考。可以基于VTOL的navigator模块的自动模式切换逻辑设计空地切换架构。

### 1.3 其他飞控

| 项目 | 链接 | 说明 | 状态 |
|------|------|------|------|
| Betaflight | https://github.com/betaflight/betaflight | 竞速/穿越机飞控，性能优化极佳 | 活跃维护，不支持UGV，可参考其PID调优 |
| ROSflight | https://github.com/ARK-Electronics/ROSflight | 专为ROS设计的轻量级飞控固件，支持多旋翼 | 活跃维护，适合与研究级ROS集成 |
| dRehmFlight | https://github.com/nickrehm/dRehmFlight | 适用于Arduino的轻量级VTOL飞控，适合快速原型 | 个人项目，适合DIY原型验证 |

---

## 二、机器人框架

### 2.1 ROS / ROS2

| 项目 | 链接 | 说明 |
|------|------|------|
| ROS2 Humble | https://docs.ros.org/en/humble/ | LTS版本，推荐用于混合机器人系统（支持截至2027年5月） |
| ROS2 Jazzy | https://docs.ros.org/en/jazzy/ | 2024年LTS版本（支持截至2029年），功能更完整 |
| Nav2 | https://navigation.ros.org/ | ROS2导航栈，内置A*, DWA, Regulated Pure Pursuit等全局+局部规划器 |
| MoveIt2 | https://moveit.picknik.ai/ | 运动规划框架，集成OMPL（含RRT*, PRM等） |
| micro-ROS | https://micro.ros.org/ | 将ROS2引入微控制器，适合混合平台中低成本MCU节点 |

> 关注点：Nav2是混合平台地面导航的核心依赖，micro-ROS可部署在飞控协处理器上做控制层集成。

---

## 三、通信协议与SDK

| 项目 | 链接 | 说明 | 状态 |
|------|------|------|------|
| MAVLink | https://mavlink.io | 无人机行业标准通信协议（v1/v2），支持UDP/TCP/串口 | 活跃维护 |
| MAVSDK | https://mavsdk.mavlink.io | PX4/ArduPilot官方SDK，支持C++/Python/Swift/Java | 活跃维护 |
| FastRTPS / DDS | https://www.eprosima.com/ | PX4 ROS2接口底层通信（ROS2 Middleware） | PX4 v1.13+默认 |
| uXRCE-DDS (micro-ROS Agent) | https://micro.ros.org/docs/overview/transport/ | micro-ROS到ROS2的桥接 | 适合MCU场景 |

> 关注点：推荐使用MAVSDK作为飞控与上层规划器之间的通信通道。ROS2 DDS作为混合平台内部模块间通信主干。

---

## 四、GitHub 相关话题项目

按 GitHub topic 搜索整理，以下为与混合/变形无人机、UAV-UGV协同相关的开源项目。

### 4.1 topic: hybrid-uav

| 项目 | 链接 | 说明 | Stars (约) | 语言 |
|------|------|------|-----------|------|
| HybridUAV_ROS | https://github.com/topics/hybrid-uav | 混合无人机ROS相关项目合集（话题页，内容为空，暂无仓库使用此标签） | 话题页 | 多种 |
| tilting-rotor | https://github.com/topics/tilting-rotor | 倾转旋翼相关开源项目（话题页，内容为空，暂无仓库使用此标签） | 话题页 | 多种 |
| mavros | https://github.com/mavlink/mavros | ROS1 MAVLink 扩展包，无人机与ROS的桥梁 | ~1k | C++ |

### 4.2 topic: transformable-drone

| 项目 | 链接 | 说明 | Stars (约) | 语言 |
|------|------|------|-----------|------|
| transformable-quadrotor | https://github.com/topics/transformable-drone | 变形四旋翼合集（话题页，内容为空，暂无仓库使用此标签） | 话题页 | 多种 |
| Morphing-Drone | https://github.com/asvin24/Morphing-Drone | 变形机构的机械设计与控制论文配套代码。描述：坦克-无人机变形尝试 | ~0 | C++/Python |

### 4.3 topic: uav-ugv-collaboration

| 项目 | 链接 | 说明 | Stars (约) | 语言 |
|------|------|------|-----------|------|
| mrs_uav_system | https://github.com/ctu-mrs/mrs_uav_system | 捷克理工大学MRS组的多机UAV系统（含UAV-UGV协同功能） | ~1.5k | C++/Python |
| multi_uav_ugv | https://github.com/topics/uav-ugv-collaboration | 相关项目话题合集（话题页，内容为空，暂无仓库使用此标签） | 话题页 | 多种 |
| ROSflight + ROS | --- | 协同控制的常见实现组合 | N/A | C++ |

### 4.4 具体推荐开源仓库

| 仓库名称 | 链接 | 说明 | 推荐理由 |
|---------|------|------|---------|
| PX4-Autopilot | https://github.com/PX4/PX4-Autopilot | 专业飞控 | VTOL transition机制可以直接参考 |
| ArduPilot/ardupilot | https://github.com/ArduPilot/ardupilot | 全平台飞控 | 同时具备Copter和Rover的支持 |
| mavros | https://github.com/mavlink/mavros | ROS-MAVLink桥接 | 飞控-ROS集成的标准方案 |
| nav2 | https://github.com/ros-navigation/nav2 | ROS2导航栈 | 地面部分导航的完整方案 |
| cartographer | https://github.com/cartographer-project/cartographer | 实时SLAM（Google开源） | 地面/空中同时建图的参考 |
| Fast-Drone-250 | https://github.com/ZJU-FAST-Lab/Fast-Drone-250 | 浙江大学FAST Lab快速四旋翼开源项目 | 可学习其轨迹规划与状态估计架构 |

---

## 五、技术博客与报告

### 5.1 UAV/UGV 协同控制

| 标题 | 来源 | 链接 | 说明 | 类型 |
|------|------|------|------|------|
| UAV-UGV Collaboration: A Survey | arXiv 综述 | https://arxiv.org/abs/2306.15801（参考搜索） | 全面的UAV-UGV协同综述论文，覆盖编队、感知、任务分配。注：原链接2101.05962内容与该主题无关，已替换为搜索建议 | 学术综述 |
| Multi-Robot Systems: A Survey of UAV-UGV Collaboration | MDPI Drones | https://www.mdpi.com/journal/drones (搜索UAV-UGV survey) | 多机器人协同综述（免费获取） | 学术综述 |
| Planning and Control for UAV-UGV Collaborative Systems | IEEE RAL (2022) | IEEE Xplore（搜索标题） | 空地协同规划与控制框架 | 学术论文（付费墙） |

### 5.2 变形无人机DIY与教程

| 标题 | 来源 | 链接 | 说明 | 类型 |
|------|------|------|------|------|
| How does a Quadcopter Work? | DroneBot Workshop | https://dronebotworkshop.com/how-does-a-quadcopter-work/ | 从零搭建四旋翼的电子、机械、飞控配置教程 | 教程（免费） |
| Drones & Quadcopters Index | DroneBot Workshop | https://dronebotworkshop.com/drone-index/ | 四旋翼/无人机相关教程汇总索引页 | 教程（免费） |
| Building a Transformable Drone | Hackaday.io | https://hackaday.io/ (搜索transformable drone) | 多个变形无人机DIY项目 | DIY项目 |
| How to Build an FPV Quadcopter | Oscar Liang | https://oscarliang.com/ | 飞行器搭建、PID调优、飞控配置的完整教程 | 教程（免费） |
| Betaflight Tuning Guide | Betaflight Docs | https://betaflight.com/docs/development/Tuning | 飞控PID调整和滤波配置 | 文档（免费） |

### 5.3 四旋翼建模仿真

| 标题 | 来源 | 链接 | 说明 | 类型 |
|------|------|------|------|------|
| Quadrotor Dynamics and Control | R. Beard / BYU | https://www.mathworks.com/matlabcentral/fileexchange/ (搜索Quadrotor Simulation) | 四旋翼动力学建模与PID控制仿真（MATLAB/Simulink） | 学术代码 |
| Crazyflie Simulation | Bitcraze | https://github.com/whoenig/crazyflie_ros2 | Crazyflie微型四旋翼ROS2仿真与真实飞行 | 仿真项目 |
| PX4 Gazebo SITL | PX4 Docs | https://docs.px4.io/main/en/simulation/gazebo.html | 官方SITL仿真环境设置教程 | 教程（免费） |
| ArduPilot SITL | ArduPilot Dev Guide | https://ardupilot.org/dev/docs/sitl-simulator-software-in-the-loop.html | 软件在环仿真环境 | 教程（免费） |

### 5.4 混合平台设计与控制

| 标题 | 作者/来源 | 链接 | 说明 | 获取方式 |
|------|----------|------|------|---------|
| Design and Control of a Hybrid UAV-UGV Platform | IEEE Access, 2020 | 见论文索引 | 混合平台设计与控制完整方案 | 开放获取（IEEE） |
| Transition Control of a Transformable UAV-UGV | IEEE RAL, 2023 | 见论文索引 | 变形过渡阶段控制律设计 | 付费墙 |
| PARGS项目网站 | Skoltech | https://www.skoltech.ru/en/ | 近年最完整的可分离式空地平台项目（注：公开资料有限） | 免费 |
| Nonlinear Control for Aerial-Ground Vehicles | arXiv | https://arxiv.org/search (搜索aerial-ground vehicle control) | 多种非线性控制方法在空地平台中的比较 | arXiv |


---

## 六、推荐的技术栈组合

| 层级 | 推荐方案 | 备选方案 |
|------|---------|---------|
| 飞控固件 | PX4 Autopilot（VTOL切换逻辑可参考） | ArduPilot（Rover+Copter双支持） |
| 机载计算（飞控层） | Pixhawk 6X (PX4) + micro-ROS | Cube Orange+ (ArduPilot) |
| 机载计算（任务层） | Raspberry Pi 5 / NVIDIA Jetson Orin | Intel NUC / Khadas VIM4 |
| 操作系统 | Ubuntu 22.04 + ROS2 Humble | Ubuntu 24.04 + ROS2 Jazzy |
| 通信中间件 | DDS（Fast-DDS / Cyclone DDS） | MAVSDK + MAVLink |
| 地面导航 | Nav2（ROS2导航栈） | 自定义A* + DWA |
| 空中导航 | PX4 EKF2 + 外部VIO | ArduPilot EKF + 外部里程计 |
| SLAM | Cartographer / RTAB-Map | ORB-SLAM3 / VINS-Fusion |
| 仿真 | PX4-Gazebo SITL + ROS2 | ArduPilot SITL + Gazebo |
| 变形机构控制 | micro-ROS + 舵机驱动节点 | 独立STM32控制器 + 串口通信 |

> 说明：以上技术栈经过社区验证，适合混合UAV-UGV平台的原型开发。推荐以PX4 + ROS2为主线方案，其VTOL transition逻辑对空地模式切换有直接借鉴意义。

---

## 七、备注

- 所有链接均为公开可访问（除标注"付费墙"外）
- GitHub topic 搜索页链接仅用作发现相关项目的起点，topic页本身不包含仓库内容
- 标注"需搜索"的链接需在对应平台手动搜索标题获取原文
- 学术论文访问权限因机构订阅而异，建议通过学校/机构图书馆获取全文
- 本索引将持续更新，欢迎通过Issue提交补充或修正
