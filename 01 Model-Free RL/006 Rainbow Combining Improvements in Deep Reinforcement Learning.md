# Rainbow: Combining Improvements in Deep Reinforcement Learning

Authors: Mateo Hessel, Joseph Modayil, Hado van Hasselt, Tom Schaul, Georg Ostrovski, Will Dabney, Dan Horgan, Bilal Piot, Mohammad Azar, David Silver

Year: 2017

Algorithm: Rainbow DQN

- Problems

  - There are several independent improvements to the DQN algorithm. But it's unclear whether these improvements can be fruitfully combined.

- Hypothesis

  - Combining six extensions to the DQN algorithm can provide the state-of-the-art performance with improved data efficiency.
  - The chosen six extensions: DDQN, Prioritized DDQN, Dueling DDQN(with prioritized experience replay), A3C, Distributional DQN, Noisy DQN

- Methods

  - Replay the 1-step distributional loss with a multi-step variant. The resulting loss is 

    ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/pic/006_1.png)

  - Combine this multi-step distributional loss with double Q-learning

  - Instead of using TD error in prioritized experience replay, prioritize the transitions by the KL loss

  - Network architecture: dueling network

    - The network has an action stream and an advantage stream after sharing some common layers

    - The values and advantages are aggregated, then passed through a softmax layer to obtain the normalized parametric distributions:

      ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/pic/006_2.png)

  - Replace all linear layers with their noisy equivalence:

    ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/pic/006_3.png)