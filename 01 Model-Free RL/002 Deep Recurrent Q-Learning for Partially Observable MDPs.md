# Deep Recurrent Q-Learning for Partially Observable MDPs

Authors: Matthew Hausknecht and Peter Stone

Year: 2015

Algorithm: Deep Recurrent Q-Learning

- Problems

  - The original DQN requires 4 frames to be observed, which implies that the states can only be partially observed for any games requiring more than 4 frames for the agent to understand the current states.
  - Many real-world tasks can only provide noisy and incomplete state information, thus they are only partially observable.

- Hypothesis

  - By combining Deep Q Network's structure and the recurrent neural network, the Deep Recurrent Q Network (DRQN) can better handle tasks that are partially observable, and perform better than standard DQN on fully observable tasks.

- Methods

  - Process the state image by three convolutional layers, and feed the outputs to the fully connected LSTM layer.

    ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/pic/002_1.png)

  - Stable recurrent updates

    - Bootstrapped sequential updates: Select episodes randomly from replay memory, and updates begin at the start of the episode, then proceed forward to the end of the episode.
    - Bootstrapped random updates: Select episodes randomly from replay memory, and updates begin at random points in the episode, then proceed for only unroll iterations timesteps.
    - Both types of updates are viable and yield convergent policies with similar performance.