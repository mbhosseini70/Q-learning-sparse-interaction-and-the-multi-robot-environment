# Multi-Agent Reinforcement Learning: Implementing and Evaluating Q-Learning and Sparse Interaction Algorithms
This repository contains the implementation of Regular Q-learning and the Sparse Interaction Algorithm across three distinct environments: Basic Environment, Extended Environment, and Four-Robot Environment. The project focuses on the coordination and movement of multiple robots within gridworld scenarios, where agents must navigate to goal locations while avoiding penalties for miscoordination. The environments are implemented following the PettingZoo API.

The implementation is based on the paper "[Learning of Coordination: Exploiting Sparse Interactions in Multiagent Systems](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=d970c6af606fea64bcb8a8e2a449d06e5fcc9ad6)" by Melo & Veloso (AAMAS, 2009). The approach seeks to create agents that learn the situations in which they need to coordinate and in which they don’t, by exploiting local interactions. Each agent learns from experience which situations require coordination in a setting of partial observability.


## A Guide for Navigating the Code File

### Environment Setup (Cells 1-2)

#### 1st Cell: Import Required Libraries
This section covers the import of necessary libraries.

#### 2nd Cell: Environment Setup and Its Visualization
This section contains the Environment Class definition, initialization of various environment types, and code for visualizing the environment states.

### Regular Q-Learning Implementation (Cells 3-9)

#### 3rd Cell: Regular Q-Learning Implementation
This part includes the QLearningAgent Class, function for running the algorithm, function for evaluating the algorithm, the main execution block, and the plotting function.

#### 4th Cell: The Execution of Regular Q-Learning on Basic Environment
This part includes the main execution block that runs the learning process in the basic environments.

#### 5th Cell: The Visualization of Regular Q-Learning on Basic Environment
This part includes the visualization of the results for the basic environments.

#### 6th Cell: The Execution of Regular Q-Learning on Extended Environment
This part includes the main execution block that runs the learning process in the extended environments.

#### 7th Cell: The Visualization of Regular Q-Learning on Extended Environment
This part includes the visualization of the results for the extended environments.

#### 8th Cell: The Execution of Regular Q-Learning on Four_Robot Environment
This part includes the main execution block that runs the learning process in the Four_Robot environments.

#### 9th Cell: The Visualization of Regular Q-Learning on Four_Robot Environment
This part includes the visualization of the results for the Four_Robot environments.

### Sparse Interaction Algorithm Implementation (Cells 10-18)

#### 10th Cell: Environment Setup for Sparse Interaction Algorithm
This part sets up the environment for the Sparse Interaction Algorithm.

#### 11th Cell: Sparse Interaction Algorithm Implementation
This section features a class that implements the Sparse Interaction Algorithm. It also includes a demonstration consisting of two episodes, showcasing the agents' decision-making process in the environment. Note that this process is the first step of training; the actions taken are predominantly random.

#### 12th Cell: Functions to Run sparse interaction algorithm
This part includes function for running the algorithm in each episode, function for evaluating the algorithm, the main execution block, and the plotting function.

#### 13th Cell: The Execution of Sparse Interaction Algorithm on Basic Environment
This part includes the main execution block that runs the learning process in the basic environments.

#### 14th Cell: The Visualization of Sparse Interaction Algorithm on Basic Environment
This part includes the visualization of the results for the basic environments.

#### 15th Cell: The Execution of Sparse Interaction Algorithm on Extended Environment
This part includes the main execution block that runs the learning process in the extended environments.

#### 16th Cell: The Visualization of Sparse Interaction Algorithm on Extended Environment
This part includes the visualization of the results for the extended environments.

#### 17th Cell: The Execution of Sparse Interaction Algorithm on Four_Robot Environment
This part includes the main execution block that runs the learning process in the Four_Robot environments.

#### 18th Cell: The Visualization of Sparse Interaction Algorithm on Four_Robot Environment
This part includes the visualization of the results for the Four_Robot environments.


## Project Deatil

### Environments

Designing and implementing environments play an important role in our project. We follow the PettingZoo API, a multi-agent extension of the Gymnasium API, to simulate different environments for reinforcement learning. Our environments are of a parallel nature, utilizing the `ParallelEnv` class.

#### Key Components
1. **Initialization (`__init__`):** The constructor initializes an instance of the `Environments` class.
2. **Environment Initialization (`init_environment`):** Specifies the type of environment (`basic`, `extended`, or `four_robot`) and calls the respective initialization functions.
3. **Common Environment Initialization (`init_common_environment`):** Defines attributes shared by all environments, such as penalties, agent positions, and coordination actions.
4. **Movement (`direction_offsets`):** Converts action indices into directional movements within a grid.
5. **Reset (`reset`):** Resets the environment to its initial state.
6. **Step (`step`):** Processes actions for all agents, updates the environment state, and checks for miscoordination.
7. **Update Rewards and Dones (`update_rewards_and_dones`):** Updates rewards and done status based on agent positions and actions.
8. **Miscoordination Check (`is_miscoordination`):** Checks for miscoordination among agents.
9. **Apply Action (`apply_action`):** Applies an action with a certain success rate.
10. **Goal (`goal`):** Returns the goal position for each agent.
11. **Observe (`observe`):** Converts the grid environment to an array.
12. **Render (`render`):** Renders a visual representation of the environment.

### Initial State of Each Environment

#### Basic Environment
- **Render Output:** A grid.
- **Observe Output:** An array from the perspective of different agents, with specific values for the agent, other agents, goals, and doorways.

#### Extended Environment
- Similar structure with more complex features.

#### Four-Robot Environment
- Initial positions of each agent are the goals of other agents. Prioritizes showing agent names over goals.

### Algorithms

#### Regular Q-learning

**Class: `QLearningAgent`**
1. **Initialization (`__init__`):** Sets up parameters like the number of states, actions, learning rate, discount factor, exploration rate, minimum exploration rate, and epsilon decay.
2. **Select Action (`select_action`):** Decides whether to explore or exploit based on epsilon value.
3. **Update Q-Table (`update_q_table`):** Updates Q-values using Temporal Difference learning.
4. **Decay Epsilon (`decay_epsilon`):** Decays the epsilon value after each episode.
5. **Reset Epsilon (`reset_epsilon`):** Resets epsilon to one at the end of each run.

**Running the Environment**
1. **Run Episode (`run_episode`):** Runs an episode, updating Q-tables and tracking metrics.
2. **Evaluate Agent (`evaluate_agent`):** Evaluates an agent's performance over multiple episodes.
3. **Run Simulation (`run_simulation`):** Simulates multiple runs of training and evaluation episodes.
4. **Plot Results (`plot_training_evaluation_results`):** Plots training and evaluation results.

#### Sparse Interaction Algorithm

**Class: `SparseInteractionLearningAgent`**
1. **Initialization and Methods:** Similar structure with additional methods for sparse interaction.
2. **Active Perception (`active_perception`):** Acts like a camera to detect nearby agents.
3. **Update Rewards and Dones (`update_rewards_and_dones`):** Penalizes agents based on coordination actions.
4. **Apply Action (`apply_action`):** Updates the agent's position based on the action.

**Running the Environment**
1. **Run Episode (`run_episode2`):** Similar to `run_episode` with additional logic for sparse interaction.
2. **Evaluate Agent (`evaluate_agent2`):** Similar to `evaluate_agent` with additional logic for sparse interaction.
3. **Run Simulation (`run_simulation2`):** Similar to `run_simulation` with additional logic for sparse interaction.
4. **Plot Results (`plot_training_evaluation_results`):** Similar to `plot_training_evaluation_results`.

### Discussion

#### Q-Learning Results
- **Basic Environment:** Agents initially exhibit random behavior but learn to reduce miscoordination and achieve goals over time, increasing rewards and efficiency.
- **Extended and Four-Robot Environments:** More complex, but similar learning patterns observed.

#### Comparison with Sparse Interaction Algorithm
- **Convergence:** Sparse Interaction Algorithm converges slower but yields better results, reducing miscoordination to zero and increasing rewards by learning efficient cooperation strategies.
