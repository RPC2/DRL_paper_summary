# Mastering Chess and Shogi by Self-Play with a General Reinforcement Learning Algorithm

Authors: David Silver, Thomas Hubert, Julian Schrittwieser, Ioannis Antonoglou, Matthew Lai, Arthur Guez, Marc Lanctot, Laurent Sifre, Dharshan Kumaran, Thore Graepel, Timothy Lillicrap, Karen Simonyan, Demis Hassabis

Algorithm: AlphaZero

Year: 2017

- Introduction

  - This algorithm is a generic reinforcement learning algorithm to play the games of chess, shogi, and Go, without any additional domain knowledge except the rules of the game.

- Methods

  - AlphaZero uses a general-purpose Monte-Carlo Tree Search algorithm.
  - Each simulation proceeds by selecting in each state s a move a with low visit count, high move probability, and high value according to the current neural network. The search returns a vector representing a probability distribution over moves.
  - The parameters of the network is randomly initialized, then trained by self-play reinforcement learning.
  - The reward signal is -1 for a loss, 0 for a draw, and +1 for a win.
  - The parameters are updated to minimize the error between the predicted outcome and the actual game outcome.

- Differences between AlphaZero and AlphaGo Zero:

  - | AlphaZero                                                    | AlphaGo Zero                                                 |
    | :----------------------------------------------------------- | :----------------------------------------------------------- |
    | Optimizes the expected outcome, taking account of draws or potentially other outcomes | Optimizes the probability of winning, assuming binary win/loss outcomes |
    | Does not augment the training data                           | Augments the training data                                   |
    | Simply maintains a single neural network that is updated continually | Self-play games were generated by the best player from all previous iterations |
    | Reuse the same hyper-parameters for all games without game-specific tuning | Tuned the hyper-parameters of its search by Bayesian optimization |

