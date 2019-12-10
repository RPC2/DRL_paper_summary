# Deep Reinforcement Learning with Double Q-learning

**Authors**: [DeepMind] Hado van Hasselt, Arthur Guez, David Silver

**Year**: 2015

**Algorithm**: **Double DQN**

**Links:** [[arxiv](https://arxiv.org/abs/1509.06461)]

### Highlights

- **Action value overestimation in Deep Q-learning**
- **Double Q-learning**

### Prerequisite

- DQN algorithm [[paper](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01 Model-Free RL/001 Playing Atari with Deep Reinforcement Learning.md)]

### Problems to solve

- Q-learning algorithm is known to overestimate action values under certain conditions.
- Overestimation of action values causes instabilities.

### Q-learning & Double Q-learning

- **Q-learning**
  - <img src="https://latex.codecogs.com/svg.latex?\large&space;Y_t^{Q}&space;=&space;R_{t&plus;1}&space;&plus;&space;\gamma&space;Q(S_{t&plus;1},&space;\arg\max_{a}Q(S_{t&plus;1},&space;a;\theta_t);\theta_t)" title="\large Y_t^{Q} = R_{t+1} + \gamma Q(S_{t+1}, \arg\max_{a}Q(S_{t+1}, a;\theta_t);\theta_t)" />
- **Double Q-learning**: two value functions are learned by assigning each experience randomly to update one of the two value functions. One is used to determine the greedy policy and the other to determine its value.
  - <img src="https://latex.codecogs.com/svg.latex?\large&space;Y_t^{DoubleQ}&space;\equiv&space;R_{t&plus;1}&space;&plus;&space;\gamma&space;Q(S_{t&plus;1},&space;\arg\max_{a}Q(S_{t&plus;1},&space;a;\theta_t);\theta_t')" title="\large Y_t^{DoubleQ} \equiv R_{t+1} + \gamma Q(S_{t+1}, \arg\max_{a}Q(S_{t+1}, a;\theta_t);\theta_t')" />

### Overoptimism due to estimation errors

- Estimation errors of any kind can induce an upward bias, regardless of whether these errors are due to environmental noise, function approximation, non-stationarity, or any other source.
- **Theorem**: 
  - For Q-Learning, under the condition that <img src="https://latex.codecogs.com/svg.latex?\sum_a(Q_t(s,a)-V_*(s))=0" title="\sum_a(Q_t(s,a)-V_*(s))=0" />(arbitrary value estimates are unbiased), but that<img src="https://latex.codecogs.com/svg.latex?\frac{1}{m}\sum_a(Q_t(s,a)-V_*(s))^2=C" title="\frac{1}{m}\sum_a(Q_t(s,a)-V_*(s))^2=C" />, then we have<img src="https://latex.codecogs.com/svg.latex?\max_aQ_t(s,a)\ge&space;V^*(s)&plus;\sqrt{\frac{C}{m-1}}" title="\max_aQ_t(s,a)\ge V^*(s)+\sqrt{\frac{C}{m-1}}" />. This lower bound is tight. 
  - Under the same conditions, **the lower bound on the absolute error of Double Q-learning estimate is zero**.
- For Q-Learning, the overoptimism increases with the number of actions, but Double Q-learning is unbiased.
  - ![004_1](../imgs/004_1.png)

### Method

- Double DQN
  - The idea of Double Q-learning is to reduce overestimations by decomposing the **max** operation in the target into action selection and action evaluation. The paper proposed to evaluate the greedy policy according to the **online network** (<img src="https://latex.codecogs.com/svg.latex?\large&space;\theta_t" title="\large \theta_t" />), but using the **target network** (<img src="https://latex.codecogs.com/svg.latex?\large&space;\theta_t^-" title="\large \theta_t^-" />) to estimate its value.
    - <img src="https://latex.codecogs.com/svg.latex?\large&space;Y_t^{DoubleQ}&space;\equiv&space;R_{t&plus;1}&space;&plus;&space;\gamma&space;Q(S_{t&plus;1},&space;\arg\max_{a}Q(S_{t&plus;1},&space;a;\theta_t);\theta_t^-)" title="\large Y_t^{DoubleQ} \equiv R_{t+1} + \gamma Q(S_{t+1}, \arg\max_{a}Q(S_{t+1}, a;\theta_t);\theta_t^-)" />
  - Empirical results show that double Q-learning can be used at scale to successfully reduce overoptimism, resulting in more stable and reliable learning.
