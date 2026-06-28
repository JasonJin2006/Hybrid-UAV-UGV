# 动力与能源（Power and Energy）

## 概览

| Topic | Key Challenges | Key Technologies | Popular Platforms/Tools |
|-------|---------------|------------------|------------------------|
| 推力-重量比权衡 | 飞行推力和地面扭矩需求矛盾；额外变形机构增加重量 | 混合推进系统（串联/并联）；高功率密度电机；轻量化结构材料 | MATLAB/Simulink；OpenMDAO；XFOIL |
| 动力分配策略 | 飞行与地面运动模式切换的动态响应；能量管理实时性 | 深度强化学习（DRL）；模糊逻辑控制；基于规则的能量管理策略（EMS） | TensorFlow/PyTorch；Simulink Stateflow |
| 电池选型与管理 | 能量密度与放电倍率平衡；BMS热管理；飞行安全 | 锂聚合物（LiPo）；锂离子（Li-ion）；氢燃料电池；电池管理系统（BMS） | COMSOL；BTMS设计工具；C-rating计算器 |

---

## 推力-重量比权衡

### 1 混合推进系统在小型无人机中的概念设计与优化选型

- **作者/年份**：Yilmaz E. et al., 2023
- **来源**：*Aerospace Science and Technology*
- **核心贡献**：提出针对小型无人机混合推进系统的非线性约束优化方法，综合考翼载荷、展弦比、失速速度、电池功率和燃料电池功率的多目标权衡
- **关键词**：小型无人机；混合推进；优化选型；燃料电池
- **链接**：[SciSpace](https://scispace.com/papers/conceptual-design-and-optimal-sizing-of-a-small-unmanned-3hx3dx39) [需手动下载]

### 2 串列混合电推进系统在VTOL飞行器中的尺寸确定方法

- **作者/年份**：Zhang L. et al., 2025
- **来源**：*Aerospace Science and Technology* (Vol. 158)
- **核心贡献**：提出解析方法对VTOL飞行器的串列混合电推进系统进行动力源组件选型，给出推力-重量比与续航之间的解析关系
- **关键词**：VTOL；混合电推进；尺寸确定；垂直起降
- **链接**：https://www.sciencedirect.com/science/article/pii/S1270963825008168 [需手动下载]

### 3 并联混合推进系统设计与MALE级无人机集成

- **作者/年份**：Demir U. et al., 2025
- **来源**：*Heliyon* (Vol. 11, Issue 4)
- **核心贡献**：设计了针对MALE级无人机的并联混合推进系统，通过发动机选型和电力系统匹配实现推力重量比优化
- **关键词**：MALE无人机；并联混合推进；动力系统集成
- **链接**：https://www.sciencedirect.com/science/article/pii/S2405844025012526 [需手动下载]

---

## 动力分配策略

### 4 混合动力无人机能量管理框架

- **作者/年份**：Li Z. et al., 2025
- **来源**：*Energy* (Vol. 312)
- **核心贡献**：提出面向混合动力无人机的新型能量管理框架，采用自适应分层策略协调燃料电池与电池的功率分配
- **关键词**：能量管理；混合动力无人机；燃料电池；自适应控制
- **链接**：https://www.sciencedirect.com/science/article/pii/S0360544225013933 [需手动下载]

### 5 氢燃料电池混合无人机能量管理策略综述

- **作者/年份**：MDPI Aerospace Editorial, 2025
- **来源**：*MDPI Aerospace* (Vol. 12, No. 12, 1097)
- **核心贡献**：系统综述氢燃料电池混合无人机的能量管理策略（EMS），涵盖基于规则、基于优化和基于学习的三类方法，分析混合动力系统拓扑结构
- **关键词**：氢燃料电池；混合无人机；能量管理策略；综述
- **链接**：https://www.mdpi.com/2226-4310/12/12/1097 [开放获取]

### 6 基于深度强化学习的混合电动无人机高效能量管理策略

- **作者/年份**：Wang H. et al., 2025
- **来源**：*Applied Energy* (Vol. 384)
- **核心贡献**：针对混合电动无人机提出基于强化学习的能量和涡轮轴发动机转速协同控制策略，在动态飞行剖面下实现最优功率分配
- **关键词**：深度强化学习；能量管理；混合电动无人机；涡轮轴发动机
- **链接**：https://www.sciencedirect.com/science/article/pii/S0306261925005677 [需手动下载]

### 7 基于强化学习的可持续混合无人机能量管理

- **作者/年份**：Chen X. et al., 2026
- **来源**：*CEAS Aeronautical Journal*
- **核心贡献**：提出基于强化学习的可持续混合无人机能量管理系统，在最小化生态影响的同时保持运行效率
- **关键词**：强化学习；可持续航空；混合动力；能量管理
- **链接**：https://link.springer.com/article/10.1007/s13272-026-00944-4 [需手动下载]

### 8 混合动力无人机能量管理与系统设计

- **作者/年份**：Zhang Y. et al., 2022
- **来源**：*Energy Science & Engineering* (Vol. 10, Issue 9)
- **核心贡献**：评估燃料电池混合无人机多种能量管理策略和系统优化设计方法，对比不同拓扑结构下的能量利用效率
- **关键词**：燃料电池混合动力；系统设计；能量管理策略
- **链接**：https://scijournals.onlinelibrary.wiley.com/doi/full/10.1002/ese3.1262 [开放获取]

### 9 模糊逻辑与多因子强化学习的混合燃料电池固定翼无人机功率管理

- **作者/年份**：Al-Dujaili A. et al., 2025
- **来源**：*Nature Scientific Reports* (Vol. 15)
- **核心贡献**：结合模糊逻辑编程和多因子强化学习（MFRL）方法，对混合燃料电池固定翼无人机进行功率管理，实现油耗优化
- **关键词**：模糊逻辑；多因子强化学习；燃料电池；固定翼无人机
- **链接**：https://www.nature.com/articles/s41598-025-32313-2 [开放获取]

### 10 变形四旋翼飞行器综述：增强多功能性与适应性

- **作者/年份**：Raza A. et al., 2024
- **来源**：*MDPI Drones* (Vol. 8, No. 12, 762)
- **核心贡献**：全面综述变形四旋翼研究进展，涵盖变形概念、驱动机构和飞控策略，分析变形过程中动力分配变化
- **关键词**：变形四旋翼；动力分配；飞行控制；驱动机构
- **链接**：https://www.mdpi.com/2504-446X/8/12/762 [开放获取]

### 11 混合动力无人机混合推进系统性能评估

- **作者/年份**：Kim S. et al., 2025
- **来源**：*MDPI Electronics* (Vol. 14, No. 14, 2873)
- **核心贡献**：对无人机混合推进系统进行综合性能评估，验证混合动力系统在延长续航和提升负载能力方面的有效性
- **关键词**：混合动力系统；性能评估；无人机续航；推进效率
- **链接**：https://www.mdpi.com/2079-9292/14/14/2873 [开放获取]

### 12 无人机混合动力装置设计与能量管理

- **作者/年份**：Marchese V. et al., 2025
- **来源**：*MDPI Energies* (Vol. 18, No. 12, 3101)
- **核心贡献**：设计无人机混合动力装置，通过优化能量管理提高自主飞行时间，提供完整的建模仿真和实验验证
- **关键词**：混合动力装置；能量管理；UAV自主性；系统优化
- **链接**：https://www.mdpi.com/1996-1073/18/12/3101 [开放获取]

---

## 电池选型与管理

### 13 LiPo电池建模及其在无人机动态无线充电中的应用

- **作者/年份**：Ali A. et al., 2022
- **来源**：*IEEE Access* (Vol. 10)
- **核心贡献**：提出基于戴维南等效电路模型的LiPo电池建模方法，适用于无人机动态无线充电场景
- **关键词**：LiPo电池；等效电路模型；无线充电；UAV
- **链接**：https://ieeexplore.ieee.org/document/9922909 [需手动下载]

### 14 无人机电池建模方法比较研究

- **作者/年份**：MDPI Batteries Editorial, 2025
- **来源**：*MDPI Batteries* (Vol. 16, No. 2, 55)
- **核心贡献**：系统比较无人机电池的不同建模方法，评估各方法在优化UAV性能和可靠性方面的适用性
- **关键词**：电池建模；无人机；性能优化；锂聚合物
- **链接**：https://www.mdpi.com/2032-6653/16/2/55 [开放获取]

### 15 基于电池模型的小型低成本多旋翼无人机推力控制器

- **作者/年份**：Johnson M. et al., 2013
- **来源**：*IEEE/ASME AIM Conference*
- **核心贡献**：利用电池动态特性构建基于电池模型的推力控制器，适用于无执行器反馈的低成本多旋翼平台
- **关键词**：电池模型；推力控制；低成本多旋翼；LiPo
- **链接**：https://www.researchgate.net/publication/258567656 [需手动下载]

---

## 参考文献与扩展阅读

- **能量管理策略综述**：Zhang Y. et al. (2022), *Energy management and system design for fuel cell hybrid unmanned aerial vehicles*, Energy Science & Engineering.
- **变形无人机动力系统**：Raza A. et al. (2024), *Morphing Quadrotors: A Review*, MDPI Drones.
- **LiPo电池技术指南**：Unmanned Systems Technology, *LiPo Batteries for Drones & UAV*, https://www.unmannedsystemstechnology.com/expo/lithium-polymer-lipo-batteries/ [行业综述]
