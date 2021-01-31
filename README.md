
# GASI: Game Advantage State Indentification
# Comparing of Quantum and Classical Nearest Centroid Algorithms for Game State Advantage Classification

Presented by QriKET: `Ian Boraks; Amir Ebrahimi; Sehmilul Hoque; Aleks Siemenn; Tavin Turner`

## Introduction

We demonstrate the nearest centroid classification via implementations in 1) a fully classical model and 2) a model taking advantage of quantum distance estimation. Nearest centroid clustering was used to identify game state advantage in generated game boards, with comparable applications beyond the given application, from rapid medical classification to sentiment analysis. The quantum model is compared with the classical model to evaluate the efficacy of the quantum model in comparison to that of the classical model. Additionally, this comparison is gameified, pitting human, classical, and quantum classifications against each other in an interactive game.

## Basic principles

Nearest centroid classification is a supervised learning task which takes labelled training data and computes a best centroid of the data in its feature space. This centroid is mapped to our training data via Euclidean distance in both the classical and quantum models. The Euclidian distance is calculated with the form $l_{xy}=\sqrt{||x||^2+||y||^2-2||x||||y||c_{xy}$ where $c_{xy}$ is the inner product of $x$ and $y$. In the quantum model, this inner product is calculated using a quantum algorithm that provides an exponential speedup from O(n) to O(log(n)).

We generate N number of chess boards captured at a random point in the game. 0.9\*N chess boards are used to train the classical and quantum ML and 0.1\*N chess boards are used to test them. The chest boards have two feature vectors representing their game-states which include: $x_1=\frac{\textrm{sum(black piece values)}}{\textrm{sum(white piece values)}}$ and $x_2=\frac{\textrm{max(black best move value)}}{\textrm{max(white best move value)}}$.  Where the conventional chess piece values are used to compute these features: ![chess values](https://puu.sh/HcaCA/04c3958598.png)

The **best move value** is computed by determing which legal chess move results in capturing the highest value piece of the opponent; capturing the king results in 40 points.  A label is assigned to each chess game-state as to whether the black or white pieces have the game-state advantage. Black wins if $\textrm{sum(black pieces) - max(white best move value)} > \textrm{sum(white pieces) - max(black best move value)}$.

The player competes head-to-head with the trained classical and quantum centroid clustering algorithms to see who more accurately predicts the game-state advantage relative to ground truth!

## Elements and rules

To play the game, the player (you) receives 5 chess game-states, of which neither ML algorithm has seen within its training/testing data. The player attempts to compute whether the black or white opponent has the game-state advantage for that turn. With $N=400$ classical ML accuracy = 86.0% and quantum ML accuracy = 78%.

Classical ML clustering decision boundary on **training data**:
![classical_training](https://i.imgur.com/x1noXUU.png)

Classical ML clustering decision boundary on **testing data**:
![classical_testing](https://i.imgur.com/K8SmPpo.png)

Quantum ML clustering decision boundary on **training data**:
![quantum_training](https://i.imgur.com/MergQ2s.png)

Quantum ML clustering decision boundary on **testing data**:
![quantum_testing](https://i.imgur.com/UWOiRdN.png)

### Abstract game prediction
A similar version was produced with an abstract game definition to provide another perspective of game advantage. With $N=300$ classical ML agguracy = 73.3% and quantum ML accuracy = 96.6%.

Classical ML clustering decision boundary on abstract **training data**:
![cc2](https://i.imgur.com/ktGN647.png)

Classical ML clustering decision boundary on abstract **testing data**:
![ct2](https://i.imgur.com/Sbe5A2r.png)

Quantum ML clustering decision boundary on abstract **training data**:
![qc2](https://i.imgur.com/o6nUMwl.png)

Quantum ML clustering decision boundary on abstract **testing data**:
![qt2](https://i.imgur.com/XxMwQjO.png)

## Demonstrations:

The player selects their decision of whether black or white has the game-state advantage.

The results of human vs. classical ML vs quantum ML are displayed at the end of the game!

![game_screenshot](https://i.imgur.com/kx6d4ZM.png)
![truth_table](https://i.imgur.com/pVBpgaJ.png)


## GitHub Repo: https://github.com/iQuHACK/2021_QriKET
