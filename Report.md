# Report of Continuous Control project

This project is one of the assignment of Udacity Deep Reinforcement Learning Nanodegree. The code base of this project can be found [here](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher). In ths environment,, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible. We will make use of 20 distributed indentical agents to train and eventually we will see if the goal can be archieved.

My implementation of this project is based on the DDPG (Deep Deterministic Policy Gradient) architecture implemented in the [Bipedal project](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-bipedal). In this implementation, actor-critic approach and memory replay are used for the training.

## State and Action Spaces
The observation space of the agent consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

## Learning Algorithm
The learning Algorithm is based on DDPG algorithm ([reference paper](https://arxiv.org/abs/1509.02971)). There were two neural networks being used in this project, one is for actor and another is for critic. The network of actor and critics are slightly different. The actor network has input of action sizes(33), hidden layers of 400 and 300 units respectively and a output layer of tanh layer. The critic network has input of action sizes as 33 and hidden layers of 400 and 300 units respectively as well. However, actions (size of 4) were not included until the 2nd hidden layer.

The hyperparameter I used are listed below as well, turns out the size of batch size and TAU (soft update of target parameters) played a major role in improving the training time.


Replay buffer size: 100000
Minibatch size: 512
Discount facotr: 0.99
Soft update of target parameters: 0.001
Learning rate of the actor: 0.0001
Learning rate of the critic: 0.001
L2 weight decay: 0

## Results

## Idea of future works
Definitely would be try adding optimization methods like Proximal Policy Optimization (PPO) and see will it be able to show any impact to training behavior and performance.


# Dillinger

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

