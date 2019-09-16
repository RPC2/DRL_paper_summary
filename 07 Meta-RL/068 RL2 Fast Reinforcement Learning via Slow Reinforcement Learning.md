# 068 RL^2: Fast Reinforcement Learning via Slow Reinforcement Learning

Authors: Yan Duan, John Schulman, Xi Chen, Peter L. Bartlett, Ilya Sutskever, Pieter Abbeel

Algorithm: RL^2

Year: 2016

- Overview
  - The authors propose to represent an RL algorithm as an RNN, and train it using standard reinforcment learning algorithm. This formulation contains two parts: the fast part - the RNN, which learns to solve an MDP, and the slow part - the TRPO, which is used to update the parameters of the RNN.
- Method
  - ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/068_1.png)
  - "Fast": The RNN takes in the input on action, next state, reward, and termination flag, then outputs an action and generates the next hidden state.
  - "Slow": The RNN itself is updated through TRPO.



Confusion / Opinion: It is unclear to me on why the RNN part is an RL algorithm. How is it different from other RL algorithms learning policies in the form of an RNN?