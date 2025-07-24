# 🤖 Human–Exoskeleton Gait Model Control

This repository implements the control system for a human–exoskeleton gait simulation framework using both reinforcement learning and predictive control. It supports independent control of the musculoskeletal human model (`myoleg`), the wearable exoskeleton model, and their integrated coupling for synchronized gait simulation.

Built on the structural integration provided in [`legsim`](https://github.com/kekellyu/legsim), the control framework uses MyoSuite’s DEPRL algorithm and a custom DDPC controller to train adaptive, human-like walking behaviors for personalized rehabilitation applications.

---

## 🧠 What It Does

- Trains the **musculoskeletal model** to walk independently using **DEP-augmented reinforcement learning (DEPRL)**
- Controls the **exoskeleton model** using **Data-Driven Predictive Control (DDPC)** for stable gait tracking
- Coordinates both models in an **integrated simulation**, enabling **human–robot gait synchronization**
- Simulates realistic, continuous double-pendulum gait cycles with tendon coupling
- Supports virtual prototyping for patient-specific exoskeleton design

---

## ⚙️ Control Modes

### 1. **Musculoskeletal Model**
- Controlled via DEPRL (Differential Extrinsic Plasticity + RL)
- 28 degrees of freedom
- Learns natural gait with biological realism
- Modified to support continuous walking in MuJoCo

### 2. **Exoskeleton Model**
- Controlled via Data-Driven Predictive Control (DDPC)
- 18 degrees of freedom
- Tracks predefined motion while managing payload and limb dynamics
- Prioritizes smooth motion with stable joint trajectories

### 3. **Integrated Human–Exoskeleton Model**
- Controlled using a combined RL strategy
- Tendon-coupled joint interactions
- Reward function encourages cyclicity and synchronization
- Supports gait alignment between user and exoskeleton

### Updates

1. Integrated `myoleg` musculoskeletal model with an 18-DOF exoskeleton
2. Replaced muscle actuators with exoskeleton-only actuation
3. Initialized `qpos` and `qvel` to a stable, upright standing pose
4. Removed free joints to maintain model rigidity
5. Redirected RL learning pipeline from `myoleg` to exoskeleton

---

