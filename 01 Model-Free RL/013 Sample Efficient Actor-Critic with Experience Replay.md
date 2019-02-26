# Sample Efficient Actor-Critic with Experience Replay

Authors: Ziyu Wang, Victor Bapst, Nicolas Heess, Volodymyr Mnih, Remi Munos, Koray Kavukcuoglu, Nando de Freitas

Year: 2017

- Problems

  - Deep Q learning's limitations:
    1. The deterministic nature of the optimal policy limits its use in adversarial domains
    2. Finding the greedy action with respect to the Q function is costly for large action spaces

  - Policy gradient methods, including A3C,  are sample inefficient

- Aim of the paper

  - Address the sample inefficiency problem for deep RL
    - By introducing an actor critic with experience replay (ACER)
  - Introduce its innovations:
    - Truncated importance sampling with bias correction
    - Stochastic dueling network architectures
    - efficient trust region policy optimization

- Methods

  - Multi-step estimation of the state-action value function

    - The Retrace estimator: (From the Retrace algorithm proposed by Munos et al., 2016)

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/013_1.png)

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/013_2.png)

    - To compute the estimate Q, use a convolutional neural network with two output streams that outputs the estimate Q(x_t, a_t) and the policy \pi(a_t|x_t).

    - As Retrace uses multi-step returns, it can significantly reduce bias in the estimation of the policy gradient.

    - Update the gradients:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/013_3.png)

    - The purpose of using the multi-step estimator Q^{ret} is: (1) To reduce bias in the policy gradient, and (2) to enable faster learning of the critic, hence further reducing bias

  - Importance weight truncation with bias correction

    - To avoid high-variance, decomposite g as:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/013_4.png)

      - The clipping of the importance weight (the first term) ensures that the variance of the gradient estimate is bounded.
      - The correction term (the second term) ensures that our estimate is unbiased.

    - "Truncation with bias correction" trick:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/013_5.png)

    - The off-policy ACER gradient:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/013_6.png)

  - Efficient Trust Region Policy Optimization

    - Average policy network: a running average of past policies and forces the updated policy to not deviate far from this average.

    - Calculation steps:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/013_7.png)

  - Algorithm:

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/013_8.png)

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/013_9.png)

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/013_10.png)