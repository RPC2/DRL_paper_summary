# Playing Atari with Deep Reinforcement Learning

Authors: Volodymyr Minh, Koray Kavukcuoglu, David Silver, Alex Graves, Ioannis Antonoglou, Daan Wierstra, Martin Riedmiller

Year: 2013

Algorithm: DQN

- Problems
  - Unlike deep learning, reinforcement learning algorithms have reward signals that are frequently sparse, noisy, and delayed.
  - Deep learning assumes data samples to be independent, whereas in reinforcement learning, many states are highly correlated.
  - As the agent learns more behaviors, the distribution of data changes, which is challenging for deep learning models as they assume a fixed distribution.
- Hypothesis
  - A convolutional neural network with experience replay can break the correlations among samples, and thus fix the problems.
- Methods
  - Use Q-learning methods to learn the Q values of each state.
  - Instead of using a linear policy, use a neural network as the action-value function approximator.
  - Store the transitions of states, relevant actions, and reward signals in the replay memory.
  - Randomly sample a batch of replay memory to compute the loss function by comparing the output of policy network and target network, then perform stochastic gradient descent to adjust the parameters of the policy network.
  - This algorithm is model-free as it directly uses samples from the emulator without explicitly constructing a model of the emulator.
  - This algorithm is off-policy as it follows a greedy strategy (taking the argmax of predicted Q values).
- Algorithm

![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/pic/001_1.png)