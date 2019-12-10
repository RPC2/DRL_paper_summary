# Rainbow: Combining Improvements in Deep Reinforcement Learning

**Authors**: Matteo Hessel, Joseph Modayil, Hado van Hasselt, Tom Schaul, Georg Ostrovski, Will Dabney, Dan Horgan, Bilal Piot, Mohammad Azar, David Silver

**Year**: 2017

**Algorithm**: **Rainbow DQN**

**Links:** [[arxiv](https://arxiv.org/abs/1710.02298)]

### Highlights

- **Integrated Agent** = **Double + PER + Dueling** + **Multi-step Learning** + **Distributional RL** + **Noisy Nets**

### Prerequisite

- DQN algorithm [[paper](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/001%20Playing%20Atari%20with%20Deep%20Reinforcement%20Learning.md)]
- Double Q-Learning [[paper](https://arxiv.org/abs/1509.06461)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/004%20Deep%20Reinforcement%20Learning%20with%20Double%20Q-learning.md)]
- Priorized Experience Replay [[paper](https://arxiv.org/abs/1511.05952)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/005%20Prioritized%20Experience%20Replay.md)]
- Dueling DQN [[paper](https://arxiv.org/abs/1511.06581)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/003%20Dueling%20Network%20Architectures%20for%20Deep%20Reinforcement%20Learning.md)]

### Background

- Multiple improvements have been applied to DQN separately. This paper intends to combine all these improvements together.

#### DRL and DQN

- In DQN, deep neural nets and reinforcement learning were combined by using a CNN as a function approximator for the action values given high-dimensional sensory data.

#### Double Q-Learning

- Conventional Q-learning is affected by an overestimation bias, which can harm learning. Double Q-learning addresses this overestimation by decoupling the selection of the action from its evaluation. It uses the target of 
  - <img src="https://latex.codecogs.com/svg.latex?\large&space;Y_t^{DoubleQ}&space;\equiv&space;R_{t&plus;1}&space;&plus;&space;\gamma&space;Q(S_{t&plus;1},&space;\arg\max_{a}Q(S_{t&plus;1},&space;a;\theta_t);\theta_t^-)" title="\large Y_t^{DoubleQ} \equiv R_{t+1} + \gamma Q(S_{t+1}, \arg\max_{a}Q(S_{t+1}, a;\theta_t);\theta_t^-)" />

#### Prioritized Experience Replay

- PER samples transitions with probability <img src="https://latex.codecogs.com/svg.latex?\large&space;p_{t}" title="\large p_{t}" /> relative to the last encountered absolute **TD error**:
  - <img src="https://latex.codecogs.com/svg.latex?\large&space;p_{t}&space;\propto&space;|R_{t&plus;1}&space;&plus;&space;\gamma_{t&plus;1}\max_{a'}&space;Q_{&space;\bar{\theta}}(S_{t&plus;1},&space;a^\prime)-Q_{\theta}(S_t,&space;A_t)|^\omega" title="\large p_{t} \propto |R_{t+1} + \gamma_{t+1}\max_{a'} Q_{ \bar{\theta}}(S_{t+1}, a^\prime)-Q_{\theta}(S_t, A_t)|^\omega" />
  - where <img src="https://latex.codecogs.com/svg.latex?\large&space;\omega" title="\large \omega" /> is a hyperparameter that determines the shape of the distribution.
- TD error shows how far the value is from its next-step bootstrap estimate, indicating how "surprising" or unexpected the transition is.
- New transitions are inserted into the replay buffer with maximum priority, providing a bias towards recent transitions. 

#### Dueling networks

- The dueling network is an architecture designed for value based RL. It features two streams of computation, the value and advantage streams, sharing a convolutional encoder, and merged by a special aggregator.
- This corresponds to the following factorization of action values:
  - <img src="https://latex.codecogs.com/svg.latex?\large&space;Q_\theta(s,&space;a)&space;=&space;V_\eta(f_\xi(s))&space;&plus;&space;a_\psi(f_\xi(s),&space;a)&space;-&space;\frac&space;{\sum&space;a_\psi(f_\xi(s),&space;a^\prime)}{N_{\text{actions}}}" title="\large Q_\theta(s, a) = V_\eta(f_\xi(s)) + a_\psi(f_\xi(s), a) - \frac {\sum a_\psi(f_\xi(s), a^\prime)}{N_{\text{actions}}}" />
  - <img src="https://latex.codecogs.com/svg.latex?\large&space;\xi" title="\large \xi" />, <img src="https://latex.codecogs.com/svg.latex?\large&space;\eta" title="\large \eta" />, <img src="https://latex.codecogs.com/svg.latex?\large&space;\psi" title="\large \psi" />: the parameters of the shared encoder <img src="https://latex.codecogs.com/svg.latex?\large&space;f_\xi" title="\large f_\xi" />, of the value stream <img src="https://latex.codecogs.com/svg.latex?\large&space;v_\eta" title="\large v_\eta" />, and of the advantage stream <img src="https://latex.codecogs.com/svg.latex?\large&space;a_\psi" title="\large a_\psi" />; <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta&space;=&space;\{\xi,&space;\eta&space;,&space;\psi\}" title="\large \theta = \{\xi, \eta , \psi\}" /> is their concatenation.

#### Multi-step Learning

- Use **multi-step return** instead of one-step reward:
  - <img src="https://latex.codecogs.com/svg.latex?\large&space;R_t^{(n)}\equiv\sum_{k=0}^{n-1}\gamma^{(k)}R_{t&plus;k&plus;1}" title="\large R_t^{(n)}\equiv\sum_{k=0}^{n-1}\gamma^{(k)}R_{t+k+1}" />
- The alternative loss: <img src="https://latex.codecogs.com/svg.latex?\large&space;(R_t^{(n)}&plus;\gamma_t^{(n)}\max_{a'}q_{\bar\theta}(S_{t&plus;n},a^\prime)-q_\theta(S_t,A_t))^2" title="\large (R_t^{(n)}+\gamma_t^{(n)}\max_{a'}q_{\bar\theta}(S_{t+n},a^\prime)-q_\theta(S_t,A_t))^2" />

- The value function can be learned faster in this way, because the value can be more accurately estimated with multi-step return.

#### Distributional RL

- The agent can learn to approximate the distribution of returns instead of the expected return. The distributional perspective allows the agent to gain information on the risks of the actions. (e.g. the value  = {10: 90%, 110: 10%} vs. {15: 50%, 25: 50%})
- Distributed RL use a discrete distribution to model the value distribution. <img src="https://latex.codecogs.com/svg.latex?\large&space;[V_{min},&space;V_{max}]" title="\large [V_{min}, V_{max}]" /> is divided into <img src="https://latex.codecogs.com/svg.latex?\large&space;N_{atoms}" title="\large N_{atoms}" /> equal parts to build the support <img src="https://latex.codecogs.com/svg.latex?\large&space;\mathbf{z}" title="\large \mathbf{z}" />. The probability distribution <img src="https://latex.codecogs.com/svg.latex?\large&space;d_t" title="\large d_t" /> at time <img src="https://latex.codecogs.com/svg.latex?\large&space;t" title="\large t" /> is defined on the support <img src="https://latex.codecogs.com/svg.latex?\large&space;\mathbf{z}" title="\large \mathbf{z}" />, with the probability pass  <img src="https://latex.codecogs.com/svg.latex?\large&space;p^i_\theta(S_t,A_t)" title="\large p^i_\theta(S_t,A_t)" /> on each atom <img src="https://latex.codecogs.com/svg.latex?\large&space;i" title="\large i" />, such that<img src="https://latex.codecogs.com/svg.latex?\large&space;d_t=(\mathbf{z},\mathbf{p}_\theta(S_t,A_t))" title="\large d_t=(\mathbf{z},\mathbf{p}_\theta(S_t,A_t))" />.
- KL-Divergence is used to measure the distance between the distribution $d_t$ and the target distribution <img src="https://latex.codecogs.com/svg.latex?\large&space;d_t'&space;\equiv&space;(R_{t&plus;1}&plus;\gamma_{t&plus;1}\mathbf{z},\mathbf{p}_{\bar\theta}(S_{t&plus;1},\bar&space;a^*_{t&plus;1}))" title="\large d_t' \equiv (R_{t+1}+\gamma_{t+1}\mathbf{z},\mathbf{p}_{\bar\theta}(S_{t+1},\bar a^*_{t+1}))" />
  - Hence, the resulting loss is <img src="https://latex.codecogs.com/svg.latex?\large&space;D_{KL}(\Phi_z&space;d_t'||d_t)" title="\large D_{KL}(\Phi_z d_t'||d_t)" />
  - Here <img src="https://latex.codecogs.com/svg.latex?\large&space;\Phi_\mathbf{z}" title="\large \Phi_\mathbf{z}" /> is the L2-projection of the target distribution onto the fixed support <img src="https://latex.codecogs.com/svg.latex?\large&space;\mathbf{z}" title="\large \mathbf{z}" />, and <img src="https://latex.codecogs.com/svg.latex?\large&space;\bar&space;a^*_{t&plus;1}&space;=&space;\arg\max_a&space;Q_{\bar&space;\theta}(S_{t&plus;1},a)" title="\large \bar a^*_{t+1} = \arg\max_a Q_{\bar \theta}(S_{t+1},a)" /> is the greedy action w.r.t. the mean action values <img src="https://latex.codecogs.com/svg.latex?\large&space;q_{\bar&space;\theta}(S_{t&plus;1},&space;a)&space;=&space;\mathbf{z}^\top&space;\mathbf{p}_\theta(S_{t&plus;1},&space;a)" title="\large q_{\bar \theta}(S_{t+1}, a) = \mathbf{z}^\top \mathbf{p}_\theta(S_{t+1}, a)" /> in state <img src="https://latex.codecogs.com/svg.latex?\large&space;S_{t&plus;1}" title="\large S_{t+1}" />.

#### Noisy Nets

- <img src="https://latex.codecogs.com/svg.latex?\large&space;\epsilon" title="\large \epsilon" />-greedy has limitations in games, where many actions must be executed to collect the first reward. Hence, Noisy Nets proposed a **noisy linear layer** that combines a deterministic and noisy stream,
  - <img src="https://latex.codecogs.com/svg.latex?\large&space;y=(b&plus;Wx)&plus;(b_{noisy}\odot\epsilon^b&plus;(W_{noisy}\odot\epsilon^w)x)" title="\large y=(b+Wx)+(b_{noisy}\odot\epsilon^b+(W_{noisy}\odot\epsilon^w)x)" />
  - This can be used in place of the standard linear <img src="https://latex.codecogs.com/svg.latex?\large&space;y=(b&plus;Wx)" title="\large y=(b+Wx)" />.
- Over time, the network can learn to ignore the noisy stream, but will do so at different rates in different parts of the state space, allowing state-conditional exploration with a form of self-annealing.

### Method

#### The Integrated Agent

- Replace the 1-step **distributional** loss with a **multi-step variant.** Then construct the target distribution as follows:
  
- <img src="https://latex.codecogs.com/svg.latex?\large&space;d_t^{(n)}&space;\equiv&space;(R_{t}^{(n)}&plus;\gamma_{t}^{(n)}\mathbf{z},\mathbf{p}_{\bar\theta}(S_{t&plus;n},\bar&space;a^*_{t&plus;n}))" title="\large d_t^{(n)} \equiv (R_{t}^{(n)}+\gamma_{t}^{(n)}\mathbf{z},\mathbf{p}_{\bar\theta}(S_{t+n},\bar a^*_{t+n}))" />
  
- The resulting loss is <img src="https://latex.codecogs.com/svg.latex?\large&space;D_{KL}(\Phi_z&space;d_t^{(n)}||d_t)" title="\large D_{KL}(\Phi_z d_t^{(n)}||d_t)" />.

- **Double Q-Learning:** using the greedy action in $S_{t+n}$ selected according to the *online network* as the bootstrap action <img src="https://latex.codecogs.com/svg.latex?\large&space;a^*_{t&plus;n}" title="\large a^*_{t+n}" /> and evaluating such action using the *target network*. 

- **PER:** all distributional Rainbow variants prioritize transitions by the KL loss, since this is what the algorithm is minimizing: <img src="https://latex.codecogs.com/svg.latex?\large&space;p_t&space;\propto&space;(D_{KL}(\Phi_z&space;d_t^{(n)}||d_t))^\omega" title="\large p_t \propto (D_{KL}(\Phi_z d_t^{(n)}||d_t))^\omega" />. The KL loss as priority might be more robust to noisy stochastic environments because the loss can continue to decrease even when the returns are not deterministic.

- **Dueling Network**: 

  - Shared representation <img src="https://latex.codecogs.com/svg.latex?\large&space;f_\xi(s)" title="\large f_\xi(s)" />, which is fed into **value stream** <img src="https://latex.codecogs.com/svg.latex?\large&space;v_\eta" title="\large v_\eta" /> with <img src="https://latex.codecogs.com/svg.latex?\large&space;N_{atoms}" title="\large N_{atoms}" /> outputs, and into **advantage stream** <img src="https://latex.codecogs.com/svg.latex?\large&space;a_\xi" title="\large a_\xi" /> with <img src="https://latex.codecogs.com/svg.latex?\large&space;N_{atoms}\times&space;N_{atoms}" title="\large N_{atoms}\times N_{atoms}" /> outputs, where <img src="https://latex.codecogs.com/svg.latex?\large&space;a_\xi^i(f_\xi(s),a)" title="\large a_\xi^i(f_\xi(s),a)" /> denotes the output corresponding to atom <img src="https://latex.codecogs.com/svg.latex?\large&space;i" title="\large i" /> and action <img src="https://latex.codecogs.com/svg.latex?\large&space;a" title="\large a" />.
  - For each atom <img src="https://latex.codecogs.com/svg.latex?\large&space;z^i" title="\large z^i" />, the value and advantage stream are aggregated, as in dueling DQN, and then passed through a softmax layer to obtain the normalized parametric distributions used to estimate the returns' distributions:
  - <img src="https://latex.codecogs.com/svg.latex?\large&space;p_\theta^i(s,a)=\frac{\exp(v_\eta^i(\phi)&plus;a^i_\psi(\phi,a)-\bar&space;a_\psi^i(s))}{\sum_j\exp(v_\eta^i(\phi)&plus;a^i_\psi(\phi,a)-\bar&space;a_\psi^i(s))}" title="\large p_\theta^i(s,a)=\frac{\exp(v_\eta^i(\phi)+a^i_\psi(\phi,a)-\bar a_\psi^i(s))}{\sum_j\exp(v_\eta^i(\phi)+a^i_\psi(\phi,a)-\bar a_\psi^i(s))}" />
  
  
  
- where <img src="https://latex.codecogs.com/svg.latex?\large&space;\phi=f_\xi(s)" title="\large \phi=f_\xi(s)" /> and <img src="https://latex.codecogs.com/svg.latex?\large&space;\bar&space;a_\psi^i(s)=\frac{1}{N_{actions}}\sum_{a'}a_\psi^i(\phi,a^\prime)" title="\large \bar a_\psi^i(s)=\frac{1}{N_{actions}}\sum_{a'}a_\psi^i(\phi,a')" />
  
- Then all linear layers are replaced with their **noisy** equivalent described before. Here, we use **facrotised Gaussian noise** to reduce the number of independent noise variables.

### Results and discussion

- The integrated agent provides SOTA performance on Atari 2600, both in terms of data efficiency and final performance.
  
  - ![Screen Shot 2019-11-09 at 3.33.51 PM](../imgs/006_1.png)
- From the above ablation studies, we can assess the effects of different components respectively
  - **Prioritized replay** and **multi-step learning** were the two most crucial components of Rainbow, in that removing either component caused a large degradation in median performance.
    - **PER** improves data efficiency, by replaying more often transitions from which there is more to learn. 
    - Learning from **multi-step** bootstrap targets shifts the bias-variance trade-off and helps to propagate newly observed rewards faster to previously visited states.
  - **Distributional Q-learning** ranked immediately below the previous techniques related to the agent's performance.
  - The agent performed better when **Noisy Nets** were included in terms of median performance. It's used to address the limitation of <img src="https://latex.codecogs.com/svg.latex?\large&space;\epsilon" title="\large \epsilon" />-greedy policies, where many actions must be executed to collect the first reward.
  - **Dueling network** is expected to help generalize across actions by separately representing state values and action advantages. In aggregate, we don't observe a significant difference when removing the dueling network from Rainbow. However, extensive experiments showed the impact of Dueling varied between games. 
  - In the case of **Double Q-learning**, the observed difference in median performance is limited. In the above settings of experiments, <img src="https://latex.codecogs.com/svg.latex?\large&space;[V_{min},&space;V_{max}]" title="\large [V_{min}, V_{max}]" />was set to [-10, 10] so as to enable distributional RL. Extensive investigation showed that comparing Rainbow to the double-ablated agent, the actual returns are often higher than 10, and therefore fall outside the support of the distribution from -10 to +10. This leads to underestimated returns. In this case, the function of double Q-learning to mitigate the overestimation of value was then disabled. Note the importance of double Q-learning may increase if the support of the distributions is expanded.