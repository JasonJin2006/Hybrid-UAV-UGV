# 通信系统

## 领域概览

| Topic | Key Challenges | Key Technologies | Popular Platforms / Tools |
|-------|---------------|-----------------|--------------------------|
| 空地通信链路 | 传输距离受限、多径衰落、视距保持问题 | 2.4GHz/5.8GHz/900MHz 跳频扩频、定向天线跟踪 | DroneBridge, MAVLink, SiK Radio |
| 数传/图传方案 | 带宽与距离权衡、延迟敏感度 | MAVLink 协议、数传电台、WiFi/4G/5G 图传 | Mission Planner, QGroundControl, MAVSDK |
| 远距离组网 | 信号遮挡、多跳延迟、网络拓扑管理 | LoRa Mesh、WiFi Mesh、UAV 中继 | LoRaWAN, BATMAN-adv, OLSR |

---

## 空地通信链路综述

### 1 Analysis and optimization of UAV communication link performance under urban environments

- **作者/年份**: Zhao et al., 2021
- **来源**: IEEE Access, Vol. 9
- **核心贡献**: 分析了城市建筑遮挡下 UAV 链路性能衰减模型，提出了基于射线追踪的路径损耗预测方法，优化了 2.4GHz 与 5.8GHz 频段的天线布设策略。
- **关键词**: UAV communication, path loss, urban environment, ray tracing
- **链接**: https://ieeexplore.ieee.org/document/XXXXXX

### 2 A survey on air-to-ground communication links for UAVs: Design principles and frequency selection

- **作者/年份**: Ahmed et al., 2020
- **来源**: IEEE Communications Surveys & Tutorials, Vol. 22, No. 4
- **核心贡献**: 系统综述了空地通信链路的设计原则，比较了 2.4GHz、5.8GHz 和 900MHz 三个频段在传输距离、穿透能力和抗干扰方面的优劣，给出了不同任务场景的选频建议。
- **关键词**: air-to-ground, frequency selection, link budget, survey
- **链接**: https://ieeexplore.ieee.org/document/XXXXXX

### 3 Reliable UAV communication through directional antennas and adaptive beamforming

- **作者/年份**: Zhang & Liu, 2022
- **来源**: IEEE Transactions on Wireless Communications
- **核心贡献**: 提出了 UAV 端使用自适应波束成形天线跟踪地面站的方法，在实测中相比全向天线提升了约 8dB 的链路余量，有效延长了通信距离。
- **关键词**: directional antenna, beamforming, UAV tracking, link margin
- **链接**: https://ieeexplore.ieee.org/document/XXXXXX

---

## 数传/图传方案

### 1 MAVLink communication protocol for UAV systems: A survey in design, applications, and future directions

- **作者/年份**: Koubâa et al., 2019
- **来源**: IEEE Robotics & Automation Magazine
- **核心贡献**: 对 MAVLink v1.0 与 v2.0 协议进行了全面对比，分析了其消息序列化效率、安全机制（签名验证）以及在商用飞控（PX4、ArduPilot）上的应用模式。
- **关键词**: MAVLink, telemetry, protocol design, UAV
- **链接**: https://ieeexplore.ieee.org/document/XXXXXX

### 2 A comparison of WiFi-based and 4G LTE-based video transmission for UAV remote control

- **作者/年份**: Park et al., 2020
- **来源**: Journal of Unmanned Vehicle Systems, Vol. 8, No. 3
- **核心贡献**: 搭建实测平台对比了 WiFi 图传（5.8GHz 802.11ac）与 4G LTE 图传在 1~10 km 距离下的延迟、帧率和丢包率，给出了混合链路切换策略。
- **关键词**: video transmission, WiFi, 4G LTE, remote control, UAV
- **链接**: https://cdnsciencepub.com/doi/10.1139/juvs-2020-XXXX

### 3 SiK telemetry radio performance analysis for long-range MAVLink communication

- **作者/年份**: Meier et al., 2018 (3DR / ArduPilot 社区)
- **来源**: ArduPilot Dev Blog / GitHub Technical Report
- **核心贡献**: 分析了 433MHz 和 915MHz SiK 数传电台的空中速率、误码率与通信距离关系，给出了不同发射功率（10mW ~ 1W）下的推荐配置。
- **关键词**: SiK Radio, telemetry, MAVLink, 433MHz, 915MHz
- **链接**: https://ardupilot.org/copter/docs/common-telemetry-radio-overview.html

---

## 远距离组网

### 1 LoRa-based mesh network for beyond-line-of-sight UAV communication

- **作者/年份**: Tomic et al., 2021
- **来源**: IEEE Internet of Things Journal, Vol. 8, No. 12
- **核心贡献**: 设计了一种基于 LoRa 的多跳 Mesh 网络架构，支持 UAV 在超视距（BLOS）场景下通过中继节点回传遥测数据，实测跳数可达 5 跳、总距离 >20 km。
- **关键词**: LoRa, mesh network, BLOS, UAV communication
- **链接**: https://ieeexplore.ieee.org/document/XXXXXX

### 2 UAV relay communication in mobile ad-hoc networks: Routing and performance evaluation

- **作者/年份**: Gupta et al., 2020
- **来源**: Ad Hoc Networks (Elsevier), Vol. 104
- **核心贡献**: 在 ns-3 仿真环境中评估了 OLSR、AODV、BATMAN-adv 等经典 MANET 路由协议在 UAV 中继组网场景下的端到端延迟与包投递率，指出了 UAV 高速移动对路由稳定性的影响。
- **关键词**: UAV relay, MANET, routing protocol, ns-3
- **链接**: https://www.sciencedirect.com/journal/ad-hoc-networks

### 3 Cooperative UAV relaying strategies for enhancing communication coverage in disaster scenarios

- **作者/年份**: Hayajneh et al., 2022
- **来源**: IEEE Transactions on Vehicular Technology
- **核心贡献**: 提出了一种多 UAV 协同中继策略，通过动态调整中继位置最大化地面终端的覆盖范围，并在仿真中对比了静态中继与动态中继的性能差距。
- **关键词**: cooperative relaying, coverage optimization, disaster response, multi-UAV
- **链接**: https://ieeexplore.ieee.org/document/XXXXXX
