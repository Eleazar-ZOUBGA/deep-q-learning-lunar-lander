# 🚀 Deep Q-Learning – Lunar Lander

Final graded assignment from the **Reinforcement Learning** course (Course 3, Week 3) of the [Machine Learning Specialization](https://www.coursera.org/specializations/machine-learning-introduction) by Andrew Ng on Coursera.

---

## 📌 Project Overview

This project implements a **Deep Q-Learning (DQN)** agent trained to safely land a spacecraft on the surface of the moon using OpenAI Gym's `LunarLander-v2` environment.

The agent learns through trial and error to control the lander's engines and achieve a smooth landing on the designated pad — earning a score of 200+ points when successful.

---

## 🧠 Key Concepts

- **Deep Q-Network (DQN):** A neural network that approximates the optimal action-value function Q*(s, a), allowing the agent to handle continuous state spaces.
- **Target Network:** A separate, periodically updated copy of the Q-Network used to generate stable training targets and reduce oscillations during learning.
- **Experience Replay:** A memory buffer that stores past transitions `(state, action, reward, next_state)` and samples random mini-batches for training, breaking temporal correlations in the data.
- **Soft Update:** The target network weights are updated gradually using the rule `w⁻ ← τw + (1 − τ)w⁻`, ensuring slow and stable target value changes.

---

## 🌍 Environment: LunarLander-v2

| Property | Details |
|---|---|
| **State Space** | 8 continuous variables (position, velocity, angle, contact legs) |
| **Action Space** | 4 discrete actions (do nothing, fire left/main/right engine) |
| **Goal** | Land safely on the pad and score ≥ 200 points |
| **Termination** | Crash, out-of-bounds, or safe landing |

---

## 🏗️ Architecture & Hyperparameters

The Q-Network is a fully connected neural network built with TensorFlow/Keras:

| Hyperparameter | Value |
|---|---|
| Memory buffer size | 100,000 |
| Discount factor (γ) | 0.995 |
| Learning rate (α) | 1e-3 |
| Target update frequency (C) | 4 steps |
| Optimizer | Adam |
| Loss | Mean Squared Error (MSE) |

---

## 🛠️ Tech Stack

- Python
- TensorFlow / Keras
- OpenAI Gym (`LunarLander-v2`)
- NumPy

---

## 📂 Structure

```
deep-q-learning-lunar-lander/
│
├── C3_W3_A1_Assignment.ipynb   # Main notebook with implementation
├── utils.py                    # Helper functions
└── README.md
```

---

## 📈 Results

The agent successfully learns to land the lunar lander after sufficient training episodes, consistently achieving scores above the 200-point threshold that defines a solved environment.

---

## 📚 References

- [Mnih et al., 2015 – Human-level control through deep reinforcement learning](https://www.nature.com/articles/nature14236)
- [OpenAI Gym – LunarLander-v2 documentation](https://www.gymlibrary.dev/environments/box2d/lunar_lander/)
- [Machine Learning Specialization – Coursera](https://www.coursera.org/specializations/machine-learning-introduction)
