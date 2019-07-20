# Progressive Neural Networks

Authors: Andrei A. Rusu, Neil C. Rabinowitz, Guillaume Desjardins, Hubert Soyer, James Kirkpatrick, Koray Kavukcuoglu, Razvan Pascanu, Raia Hadsell

Year: 2016

Algorithm: Progressive Networks

- Problems to solve

  - The usual transfer learning practice is unsuitable for transferring across multiple tasks: If we wish to leverage knowledge acquired across a sequence of experiences, which model should we use to initialize subsequent models? —> Requires transfer learning without catastrophic forgetting, but also foreknowledge of task similarity.

- Method: Progressive Networks

  - The goals:

    1. Solve K independent tasks at the end of training
    2. Accelerate learning via transfer when possible
    3. Avoid catastrophic forgetting

  - It retains a pool of pretrained models throughout training, and learn lateral connecctions from these to extract useful features for the new task.

  - The progressive network starts with a single column, where the network parameters are trained to convergence. When switching to a new task, a new set of network parameters are randomly initialized, where each layer receives input from both the previous layer in the first and the second network. See the figure below:

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/043_1.png)

  - This generalizes to K tasks as follows:

    ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/043_2.png)

  - Downside of this approach: The growth in number of parameters with the number of tasks.