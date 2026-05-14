# StumpEye-cricket-ballpath-predictor
Physics-ML engine for automated cricket ball-path estimation using 3D kinematics and numerical integration.
> 🚧 Active development — work in progress.

## Overview
A physics-based synthetic data engine to generate realistic cricket ball 
trajectories for training AI-powered DRS (Decision Review System) models.
Built for StumpEye — developers of the world's first patented wireless 
stump camera system, official partner of Navi Mumbai Premier League 2024.

## Problem
Training accurate DRS models requires 100,000+ labeled ball trajectories. 
Real-world data collection from 300+ hours of footage yields only ~5,000 
deliveries — 5% of the needed volume. Manual labeling would require 5,000+ 
hours of work.

**Solution:** Generate synthetic training data using physics simulation 
with ground truth labels.

## Physics Model
Forces modelled per delivery:
- Gravity
- Aerodynamic drag (Cd: 0.4–0.5)
- Magnus force / spin (Cl: 0.1–0.3)
- Seam swing effects
- Pitch bounce (coefficient of restitution: 0.5–0.7)

Numerical integration: **Runge-Kutta 4th order**

## Tech Stack
- **Language:** Python 3.8+
- **Physics:** NumPy, SciPy
- **Visualisation:** Matplotlib, Plotly
- **Data:** Pandas, JSON/CSV output
- **Rendering (planned):** Blender Python API

## Output Per Trajectory
| Output | Format |
|---|---|
| Synthetic video (stump-cam POV) | MP4, 1920x1080 @ 60fps |
| Trajectory metadata | JSON/CSV |
| 2D ball tracking coordinates | JSON/CSV |
| 3D world-space coordinates | JSON/CSV |
| LBW decision label (Yes/No) | JSON |

## Progress
- [x] Physics engine — flight dynamics (gravity, drag, Magnus force)
- [x] Numerical integration (RK4)
- [x] Bounce model — coefficient of restitution, spin retention
- [ ] 3D scene creation (Blender)
- [ ] Physics-to-rendering pipeline
- [ ] Large-scale batch generation (target: 100,000+ trajectories)
- [ ] Validation against real StumpEye footage

## Context
StumpEye holds patents in 8+ countries and has deployed at 
professional cricket leagues. Advisory board includes Simon Taufel, 
5x ICC Umpire of the Year.

Built by [@mahika-ravi](https://github.com/mahika-ravi) 
as part of AI Internship at StumpEye (UK, Remote).
