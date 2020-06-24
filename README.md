# Summary of key papers in Deep Reinforcement Learning

This repository contains the summaries of key papers in deep reinforcement learning, and the list is heavily based on key papers in OpenAI [Spinning Up](https://spinningup.openai.com/en/latest/index.html). The summaries aim to provide a high-level overview of each paper, listing out the key problems the authors tried to solve and the main contributions / algorithms proposed. 

This list is well organized so that the former papers serve as prerequisites for the later ones. Readers are encouraged to read the original papers if they are interested in digging more into any specific details.

These summaries are co-authored by [Cynthia Chen](https://github.com/RPC2) and [Yawen Duan](https://github.com/kmdanielduan).

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

[23] Action-depedent Control Variates for Policy Optimization via Stein’s Identity, Liu et al, 2017. **Algorithm: Stein Control Variates.** [[paper](https://arxiv.org/abs/1710.11198)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/023%20Action-dependent%20Control%20Variates%20for%20Policy%20Optimization%20via%20Stein's%20Identity.md)]

[24] The Mirage of Action-Dependent Baselines in Reinforcement Learning, Tucker et al, 2018. **Contribution:** interestingly, critiques and reevaluates claims from earlier papers (including Q-Prop and stein control variates) and finds important methodological errors in them. [[paper](https://arxiv.org/abs/1802.10031)]



## 2. Exploration

### a. Intrinsic Motivation

[39] Exploration by Random Network Distillation, Burda et al, 2018. **Algorithm: RND** [[paper](https://arxiv.org/abs/1810.12894)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/02%20Exploration/039%20Exploration%20by%20Random%20Network%20Distillation.md)]



## 3. Transfer and Multitask RL

[43] Progressive Neural Networks, Rusu et al, 2016. **Algorithm: Progressive Networks** [[paper](https://arxiv.org/abs/1606.04671)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/03%20Transfer%20and%20Multitask%20RL/043%20Progressive%20Neural%20Networks.md)]

[44] Universal Value Function Approximators, Schaul et al, 2015. **Algorithm: UVFA.** [[paper](http://proceedings.mlr.press/v37/schaul15.pdf)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/03%20Transfer%20and%20Multitask%20RL/044%20Universal%20Value%20Function%20Approximators.md)]

[45] Reinforcement Learning with Unsupervised Auxiliary Tasks, Jaderberg et al, 2016. **Algorithm: UNREAL** [[paper](https://arxiv.org/abs/1611.05397)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/03%20Transfer%20and%20Multitask%20RL/045%20Reinforcement%20Learning%20with%20Unsupervised%20Auxiliary%20Tasks.md)]

[50] Hindsight Experience Replay, Andrychowicz et al, 2017. **Algorithm: Hindsight Experience Replay (HER)** [[paper](https://arxiv.org/abs/1707.01495)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/03%20Transfer%20and%20Multitask%20RL/050%20Hindsight%20Experience%20Replay.md)]



## 6. Model-Based RL

### a. Model is Learned

[59] Imagination-Augmented Agents for Deep Reinforcement Learning, Weber et al, 2017. **Algorithm: I2A** [[paper](https://arxiv.org/abs/1707.06203)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/06%20Model-Based%20RL/059%20Imagination-Augmented%20Agents%20for%20Deep%20Reinforcement%20Learning.md)]

[60] Neural Network Dynamics for Model-Based Deep Reinforcement Learning with Model-Free Fine-Tuning, Nagabandi et al, 2017. **Algorithm: MBMF** [[paper](https://arxiv.org/abs/1708.02596)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/06%20Model-Based%20RL/060%20Neural%20Network%20Dynamics%20for%20Model-Based%20Deep%20Reinforcement%20Learning%20with%20Model-Free%20Fine-Tuning.md)]

[61] Model-Based Value Expansion for Efficient Model-Free Reinforcement Learning, Feinberg et al, 2018. **Algorithm: MVE** [[paper](https://arxiv.org/abs/1803.00101)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/06%20Model-Based%20RL/061%20Model-Based%20Value%20Expansion%20for%20Efficient%20Model-Free%20Renforcement%20Learning.md)]

### b. Model is Given

[66] Mastering Chess and Shogi by Self-Play with a General Reinforcement Learning Algorithm, Silver et al, 2017. **Algorithm: AlphaZero** [[paper](https://arxiv.org/abs/1712.01815)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/06%20Model-Based%20RL/066%20Mastering%20Chess%20and%20Shogi%20by%20Self-Play%20with%20a%20General%20Reinforcement%20Learning%20Algorithm.md)]

[67] Thinking Fast and Slow with Deep Learning and Tree Search, Anthony et al, 2017. **Algorithm: ExIt** [[paper](https://arxiv.org/abs/1705.08439)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/06%20Model-Based%20RL/067%20Thinking%20Fast%20and%20Slow%20with%20Deep%20Learning%20and%20Tree%20Search.md)]



## 7. Meta-RL

[68] RL^2: Fast Reinforcement Learning via Slow Reinforcement Learning, Duan et al, 2016. **Algorithm: RL^2** [[paper](https://arxiv.org/abs/1611.02779)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/07%20Meta-RL/068%20RL2%20Fast%20Reinforcement%20Learning%20via%20Slow%20Reinforcement%20Learning.md)]

[69] Learning to Reinforcement Learn, Wang et al, 2016. [[paper](https://arxiv.org/abs/1611.05763)] [summary]

[70] Model-Agnostic Meta-Learning for Fast Adaptation of Deep Networks, Finn et al, 2017. **Algorithm: MAML** [[paper](https://arxiv.org/abs/1703.03400)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/07%20Meta-RL/070%20Model-Agnostic%20Meta-Learning%20for%20Fast%20Adaptation%20of%20Deep%20Networks.md)]