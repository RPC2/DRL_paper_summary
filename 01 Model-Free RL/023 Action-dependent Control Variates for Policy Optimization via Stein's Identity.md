# Action-Dependent Control Variates for Policy Optimization via Stein's Identity

Authors: Hao Liu, Yihao Feng, Yi Mao, Dengyong Zhou, Jian Peng, Qiang Liu

Algorithm: Stein Control Variates

Year: 2017

Problems

- Policy gradient methods often suffer from large variance issue on gradient estimation, which leads to poor sample efficiency during training.

Hypothesis

- Using a control variate (with Stein's identity) in policy gradient methods can reduce the variance and improve the sample efficiency.

Methods

- Control Variate method: Subtracting a Monte Carlo gradient estimator by a baseline function (which theoretically has zero expectation). If this baseline function is properly chosen, it can cancel out the variance of the original gradient estimator.

  - In REINFORCE: A constant baseline function is usually chosen
  - In A2C: A state-dependent baseline function is usually chosen

-  Stein's identity

  - ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/023_1.png)
  - Stein's identity defines an infinite set of identities, indexed by the arbitrary function \phi(s,a), which is very flexible.

- Stein Control Variate for Policy Gradient

  - ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/023_2.png)

  - PPO with Stein Control Variate

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/023_3.png)

    Algorithm:

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/023_4.png)

    

