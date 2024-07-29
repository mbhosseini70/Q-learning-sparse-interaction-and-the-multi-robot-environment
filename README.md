# Q-learning-sparse-interaction-and-the-multi-robot-environment
This repository contains the implementation of Regular Q-learning and the Sparse Interaction Algorithm across three distinct environments: Basic Environment, Extended Environment, and Four-Robot Environment. The project focuses on the coordination and movement of multiple robots within gridworld scenarios, where agents must navigate to goal locations while avoiding penalties for miscoordination. The environments are implemented following the PettingZoo API.

The implementation is based on the paper "[Learning of Coordination: Exploiting Sparse Interactions in Multiagent Systems](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=d970c6af606fea64bcb8a8e2a449d06e5fcc9ad6)" by Melo & Veloso (AAMAS, 2009). The approach seeks to create agents that learn the situations in which they need to coordinate and in which they don’t, by exploiting local interactions. Each agent learns from experience which situations require coordination in a setting of partial observability.


# A Guide for Navigating the Code File

## Environment Setup (Cells 1-2)

### 1st Cell: Import Required Libraries
This section covers the import of necessary libraries.

### 2nd Cell: Environment Setup and Its Visualization
This section contains the Environment Class definition, initialization of various environment types, and code for visualizing the environment states.

## Regular Q-Learning Implementation (Cells 3-9)

### 3rd Cell: Regular Q-Learning Implementation
This part includes the QLearningAgent Class, function for running the algorithm, function for evaluating the algorithm, the main execution block, and the plotting function.

### 4th Cell: The Execution of Regular Q-Learning on Basic Environment
This part includes the main execution block that runs the learning process in the basic environments.

### 5th Cell: The Visualization of Regular Q-Learning on Basic Environment
This part includes the visualization of the results for the basic environments.

### 6th Cell: The Execution of Regular Q-Learning on Extended Environment
This part includes the main execution block that runs the learning process in the extended environments.

### 7th Cell: The Visualization of Regular Q-Learning on Extended Environment
This part includes the visualization of the results for the extended environments.

### 8th Cell: The Execution of Regular Q-Learning on Four_Robot Environment
This part includes the main execution block that runs the learning process in the Four_Robot environments.

### 9th Cell: The Visualization of Regular Q-Learning on Four_Robot Environment
This part includes the visualization of the results for the Four_Robot environments.

## Sparse Interaction Algorithm Implementation (Cells 10-18)

### 10th Cell: Environment Setup for Sparse Interaction Algorithm
This part sets up the environment for the Sparse Interaction Algorithm.

### 11th Cell: Sparse Interaction Algorithm Implementation
This section features a class that implements the Sparse Interaction Algorithm. It also includes a demonstration consisting of two episodes, showcasing the agents' decision-making process in the environment. Note that this process is the first step of training; the actions taken are predominantly random.

### 12th Cell: Functions to Run sparse interaction algorithm
This part includes function for running the algorithm in each episode, function for evaluating the algorithm, the main execution block, and the plotting function.

### 13th Cell: The Execution of Sparse Interaction Algorithm on Basic Environment
This part includes the main execution block that runs the learning process in the basic environments.

### 14th Cell: The Visualization of Sparse Interaction Algorithm on Basic Environment
This part includes the visualization of the results for the basic environments.

### 15th Cell: The Execution of Sparse Interaction Algorithm on Extended Environment
This part includes the main execution block that runs the learning process in the extended environments.

### 16th Cell: The Visualization of Sparse Interaction Algorithm on Extended Environment
This part includes the visualization of the results for the extended environments.

### 17th Cell: The Execution of Sparse Interaction Algorithm on Four_Robot Environment
This part includes the main execution block that runs the learning process in the Four_Robot environments.

### 18th Cell: The Visualization of Sparse Interaction Algorithm on Four_Robot Environment
This part includes the visualization of the results for the Four_Robot environments.



