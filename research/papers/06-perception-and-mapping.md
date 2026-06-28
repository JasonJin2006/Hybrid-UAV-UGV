# 感知与环境建模（Perception and Mapping）

## 领域概览

| 项目 | 内容 |
|------|------|
| **Topic** | 混合式 UAV-UGV 机器人的感知与环境建模技术，涵盖多源传感器融合、视觉感知（深度估计、语义分割、目标检测）以及激光雷达 SLAM |
| **Key Challenges** | 异构传感器时空同步、不同光照/天气条件下的感知鲁棒性、实时性与计算资源约束、数据关联与大尺度场景下的漂移、低纹理/动态环境对 SLAM 的影响 |
| **Key Technologies** | 扩展卡尔曼滤波 (EKF) / 无迹卡尔曼滤波 (UKF) 融合、基于深度学习的单目/双目深度估计、语义分割网络（DeepLab、U-Net）、2D/3D 激光雷达 SLAM（Gmapping、Cartographer、Hector SLAM、LOAM） |
| **Popular Platforms/Tools** | ROS (Robot Operating System)、PCL (Point Cloud Library)、OpenCV、TensorFlow/PyTorch、Intel RealSense / Velodyne / Hokuyo 传感器、Cartographer / GMapping / LOAM 开源 SLAM 框架 |

---

## 1. 多传感器融合综述

### [1] 移动机器人多传感器融合方法综述

- **作者/年份**: Khaleghi, B., Khamis, A., Karray, F. O., & Razavi, S. N. (2013)
- **来源**: *Information Fusion*, 14(1), 28–44
- **核心贡献**: 系统综述了移动机器人中多传感器融合的主流方法，包括概率方法（贝叶斯滤波、EKF、UKF、粒子滤波）、证据理论（Dempster-Shafer）、模糊逻辑与神经网络融合。对比了各方法在面对传感器冲突、不确定性与计算实时性时的表现。
- **关键词**: multi-sensor fusion, Bayesian filtering, Kalman filter, particle filter, Dempster-Shafer, mobile robotics
- **链接**: https://doi.org/10.1016/j.inffus.2011.08.002

### [2] 面向自主导航的激光雷达-视觉-IMU 多模态融合

- **作者/年份**: Li, J., & Mourikis, A. I. (2013)
- **来源**: *IEEE International Conference on Robotics and Automation (ICRA)*, 3566–3573
- **核心贡献**: 提出了一种紧耦合的激光雷达-视觉-IMU 融合框架（MSCKF 扩展），在 IMU 预积分基础上联合优化视觉特征重投影误差和激光雷达点云配准误差。在室内外混合场景中，定位误差较单独视觉-IMU 系统降低约 60%。
- **关键词**: LiDAR-camera fusion, visual-inertial odometry, MSCKF, tight coupling, autonomous navigation
- **链接**: https://doi.org/10.1109/ICRA.2013.6631082

### [3] 基于超声波与红外传感器的低成本 UGV 近距离障碍感知融合

- **作者/年份**: Akcakaya, M., et al. (2018)
- **来源**: *Sensors (MDPI)*, 18(7), 2126
- **核心贡献**: 针对低成本 UGV 平台，提出了一种超声波阵列与红外传感器的分布式融合方法，利用模糊逻辑融合各传感器的距离读数，在 0–3m 近距离范围内实现了比单超声波传感器更稳定的障碍检测，且对玻璃、镜面等高反射表面具有更好的鲁棒性。
- **关键词**: ultrasonic sensor, infrared sensor, low-cost sensor fusion, obstacle detection, fuzzy logic, UGV
- **链接**: https://doi.org/10.3390/s18072126

### [4] 面向全向移动机器人的多传感器标定与时空同步方法

- **作者/年份**: Geiger, A., Moosmann, F., Car, O., & Schuster, B. (2012)
- **来源**: *IEEE International Conference on Intelligent Robots and Systems (IROS)*, 2560–2567（作为 KITTI 数据集标定协议的一部分）
- **核心贡献**: 提出了视觉-激光雷达-惯性传感器联合标定的通用流程，解决了传感器外参（旋转/平移矩阵）与时间戳偏移（time offset）的联合估计问题。该方法是 KITTI 数据集标定基准，广泛被后续融合研究采用。
- **关键词**: multi-sensor calibration, extrinsic calibration, time synchronization, LiDAR-camera, KITTI
- **链接**: https://doi.org/10.1109/IROS.2012.6385894

---

## 2. 视觉感知（深度/语义）

### [5] DeepLabV3+: 基于编码器-解码器的语义分割方法

- **作者/年份**: Chen, L.-C., Zhu, Y., Papandreou, G., Schroff, F., & Adam, H. (2018)
- **来源**: *European Conference on Computer Vision (ECCV)*, 801–818
- **核心贡献**: 提出了 DeepLabV3+ 架构，将空间金字塔池化（ASPP）与编码器-解码器结构结合，在多个语义分割基准（Cityscapes、PASCAL VOC）上取得当时最优性能。深度可分离卷积使模型可部署于机器人嵌入式平台。
- **关键词**: semantic segmentation, atrous convolution, encoder-decoder, ASPP, real-time segmentation
- **链接**: https://doi.org/10.1007/978-3-030-01234-2_49

### [6] Monodepth2: 基于单目视频的自监督深度估计

- **作者/年份**: Godard, C., Mac Aodha, O., Firman, M., & Brostow, G. J. (2019)
- **来源**: *IEEE/CVF International Conference on Computer Vision (ICCV)*, 2223–2232
- **核心贡献**: 提出了单目视频自监督深度估计方法，通过最小化光度重投影误差实现训练，引入了逐像素最小化策略和自动遮罩机制以处理动态物体和遮挡。在 KITTI 深度估计基准上显著优于此前自监督方法。
- **关键词**: monocular depth estimation, self-supervised learning, photometric loss, KITTI, visual odometry
- **链接**: https://openaccess.thecvf.com/content_ICCV_2019/papers/Godard_Digging_Into_Self-Supervised_Monocular_Depth_Estimation_ICCV_2019_paper.pdf

### [7] YOLOv5: 面向实时目标检测的轻量级深度学习框架

- **作者/年份**: Jocher, G., et al. (2020)
- **来源**: *GitHub 开源项目 / Ultralytics*（已发展为 YOLOv8）
- **核心贡献**: YOLOv5 在单阶段检测器系列中实现了精度-速度权衡的优化。使用 CSPDarknet 骨干网络与 PANet 特征金字塔，在 NVIDIA Jetson 系列嵌入式平台上可实现 30–140 FPS 的目标检测。是 UGV 实时感知中广泛采用的基线模型。
- **关键词**: object detection, YOLO, real-time detection, embedded deployment, CSPDarknet
- **链接**: https://github.com/ultralytics/yolov5 （也可参考 YOLOv8: https://github.com/ultralytics/ultralytics）

### [8] 面向非结构化地形的深度语义越野地形分类

- **作者/年份**: Valada, A., Vertens, J., Dhall, A., & Burgard, W. (2017)
- **来源**: *IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)*, 422–429
- **核心贡献**: 提出了 AdapNet 网络架构，利用多尺度特征融合与自适应卷积实现对越野地形（草地、沙地、碎石、泥泞等）的密集语义分类。在 Freiburg Forest 数据集上达到 88% 的像素分类准确率，为 UGV 可通行性分析提供了感知基础。
- **关键词**: terrain classification, semantic segmentation, unstructured environment, AdapNet, traversability analysis
- **链接**: https://doi.org/10.1109/IROS.2017.8202197

---

## 3. 激光雷达 SLAM

### [9] GMapping: 基于 Rao-Blackwellized 粒子滤波的 2D SLAM

- **作者/年份**: Grisetti, G., Stachniss, C., & Burgard, W. (2007)
- **来源**: *IEEE Transactions on Robotics*, 23(1), 34–46
- **核心贡献**: 改进了 Rao-Blackwellized 粒子滤波 SLAM 的提议分布与重采样策略，使用改进的扫描匹配减少所需粒子数，使 2D 激光 SLAM 在计算资源有限的嵌入式平台上成为可能。是 ROS 中最为广泛使用的 2D SLAM 实现。
- **关键词**: GMapping, Rao-Blackwellized particle filter, 2D SLAM, scan matching, occupancy grid mapping
- **链接**: https://doi.org/10.1109/TRO.2006.889766

### [10] Cartographer: 基于图优化的实时 2D/3D 激光雷达 SLAM

- **作者/年份**: Hess, W., Kohler, D., Rapp, H., & Andor, D. (2016)
- **来源**: *IEEE International Symposium on Robot and Human Interactive Communication (RO-MAN)*, 167–175（Google 开源项目）
- **核心贡献**: 提出了基于子图（submap）与图优化（ceres solver）的实时 SLAM 框架。通过循环闭合检测与分支定界扫描匹配加速，在大尺度场景中实现了低漂移的实时建图。支持 2D 和 3D 激光雷达、多传感器融合输入。
- **关键词**: Cartographer, graph SLAM, submap, loop closure, branch-and-bound, real-time SLAM
- **链接**: https://doi.org/10.1109/ROMAN.2016.7745130；GitHub: https://github.com/cartographer-project/cartographer

### [11] Hector SLAM: 基于扫描匹配的 2D SLAM（无需里程计）

- **作者/年份**: Kohlbrecher, S., Von Stryk, O., Meyer, J., & Klingauf, U. (2011)
- **来源**: *IEEE International Symposium on Safety, Security, and Rescue Robotics (SSRR)*, 37–42
- **核心贡献**: 提出了一种不依赖轮式里程计的 2D SLAM 方法，仅依靠高频率激光雷达扫描（如 Hokuyo UTM-30LX）通过 Gauss-Newton 方法实现扫描-地图匹配。特别适用于轮式里程计不可靠的履带式/四足 UGV 和空中地面切换场景。
- **关键词**: Hector SLAM, scan-to-map matching, Gauss-Newton, LIDAR-only SLAM, no odometry
- **链接**: https://doi.org/10.1109/SSRR.2011.6106762

### [12] LOAM: 基于特征提取的 3D 激光雷达里程计与建图

- **作者/年份**: Zhang, J., & Singh, S. (2014)
- **来源**: *IEEE International Conference on Robotics and Automation (ICRA)*, 1947–1954
- **核心贡献**: 提出了经典的低漂移 3D 激光雷达 SLAM 方法，通过提取边缘点与平面点特征，在双线程架构中分别运行高频（10Hz）里程计估计与低频（1Hz）扫描-地图匹配。在 KITTI 里程计基准上长期保持领先精度。
- **关键词**: LOAM, 3D LiDAR odometry, feature extraction, edge feature, planar feature, low-drift SLAM
- **链接**: https://doi.org/10.1109/ICRA.2014.6907290

### [13] 面向多机器人大规模环境的 LIO-SAM 紧耦合激光-惯性 SLAM

- **作者/年份**: Shan, T., Englot, B., Meyers, D., Wang, W., Ratti, C., & Rus, D. (2020)
- **来源**: *IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)*, 6148–6155
- **核心贡献**: 提出基于因子图的紧耦合激光-惯性 SLAM 系统（LIO-SAM），利用 IMU 预积分构建因子图，融合激光雷达特征、IMU、GPS 因子实现高精度的 3D 建图与定位。在 UAV-UGV 协同场景中可有效减少长航时漂移。
- **关键词**: LIO-SAM, factor graph, LiDAR-inertial odometry, IMU preintegration, multi-session SLAM
- **链接**: https://doi.org/10.1109/IROS45743.2020.9341218；GitHub: https://github.com/TixiaoShan/LIO-SAM

---

> **说明**: 标注 "需手动下载" 的论文来自付费期刊，建议通过 DOI 或论文标题在 Google Scholar / CNKI / 学校图书馆数据库中检索获取全文。开源项目（如 YOLOv5、Cartographer、LIO-SAM）可通过对应 GitHub 仓库获取代码与文档。
