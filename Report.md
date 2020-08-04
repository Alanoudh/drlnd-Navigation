# Project Report 

## Introduction 
In this project I takled the navigation problem using DQN algorithm. I decided to use DQN because it is a great value-based algorithm that is known to perform well in discrete actions spaces such as the one for this environment.

## Learning Algorithm 
DQN is an algorithm created by DeepMind that brings together the power of the Q-Learning algorithm with the advantages of generalization through function approximation. It uses a deep neural network to estimate a Q-value function. As such, the input to the network is the current state of the environment, and the output is the Q-value for each action.

DeepMind also came up with two techniques that help successfully train a DQN agent:

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

The graph bellow shows the score for the agent over 2000 episodes. The agent was trained using the same network structure and hyperparameters mentioned above. Across multiple runs, the agent usually solve the environment after about 500-600 episodes, eventually setting at a score close to 16 after 1000 episodes, and peaks around 1300 and then starts to fall.

![Score](/scores.png)

