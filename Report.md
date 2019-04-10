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

The models take 18422 secs to finish, and we can see it progress gradually through out the training cycle.

Episode 25	Average Score: 0.12 Min Score: 0.00 Highest Score: 0.46 Elapsed time: 931 secs  
Episode 50	Average Score: 0.56 Min Score: 0.00 Highest Score: 2.04 Elapsed time: 2065 secs  
Episode 75	Average Score: 1.45 Min Score: 0.00 Highest Score: 4.47 Elapsed time: 3306 secs  
Episode 100	Average Score: 2.16 Min Score: 0.00 Highest Score: 5.81 Elapsed time: 4524 secs  
Episode 125	Average Score: 3.73 Min Score: 0.02 Highest Score: 8.91 Elapsed time: 5752 secs  
Episode 150	Average Score: 5.88 Min Score: 1.78 Highest Score: 13.68 Elapsed time: 6967 secs  
Episode 175	Average Score: 8.56 Min Score: 1.78 Highest Score: 18.65 Elapsed time: 8185 secs  
Episode 200	Average Score: 11.64 Min Score: 3.15 Highest Score: 19.90 Elapsed time: 9395 secs  
Episode 225	Average Score: 13.98 Min Score: 7.54 Highest Score: 19.90 Elapsed time: 10609 secs  
Episode 250	Average Score: 16.24 Min Score: 11.16 Highest Score: 23.17 Elapsed time: 11820 secs  
Episode 275	Average Score: 18.18 Min Score: 13.30 Highest Score: 25.22 Elapsed time: 13037 secs  
Episode 300	Average Score: 20.15 Min Score: 13.30 Highest Score: 28.33 Elapsed time: 14248 secs  
Episode 325	Average Score: 23.26 Min Score: 16.02 Highest Score: 30.89 Elapsed time: 15463 secs  
Episode 350	Average Score: 26.59 Min Score: 18.07 Highest Score: 34.06 Elapsed time: 16674 secs  
Episode 375	Average Score: 29.18 Min Score: 19.67 Highest Score: 34.55 Elapsed time: 17889 secs  
Episode 386	Average Score: 30.07 Min Score: 19.67 Highest Score: 34.55 Elapsed time: 18422 secs  

Environment solved in 386 episodes!  
Average Score of last 100 run: 30.071 Total elapsed time: 18422 secs

![training_plot_chart](https://github.com/phchoi/drlnd-continuous-control/blob/master/training.png)



## Idea of future works
Definitely would be try adding optimization methods like Proximal Policy Optimization (PPO) and see will it be able to show any impact to training behavior and performance.


