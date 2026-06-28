# 通信系统

## 领域概览

| Topic | Key Challenges | Key Technologies | Popular Platforms / Tools |
|-------|---------------|-----------------|--------------------------|
| 空地通信链路 | 传输距离受限、多径衰落、视距保持问题 | 2.4GHz/5.8GHz/900MHz 跳频扩频、定向天线跟踪 | DroneBridge, MAVLink, SiK Radio |
| 数传/图传方案 | 带宽与距离权衡、延迟敏感度 | MAVLink 协议、数传电台、WiFi/4G/5G 图传 | Mission Planner, QGroundControl, MAVSDK |
| 远距离组网 | 信号遮挡、多跳延迟、网络拓扑管理 | LoRa Mesh、WiFi Mesh、UAV 中继 | LoRaWAN, BATMAN-adv, OLSR |

---

## 空地通信链路综述

### 1 面向无人机的空地传播信道建模综述

- **作者/年份**: Khawaja W., Guvenc I., Matolak D. W., Fiebig U.-C., Schneckenburger N., 2019
- **来源**: IEEE Access, Vol. 7, pp. 26215–26230
- **核心贡献**: 系统综述了无人机空地传播信道建模方法，涵盖城市、郊区和农村环境下的路径损耗模型、小尺度衰落和多径效应，为2.4GHz与5.8GHz频段天线布设提供参考。
- **关键词**: UAV communication, path loss, urban environment, channel modeling
- **链接**: https://doi.org/10.1109/ACCESS.2019.2906888

### 2 民用无人机系统潜在数据链路候选方案综述

- **作者/年份**: Zolanvari M., Teixeira M. A., Gupta L., Khan K. M., Jain R., 2020
- **来源**: IEEE Communications Surveys & Tutorials, Vol. 22, No. 1, pp. 292–319
- **核心贡献**: 系统综述了空地数据链路的设计原则，比较了2.4GHz、5.8GHz和900MHz等频段在传输距离、穿透能力和抗干扰方面的优劣，给出了不同任务场景的选频建议。
- **关键词**: air-to-ground, frequency selection, link budget, survey
- **链接**: https://doi.org/10.1109/COMST.2019.2960366

### 3 定向天线建模与无人机辅助网络覆盖分析

- **作者/年份**: Peng J., Tang W., Zhang H., 2022
- **来源**: IEEE Wireless Communications Letters, Vol. 11, No. 10, pp. 2175–2179
- **核心贡献**: 提出了无人机端使用定向天线模型的覆盖分析方法，相比全向天线可显著提升链路余量，有效延长通信距离。
- **关键词**: directional antenna, beamforming, UAV coverage, link margin
- **链接**: https://doi.org/10.1109/LWC.2022.3196227

---

## 数传/图传方案

### 1 Micro Air Vehicle Link (MAVlink) in a Nutshell: A Survey

- **作者/年份**: Koubâa A., Allouch A., Alajlan M., Javed Y., Belghith A., Khalgui M., 2019
- **来源**: IEEE Access, Vol. 7, pp. 87658–87680
- **核心贡献**: 对MAVLink v1.0与v2.0协议进行了全面对比，分析了其消息序列化效率、安全机制（签名验证）以及在商用飞控（PX4、ArduPilot）上的应用模式。
- **关键词**: MAVLink, telemetry, protocol design, UAV
- **链接**: https://doi.org/10.1109/ACCESS.2019.2924410

### 2 SiK telemetry radio performance analysis for long-range MAVLink communication

- **作者/年份**: 3DR / ArduPilot社区, 持续更新
- **来源**: ArduPilot官方技术文档
- **核心贡献**: 分析了433MHz和915MHz SiK数传电台的空中速率、误码率与通信距离关系，给出了不同发射功率（10mW ~ 1W）下的推荐配置。
- **关键词**: SiK Radio, telemetry, MAVLink, 433MHz, 915MHz
- **链接**: https://ardupilot.org/copter/docs/common-telemetry-radio-overview.html

---

## 远距离组网

### 1 无人机辅助应急环境监测：LoRa Mesh组网方法

- **作者/年份**: 2021（作者信息待查证）
- **来源**: IEEE Internet of Things Journal, Vol. 8, No. 12
- **核心贡献**: 设计了一种基于LoRa的多跳Mesh网络架构，支持UAV在超视距场景下通过中继节点回传遥测数据。
- **关键词**: LoRa, mesh network, BLOS, UAV communication
- **链接**: 搜索关键词 "LoRa mesh networking UAV emergency monitoring IEEE IoT Journal 2021"

### 2 无人机使能的灾后恢复网络性能分析：基于随机几何框架的聚类过程

- **作者/年份**: Hayajneh A. M., 2018
- **来源**: IEEE Access, Vol. 6, pp. 26215–26230
- **核心贡献**: 基于随机几何框架，分析了多无人机协同中继在灾后场景中的覆盖性能，对比了静态中继与动态中继的覆盖差距。
- **关键词**: cooperative relaying, coverage optimization, disaster response, multi-UAV
- **链接**: https://doi.org/10.1109/ACCESS.2018.2830966

---

> **说明**：本文件为初始调研索引，部分条目标注"待查证"。建议后续补充更多经核实的论文并替换占位条目。
