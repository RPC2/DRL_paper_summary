# Dueling Network Architectures for Deep Reinforcement Learning

**Authors**: Ziyu Wang, Tom Schaul, Matteo Hessel, Hado van Hasselt, Marc Lanctot, Nando de Freitas

**Year**: 2015

**Algorithm**: Dueling DQN

**Link**: [[arxiv](https://arxiv.org/abs/1511.06581)]

### Highlight

- **Dueling Architecture: Separating state value function and action advantage function**

### Prerequisites

- DQN algorithm [[paper](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)] [[summary](https://github.com/RPC2/DRL_paper_summary/blob/master/01 Model-Free RL/001 Playing Atari with Deep Reinforcement Learning.md)]
- Knowledge on advantage function

### Problems to solve

- 

### Methods

- **The Dueling Architecture**: It modifies the original DQN network structure by introducing two streams of fully connected layer after all the convolution operations: one serves as the state value estimator, and another calculates the advantage for each action.

- The two streams are combined through the equation <img src="https://latex.codecogs.com/svg.latex?\large&space;Q(s,a;\theta, \alpha, \beta) = V(s; \theta,\beta) + (A(s,a;\theta,\alpha) - \frac{1}{|A|}\sum_{a'} A(s, a';\theta,\alpha))" title="\large Q(s,a;\theta, \alpha, \beta) = V(s; \theta,\beta) + (A(s,a;\theta,\alpha) - \frac{1}{|A|}\sum_a' A(s, a';\theta,\alpha))" />, 

  where <img src="https://latex.codecogs.com/svg.latex?\large&space;\alpha" title="alpha" /> and <img src="https://latex.codecogs.com/svg.latex?\large&space;\beta" title="beta" /> are the parameters of the two streams of fully-connected layers.

  (For how this equation is developed, please refer to the original paper.)

  The dueling network can thus produce separate estimations of the state-value function <img src="https://latex.codecogs.com/svg.latex?V" title="V" />and advantage function<img src="https://latex.codecogs.com/svg.latex?A" title="A" /> without other supervision.

- The network structure:

  (top: the regular single-stream DQN, bottom: the dueling Q-network)

  ![algo](../imgs/003_1.png)

### Comments

- **Key insights**: In some states, which actions to take for the agent doesn't have significant meanings to the scoring of the game. In Breakout and Pong, it might be the times when the ball is very far away from the sliding bar. In Enduro (a car racing game), it is when a collision is unlikely to happen. For algorithms that are bootstrapping based, 