# Addressing Function Approximation Error in Actor-Critic Methods

Authors: Scott Fujimoto, Herke van Hoof, David Meger

Algorithm: TD3

Year: 2018

- Problems

  - Function estimation errors can often lead to overestimation of the state value and thus, suboptimal policies

- Overview of the solution

  - Builds on Double Q-learning: Take the minimum value between a pair of critics to limit overestimation

- Solutions

  - Regarding the overestimation of bias:

    - By selecting the action that maximizes Q-value, we usually get our estimation result higher than the actual Q value if there are errors in our Q-value estimations.

    - The original Double Q-learning formulation (where the actors are optimized with respect to critics):

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/017_1.png)

    - The Clipped Double Q-learning update:

      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/017_2.png)

    - With this clipped double Q-learning update, the overestimation of state value is reduced, and as a lower variance estimation error will have lower expected minimum values, this way of update also favors low-variance value estimates. —> Safer policy updates with stable learning targets

  - Regarding variance:

    - High variance estimates provide a noisy gradient for the policy update, which reduces learning speed

    - Avoiding the accumulation of error

      - Why: In TD update, an estimate of the Q value is built from an estimate of the subsequent state, which contains certain amount of error. When the state sequence is long, this estimation error can accumulate and result in large overestimation bias and suboptimal policies

      - How: Introduce an error term and subtract from the original Q value calculation

        ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/017_3.png)

    - Target networks and delayed policy update

      - Problems: 
        1. Without a stable target, residual function approximation error and volatility will increase, which leads to a higher chance for policy to diverge. 
        2. Actor-critic methods fail to learn when policy updates with high variance value estimates
      - Solution:
        - Forcing the policy network to be updated at a lower frequency than the value network, to first minimize error before introducing a policy update

    - Target policy smoothing regularization

      - Why: A learning target using a deterministic policy is highly susceptible to inaccuracies induced by function approximation error, increasing the variance of the target

      - How: Target policy smoothing

        (Enforcing that similar actions should have similar value)

        Fit the value approximation of a state around a small area of the target action

         ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/017_4.png)

