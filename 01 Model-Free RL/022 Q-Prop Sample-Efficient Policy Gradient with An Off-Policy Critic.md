# Q-Prop: Sample-Efficient Policy Gradient with an Off-Policy Critic

Authors: Shixiang Gu, Timothy Lilicrap, Zoubin Ghahramani, Richard E. Turner, Sergey Levine

Algorithm: Q-Prop

Year: 2016

- Problems

  - Policy gradient methods can suffer from high variance, and TD-style methods are biased and costly to stable. An ideal algorithm should further balance these two.
  - To deal with the high variance, a large number of samples is usually required.

- Overview of the solution

  - Q-Prop: Combines the stability of policy gradients with the efficiency of off-policy RL.
  - Uses a Taylor expansion of the off-policy critic as a control variate.
  - This will result in a gradient term through the critic, and a Monte Carlo policy gradient term consisting of the residuals in advantage approximations.

- Q-Prop estimator

  - The first order Taylor expansion of an arbitrary function f(s_t, a_t):

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/022_1.png)

    This is the control variate for the policy gradient estimator.

  - Derivation process

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/022_2.png)

  - Q-Prop more closely resembles an actor-critic method, where the critic can be updated off-policy but the actor is always updated on-policy with an additional REINFORCE correction term so that it remains a MC policy gradient method regardless of the parameterization, training method, and performance of the critic.

- Algorithm

  ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/022_3.png)

