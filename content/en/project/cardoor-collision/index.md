---
title: Car Door Collision Alarm
summary: Preventing accidents with simple intelligent alerts
tags:
- Embedded Systems
- Control Systems

date: "2021-03-01T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: 

image:
  caption: 
  focal_point: Smart
---
## **Overview**
This project focuses on preventing accidents caused by opening vehicle doors into oncoming traffic through a simple embedded warning system.

> Reduces risk of roadside accidents with an intuitive, real-time proximity warning system.
---

## **Problem**
- Accidents caused by lack of awareness when opening car doors
- Limited low-cost safety solutions for this scenario

---

## **Solution**
I developed a **distance-based alert system** that warns users of approaching vehicles before opening the door.

---

## **System Design**
### Hardware
- IR distance sensor for proximity detection
- Buzzer for audio alert
- Analog and digital control components

### Control Logic
- Warning intensity increases as distance decreases
- Sound frequency and volume vary dynamically

---

## **Engineering Concepts**
- On-off control systems
- Sensor response calibration Signal processing (FFT, filtering, Hamming window)


### Tools & Technologies
- Analog electronics (op-amp comparator)
- Relay and BJT switching
- Embedded control logic

---

## **Key Features**
- Real-time proximity detection
- Adaptive audio feedback
- Simple and cost-effective implementation

---

## **Outcome**
- Functional prototype demonstrating effective collision warning
- Applicable for real-world vehicle safety enhancement
