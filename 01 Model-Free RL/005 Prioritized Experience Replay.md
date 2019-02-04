# Prioritized Experience Replay

Authors: Tom School, John Quan, Ioannis Antonoglou, David Silver

Year: 2015

Algorithm: Prioritized Experience Replay (PER)

- Problem

  - In the originally proposed Deep Q Network algorithm, the agent samples transitions uniformly, regardless of their significance.

- Hypothesis

  - Instead of random sampling, prioritizing to sample the experiences which the agent makes significant mistakes, as measured by the magnitude of TD error, can prompt the agent to correct the neural network more effectively, and thus improve the learning efficiency and its performance.

- Methods

  - The importance of each transition is measured by the amount an agent can learn from this transition (expected learning progress), and TD error is a reasonable proxy as it shows how "surprising" this transition is.

  - Use stochastic sampling method to avoid overfitting:

    ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/pic/005_1.png),

    where p is each transition's priority value.

    - When alpha > 0, the agent samples greedily.
    - When alpha = 0, it's uniform sampling.

  - If any transition's TD error is zero, add a small positive constant to its priority to prevent this transition from having zero probability to be sampled from memory.

  - Correct the bias introduced by prioritized replay by using importance-sampling weights:

    ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/pic/005_2.png)

- Algorithm

  ![alt text](https://github.com/RPC2/DRL_paper_summary/blob/master/pic/005_3.png)