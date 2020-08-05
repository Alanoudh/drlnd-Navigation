# Project Report 

## Introduction 
In this project I takled the navigation problem using DQN algorithm. I decided to use DQN because it is a model-free and value-based reinforcement learning algorithm that learns a policy telling an agent what action to take under what circumstances. DQN usually peform well in various environments, and it outperforms other algorithms such as Q-learning and SARSA. 

## Learning Algorithm 
DQN is a reinforcement learning algorithm that combines Q-Learning with deep neural networks to estunate a Q-value function, and to let RL work for complex, high-dimensional environments, like video games, or robotics. It has the capability of generalization through function approximation. The deep neural network takes as an input the state, and outputs the Q-value for each action.

Traditinal DQN has some shortcomings, therefore, DeepMind came up with two techniques that help successfully train a DQN agent:

* Replay buffer: Stores a finite collection of previous experiences that can be sampled randomly in the learning step. This helps break the correlation between consecutive actions, which leads to better conversion.
* Separate target network: Similar to the local network in structure, this network helps prevent large fluctuations in network updates, which leads to more stable training.

In this project I used both techniques to train the DQN agent.

### DQN Architecture 
The model architecture used is the same for both the local and target networks. <br />
* Number of layers: it consists of 3 fully-connected layers. 
* Units in each layer: the input layer has 37 units (takes as an input a vector of size 37). The first and second hidden layers contain 64 units each. The output layer has 4 output units (action number).
* Activation function: The first 2 layers use a ReLU activation, while the output layer has the no activation function.

### HyperParameters: 
RL hyperparameters:
* n_episodes (int): maximum number of training episodes= 2000
* max_t (int): maximum number of timesteps per episode = 1000
* GAMMA = 0.99            # discount factor

DQN hyperparameters: 
* BUFFER_SIZE = int(1e5)  # replay buffer size
* BATCH_SIZE = 64         # minibatch size
* TAU = 1e-3              # for soft update of target parameters
* LR = 5e-4               # learning rate 
* UPDATE_EVERY = 4        # how often to update the target network

## Results

The graph bellow shows the score for the agent over 2000 episodes. The agent was trained using the network architecture and hyperparameters mentioned earlier. The agent usually solve the environment after 500 episodes, and setting at a score close to 16 after 1000 episodes, and peaks around 1300 and then starts to fall.

![Score](/scores.png)

## Future Work
Inorder to improve upon the result, there are multiple things we could implement and experiment with:
* Using different valiation of DQN, such as: double Q-Learning, Dueling DQN, and Prioritized Experience Replay.
* Trying simpler techniques such as SARSA and Q-Learning

A source of inspiration, and a good reading to get started towards this goal is DeepMind's Rainbow paper (https://arxiv.org/abs/1710.02298).
