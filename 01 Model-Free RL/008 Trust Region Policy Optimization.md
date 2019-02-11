# Trust Region Policy Optimization

Authors: John Schulman, Sergey Levine, Philipp Moritz, Michael Jordan, Pieter Abbeel

Year: 2015

Algorithm: TRPO

- Problem

  - The policy improvement process in policy gradient methods contain a lot of inefficient update steps.

- Hypothesis

  - Minimizing a certain surrogate objective function guarantees policy improvement with non-trivial step sizes.

- Methods

  - Two ways to collect sets of trajectories:

    - Single-path method: applicable in the model-free setting

      - The Q(s,a) is computed at each state-action pair by taking the discounted sum of future rewards along the trajectory

    - Vine method: requiring the system to be restored to particular states, and is especially useful for simulation.

      ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/008_1.png)

  - Optimize a surrogate objective with a penalty on KL divergence.

  - Enforce a constraint (i.e., a trust region constraint) on the KL divergence between the new policy and the old policy during each update.

    ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/008_0.png)

    This method of optimization guarantees monotonic improvement. i.e., the new policy generated is no worse than the old policy. 

    (For the deduction process of this equation and proofs of relative theorems, please refer to the original paper, or read the [algorithm docs](https://spinningup.openai.com/en/latest/algorithms/trpo.html) from OpenAI Spinning Up.)

  - Algorithm from the paper:

    ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/008_2.png)

    