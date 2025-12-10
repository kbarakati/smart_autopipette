# Autonomous Obstacle-Aware Navigation for Pipetting Robots using Reinforcement Learning

This repository contains the full implementation of **AutoPipetteEnv**, a LiDAR-driven reinforcement learning framework enabling collision-aware motion inside automated laboratory pipetting systems.

---

## 🧭 Navigation Behavior Comparison
<div align="center" style="display:flex; justify-content:center; gap:20px;">
  
  <video src="<video controls src="https://github.com/kbarakati/smart_autopipette/blob/main/media/5_obstacles_5.mp4" title="PASTE_5_OBSTACLES_LINK_HERE"></video>"
         width="360" autoplay loop muted playsinline></video>

  <video src="<video controls src="https://github.com/kbarakati/smart_autopipette/blob/main/media/10_obstacles_4.mp4" title="PASTE_10_OBSTACLES_LINK_HERE"></video>"
         width="360" autoplay loop muted playsinline></video>

</div>
<p align="center"><em>
Left: 5 obstacles. Right: 10 obstacles.
</em></p>

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
