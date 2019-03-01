# Deterministic Policy Gradient Algorithms

Authors: David Silver, Guy Lever, Nicolas Heess, Thomas Degris, Daan Wierstra, Martin Riedmiller

Year: 2014

- Background

  - It was believed that the deterministic policy gradient did not exist

- Intention of this paper

  - Show that the deterministic policy gradient does exist
  - Show that this algorithm has a simple model-free form that follows the gradient of the action-value function

- Explanation of the algorithm

  - Crucial difference between the stochastic and deterministic policy gradients:

    - Sthochastic: the policy gradient integrates over both state and action spaces
    - Deterministic: the policy gradient only integrates over the state space

  - Basic idea

    - Choose actions according to a stochastic behavior policy
    - Learn a deterministic target policy

  - Action-value gradients

    - The policy improvement with a neural network can be decomposed into the gradient of the action-value with respect to actions, and the gradient of the policy with respect to the policy parameters:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_1.png)

  - Deterministic policy gradient theorem

    - The performance objective can be written as an expectation:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_2.png)

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_3.png)

  - Limit of the stochastic policy gradient

    As the variance parameter sigma gets close to zero, the stochastic policy gradient converges to the deterministic gradient.

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_4.png)

  - On-policy Deterministic Actor-Critic

    - Using the Sarsa update to estimate the action-value function:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_5.png)

  - Off-policy Deterministic Actor-Critic

    - Modify the performance objective to be the value function (which is the expected value over target policy and the state distribution of the behavior policy)

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_6.png)

    - The off-policy deterministic policy gradient:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_7.png)

    - Off-policy deterministic algorithm: the critic uses Q-learning updates to estimate the action-value function

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_8.png)

  - Compatible function approximation

    - The following theorem applies to both on-policy and off-policy algorithms:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_9.png)

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_10.png)

    - The Compatible Off-Policy Deterministic Actor-Critic (COPDAC) algorithm with a simple Q-learning critic:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/015_11.png)