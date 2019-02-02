# Scalable trust-region method for deep reinforcement learning using Kronecker-factored approximation

Authors: Yuhuai Wu, Elman Mansimov, Shun Liao, Roger Grosse, Jimmy Ba

Year: 2017

Algorithm: ACKTR

- Problems
  - Using simple variants of Stochastic Gradient Descent (SGD) to optimize neural networks is inefficient.
  - Trust-region policy optimization (TRPO) is impractical for large models, and it suffers from sample inefficiency.
- Hypothesis
  - Kronecker-factored approximated curvature (K-FAC) could improve the sample efficiency of deep RL.
- Methods
  - **Actor** 
    - Use the Kronecker-factored trust region (ACKTR) to compute the natural gradient update, then apply the natural gradient update to both the actor and the critic.
    - Fisher metric is defined as (pic)
  - **Critic** 
    - The learning process is similar to a least-squares function approximation problem
    - Since the second-order algorithm is Gauss-Newton, which is equivalent to the Fisher matrix for a Gaussian observation model, K-FAC is also applied to the critic.
  - To avoid instability in training, let the two networks share lower-layer representations, but have distinct output layers. --> Assume independence of the two output distributions
  - Step-size selection and trust-region optimization
    - Instead of natural gradient, use trust-region approach to limit the update. --> Avoid premature convergence to a near-deterministic policy.

