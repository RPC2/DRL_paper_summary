# Exploration by Random Network Distillation

Authors: Yuri Burda, Harrison Edwards, Amos Storkey, Oleg Klimov

Algorithm: RND

Year: 2018

- Problems
  - RL tends to fail when rewards are sparse and hard to find.
  - How to encourage exploration in a directed way without explicit rewards?
- Methods
  - Random Network Distillation
    - The target network: fixed, randomly initialized
    
    - The predictor network: trained on data collected by the agent
    
    - The predictor network is trained on gradient descent to minimize the expected MSE wrt its parameters theta_f
    
      ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/039_1.png)
    
  - Combining intrinsic and extrinsic rewards
  
    - The paper uses two value heads for computing both intrinsic and extrinsic rewards
    - Obtaining two rewards also enables taking different discount factors for intrinsic and extrinsic rewards
- Pseudocode

  ![img](https://github.com/RPC2/DRL_paper_summary/blob/master/imgs/039_2.png)