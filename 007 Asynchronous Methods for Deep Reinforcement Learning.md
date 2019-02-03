# Asynchronous Methods for Deep Reinforcement Learning

Authors: Volodymyr Mnih, Adria Puigdomenech Badia, Mehdi Mirza, Alex Graves, Tim Harley, Timothy P.Lilicrap, David Silver, Koray Kavukcuoglu

Year: 2016

Algorithm: A3C

- Problems

  - The simple combination of reinforcement learning and deep neural network can be unstable because the samples are highly correlated.
  - Experience replay algorithms can stablize this combination and decorrelate updates, but come with the cost of extra memory and computational resources.

- Hypothesis

  - Asynchronously execute multiple agents in parallel on multiple instances of the environment can fix the problems and improve training efficiency.

    - Since agents are in different states, the data collected are decorrelated. --> Avoid using experience replay --> Save memory and computational resources
    - It enables several fundamental on-policy RL algorithms.

    (This algorithm enables training on standard multi-core CPU --> Requires less time, less resources)

- Methods

  - Asynchronous RL Framework
    - Aim: Finding RL algorithms that can train the deep neural network without large resource requirements
    - High-level idea: Use asynchronous actor-learners, then observe them running in parallel. At each step it computes a gradient of the network loss, and update the target network every M steps with M as the update frequency.
    - Give each thread a different exploration policy
  - Algorithm:

  ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/pic/007_1.png)