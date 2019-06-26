# 070 Model-Agnostic Meta-Learning for Fast Adaptation of Deep Networks

Authors: Chelsea Finn, Pieter Abbeel, Sergey Levine

Algorithm: MAML

Year: 2017

- Goals of the algorithm

  - Meta-Learning: To learn and adapt quickly from only a few examples, and produce good generalization performance on the task.

- Key summary of the method

  - Train the model's initial parameters such that the model has maximal performance on a new task, where the parameters will be updated through some gradient descent steps with a small amount of data of the new task.
  - The algorithm can be applied on different model types, including fully connected CNN, and several distinct domains, including few-shot regression, image classification, and reinforcement learning.

- Algorithm

  - Intuition: MAML provides a good initialization of a model's parameters to be adapted to a specific task. This is done by: (1) Adjusting the gradients towards different tasks one or more (but relatively few) times, then (2) Use the accumulated gradients across different tasks obtained in this iteration to perform the meta-gradient update.

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/070_1.png)

  - Algorithm

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/070_2.png)