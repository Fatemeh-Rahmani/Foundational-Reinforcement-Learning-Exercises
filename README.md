##  Core Concepts  

This set of exercises covers the following key topics:

  * **Multi-Armed Bandits:** Exploration vs. Exploitation, Epsilon-Greedy Strategy.
  * **Markov Decision Processes (MDPs):** Defining states, actions, rewards, and transitions.
  * **Dynamic Programming (DP):**
      * Policy Evaluation (Bellman Expectation Equation)
      * Value Iteration (Bellman Optimality Equation)
  * **Model-Free Prediction:**
      * Monte Carlo (MC) Prediction
      * Temporal-Difference (TD) Learning (TD(0))
      * Bootstrapping
  * **Model-Free Control:**
      * **SARSA** (On-Policy TD Control)
      * **Q-Learning** (Off-Policy TD Control)
  * **Environment Design:** Building custom environments (GridWorld, Windy Gridworld, etc.).

-----

##  Exercises Overview

Here is a breakdown of each exercise notebook. A good order for a course would be to follow them as listed below.

### 1\. 10-Armed Bandit

  * **File:** `10-armed-bandit.ipynb`
  * **Summary:** A great starting point. This notebook introduces the exploration/exploitation trade-off by implementing and comparing several epsilon-greedy agents (ε=0, ε=0.01, ε=0.1) on the 10-Armed Bandit problem.
  * **Key Concepts:** Multi-Armed Bandits, Sample-Average Method, Epsilon-Greedy, Action-Value Estimates (Q-values).
  * **Visualizations:**
      * Average reward over time, showing how exploration leads to higher long-term rewards.
      * Percentage of optimal actions taken, demonstrating the effectiveness of different exploration strategies.

### 2\. Battery Agent (MDP Value Iteration)

  * **File:** `Battery-Agent.ipynb`
  * **Summary:** This notebook provides a simple, two-state (High Charge, Low Charge) introduction to Markov Decision Processes (MDPs). It uses **Value Iteration** to find the optimal state values (V\*) and extract the optimal policy (π\*).
  * **Key Concepts:** MDPs, Value Iteration, Bellman Optimality Equation, State Values (V\*), Optimal Policy (π\*).
  * **Visualizations:** Prints the final converged state values and the resulting optimal policy (e.g., "Search" at High Charge, "Wait" at Low Charge).

### 3\. Gambler's Problem

  * **File:** `gamblers-problem.ipynb`
  * **Summary:** A larger and more complex 1D MDP (100 states) solved with **Value Iteration**. The agent (gambler) must learn the optimal amount to bet (policy) to reach a goal of $100, given a probability of winning each flip.
  * **Key Concepts:** Dynamic Programming, Value Iteration, Bellman Optimality.
  * **Visualizations:**
      * Convergence of the Value Function over iterations.
      * The final optimal policy (stake amount vs. current capital).

### 4\. GridWorld (Policy Evaluation & Value Iteration)

  * **File:** `GridWorld.ipynb`
  * **Summary:** This notebook provides a fantastic side-by-side comparison of two core Dynamic Programming methods on a 5x5 grid. It simultaneously calculates:
    1.  The value function for a **uniform random policy** (Policy Evaluation).
    2.  The **optimal value function** (Value Iteration).
  * **Key Concepts:** Dynamic Programming, Policy Evaluation, Value Iteration, Bellman Expectation vs. Optimality, GridWorlds.
  * **Visualizations:** Heatmaps of the final value functions for both the random policy ($V_\pi$) and the optimal policy ($V^*$), allowing for easy comparison.

### 5\. GridWorld (Policy Evaluation Convergence)

  * **File:** `GridWorld-Policy-Evaluation.ipynb`
  * **Summary:** This notebook is a more focused look at **Policy Evaluation**. It iteratively applies the Bellman expectation equation to a 4x4 grid and visualizes how the value function converges to the true value for a random policy over multiple sweeps.
  * **Key Concepts:** Dynamic Programming, Policy Evaluation, Bellman Expectation Equation.
  * **Visualizations:** A series of heatmaps showing the value function at k=0, 1, 2, 3, 10, and 100 iterations.

### 6\. Random Walk (TD vs. MC)

  * **File:** `Random_Walk.ipynb`
  * **Summary:** This notebook is the first step into Model-Free learning. It implements and compares **Temporal-Difference (TD(0))** and **Monte Carlo (MC)** prediction on a simple 1D Random Walk environment.
  * **Key Concepts:** Model-Free Prediction, TD Learning, MC Prediction, Bootstrapping, RMSE.
  * **Visualizations:**
      * Convergence of TD(0)'s value estimates over 1, 10, and 100 episodes.
      * Root-Mean-Squared Error (RMSE) comparison, clearly showing that TD converges faster than MC on this task.

### 7\. Cliff Walking (Q-Learning vs. SARSA)

  * **File:** `Cliff-Walking.ipynb`
  * **Summary:** This is a classic control problem for comparing on-policy vs. off-policy TD learning. The agent must find a path from a start to a goal while avoiding a "cliff" that gives a large negative reward. It implements both **Q-Learning** (off-policy) and **SARSA** (on-policy).
  * **Key Concepts:** Model-Free Control, Q-Learning (Off-policy), SARSA (On-policy), Epsilon-Greedy Policy.
  * **Visualizations:**
      * Learning curves (cumulative reward per episode) comparing the performance of Q-Learning vs. SARSA.
      * The final learned policy grid for both algorithms, illustrating the "safe" path of SARSA vs. the "optimal" (but risky) path of Q-Learning.

### 8\. Windy Gridworld (SARSA)

  * **File:** `Windy-Gridworld-SARSA.ipynb`
  * **Summary:** A more advanced control problem. This notebook implements **SARSA** in a custom GridWorld where a "wind" in certain columns pushes the agent off course. It also includes parameters to test variations like King's Moves (diagonal) and stochastic wind.
  * **Key Concepts:** SARSA (On-Policy Control), Stochastic Environments, Action-Value Function (Q-values).
  * **Visualizations:**
      * Learning curve (episodes vs. time steps).
      * Heatmap of the final optimal value function (V\*).
      * Grid-based plot of the final learned policy (arrows).
