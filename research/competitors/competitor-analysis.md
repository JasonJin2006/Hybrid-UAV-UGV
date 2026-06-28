# 竞品分析 — 陆空两栖机器人/相关产品

> 更新日期：2026-06-28

## 概览

| 产品类型 | 代表品牌 | 产品数 | 与本项目关系 | 分析价值 |
|----------|---------|--------|-------------|---------|
| 工业无人机（空中平台） | 大疆、科比特、极飞 | 5 | 提供空中飞行的技术标杆 | 飞控、续航、载荷、通信方案 |
| 无人车/UGV（地面平台） | AgileX、松灵、星尘智能 | 4 | 提供地面行驶的技术标杆 | 底盘、悬挂、驱动方案 |
| 企业级飞控 | Auterion、CubePilot | 2 | 飞控软硬件参考 | PX4商业发行版、开源飞控生态 |
| 陆空两栖/变形平台 | PARGS、Festo、Skoltech | 4 | 直接竞品 | 构型设计、切换机构、过渡控制 |

---

## 一、工业无人机（空中平台标杆）

| 产品名 | 公司 | 年份 | 构型 | 重量 | 续航 | 载重 | 控制方式 | 特点 | 参考价格 | 链接 |
|--------|------|------|------|------|------|------|---------|------|---------|------|
| DJI Matrice 350 RTK | 大疆创新 (DJI) | 2023 | 四旋翼 | ≈6.5kg（含电池） | 55min（无负载） | ≤2.7kg（单云台） | DJI Pilot 2 / SDK / OSDK | IP55防护、六向避障、支持RTK定位、TB60智能电池 | ≈¥60,000（机身） | [dji.com](https://www.dji.com/matrice-350-rtk) |
| DJI Matrice 30T | 大疆创新 (DJI) | 2022 | 四旋翼折叠 | ≈3.7kg（含电池） | 43min | ≤0.8kg | DJI Pilot 2 / SDK | 一体化防水机身、多传感器融合、LTE备份链路、六向避障 | ≈¥78,000（套装含H20T） | [dji.com](https://www.dji.com/matrice-30) |
| DJI M300 RTK | 大疆创新 (DJI) | 2020 | 四旋翼 | ≈6.3kg | 55min | ≤2.7kg | DJI Pilot / SDK | 上代旗舰、三云台、双目视觉+ToF避障 | 已停产/二手≈¥40,000 | [dji.com](https://www.dji.com/matrice-300-rtk) |
| 科比特 MMC-120H | 科比特航空 | 2023 | 六旋翼 | ≈12kg | 60min | ≤5kg | 私有遥控/地面站 | 大载重、六旋翼冗余、工业级防水IP65 | ≈¥120,000（预估） | 科比特官网（需询价） |
| 极飞 P150 | 极飞科技 (XAG) | 2024 | 四旋翼 | ≈28kg（含满载） | 15min（喷洒作业） | ≤40L/32kg | 极飞App / 遥控器 | 农业专用、RTK定位、地形跟随、播撒/喷洒一体 | ≈¥38,000（裸机） | [xag.com](https://www.xa.com/p150) |
| DJI FlyCart 30 | 大疆创新 (DJI) | 2024 | 八轴（四旋翼双臂） | ≈42kg（空机） | 18min（满载16km） | ≤30kg | DJI Pilot 2 / SDK | 运载专用、折叠货箱/索降、ADS-B、降落伞 | ≈¥120,000 | [dji.com](https://www.dji.com/flycart-30) |

> 说明：DJI系列在飞控稳定性、避障能力、SDK生态完整性上处于行业绝对领先地位。M350 RTK是行业级标杆。FlyCart 30虽为运载用途，但其载荷能力与结构设计对混合平台有参考意义。

---

## 二、UGV 地面无人车平台（地面平台标杆）

| 产品名 | 公司 | 年份 | 构型 | 重量 | 续航 | 载重 | 控制方式 | 特点 | 参考价格 | 链接 |
|--------|------|------|------|------|------|------|---------|------|---------|------|
| AgileX Hunter SE | AgileX (松灵/深圳) | 2023 | 四轮差速/阿克曼 | ≈50kg | 8h（空载） | ≤65kg | CAN / ROS / RC | 大载重、IP54、独立悬挂、支持ROS/ROS2、可选阿克曼转向 | ≈¥25,000 | [agilex.com](https://www.agilex.ai/) |
| AgileX Bunker Mini | AgileX (松灵/深圳) | 2022 | 履带式 | ≈35kg | 4h | ≤30kg | CAN / ROS / RC | 全向履带、可爬30°斜坡、IP65 | ≈¥18,000 | [agilex.com](https://www.agilex.ai/) |
| AgileX Ranger Mini V2 | AgileX (松灵/深圳) | 2024 | 四轮四驱 | ≈45kg | 6h | ≤40kg | CAN / ROS / RC | 越野底盘、独立悬挂、大载重、支持云台扩展 | ≈¥28,000 | [agilex.com](https://www.agilex.ai/) |
| 松灵 SCOUT Mini | 松灵机器人 (AgileX子品牌) | 2022 | 四轮差速 | ≈28kg | 4h | ≤20kg | CAN / ROS / RC | 小型化、轻量级、适合室内/半室外 | ≈¥12,000 | [agilex.com](https://www.agilex.ai/) |

> 说明：AgileX在UGV开源机器人领域占据主导地位，其产品线覆盖轻量到重载，所有产品均提供ROS/ROS2接口与SDK，是构建混合平台地面模块的理想参考。

---

## 三、企业级飞控与开源飞控生态

| 产品名 | 公司 | 年份 | 类型 | 支持硬件 | 特点 | 参考价格 | 链接 |
|--------|------|------|------|---------|------|---------|------|
| Auterion Enterprise PX4 | Auterion (瑞士) | 2023 | 企业级飞控发行版 | Cube Orange+/Purple+ | PX4企业发行版、OTA更新、RBAC安全、网络化云控 | 授权制（需询价） | [auterion.com](https://auterion.com) |
| Auterion Skynode | Auterion (瑞士) | 2022 | 机载计算+飞控一体 | 内置STM32+ARM | 集成飞控与边缘计算（NXP i.MX 8）、5G通信 | $4,000+（预估） | [auterion.com](https://auterion.com) |
| CubePilot Cube Orange+ | CubePilot (澳大利亚) | 2023 | 开源飞控硬件 | STM32H743 | 三冗余IMU、双GPS、Pixhawk标准、支持ArduPilot/PX4 | ≈¥3,000（不含外设） | [cubepilot.org](https://cubepilot.org) |
| Holybro Pixhawk 6X | Holybro (香港) | 2023 | 开源飞控硬件 | STM32H753 | 最新Pixhawk标准、FMUv6X、多个传感器冗余 | ≈¥2,500 | [holybro.com](https://holybro.com) |

> 说明：Auterion是PX4的官方商业发行版维护方，其Skynode是飞控+机载计算一体化方案。CubePilot和Holybro提供Pixhawk标准下的硬件方案。

---

## 四、陆空两栖/变形平台（直接竞品或相近产品）

| 产品名 | 公司/机构 | 年份 | 构型 | 重量 | 续航（空中/地面） | 载重 | 控制方式 | 特点 | 参考价格 | 链接 |
|--------|----------|------|------|------|------------------|------|---------|------|---------|------|
| PARGS (Photonics Aerial Robotics Ground System) | Skoltech (俄罗斯) | 2021 | 四旋翼+轮式底盘可分离 | ≈6kg | 20min（飞）/ 2h（走） | ≤1kg | PX4 + ROS | 飞行模块与地面模块可分离，两者可独立工作。地面模块为四轮差速底盘 | 原型机/学术 | [Skoltech PARGS](https://www.skoltech.ru/en/gai/research/photonics-and-robotics/)（付费墙论文） |
| Voliro T | Voliro (瑞士/ETH Zurich) | 2022 | 六旋翼倾转（全向飞行+地面滚动） | ≈7kg | 12min（巡航） | ≤0.5kg | 私有飞控 + ROS | 倾转旋翼构型，可垂直墙面/管道表面贴附滚动检测 | 商业原型（$30,000+ 预估） | [voliro.ch](https://voliro.ch) |
| Festo BionicOpter | Festo (德国) | 2022 | 仿生蜻蜓（四翼+机身） | ≈0.2kg | 5-8min | 无 | 私有嵌入式 | 可悬停、滑翔、仿蜻蜓机动、非传统飞行+地面混合 | 研究展示/非卖品 | [festo.com](https://www.festo.com) |
| DJI RoboMaster S1 | 大疆创新 (DJI) | 2019 | 四轮麦克纳姆轮 | ≈3.3kg | 2h（低负荷） | ≤0.5kg | DJI App / 编码器 | 虽非航空航天级产品，但实现了室内"空地一体"编程竞赛平台，麦克纳姆轮全向行驶 | ¥3,499 | [dji.com/robomaster-s1](https://www.dji.com/robomaster-s1) |
| Swarmio (概念验证) | 香港科技大学 | 2023 | 四旋翼+差速底盘可变形 | ≈4kg | 15min / 1h | ≤0.3kg | PX4 + ROS2 | 变形机构为齿轮旋转式，四旋翼展开为飞行构型，合拢为行驶构型 | 原型机/学术 | IEEE ICRA 2023（付费墙） |
| 南航变形空地两栖无人机 | 南京航空航天大学 | 2022 | 四旋翼+两轮平衡车构型 | ≈3.5kg | 12min / 40min | ≤0.2kg | 私有飞控 + STM32 | 飞行模式与平衡车模式间自动切换，采用倾转机构 | 原型机/学术 | 航空学报（付费墙） |

> 说明：真正商业化的陆空两栖产品极少。大多数停留在学术原型阶段。PARGS 是技术路线最为接近（可分离式飞行+地面模块）的项目。Voliro T 代表了全向飞行+地面滚动混合形态的商用探索。

---

## 五、行业分析与差距

### 5.1 市场空白

| 维度 | 现状 | 机会 |
|------|------|------|
| 飞行+地面一体变形 | 学术原型为主，尚无量产商品 | 高——满足巡检、侦察、救援等长航程+精细操作需求 |
| 可分离式空地模块 | 仅PARGS实现 | 中——模块化设计可提升任务灵活性 |
| 大载荷空地两栖 | 无成熟产品 | 中高——军工/特种作业有明确需求 |
| 高续航（>1h地面+>30min空中） | 所有原型远低于此 | 高——能量密度瓶颈是关键技术挑战 |

### 5.2 关键差距总结

1. **续航矛盾**：空中飞行能耗大（≈200-400W悬停），地面行驶能耗低（≈30-80W）。任何有效的两栖平台都需要合理的能量管理策略
2. **重量限制**：变形机构（机械臂、旋转机构、倾转机构等）的重量会严重压缩有效载荷空间，需在结构轻量化和刚度之间权衡
3. **控制连续性**：飞行⇌地面过渡阶段的气动干扰和地面效应导致控制律复杂，目前学术原型均为低速切换
4. **商业化准备**：除大疆农业和运载无人机外，所有两栖平台均处于原型或学术研究阶段，距量产有3-5年差距

---

## 六、参考链接汇总

| 类别 | 名称 | 链接 |
|------|------|------|
| 工业无人机 | DJI Matrice 350 RTK | https://www.dji.com/matrice-350-rtk |
| 工业无人机 | DJI Matrice 30 Series | https://www.dji.com/matrice-30 |
| 无人机运载 | DJI FlyCart 30 | https://www.dji.com/flycart-30 |
| 农业无人机 | 极飞 P150 | https://www.xa.com/p150 |
| UGV 平台 | AgileX (松灵) | https://www.agilex.ai/ |
| 企业飞控 | Auterion | https://auterion.com |
| 飞控硬件 | CubePilot | https://cubepilot.org |
| 飞控硬件 | Holybro | https://holybro.com |
| 学术原型 | Skoltech PARGS | https://www.skoltech.ru/en/gai/research/photonics-and-robotics/ |
| 全向飞行 | Voliro | https://voliro.ch |
| 竞品平台 | DJI RoboMaster S1 | https://www.dji.com/robomaster-s1 |

---

## 备注

- 标有"预估"的价格为根据同类产品推测，实际价格需联系厂商询价
- 标有"学术"的产品为研究原型，不公开出售
- 北美/欧洲的竞品（如Skydio、Flyability）未列入，因它们专注于纯空中平台，与本项目的两栖混合形态差距较大
- 中国军方涉及的未公开两栖平台不在本调研范围内
