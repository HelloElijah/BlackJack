# BlackJack
BlackJack with Different Reinforcement Learning Algorithm

Investigate the difference between Temporal Difference and Monte Carol Control in short-trajectory game

<p align="center">
  <img width="460" height="300" src=images/blackjack.png>
</p>

## Package
No extra package required via Google Colab

## Abstract

In reinforcement learning, Temporal Difference evaluation is always preferable to Monte Carlo Control, because Temporal Difference evaluation does outperform Monte Carlo Control in most cases. Temporal Difference requires fewer trajectories and can reduce the impact of bias estimation over multiple iterations. Therefore, I wonder if Monte Carlo can perform better in a particular environment. The trajectory has to be short and sensitive to bias in estimation. The card game blackjack came to my mind. Each trajectory in blackjack is very short as the player need to keep the sum of cards below 21. Blackjack offers stronger randomness than other games, so the bias caused by estimation is less likely to be reduced over iterations. Thus I planned to use different RL algorithms to tackle blackjack problems and observe their performance to prove or disprove my assumption. The algorithm includes: Q-learning with Temporal Difference Evaluation, GLIE with Monte Carlo Control and SARSA

## Introduction

### Rule of blackjack

Blackjack is one of the most popular casino banking games also known as Twenty-One, which uses decks of 52 cards. In blackjack, there is no competition between players. Instead, each player competes against the dealer. The object of the game is to get closer to 21 than the dealer but will lose immediately by exceeding 21. In each round, all players and the dealer receive two cards and the dealer needs to reveal the first card. Players can choose either Stick or Hit. If the total of players exceeds 21, it is known as a bust, lose immediately. When all players choose to stick, the dealer will start taking cards until the sum of cards reaches 17. Whoever is closer to 21 than the dealer wins. Number cards count as their number, face cards count as 10, and Ace can be counted as either 1 or 10.

### Motivation

Not surprisingly, there is an optimal strategy for blackjack. It does not guarantee you a win, but if you can make the right action in every situation, you can maximize your benefits. As a result, blackjack provides a very good platform for testing the RL algorithm. The goal is to see if the agent can learn from the environment by interacting with environment and discover the optimal strategy eventually. We can compare the win rate of different RL algorithms with the win rate of the optimal strategy to see if there is room for improvement in the algorithm. Also, we can compare the agent's action with the optimal action. The most important thing is that we can compare the win rate of Temporal Difference with the win rate of Monte Carlo Control to prove or disprove my assumption mentioned in the abstract.

### Algorithm

In this paper, we will propose three different algorithms to solve the blackjack: Q-learning, GLIE, SARSA. The Q-learning algorithm is one of the most classic in RL, and it's a specific Temporal difference evaluation for learning Q-values. GLIE is very similar to Q-learning, but GLIE uses Monte Carlo evaluation to update Q-values. SARSA is another popular RL algorithm when losing to the agent is expensive. Also, we propose three different strategies for the agent to choose an action: epsilon greedy, softmax and optimistically. 

## Sample Output

<p align="center">
  <img width="600" height="300" src=images/policy.png>
</p>
<p align="center">
  <img width="1000" height="300" src=images/winrate.png>
</p>

# Reference

## Papaer
Miyazaki, K.; Kojima, T.; and Kobayashi, H. 2007. Pro-
posal and evaluation of the penalty avoiding rational policy
making algorithm with penalty level. In SICE Annual Con-
ference 2007, 2766–2773. IEEE.

Perez-Uribe, A., and Sanchez, E. 1998. Blackjack as a
test bed for learning strategies in neural networks. In 1998
IEEE International Joint Conference on Neural Networks
Proceedings. IEEE World Congress on Computational Intel-
ligence (Cat. No.98CH36227), volume 3, 2022–2027 vol.3.

Silver, D.; Sutton, R. S.; and M ̈uller, M. 2012. Temporal-
difference search in computer go. Machine learning
87(2):183–219.

Sutton, R. S., and Barto, A. G. 2018. Reinforcement learn-
ing: An introduction. MIT press.

Watkins, C. J., and Dayan, P. 1992. Q-learning. Machine
learning 8(3):279–292.

## Code

https://github.com/jng985/BlackjackEnv_gym/blob/master/plot_utils.py

https://github.com/dennybritz/reinforcement-learning
