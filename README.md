# Reinforcement Learning Algorithms

## 1. Basic Value Iteration

### Introduction

Value Iteration is a **Dynamic Programming (DP)** method used to find the **optimal policy** in **Reinforcement Learning (RL)**. It helps determine the best action to take in each state by iteratively updating value estimates.

### How It Works

- It maintains **two tables**:
  1. **V (Value Table):** Initially, all values are set to `0`.
  2. **R (Reward Table):** Initially, all values are `-1`, except the goal state which has `+10`.
- Over multiple iterations, the **V table updates**, but the **R table remains the same**.
- The process follows **only one formula**: **Bellman's Equation**.

### Bellman's Equation

The value update follows:

\[
V(s) = \max_a \sum P(s'|s, a) [R(s, a, s') + \gamma V(s')]
\]

### Where:

- **\(V(s)\)** = Value of state **\(s\)**.
- **\(R(s, a, s')\)** = Immediate reward for taking action **\(a\)** in state **\(s\)**.
- **\(\gamma\)** = Discount factor (0 to 1), which determines future rewards' importance.
- **\(P(s'|s, a)\)** = Probability of moving to **\(s'\)** after taking action **\(a\)**.

### Initial Tables

#### **Value Table (V) – Initially**

| State | V(s) |
| ----- | ---- |
| S1    | 0    |
| S2    | 0    |
| S3    | 0    |
| Goal  | 0    |

#### **Reward Table (R) – Constant**

| State | R(s) |
| ----- | ---- |
| S1    | -1   |
| S2    | -1   |
| S3    | -1   |
| Goal  | +10  |

### Iterative Updates

- At each iteration, **V-table values change** based on the Bellman update.
- After convergence, the optimal **policy** is extracted by choosing actions that maximize future rewards.
