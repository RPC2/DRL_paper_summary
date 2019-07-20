# Hindsight Experience Replay

Authors: Marcin Andrychowicz, Filip Wolski, Alex Ray, Jonas Schneider, Rachel Fong, Peter Welinder, Bob McGrew, Josh Tobin, Pieter Abbeel, Wojciech Zaremba

Year: 2017

Algorithm: HER

- Problems to solve

  - Sparse reward in RL
  - Achieve sample efficiency

- Method

  - Overview: It can be used with any off-policy RL algorithm, and is applicable whenever there are multiple goals which can be achieved.
  - Pivotal idea: Replay each episode with a different goal than the one the agent was trying to achieve
  - Multi-goal RL: 
    - The policy and value function take as input the state s and the goal g.
  - After experiencing some transitions, the replay buffer is stored with transitions not only with the original goal but also a subset of other goals.

- Algorithm

  ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/050_1.png)