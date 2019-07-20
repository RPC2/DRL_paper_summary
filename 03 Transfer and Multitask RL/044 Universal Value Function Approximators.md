# Universal Value Function Approximators

Authors: Tom Schaul, Dan Horgan, Karol Gregor, David Silver

Year: 2015

Algorithm: UVFA

- Method

  - Overview: Factoring observed values into separate embedding vectors for state and goal, and then learn a mapping from state s and goal g to these factored embedding vectors.

  - Different ways of incorporating state s and goal g into the function approximators

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/044_1.png)

  - Reinforcement Learning with UVFA algorithm

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/044_2.png)