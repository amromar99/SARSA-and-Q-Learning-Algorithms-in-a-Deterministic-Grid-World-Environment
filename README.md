# Comparison of SARSA and Q-Learning Algorithms in a Deterministic Grid World Environment

## Introduction
This report delves into the comparative analysis of Q-learning and SARSA algorithms within a deterministic grid world environment. The adjustments made to both implementations were motivated by a curiosity to explore how each algorithm approaches and solves identical tasks, aiming to uncover their distinct methods in reinforcement learning. Visualizations depicting the agent's trajectory from its starting point to the goal provide insights into their decision-making processes and adaptive strategies.

The environment consists of a 9x10 grid featuring predefined start and goal positions, alongside various blocked cells. The agent's objective is to navigate from the start to the goal while maneuvering around blocked cells to minimize steps and maximize average rewards.

![image](https://github.com/user-attachments/assets/e5f5ed7a-6894-4500-bdcb-24825805579a)
 
## Algorithms

### SARSA Algorithm (State-Action-Reward-State-Action)
SARSA is an "on-policy" reinforcement learning method where the agent updates its knowledge based on the actions taken according to its current policy. It starts by initializing Q-values and updates these values as the agent explores the environment. At each step, the agent observes its current state, selects an action, receives a reward, observes the next state, and updates the Q-value using these observations.

### Q-learning Algorithm
Q-learning is an "off-policy" reinforcement learning method that learns the value of the optimal policy independently of the agent's actions. It updates Q-values based on the highest Q-value of the following state, regardless of the current policy. This approach allows Q-learning to converge faster to the optimal policy by consistently considering the potential for the highest future rewards.

## Evaluation Criteria
To compare the performance and efficiency of SARSA and Q-learning, we use the following metrics:
- **Learning Time:** Duration taken by the algorithm to converge to an optimal policy.
- **Steps:** Total number of steps taken by the agent to reach the goal.
- **Average Reward:** Mean reward accumulated by the agent over multiple episodes.

## Results and Discussion

### Deterministic Environment (Noise = 0)

#### Alpha = 0.1

- **Epsilon = 0.2**
  - **SARSA:** Converged in 0.06 seconds, took 14 steps, average reward of 9.605.
  - **Q-learning:** Converged in 0.03 seconds, took 8 steps, average reward of 7.09.

- **Epsilon = 0.6**
  - **SARSA:** Converged in 0.10 seconds, took 14 steps, average reward of 9.05.
  - **Q-learning:** Converged in 0.06 seconds, took 8 steps, average reward of 8.3.

- **Epsilon = 1**
  - **SARSA:** Converged in 0.08 seconds, took 14 steps, average reward of 4.48.
  - **Q-learning:** Converged in 0.05 seconds, took 8 steps, average reward of 4.685.

  *Comparison with Epsilon = 0.2, 0.6, and 1 for Alpha = 0.1:* Higher epsilon values resulted in quicker learning but lower average rewards. SARSA performed best with Epsilon = 0.2, while Q-learning achieved the highest reward with Epsilon = 0.3.

#### Alpha = 0.3

- **Epsilon = 0.2**
  - **SARSA:** Converged in 0.06 seconds, took 14 steps, average reward of 9.51.
  - **Q-learning:** Converged in 0.03 seconds, took 8 steps, average reward of 6.395.

- **Epsilon = 0.6**
  - **SARSA:** Converged in 0.05 seconds, took 14 steps, average reward of 8.84.
  - **Q-learning:** Converged in 0.03 seconds, took 8 steps, average reward of 8.27.

- **Epsilon = 1**
  - **SARSA:** Converged in 0.07 seconds, took 14 steps, average reward of 2.82.
  - **Q-learning:** Converged in 0.04 seconds, took 8 steps, average reward of 3.52.

  *Comparison with Epsilon = 0.2, 0.6, and 1 for Alpha = 0.3:* Both algorithms with higher epsilon values exhibited slower learning times and lower average rewards. SARSA performed optimally with Epsilon = 0.2, while Q-learning excelled with Epsilon = 0.4.

## Conclusion
This report thoroughly examined SARSA and Q-learning algorithms in a deterministic grid world setting. SARSA demonstrated robust efficiency with Epsilon = 0.2, achieving quick convergence and a high average reward of 9.605. In contrast, Q-learning performed well with Epsilon = 0.4, converging swiftly in 0.03 seconds with 8 steps and an average reward of 7.09. Higher epsilon values expedited learning but resulted in lower rewards due to increased exploration risks. SARSA with Epsilon = 0.2 is optimal for exploitation, while Q-learning benefits from Epsilon around 0.4 for a balanced exploration-exploitation trade-off.

![image](https://github.com/user-attachments/assets/27ae805f-ed2c-4d66-8c0d-9e915591614b)


## How to Run the Code
1. Clone the repository.
2. Install the necessary dependencies using `pip install -r requirements.txt`.
3. Run the SARSA algorithm using `python sarsa_grid_world.py`.
4. Run the Q-learning algorithm using `python q_learning_grid_world.py`.
5. Analyze the results through the output logs and visualizations.

## Authors
- **Eng/Amr Mostafa Ibrahim** TA @ ITCS , Nile University , Cairo , Egypt

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
