
# 🦿 OpenAI Gymnasium Assignment: BipedalWalker-v3

🔗 **Environment Reference**:  
[https://gymnasium.farama.org/environments/box2d/bipedal_walker/](https://gymnasium.farama.org/environments/box2d/bipedal_walker/)

---

## 🎯 Overview
In this assignment, you will explore the `BipedalWalker-v3` environment, train multiple reinforcement learning agents, and modify the reward function to improve walking performance.

---

## 🔶 Part 1: Environment Interaction

### Task:
- Load the `BipedalWalker-v3` environment.
- Run it for `n` episodes using **random actions**.
- For each episode, print total reward and number of steps.

#### Input Example:
```python
n = 3
```

#### Output Example:
```
Episode 1: Total Reward = -88.42, Steps = 200
Episode 2: Total Reward = -102.15, Steps = 160
Episode 3: Total Reward = -85.67, Steps = 192
```

---

## 🔶 Part 2: Train & Compare 3 RL Algorithms

### Task:
- Use `Stable-Baselines3`, `RLlib`, or similar libraries.
- Train and compare these 3 algorithms on `BipedalWalker-v3`:
  - PPO (Proximal Policy Optimization)
  - SAC (Soft Actor-Critic)
  - A2C (Advantage Actor-Critic)

Train each for **200,000 timesteps**. Then evaluate each over **10 episodes** and report the **average reward**.

#### Output Example:
```
Algorithm: PPO
Average Reward: 245.72

Algorithm: SAC
Average Reward: 267.12

Algorithm: A2C
Average Reward: 188.39

Best Performer: SAC
```

---

## 🔶 Part 3: Custom Reward Function – Smoother Walking

### Task:
- Use a `RewardWrapper` to penalize **sudden joint movement**.
- Retrain all 3 agents with this new reward.
- Compare new performance vs. the original.

#### Reward Equation:
$$
r_{\text{custom}} = r_{\text{orig}} - \lambda \cdot \sum_{i=1}^{N} \left| \Delta \theta_i \right|
$$

In code it should looks like:
```
r_custom = r_orig - λ * sum(abs(Δθ_i))
```

Where:
- `r_orig` = original reward
- `Δθ_i` = change in joint angle for joint `i`
- `λ` = penalty weight (e.g., 0.1)

#### Output Example:
```
Custom PPO Reward: 259.84
Custom SAC Reward: 278.40
Custom A2C Reward: 210.15
```

---

## ✅ Result Checklist:
- [ ] `.ipynb` or `.py` files with code
- [ ] Output logs/screenshots
- [ ] Graph/table comparisons
- [ ] Custom reward implementation
<!-- - [ ] Short summary report -->
