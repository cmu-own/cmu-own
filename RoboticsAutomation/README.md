# 🤖 Robotics & Autonomous Automation Tutorial

Welcome to the **Robotics & Autonomous Automation** tutorial repository! This directory contains Jupyter Notebook implementations and mathematical models for fundamental robotic kinematics, path planning, and trajectory control.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmu-own/cmu-own/blob/main/RoboticsAutomation/robotics_automation.ipynb)

---

## 📌 Comprehensive Overview

Robotics Automation merges spatial kinematics, autonomous navigation, obstacle avoidance, and feedback control loops to build intelligent autonomous systems (e.g., robotic arms, AGVs, autonomous mobile robots).

This tutorial provides a complete Python-based simulation guide covering the end-to-end robotics software stack:

- 🦾 **Robotic Arm Kinematics:** Forward and Inverse Kinematics for planar multi-DOF manipulators.
- 🗺️ **Autonomous Path Planning:** A* Search Algorithm on 2D occupancy grid maps for mobile robot navigation.
- ⚙️ **Feedback Control Systems:** Proportional-Integral-Derivative (PID) closed-loop actuator trajectory tracking.

---

## 📂 Project Structure

```
RoboticsAutomation/
├── robotics_automation.ipynb   # Interactive tutorial notebook with Python code & visual plots
└── README.md                   # Project documentation & guide
```

---

## 🚀 Topics Covered in the Tutorial

1. **Forward Kinematics (2-DOF Planar Arm):**
   - Trigonometric transformations to calculate end-effector coordinates $(x, y)$ from joint angles $(\theta_1, \theta_2)$.

2. **Inverse Kinematics (Target Workspace Reachability):**
   - Solving non-linear joint equations to reach specific spatial goal positions.

3. **Grid-Based A* Path Planning:**
   - Graph search algorithm utilizing Euclidean distance heuristics to plan optimal obstacle-free paths for autonomous mobile robots.

4. **PID Control Loop Simulation:**
   - Tuning $K_p, K_i, K_d$ parameters to eliminate trajectory error and achieve steady-state response.

---

## 🛠️ Prerequisites & Installation

To run this notebook locally, install the required packages:

```bash
pip install numpy scipy matplotlib jupyter
```

---

## 💻 How to Run

### Option 1: Run Online in Google Colab 🚀
Click the badge above or use this direct link:  
👉 [Open robotics_automation.ipynb in Google Colab](https://colab.research.google.com/github/cmu-own/cmu-own/blob/main/RoboticsAutomation/robotics_automation.ipynb)

### Option 2: Run Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/cmu-own/cmu-own.git
   ```
2. Navigate to the `RoboticsAutomation` directory:
   ```bash
   cd cmu-own/RoboticsAutomation
   ```
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook robotics_automation.ipynb
   ```

---

## 📝 License

This project is open-source and created under the MIT License for educational purposes.
