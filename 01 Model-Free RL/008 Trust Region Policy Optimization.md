# Trust Region Policy Optimization

Authors: John Schulman, Sergey Levine, Philipp Moritz, Michael Jordan, Pieter Abbeel

Year: 2015

Algorithm: TRPO

- Problem
  - The policy improvement process in policy gradient methods contain a lot of inefficient update steps.
- Hypothesis
  - Minimizing a certain surrogate objective function guarantees policy improvement with non-trivial step sizes
- Methods
  - Enforce a constraint (i.e., a trust region constraint) on the KL divergence between the new policy and the old policy during each update