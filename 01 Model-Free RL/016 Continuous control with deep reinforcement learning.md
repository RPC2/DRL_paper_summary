# Continuous control with deep reinforcement learning

Authors: Timothy P. Lillicrap, Jonathan J. Hunt, Alexander Pritzel, Nicolas Heess, Tom Erez, Yuval Tassa, David Silver & Daan Wierstra

Year: 2016

- Problems

  - DQN can only handle discrete and low-dimensional action spaces, and it cannot handle continuous actions effectively (It suffers from the curse of dimensionality: As the degree of freedom increases, the number of actions increases exponentially)

- Overview of the algorithm

  - Model-free
  - Off-policy
  - Actor-critic
  - Based on deterministic policy gradient

- Details of the algorithm

  - Use experience replay

  - When updating target network, use "soft update" instead of copying network weights —> The target values change slowly and thus stablize learning (but it also makes the learning slower)

  - Batch normalization: Normalizing each dimension across the samples in a minibatch to have unit mean and variance, which also maintains a running average of the mean and variance

  - Encourage the exploration by adding noise to the actor policy

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/016_1.png)

  - Pseudocode

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/016_2.png)