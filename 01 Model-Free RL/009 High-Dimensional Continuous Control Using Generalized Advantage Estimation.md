# High-Dimensional Continuous Control Using Generalized Advantage Estimation

Authors: John Schulman, Philipp Moritz, Sergey Levine, Michael I. Jordan, Pieter Abeel

Year: 2017

Algorithm: GAE

- Problems
  - Two main challenges for policy gradient methods:
    - The large number of sample required
    - Difficulty of obtaining stable and steady improvement
  - High bias is more harmful than high variance - it can calse the algorithm to fail to converge, or to converge to a poor solution.
- Proposed solution
  - For the first challenge: Use value functions to reduce the variance of policy gradient estimates with an estimator of the advantage function.
  - For the second challenge: Use Trust Region Optimization (TRPO) Procedure for both the policy and the value function.
- GAE (Generalized Advantage Estimator)
  - What it is: A family of policy gradient estimators
  - Goal: Significantly reduce variance while maintaining a tolerable level of bias
- 