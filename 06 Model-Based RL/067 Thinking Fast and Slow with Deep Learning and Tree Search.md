# Thinking Fast and Slow with Deep Learning and Tree Search

Authors: Thomas Anthony, Zheng Tian, David Barber

Year: 2017

Algorithm: Expert Iteration (ExIT)

- Introduction
  - Sequential decision making problems require a combination of planning policies and generalization of those plans.
  - Planning new policies: tree search
  - A deep neural network: generalization of plans — Like System 1, fast
  - Tree search will use the neural network policy as a guide — Like System 2, slow
- Method
  - Process
    - Use expert (MCTS) to calculate an imitation learning target at current state
    - Train the apprentice (DNN)
    - Use the new apprentice to update the expert
    - ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/067_1.png)
  - Intuition: The apprentice (DNN, fast system 1) can provide advice for selecting promising branches, and the expert (Tree search algorithm, slow system 2) is to perform exploration and accurately determine strong move sequences.

