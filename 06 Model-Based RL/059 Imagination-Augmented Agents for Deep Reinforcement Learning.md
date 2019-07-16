# Imagination-Augmented Agents for Deep Reinforcement Learning

Authors: Théophane Weber, Sébastien Racanière, David P. Reichert, Lars Buesing, Arthur Guez, Danilo Jimenez Rezende, Adria Puigdomènech Badia, Oriol Vinyals, Nicolas Heess, Yujia Li, Razvan Pascanu, Peter Battaglia, Demis Hassabis, David Silver, Daan Wierstra

Year: 2017

Algorithm: I2A

- Problems to solve

  - Model-free RL usually requires large amounts of training data and the resulting policies do not generalize to novel tasks in the same environment. Its performance also suffers from model errors resulting from function approximation.
  - Model-based RL aims to address above shortcomings with a model of the world, synthesized from past experience.

- I2A Architecture

  - Overview: I2A can be seen as a model-free agent augmented by model-based planning's additional information about the environment.

  - Environment models: Given information from the present, it can be quiried to make predictions about the future.

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/059_1.png)

  - Rollout encoder: Process the imagined rollout as a whole and learns to interpret it.

  - Policy module: A network that takes the information from both model-based predictions and model-free path, and outputs the imagination-augmented vector and estimated value.

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/059_2.png)

- Architectural choices

  - Rollout strategy: Distilling the imagination-augmented policy into a model-free policy.
  - I2A components and environment models
    - Encoder: An LSTM with convolutional encoder, sequentially processes a trajectory.
    - Aggregator: concatenates the summaries.