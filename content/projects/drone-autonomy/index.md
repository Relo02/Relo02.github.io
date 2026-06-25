---
title: GPS-Denied Drone Autonomy — EKF, ORB-SLAM3 & MPC
date: 2024-09-01
summary: An autonomous drone platform for GPS-denied flight. EKF sensor fusion with stereo visual odometry on Jetson Orin, plus a CasADi MPC planner deployed on PX4.
tags:
  - Sensor Fusion
  - Visual Odometry
  - MPC
  - PX4
weight: 4
---

Co-developing an autonomous drone platform for **GPS-denied environments** with the AEA student
team at Politecnico di Milano.

<!--more-->

- **State estimation:** an **EKF** fusing IMU, GPS, barometer, magnetometer, and **stereo visual
  odometry (ORB-SLAM3)** pose estimates, deployed on an **NVIDIA Jetson Orin Nano**.
- **Planning & control:** an **MPC-based path planner (CasADi)**, validated in **Gazebo Harmonic**
  with ROS 2 and deployed on **Pixhawk/PX4**.
- Leading the bring-up from simulation to real-world flight.

`C++` · `CUDA` · `Python` · `ROS 2` · `CasADi` · `PX4`
