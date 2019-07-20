# Reinforcement Learning with Unsupervised Auxiliary Tasks

Authors: Max Jaderberg, Volodymyr Mnih, Wojciech Marian Czarnecki, Tom Schaul, Joel Z Leibo, David Silver, Koray Kavukcuoglu

Year: 2016

Algorithm: UNREAL

- Hypothesis
  - An agent that can flexibly control its future experiences will also be able to achieve any goal with which it is presented, such as maximizing its future rewards.
- Method
  - Overview: The architecture uses reinforcement learning to approximate both the optimal policy and optimal value function for many different pseudo-rewards. Experience replay is used to provide additional updates to the critics.
  - 