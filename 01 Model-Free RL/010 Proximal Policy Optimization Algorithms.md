# Proximal Policy Optimization Algorithms

Authors: John Schulman, Filip Wolski, Prafulla Dhariwal, Alec Radford, Oleg Klimov

Year: 2017

- Problems

  - The leading deep reinforcement learning algorithms have their own defects: Q learning is poorly understood, vanila policy gradient has poor data efficiency and robustness, and trust region policy optimization is complicated to implement, and not compatible with many architectures that include noise or parameter sharing.

- Hypothesis

  - An objective function with clipped probability ratios which forms a lower bound of the performance of the policy, and alternating between sampling data & optimization on optimizing policies will improve the performance of the algorithm while remaining simple and data-efficient.

- Solutions

  - Clipped Surrogate Objective

    - (Background) The TRPO method:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/010_0.png)

    - (Background) The surrogate objective used by TRPO:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/010_1.png)

    - The clipped surrogate objective (enforcing the constraint through the difference between the new and old policy instead of using KL divergence):

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/010_2.png)

    - The plot:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/010_3.png)

  - Algorithm

    - The objective to be maximized in each iteration:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/010_4.png)

    - The chosen advantage estimation (Generalized Advantage Estimation):

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/010_5.png)

    - The Proximal Policy Optimization (PPO) algorithm:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/010_6.png)