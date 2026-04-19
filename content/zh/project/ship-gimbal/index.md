---
title: 面向海洋机器人系统的三轴云台稳定与目标跟踪技术
summary: 基于仿真的海洋机器人系统，融合视觉感知、IMU传感与自适应控制，实现波浪扰动下的稳定目标跟踪。
tags:
- Simulation
- Control Systems
- Computer Vision
- Automation and Robotics

date: "2025-04-01T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: 
  focal_point: smart

links:
#- icon:
#  icon_pack: 
#  name: 
#  url: 
url_code: "https://github.com/deavenrivaldi/ship_gimbal_tracking"
#url_pdf: ""
#url_slides: ""
#url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""

---
## **概述**
本项目致力于开发一套应用于无人水面载具（USV）的**三轴云台稳定与目标跟踪系统**，用于应对复杂海洋环境中的动态扰动问题。

相比传统二维云台系统，该系统能够补偿由海浪引起的**多自由度（roll / pitch / yaw）扰动**，从而实现更高精度的目标稳定与跟踪。

系统采用**仿真优先（Sim-to-Real）开发方法**，在虚拟环境中完成感知、控制与系统集成的验证。

> 在非线性海洋扰动环境下，实现高鲁棒性的目标稳定与跟踪能力。
---

## **问题定义**
1. 海洋环境存在强非线性、多自由度扰动
2. 传统二维云台无法有效补偿横滚（roll）运动
3. 系统精度受以下因素影响：
    - 船体运动
    - 海浪扰动
    - 传感器与控制误差
4. 实船测试成本高、风险大、可控性低

---

## **解决方案**
提出一套基于视觉辅助的三轴云台稳定系统，融合：

- IMU惯性测量用于扰动估计
- 视觉系统用于目标检测与跟踪
- 基于PID与强化学习的闭环控制

系统在物理仿真环境中完成验证，为实际部署提供基础。

---

## **系统设计**
### 系统架构
系统分为三个主要模块：

1. 感知层
    - 摄像头（目标检测）
    - 双IMU（云台 + 船体参考）
2. 处理层
    - 目标位置 → 角度误差
    - 姿态数据 → 扰动估计
    - 多传感器融合
3. 控制层
    - 云台闭环控制
    - PID + 强化学习

### 仿真环境
- 基于 ROS 2 与 Gazebo 构建
- 包含：
    - 水动力模型（阻力、升力）
    - 海浪扰动建模
- 构建船体数字孪生模型

### 云台系统
- 三轴结构：
    - 偏航（Yaw）
    - 俯仰（Pitch）
    - 横滚（Roll）
- 实现独立姿态控制与视线稳定

### Vision-Based Tracking
1. YOLOv8 目标检测
2. OpenCV 图像处理

流程：
```
图像 → 检测 → 像素偏差 → 角度转换 → 控制输入
```

### 控制策略
1. 基于IMU与视觉的闭环控制
2. PID实现基础稳定
3. 强化学习提升复杂环境适应能力

### 硬件架构
- PC：高层控制与RL推理
- ROS 2：通信中间件
- Jetson：视觉与传感处理
- 电机控制器：执行控制指令

---

## **主要特点**
- 三轴全自由度稳定控制
- 视觉 + IMU 融合感知
- 仿真驱动开发流程（Sim-to-Real）
- 强化学习增强鲁棒性
- 真实物理环境建模
- 模块化系统架构

---

## **项目成果**
_正在做_
