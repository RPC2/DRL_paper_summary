# Summary of key papers in Deep Reinforcement Learning

This repository contains the summaries of key papers in deep reinforcement learning listed in OpenAI [Spinning Up](https://spinningup.openai.com/en/latest/index.html). The summaries aim to provide a high-level overview of each paper, listing out the key problems the authors tried to solve and the main contributions / algorithms proposed. 

This list is well organized so that the former papers serve as prerequisites for the later ones. Readers are encouraged to read the original papers if they are interested in digging more into any specific details.



## 1. Model-Free Reinforcement Learning

### a. Deep-Q-Learning

[1] Playing Atari with Deep Reinforcement Learning, Mnih et al, 2013. **Algorithm: DQN.** [[paper](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/001%20Playing%20Atari%20with%20Deep%20Reinforcement%20Learning.md)]

[2] Deep Recurrent Q-Learning for Partially Observable MDPs, Hausknecht and Stone, 2015. **Algorithm: Deep Recurrent Q-Learning.** [[paper](https://arxiv.org/abs/1507.06527)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/002%20Deep%20Recurrent%20Q-Learning%20for%20Partially%20Observable%20MDPs.md)]

[3] Dueling Network Architectures for Deep Reinforcement Learning, Wang et al, 2015. **Algorithm: Dueling DQN.** [[paper](https://arxiv.org/abs/1511.06581)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/003%20Dueling%20Network%20Architectures%20for%20Deep%20Reinforcement%20Learning.md)]

[4] Deep Reinforcement Learning with Double Q-learning, Hasselt et al 2015. **Algorithm: Double DQN.** [[paper](https://arxiv.org/abs/1509.06461)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/004%20Deep%20Reinforcement%20Learning%20with%20Double%20Q-learning.md)]

[5] Prioritized Experience Replay, Schaul et al, 2015. **Algorithm: Prioritized Experience Replay (PER).** [[paper](https://arxiv.org/abs/1511.05952)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/005%20Prioritized%20Experience%20Replay.md)]

[6] Rainbow: Combining Improvements in Deep Reinforcement Learning, Hessel et al, 2017. **Algorithm: Rainbow DQN.** [[paper](https://arxiv.org/abs/1710.02298)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/006%20Rainbow%20Combining%20Improvements%20in%20Deep%20Reinforcement%20Learning.md)]



### b. Policy Gradients

[7] Asynchronous Methods for Deep Reinforcement Learning, Mnih et al, 2016. **Algorithm: A3C.** [[paper](https://arxiv.org/abs/1602.01783)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/007%20Asynchronous%20Methods%20for%20Deep%20Reinforcement%20Learning.md)]

[8] Trust Region Policy Optimization, Schulman et al, 2015. **Algorithm: TRPO.** [[paper](https://arxiv.org/abs/1502.05477)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/008%20Trust%20Region%20Policy%20Optimization.md)]

[9] High-Dimensional Continuous Control Using Generalized Advantage Estimation, Schulman et al, 2015. **Algorithm: GAE.** [[paper](https://arxiv.org/abs/1506.02438)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/009%20High-Dimensional%20Continuous%20Control%20Using%20Generalized%20Advantage%20Estimation.md)]

[10] Proximal Policy Optimization Algorithms, Schulman et al, 2017. **Algorithm: PPO-Clip, PPO-Penalty.** [[paper](https://arxiv.org/abs/1707.06347)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/010%20Proximal%20Policy%20Optimization%20Algorithms.md)]

[11] Emergence of Locomotion Behaviours in Rich Environments, Heess et al, 2017. **Algorithm: PPO-Penalty.** [[paper](https://arxiv.org/abs/1707.02286)]

[12] Scalable trust-region method for deep reinforcement learning using Kronecker-factored approximation, Wu et al, 2017. **Algorithm: ACKTR.** [[paper](https://arxiv.org/abs/1708.05144)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/012%20Scalable%20trust-region%20method%20for%20deep%20reinforcement%20learning%20using%20Kronecker-factored%20approximation.md)]

[13] Sample Efficient Actor-Critic with Experience Replay, Wang et al, 2016. **Algorithm: ACER.** [[paper](https://arxiv.org/abs/1611.01224)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/013%20Sample%20Efficient%20Actor-Critic%20with%20Experience%20Replay.md)]

[14] Soft Actor-Critic: Off-Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor, Haarnoja et al, 2018. **Algorithm: SAC.** [[paper](https://arxiv.org/abs/1801.01290)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/014%20Soft%20Actor-Critic%20Off%20Policy%20Maximum%20Entropy%20Deep%20Reinforcement%20Learning%20with%20a%20Stochastic%20Actor.md)]



### c. Deterministic Policy Gradients

[15] Deterministic Policy Gradient Algorithms, Silver et al, 2014. **Algorithm: DPG.** [[paper](http://proceedings.mlr.press/v32/silver14.pdf)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/015%20Deterministic%20Policy%20Gradient%20Algorithms.md)]

[16] Continuous Control With Deep Reinforcement Learning, Lillicrap et al, 2015. **Algorithm: DDPG.** [[paper](https://arxiv.org/abs/1509.02971)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/016%20Continuous%20control%20with%20deep%20reinforcement%20learning.md)]

[17] Addressing Function Approximation Error in Actor-Critic Methods, Fujimoto et al, 2018. **Algorithm: TD3.** [[paper](https://arxiv.org/abs/1802.09477)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/017%20Addressing%20Function%20Approximation%20Error%20in%20Actor-Critic%20Methods.md)]



### d. Distributional Reinforcement Learning

[18] A Distributional Perspective on Reinforcement Learning, Bellemare et al, 2017. **Algorithm: C51.** [[paper](https://arxiv.org/abs/1707.06887)]

[19] Distributional Reinforcement Learning with Quantile Regression, Dabney et al, 2017. **Algorithm: QR-DQN.** [[paper](https://arxiv.org/abs/1710.10044)] 

[20] Implicit Quantile Networks for Distributional Reinforcement Learning, Dabney et al, 2018. **Algorithm: IQN.** [[paper](https://arxiv.org/abs/1806.06923)]

[21] Dopamine: A Research Framework for Deep Reinforcement Learning, Anonymous, 2018. **Contribution:** Introduces Dopamine, a code repository containing implementations of DQN, C51, IQN, and Rainbow. [Code link.](https://github.com/google/dopamine) [[paper](https://openreview.net/forum?id=ByG_3s09KX)]



### e. Policy Gradients with Action-Dependent Baselines

[22] Q-Prop: Sample-Efficient Policy Gradient with An Off-Policy Critic, Gu et al, 2016. **Algorithm: Q-Prop.** [[paper](https://arxiv.org/abs/1611.02247)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/022%20Q-Prop%20Sample-Efficient%20Policy%20Gradient%20with%20An%20Off-Policy%20Critic.md)]

[23] Action-depedent Control Variates for Policy Optimization via Stein’s Identity, Liu et al, 2017. **Algorithm: Stein Control Variates.** [[paper](https://arxiv.org/abs/1710.11198)]

[24] The Mirage of Action-Dependent Baselines in Reinforcement Learning, Tucker et al, 2018. **Contribution:** interestingly, critiques and reevaluates claims from earlier papers (including Q-Prop and stein control variates) and finds important methodological errors in them. [[paper](https://arxiv.org/abs/1802.10031)]