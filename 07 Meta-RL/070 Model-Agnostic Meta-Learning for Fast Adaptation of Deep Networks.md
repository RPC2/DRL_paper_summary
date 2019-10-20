# Model-Agnostic Meta-Learning for Fast Adaptation of Deep Networks

**Authors**: Chelsea Finn, Pieter Abbeel, Sergey Levine

**Year**: 2017

**Algorithm**: **MAML**

**Links:** [[arxiv](https://arxiv.org/abs/1703.03400)]

### Highlights

- **A general and model-agnostic meta-learning algorithm**

### Prerequisite

- [Introduction to Policy Optimization](https://spinningup.openai.com/en/latest/spinningup/rl_intro3.html), OpenAI Spinning Up

### Problems to solve

- The challenges of learning quickly occur in few-shot classfication and reinforcement learning. An artificial agent should be able to learn and adapt quickly from only a few examples, and continue to adapt as more data becomes available.
- **The goal of meta-learning** is to train a model on a variety of learning tasks, such that it can learn quickly to solve new tasks with only a small number of training samples.

### Method

- **Intuition**: Find a efficient initialization of model parameters that are sensitive to changes in the task, such that small changes in the paramters will produce large improvements on the loss function of any task.

- **Method**: Adaptation Phase + Meta-Update Phase
  - Quick Adaptation on Tasks
    - When adapting to a new task <img src="https://latex.codecogs.com/svg.latex?\large&space;\mathcal{T}_i" title="\large \mathcal{T}_i" />, the model parameters <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta" title="\large \theta" /> become <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta'" title="\large \theta'" />, which is computed by one or more gradient descent updates on task <img src="https://latex.codecogs.com/svg.latex?\large&space;\mathcal{T}_i" title="\large \mathcal{T}_i" />.
      - One gradient update: <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta'_i=\theta-\alpha&space;\nabla_\theta\mathcal{L}_{\mathcal{T}_i}(f_\theta)" title="\large \theta'_i=\theta-\alpha \nabla_\theta\mathcal{L}_{\mathcal{T}_i}(f_\theta)" />
  - Meta-optimization
    - The model parameters <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta" title="\large \theta" /> is updated for optimizing the performance of <img src="https://latex.codecogs.com/svg.latex?\large&space;f_{\theta_i'}" title="\large f_{\theta_i'}" /> w.r.t. <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta" title="\large \theta" /> across tasks sampled before.
    - The meta-objective (sum of loss from quickly adapted models on their tasks respectively) performed over <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta" title="\large \theta" /> is 
      - <img src="https://latex.codecogs.com/svg.latex?\large&space;\min_\theta\sum_{\mathcal{T}_i&space;\sim&space;p(\mathcal{T})}\mathcal{L}_{\mathcal{T}_i}(f_{\theta_i'})=\sum_{\mathcal{T}_i\sim&space;p(\mathcal{T})}\mathcal{L}_{\mathcal{T}_i}(f_{\theta-\alpha&space;\nabla_\theta\mathcal{L}_{\mathcal{T}_i}(f_\theta)})" title="\large \min_\theta\sum_{\mathcal{T}_i \sim p(\mathcal{T})}\mathcal{L}_{\mathcal{T}_i}(f_{\theta_i'})=\sum_{\mathcal{T}_i\sim p(\mathcal{T})}\mathcal{L}_{\mathcal{T}_i}(f_{\theta-\alpha \nabla_\theta\mathcal{L}_{\mathcal{T}_i}(f_\theta)})" />
    - The meta-phase update on <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta" title="\large \theta" /> is as follows:
      - <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta&space;\gets&space;\theta-\beta&space;\nabla_\theta\sum_{\mathcal{T}_i\sim&space;p(\mathcal{T})}\mathcal{L}_{\mathcal{T}_i}(f_{\theta_i'})" title="\large \theta \gets \theta-\beta \nabla_\theta\sum_{\mathcal{T}_i\sim p(\mathcal{T})}\mathcal{L}_{\mathcal{T}_i}(f_{\theta_i'})" />
    - Computationally, the meta phase requires an additional backward pass through $f$ to compute Hessian-vector products. This process is supported by standard DL libraries.
  - In effect, the method optimizes <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta" title="\large \theta" /> such that one or a small gradient steps on a new task will produce maximally effective behavior on that task.
  - Algorithm
    - ![algo1](../imgs/070_1.png)
    - ![img](../imgs/070_2.png)

- **Species of MAML**
  - MAML can be used for supervised learning and reinforcement learning. In this section, we will focus more on its application in reinforcement learning.
  - Supervised Regression and Classification
    - The goal is to learn a new function from a few data of that task, using meta learned prior knowledge from similar tasks. e.g. the goal might be to classify images of a Segway after seeing only one or a few examples of a Segway, with a model that has previously seen many other types of objects.
    - Conceptually, meta-learning learns a model that quickly learns how to classify a new object.
    - Algorithm
      - ![algo2](../imgs/070_3.png)
  - Reinforcement Learning
    - Goal: quickly acquire a poicy for a new test task (achieving a new goal/succeeding on a previous goal in a new environment) using only a small amount of experience in the test setting.
    - Since policy gradient methods are on-policy, hence each additional gradient step during the adaptation of <img src="https://latex.codecogs.com/svg.latex?\large&space;f_\theta" title="\large f_\theta" /> requires new samples from the current policy <img src="https://latex.codecogs.com/svg.latex?\large&space;f_{\theta_{i'}}" title="\large f_{\theta_{i'}}" />. See the difference at step 5 and 8 requiring sampling trajectories from the environment corresponding to the task <img src="https://latex.codecogs.com/svg.latex?\large&space;\mathcal{T}_i" title="\large \mathcal{T}_i" />.
    - Algorithm
      - ![algo3](../imgs/070_4.png)