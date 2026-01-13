---
title: Drone trajectory planning
date: 2025-11-03
draft: false
summary: This project develops and implements an MPC based local path planning algorithms to enhance the autonomous navigation capabilities of mobile robots
links:
  - type: code
    url: https://github.com/Relo02/Drone-optimal-trajectory
    label: Source Code
---

## Problem

Autonomous navigation in GPS-denied or dynamic environments requires robust local path planning that can react to obstacles in real-time while optimizing trajectory efficiency.

## Approach

- Implemented **Model Predictive Control (MPC)** for local trajectory optimization
- Integrated with ROS 2 navigation stack with gazebo simulation and PX4 low levels controllers
- Tested on both ground robots and quadcopters
- Combined with SLAM and object detection for obstacle avoidance

## Technologies

- **Frameworks:** ROS 2, MPC library CasADi
- **Sensors:** LiDAR, IMU
- **Hardware:** [Quadcopter with pixhawk flight controller and Jetson Orin Nano]