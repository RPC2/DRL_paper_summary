# Soft Actor-Critic: Off Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor

Authors: Tuomas Harrnoja, Aurick Zhou, Pieter Abbeel, Sergey Levine

Year: 2018

- Problems

  - Two major challenges for model-free deep reinforcement learning: 
    1. Very high sample complexity
    2. Brittle convergence properties

- Overview of the algorithm

  - The actor aims to maximize expected reward while maximizing entropy (to succeed at the task while acting as randomly as possible)
    - Maximum entropy policies are robust with model and estimation errors because they improve exploration b y acquiring diverse behaviors.

- Preliminaries

  - Maximum Entropy Reinforcement Learning

    Compared with traditional reinforcement learning, the maximum entropy objective favors stochastic policies by augmenting the objective with the expected entropy of the policy:

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/014_1.png)

    - Several advantages of this objective:
      1. The policy is likely to explore more widely.
      2. The policy can find multiple modes of near-optimal behavior.
      3. Prior work has observed improved exploration with this objective

  - Deriving soft policy iteration

    - What it is

      A general algorithm for learning optimal maximum entropy policies that alternates between policy evaluation and policy improvement in the maximum entropy framework.

    - Method

      - To compute the soft Q-value, repeatedly apply the modified Bellman backup:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/014_2.png)

      - Lemma 1: With the soft Bellman backup in Eqation 2, the sequence of Q value will converge to the soft Q-value of the policy as time gets to infinity.

      - Policy improvement: For each state, update the policy according to

        ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/014_3.png)

      - Lemma 2: With soft policy improvement, for all state-action pairs, the Q values under the new policy are all higher than the Q values from the old policy.

      - Theorem 1: Repeated application of soft policy evaluation and soft policy improvement will let any initial policy converge to the optimal policy.

- Soft Actor-Critic

  - Algorithm

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/014_4.png)