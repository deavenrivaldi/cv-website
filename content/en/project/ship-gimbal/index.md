---
title: 3-Axis Gimbal Stabilization and Target Tracking for Marine Robotic Systems
summary: A simulation-driven marine robot adaptive control system for robust target tracking under dynamic wave disturbances.
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
## **Overview**
This project focuses on developing a **three-axis gimbal stabilization and tracking system** for unmanned surface vehicles (USVs) operating in dynamic marine environments.

Unlike conventional two-axis systems, the proposed design compensates for **multi-axis disturbances caused by wave motion**, enabling stable targeting and alignment under real-world conditions.

The system follows a **simulation-first (sim-to-real) approach**, integrating perception, control, and actuation within a unified robotics framework.

> Enhances targeting stability and robustness of marine robotic systems under nonlinear wave-induced disturbances.
---

## **Problem**
1. Marine environments introduce nonlinear, multi-DOF disturbances (roll, pitch, yaw)
2. Conventional 2-axis gimbal systems cannot fully compensate roll motion
3. System accuracy degrades due to:
    - Vessel motion
    - Environmental disturbances
    - Sensor and control limitations
4. Real-world testing is:
    - High cost
    - High risk
    - Difficult to control

---

## **Solution**
The project propose a **vision-assisted 3-axis gimbal stabilization system** that combines:

- IMU-based disturbance estimation
- Vision-based target tracking
- Closed-loop control with PID and reinforcement learning (RL)

The system is developed within a physics-based simulation environment, enabling safe and scalable validation before real-world deployment.

---

## **System Design**
### System Architecture
The system is structured into three main pipelines:

1. Sensing
    - Camera (target detection)
    - Dual IMU (gimbal + vessel reference)
2. Processing
    - Target position → angular error
    - IMU data → disturbance estimation
    - Sensor fusion for stabilization + tracking
3. Control
    - Closed-loop control for gimbal actuation
    - PID + RL-based adaptive strategy

### Simulation Environment
- ROS 2 + Gazebo (marine simulation)
- Physics-based modeling:
    - Hydrodynamics (drag, lift)
    - Wave disturbances (periodic + nonlinear)
- Digital twin vessel modeling for sim-to-real consistency

### Gimbal System 
- 3-axis configuration:
    - Yaw
    - Pitch
    - Roll
- Independent rotational control for:
    - Line-of-sight stabilization
    - Target alignment

### Vision-Based Tracking
1. YOLOv8 for object detection
2. OpenCV for image processing

Processing pipeline:
```
Image → Detection → Bounding box → Pixel offset → Angle conversion
```
- Pixel-to-angle mapping using camera FOV
- Output drives yaw and pitch adjustments

### Control Strategy 
1. Closed-loop stabilization using:
    - IMU feedback (disturbance rejection)
    - Vision feedback (tracking alignment)
2. PID control for baseline stability
3. Reinforcement Learning (RL) for adaptive control under nonlinear conditions

### Hardware & Communication
- PC: high-level control + RL inference
- ROS 2: communication middleware
- NVIDIA Jetson: vision + sensor processing
- Motor controller: drives gimbal actuators

---

## **Key Features**
- 3-axis stabilization for full DOF disturbance compensation
- Vision + IMU sensor fusion
- Simulation-first (sim-to-real) development pipeline
- Adaptive control using reinforcement learning
- Physics-based marine environment modeling
- Modular and scalable system architecture

---

## **Outcome**
_Work in progress_
