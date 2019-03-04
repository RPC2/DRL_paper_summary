# Addressing Function Approximation Error in Actor-Critic Methods

Authors: Scott Fujimoto, Herke van Hoof, David Meger

Year: 2018

- Problems
  - Function estimation errors can often lead to overestimation of the state value and thus, suboptimal policies
- Overview of the solution
  - Builds on Double Q-learning: Take the minimum value between a pair of critics to limit overestimation
  - 