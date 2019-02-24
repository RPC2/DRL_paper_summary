# Emergence of Locomotion Behaviors in Rich Environments

Authors: Nicolas Heess, Dhruva TB, Srinivasan Sriram, Jay Lemmon, Josh Merel, Greg Wayne, Yuval Tassa, Tom Erez, Ziyu Wang, S.M. Ali Eslami, Martin Riedmiller, David Silver

Year: 2017

- Problem
  - In standard reinforcement learning algorithms, the reward function is usually well-defined but not specific to the tasks.
  - In complex environments, the "right" reward function is less clear, and a general reward function can lead to surprising behaviors of the agents, which doesn't match the expectations. --> It has become a standard practice to carefully design the reward function

- Solution

  - Background: Proximal Policy Optimization algorithm

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/011_1.png)

  - Distributed PPO

    - Difference from original PPO:

      Use K-step returns for estimating the advantage, then use truncated backpropagation through time with a window of length K.

      K-step returns:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/011_2.png)

    - Algorithm:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/011_3.png)

