# Hindsight Experience Replay

Authors: Marcin Andrychowicz, Filip Wolski, Alex Ray, Jonas Schneider, Rachel Fong, Peter Welinder, Bob McGrew, Josh Tobin, Pieter Abbeel, Wojciech Zaremba

Year: 2017

Algorithm: HER

- Problems to solve
  - Sparse reward in RL
  - Achieve sample efficiency
- Method
  - Overview: It can be used with any off-policy RL algorithm, and is applicable whenever there are multiple goals which can be achieved.