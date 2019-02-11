# Deep Reinforcement Learning with Double Q-learning

Authors: Hado van Hasselt, Authur Guez, David Silver

Year: 2015

Algorithm: Double DQN

- Problem

  - The standard Q-learning algorithm tends to overestimate action values under certain conditions. Such overestimations are common and harmful to performance, but can be prevented.

- Hypothesis

  - Double DQN can reduce the estimation errors

- Analysis

  - Oeroptimism due to estimation errors

    - Estimation errors of any kind can induce an upward bias, regardless of whether these errors are due to environmental noise, function approximation, non-stationarity, or any other source.
    - The lower bound on the absolute error of the Double Q-learning estimate is zero. (Proved in the paper)

  - Double Q-learning: reduce overestimations by decomposing the max operation in the target into action selection and action evaluation. This is done by replacing the target y in classical DQN into:

    ![004_1](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/004_1.png)

- Algorithm:

  ![004_2](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/004_2.png)

  (The above algorithm is from [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581), Wang et al, 2015.)