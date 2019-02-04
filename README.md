# Summary of key papers in Deep Reinforcement Learning

This repository contains the summary of key papers in deep reinforcement learning listed in OpenAI [Spinning Up](https://spinningup.openai.com/en/latest/index.html). The summaries aim to provide a high-level overview of each paper, listing out the key problems the authors tried to solve and the main contributions / algorithms proposed. While technical details are omitted in these summaries, it doesn't mean they are overlooked, and readers are encouraged to read the original papers should they have any interests in digging more into this field.

### 1. Model-Free Reinforcement Learning

#### a. Deep-Q-Learning

[1] [Playing Atari with Deep Reinforcement Learning](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf), Mnih et al, 2013. **Algorithm: DQN.** [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/001%20Playing%20Atari%20with%20Deep%20Reinforcement%20Learning.md)]

[2] [Deep Recurrent Q-Learning for Partially Observable MDPs](https://arxiv.org/abs/1507.06527), Hausknecht and Stone, 2015. **Algorithm: Deep Recurrent Q-Learning.**

[3] [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581), Wang et al, 2015. **Algorithm: Dueling DQN.**

[4] [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461), Hasselt et al 2015. **Algorithm: Double DQN.**

[5] [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952), Schaul et al, 2015. **Algorithm: Prioritized Experience Replay (PER).**

[6] [Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298), Hessel et al, 2017. **Algorithm: Rainbow DQN.**

#### b. Policy Gradients

[7] [Asynchronous Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1602.01783), Mnih et al, 2016. **Algorithm: A3C.**

[8] [Trust Region Policy Optimization](https://arxiv.org/abs/1502.05477), Schulman et al, 2015. **Algorithm: TRPO.**

[9] [High-Dimensional Continuous Control Using Generalized Advantage Estimation](https://arxiv.org/abs/1506.02438), Schulman et al, 2015. **Algorithm: GAE.**

[10] [Proximal Policy Optimization Algorithms](https://arxiv.org/abs/1707.06347), Schulman et al, 2017. **Algorithm: PPO-Clip, PPO-Penalty.**

[11] [Emergence of Locomotion Behaviours in Rich Environments](https://arxiv.org/abs/1707.02286), Heess et al, 2017. **Algorithm: PPO-Penalty.**

[12] [Scalable trust-region method for deep reinforcement learning using Kronecker-factored approximation](https://arxiv.org/abs/1708.05144), Wu et al, 2017. **Algorithm: ACKTR.**

[13] [Sample Efficient Actor-Critic with Experience Replay](https://arxiv.org/abs/1611.01224), Wang et al, 2016. **Algorithm: ACER.**

[14] [Soft Actor-Critic: Off-Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor](https://arxiv.org/abs/1801.01290), Haarnoja et al, 2018. **Algorithm: SAC.**