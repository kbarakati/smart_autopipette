# Autonomous Obstacle-Aware Navigation for Pipetting Robots using Reinforcement Learning

This repository contains the full implementation of **AutoPipetteEnv**, a LiDAR-driven reinforcement learning framework enabling collision-aware motion inside automated laboratory pipetting systems.

---

## 🧭 Navigation Behavior Comparison

<div align="center">
  <img src="smart_autopipette/5_obstacles_5.gif" width="350" alt="Simple layout (5 obstacles)">
  <img src="smart_autopipette/10_obstacles_4.gif" width="350" alt="Moderate layout (10 obstacles)">
  <br>
  <em>Left: sparse deck (5 obstacles) with clear corridors. Right: moderate congestion (10 obstacles) requiring detours.</em>
</div>

## 📌 Motivation

Conventional liquid-handling robots (TECAN, Hamilton, Biomek, OT-2) assume **fully static deck geometry**. Any plate displacement, reagent swap, or human intervention introduces collision risk.

This project replaces fixed path execution with **perception-guided motion**, allowing the robot to:
- detect unexpected obstacles,
- infer free-space corridors,
- execute collision-safe motion without halting.

---

## 🧠 Core Idea

We train a pipetting robot in a PyBullet-based RL environment using:
- **360° LiDAR (72 beams)**
- **continuous velocity control**
- **PPO policy training with reward shaping**

This enables the robot to navigate congested decks while avoiding racks, plates, reservoirs, and peripheral lab modules.

---

## 🖼 Environment Visualization

<div align="center">
<img src="media/env_snapshot.png" width="450">
</div>

*Figure: Simulated deck layout with LiDAR beams (orange), obstacles (gray), start (green), and goal (cyan).*

---

## 🚀 Features

- Custom RL environment: **AutoPipetteEnv**
- LiDAR ray casting with goal filtering
- Dense reward shaping for smooth, safe motion
- PPO training with VecNormalize
- GIF trajectory playback
- Training curve visualization

---

## 🏗 Installation

```bash
git clone https://github.com/<your-username>/autopipette-rl-navigation.git
cd autopipette-rl-navigation
pip install -r requirements.txt
