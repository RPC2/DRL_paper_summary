# Neural Network Dynamics for Model-Based Deep Reinforcement Learning with Model-Free Fine-Tuning

Authors: Anusha Nagabandi, Gregory Kahn, Ronald S. Fearing, Sergey Levine

Year: 2017

Algorithm: MBMF

- Problems

  - Model-free deep reinforcement learning algorithms usually have very low sample efficiency. 
  - Model-based algorithms are more efficient but difficult to extend to deep neural networks.
  - Model-based algorithms are prone to have worse asymtotic performance due to model bias.

- Methods

  - Learned dynamics function

    - The function: a deep neural network which takes as input the current state and action. It predicts the change in state s_t over a period of time.

    - The predicted next state:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/060_1.png)

  - How to train the learned dynamics function

    - Collect training data: Execute actions and record resulting trajectories

    - Data preprocessing: Slice the trajectories into training data inputs (s_t, a_t) and output labels s_{t+1} - s_t. Normalize the observations. Apply noise.

    - Training the model: Minimizing the error

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/060_2.png)

    - For H-step validation:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/060_3.png)

  - Extracting a policy with the learned dynamics function

    - Optimize the sequence of actions A_t over a finite horizon H:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/060_4.png)

  - Use (model-free) reinforcement learning to further improve the learned dynamics function

    - Overview: (1) Train a policy to mimic the model-based controller. (2) Use the imitation policy as the initialization for a model-free RL agent.

- Algorithm

  ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/060_5.png)

  ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/060_6.png)