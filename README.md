# Q-learning-sparse-interaction-and-the-multi-robot-environment
This repository contains the implementation of Regular Q-learning and the Sparse Interaction Algorithm across three distinct environments: Basic Environment, Extended Environment, and Four-Robot Environment. The project focuses on the coordination and movement of multiple robots within gridworld scenarios, where agents must navigate to goal locations while avoiding penalties for miscoordination. The environments are implemented following the PettingZoo API.

The implementation is based on the paper "[Learning of Coordination: Exploiting Sparse Interactions in Multiagent Systems](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=d970c6af606fea64bcb8a8e2a449d06e5fcc9ad6)" by Melo & Veloso (AAMAS, 2009). The approach seeks to create agents that learn the situations in which they need to coordinate and in which they don’t, by exploiting local interactions. Each agent learns from experience which situations require coordination in a setting of partial observability.


