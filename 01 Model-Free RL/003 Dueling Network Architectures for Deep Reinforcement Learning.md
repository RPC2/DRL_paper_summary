# Dueling Network Architectures for Deep Reinforcement Learning

Authors: Ziyu Wang, Tom Schaul, Matteo Hessel, Hado van Hasselt, Marc Lanctot, Nando de Freitas

Year: 2015

Algorithm: Dueling DQN

- Problem

  - The focus of combining reinforcement learning with standard neural networks is primarily on designing improved control, or simply incorporating deep learning into reinforcement learning.

- Hypothesis

  - The proposed dueling network architecture is better-suited for model-free reinforcement learning, which can be easily combined with existing and future reinforcement learning algorithms.

- Methods

  - There are two estimators: one for estimating the state value function, and another for the state-dependent action advantage function. 

  - The dueling network can be understood as a standard CNN with changing the linear layer into two streams, then combining the two streams by a special aggregation layer.

  - The final output for both networks are both the estimations of the state-action value function Q.

    ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/pic/003_1.png)

  - Key insight:  At some moments in a game, whether the agent decides to move right or left doesn't impact the game score significantly. Therefore, some states require more critical attentions on actions, and in some states the agent can just be more relaxed. The dueling network with two streams can learn the value and advantage functions separately, and thus learn to tell the significance of each state, without having to learn the effect of each action for that state.

  - The resulting Dueling DQN can also take existing improvements of general DQN structures such as better replay memories, better exploration policies, etc.