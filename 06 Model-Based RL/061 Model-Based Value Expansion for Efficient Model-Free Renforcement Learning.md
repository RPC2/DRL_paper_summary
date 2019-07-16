# Model-Based Value Expansion for Efficient Model-Free Renforcement Learning

Authors: Vladimir Feinberg, Alvin Wan, Ion Stoica, Michael I. Jordan, Joseph E. Gonzalez, Sergey Levine

Year: 2018

Algorithm: MVE

- Problems to solve

  - Some model-free reinforcement learning algorithms propose to incorporate learned dynamics models as a source of additional data, but they rely on heuristics that limit usage of the dynamics model.
  - Model-free algorithms can achieve good asymptotic performance, but have poor sample efficiency.
  - Model-based algorithms can learn efficiently, but struggle on complex tasks.
  - This paper seeks to reduce sample complexity while supporting difficult task learning by combining model-based and model-free learning techniques through disciplined model use for value estimation.

- Method

  - Overview: It uses a dynamics model to simulate the short-term horizon (near-future MB component) and Q-learning to estimate the long-term value beyond the simulation horizon (distant-future MF component). 

  - Algorithm

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/061_1.png)