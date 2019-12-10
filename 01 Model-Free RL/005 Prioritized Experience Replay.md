# Prioritized Experience Replay

**Authors**: Tom School, John Quan, Ioannis Antonoglou, David Silver

**Year**: 2015

**Algorithm**: Prioritized Experience Replay (PER)

**Link**: [[arxiv](https://arxiv.org/abs/1511.05952)]

### Highlight

- Prioritize selecting important memories via **Weighted Importance Sampling**

### Prerequisites

- DQN algorithm [[paper](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01%20Model-Free%20RL/001%20Playing%20Atari%20with%20Deep%20Reinforcement%20Learning.md)]

### Main Contribution

- This paper proposes a method to sample more important memories, i.e., memories an agent can get more meaningful gradient updates, in DQN's replay buffer instead of sampling them uniformly.

### Methods

- Assumption: An RL agent can learn more effectively from some transitions than from others.

- A transition's **TD error** is used as the criterion to measure which transition should be prioritized, since it shows how 'surprising' or unexpected the transition is, which may be a good proxy. 

  - In the implementation, a priority queue (a [data structure](https://en.wikipedia.org/wiki/Priority_queue)) is used to store the memories. It enables finding the maximum priority transition with <img src="https://latex.codecogs.com/svg.latex?\large&space;O(1)" /> time complexity, and update the priorities <img src="https://latex.codecogs.com/svg.latex?\large&space;O(logN)" />.

- **Stochastic Prioritization**

  - Pure greedy prioritization which greedily selects memories with highest error has several problems: (1) Transitions with a low TD error on first visit may not be replayed for a long time. (2) It is sensitive to noise spikes. i.e., It can fail easily when there are approximation errors which bring noises. (3) Greedy prioritization focuses on only a subset of the experience that has high errors.

  - Stochastic sampling method

    - The probability of sampling transition <img src="https://latex.codecogs.com/svg.latex?\large&space;i" /> is <img src="https://latex.codecogs.com/svg.latex?\large&space;P(i)=\frac{p_i^\alpha}{\sum_kp_k^\alpha}" />, where <img src="https://latex.codecogs.com/svg.latex?\large&space;p(i)>0" /> is the priority of transition <img src="https://latex.codecogs.com/svg.latex?\large&space;i" />. <img src="https://latex.codecogs.com/svg.latex?\large&space;\alpha" /> determines how much prioritization is used, with <img src="https://latex.codecogs.com/svg.latex?\large&space;\alpha=0" /> corresponding to the uniform case.

    - There can be two variants for expressing <img src="https://latex.codecogs.com/svg.latex?\large&space;p(i)" />. The first one is <img src="https://latex.codecogs.com/svg.latex?\large&space;p(i)=|\delta|+\epsilon" />, and the second one is <img src="https://latex.codecogs.com/svg.latex?\large&space;p(i)=\frac{1}{rank(i)}" />, where <img src="https://latex.codecogs.com/svg.latex?\large&space;rank(i)" /> is the rank of transition <img src="https://latex.codecogs.com/svg.latex?\large&space;i"/> when the replay memory is sorted according to <img src="https://latex.codecogs.com/svg.latex?\large&space;|\delta|" />. The latter is likely to be more robust since it is sensitive to outliers.

- **Annealing the bias**

  - Estimating the expected value with stochastic updates requires those updates are with the same distribution as its expectation (?). Prioritized replay breaks this condition, and it can be corrected by introducing Importance-Sampling (IS) weights:

    <img src="https://latex.codecogs.com/svg.latex?\large&space;w_i=(\frac{1}{N}\cdot\frac{1}{P(i)})^\beta" />

    These weights can be integrated into the Q-learning update by using <img src="https://latex.codecogs.com/svg.latex?\large&space;w_i\delta_i" />. To stablize the learning process, the weights are normalized by <img src="https://latex.codecogs.com/svg.latex?\large&space;\frac{1}{max_iw_i}" />.  

- Algorithm

  ![algo](../imgs/005_3.png)

