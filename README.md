# drlnd-Navigation
In this repository you will find the files needed for implementing a DQRL agent that can navigate through a small world to collect yellow bananas and avoid collecting the blue ones. 

## The Environment
A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

0 - move forward.
1 - move backward.
2 - turn left.
3 - turn right.
The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.

## Getting Started
To start working on your local machine follow these steps:
* 1- Clone this repository.
* 2- Download the environment from one of the links below. You need only select the environment that matches your operating system:
  *Linux: click here
  *Mac OSX: click here
  *Windows (32-bit): click here
  *Windows (64-bit): click here

* 3- Place the downloaded file in the folder you cloned this repo to and unzip (or decompress) the file.
* 4- Create a Python environment for this project. 
* 5-Activate that environment and install needed dependencies

  
## Files
* 1- Navigation.ipynb 
  *Contains the whole project, every thing is clearly illustrated there
* 2- dqn_agent.py
  *The agent implementation
* 3- model.py
  *The deep learning model
