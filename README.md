# DA6400 - Reinforcement Learning Assignment 3

**Course**: DA6400 - Introduction to Reinforcement Learning  
**Institute**: Indian Institute of Technology Madras  
**Student**: Shreyas Rathod (CS24M046)  
**Date**: May 1, 2025

## 📌 Overview

This repository contains the implementation and experiments for **Programming Assignment 3** of the Reinforcement Learning course. The assignment explores **1-step SMDP Q-Learning** and **Intra-option Q-Learning** in the classic **Taxi-v3** environment from the Gymnasium library. It emphasizes learning with both **handcrafted** and **alternative macro-actions ("options")**, showcasing hierarchical reinforcement learning.

---

## 🚕 Environment

**Taxi-v3**: A grid world environment where the agent must pick up and drop off passengers at specified locations.  
**State space**: 500  
**Action space**: 6 primitive actions + 4 or 2 macro-actions depending on setup.

---

## ✅ Algorithms Implemented

### 1. SMDP Q-Learning
- Learns Q-values for both primitive actions and extended "options"
- Uses macro-actions like `go_to_R`, `go_to_G`, `go_to_Y`, `go_to_B`

### 2. Intra-option Q-Learning
- Off-policy learning
- Evaluates internal steps of options
- Faster convergence with temporally extended reasoning

### 3. Alternative Options
- Introduced new options:
  - `go_to_left_center`
  - `go_to_right_center`
- Tested both algorithms with this new set

---

## 📊 Experiments

- **5000 episodes** per setup
- Hyperparameters:
  - `Alpha` (learning rate): 0.1
  - `Gamma` (discount): 0.9
  - `Epsilon` (exploration): 0.001

### 🔍 Comparisons

| Setting                        | Avg. Reward | Convergence Speed | Notes                                 |
|-------------------------------|-------------|-------------------|----------------------------------------|
| SMDP (given options)          | -10.13      | Moderate          | Stable but slower to converge          |
| Intra-option (given options)  | -12.42      | Faster            | More fluctuations, faster convergence  |
| SMDP (new options)            | -13.10      | Slower            | Shows option reuse                     |
| Intra-option (new options)    | -13.24      | Fastest           | Quick convergence with more abstraction|

---

## 📁 Files

- `CS23M046_RL_assignment_3.ipynb`: Final notebook with code and results
- `CS24M046_RL_PA3_Report.pdf`: Detailed report with observations and plots

---

## 📈 Visualizations

Reward curves and Q-value heatmaps are included in the notebook and report.  
They illustrate:
- Fluctuation vs. stability
- Option preference vs. primitive action selection
- Hierarchical abstraction benefits

---

## 🔗 GitHub

[Repository Link](https://github.com/Shreyas-Rathod/DA6400_JanMay2025_PA3)

---

## 💡 Conclusion

This assignment highlights the practical benefits of **temporal abstraction** in RL.  
Intra-option Q-learning shows stronger performance in complex state spaces, while SMDP Q-learning remains simpler and interpretable.

